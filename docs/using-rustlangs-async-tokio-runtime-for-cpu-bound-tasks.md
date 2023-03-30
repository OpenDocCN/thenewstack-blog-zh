# 使用 Rustlang 的异步 Tokio 运行时执行 CPU 相关的任务

> 原文：<https://thenewstack.io/using-rustlangs-async-tokio-runtime-for-cpu-bound-tasks/>

尽管术语`async`及其与异步网络 I/O 的关联，这篇博客文章认为，Rust `async`生态系统核心的 [Tokio](https://tokio.rs/) 运行时对于 CPU 密集型任务也是一个很好的选择，例如那些在分析引擎中发现的任务。

## 什么是 Tokio？

 [安德鲁·兰姆

在作为 C/C++系统程序员(数据库和编译器)工作了多年，并在机器学习初创公司工作了一段时间后，Andrew 现在与 Paul Dix 和一个才华横溢的工程师团队一起在 InfluxDB IOx 工作，这是一个用于时间序列数据的新引擎。](https://twitter.com/andrewlamb1111) 

Rust 内置了对异步(`async`)编程模型的支持，类似于 JavaScript 等语言。

为了充分利用多核和异步 I/O，必须使用一个运行时，虽然 Rust 社区有几个备选方案，但 Tokio 是事实上的标准。 [Tokio.rs](https://tokio.rs/) 将其描述为:“ [Rust 编程语言](https://thenewstack.io/the-case-for-rust-as-the-future-of-javascript-infrastructure/)的异步运行时。它提供了编写网络应用程序所需的构建块。”

虽然这个描述强调了 Tokio 用于网络通信，但是运行时也可以用于其他目的，我们将在下面进行探讨。

## CPU 任务为什么要用 Tokio？

事实证明，现代分析引擎总是需要处理来自网络的客户端请求，以及使用网络与对象存储系统(如 AWS S3、GCP 云存储和 Azure Blob 存储)进行通信。

因此，在 Rust 中实现的任何这样的系统最终都将使用 Tokio 作为其网络和至少部分存储 I/O(是的，我知道，最初 Tokio 异步文件 io 并不是真正的异步，但它很快就会成为)。

分析系统也会进行 CPU 密集型计算，我将其定义为以消耗大量 CPU 进行存储重组、预计算各种索引或直接回答客户端查询的方式处理数据。这些计算通常被分解成许多独立的块，我称之为“任务”，然后并行运行，以利用现代 CPU 中可用的许多内核。

确定何时运行哪些任务通常由一个称为“任务调度器”的东西来完成，它将任务映射到可用的硬件核心/操作系统线程。

对于各种类型的任务调度器、工作池、线程池等，学术界和工业界已经进行了多年的研究。

我与几个定制任务调度器一起工作(并且实现了，我有点惭愧地承认)的经验是，它们最初很容易工作(比如 99.9%的时间)，但是随后需要很多(很多！)的时间来获得极限情况(快速关机、任务取消、耗尽等。).众所周知，它们很难测试，因为它们使用了底层线程原语，并且竞争条件比比皆是。我不建议这么做。

因此，当在 Rust 生态系统中寻找任务调度程序时，就像我们为 [InfluxDB](https://www.influxdata.com/products/influxdb/) IOx 和 DataFusion 所做的那样，你自然会选择 Tokio，它看起来相当不错:

1.  您已经有了 Tokio(没有新的依赖项)。
2.  Tokio 实现了一个[复杂的工作窃取调度器](https://tokio.rs/blog/2019-10-scheduler)。
3.  Tokio 有效地内置了对 continuations ( `async` / `await`)的语言支持，以及许多相对成熟的流、异步锁定、通道、取消等库。
4.  Tokio 以久经考验而闻名，并在 Rust 生态系统中大量使用。
5.  Tokio 通常在同一个 executor 线程上运行任务和它们运行的未来，这对于缓存局部性来说非常好。
6.  Tokio 是[有据可查的](https://tokio.rs/tokio/tutorial)，积极维护，一直在变好。( [Tokio 主机是在我写这篇博客的时候](https://tokio.rs/blog/2021-12-announcing-tokio-console)公布的)。

因此，使用`Tokio`作为 CPU 密集型任务的任务调度器是显而易见的，对吗？呜呜呜！

## 使用 Tokio 的常见异议

事实证明，使用 Tokio 是一个相当热门的话题，我想说，仍然不是每个人都 100%相信，因此这篇博客帖子。在 DataFusion 和 InfluxDB IOx 的早期，我们很担心这个问题。以下是一些常见的异议:

### 东京医生说不要:

Tokio 文档的旧版本(例如 [1.10.0](https://docs.rs/tokio/1.10.0/tokio/index.html#cpu-bound-tasks-and-blocking-code) )包含了(在我看来)著名的告诫:

*"* 如果您的代码是 CPU 受限的，并且您希望限制用于运行它的线程数量，那么您应该在另一个线程池(比如 Rayon)上运行它。"

我相信这种措辞在我们的团队以及更广泛的 Rust 社区中引起了严重的混乱。许多人认为 Tokio `Runtime`不应该用于 CPU 密集型任务。关键点实际上是*相同的* `Runtime` *实例*(相同的线程池)不应该同时用于 I/O 和 CPU，我们已经[随后澄清了](https://docs.rs/tokio/1.14.0/tokio/#cpu-bound-tasks-and-blocking-code)文档的意图(关于 [PR](https://github.com/tokio-rs/tokio/pull/4105) 的血淋淋的细节)。

顺便说一句，Tokio 文档建议使用 [Rayon](https://github.com/rayon-rs/rayon) 执行 CPU 密集型任务。对于许多应用程序来说，Rayon 是一个很好的选择，但是它不支持`async`，所以如果你的代码必须做任何 I/O，你将不得不跨越痛苦的同步/异步边界。我还发现映射一个基于拉的执行模型很有挑战性，在这个模型中，一个任务在运行到 Rayon 之前必须等待所有的输入都准备好。

### 尾巴潜伏会跟踪你

明智的人说，“使用 Tokio 进行 CPU 密集型工作会增加请求尾部延迟，这是不可接受的。”但是等等！你可能会说，“尾部延迟？🙄我正在编写一个数据库，对于高负载的 web 服务器来说，这听起来像是一个学术问题……”

不尽然:考虑一下活性检查，这是目前使用容器编排系统部署的系统的必备条件。检查您的流程是否运行良好通常是对类似`/health`的 HTTP 请求。如果由于 Tokio 充分有效地使用您的 CPU 来处理大量数据处理任务，该请求被搁置在某个任务队列中，那么 Kubernetes 将无法获得所需的 *"* 一切正常 *"* 响应，并终止您的进程。

这种推理得出了一个经典的结论:由于尾部延迟非常关键，所以不能将 Tokio 用于 CPU 密集型任务。

然而，正如 Tokio docs 建议的那样，在 CPU 完全饱和的情况下，避免被 Kubernetes 和朋友攻击的真正重要的是使用一个*单独的*线程池——一个用于“延迟很重要”的任务，如响应`/health`，另一个用于 CPU 繁重的任务。这些线程池的最佳线程数量根据您的需要而有所不同，这是另一篇文章的好主题。

也许通过将 Tokio `Runtime`想象成一个复杂的线程池，使用不同的`Runtime`实例的想法看起来更容易接受，我们将在下面演示如何使用专用的执行器来实现。

### 高的每任务开销

但是“等等！”我听到你说(或者每个人都听到你在[黑客新闻](https://news.ycombinator.com/item?id=28514226)上说)，Tokio 的每任务开销很高。我一点也不惊讶人们可以制造比 Tokio 更快地处理微小任务的线程池。

然而，我还没有见过这样一个我可以信任的系统来处理我的生产工作负载，也没有见过一个具有如此强大的生态系统支持的系统。

幸运的是，对于许多工作负载，每个任务的开销可以使用“矢量化处理”来分摊这是每个任务一次处理数千行而不是一行的一种奇特说法。你当然不能发疯；您确实需要将您的工作分成合理大小的块，并且您不能分摊所有的工作量。然而，对于我的应用程序关心的所有实例，Tokio 任务开销都消失在噪声中。

## 对于 CPU 受限的任务如何使用 Tokio？

所以，让我们假设我说服了你使用 Tokio 来处理 CPU 繁重的工作是可以的。你是怎么做到的？

首先，至关重要的是，你的代码需要遵循“异步代码不应该花很长时间而没有到达`.await`”的格言，正如 Alice Ryhl 的[帖子](https://ryhl.io/blog/async-what-is-blocking/)中所解释的。这是给调度者一个机会去调度别的，偷工减料等等。

当然，“很长时间”取决于你的应用；Ryhl 建议在优化响应尾部延迟时使用 10 到 100 微秒。我认为在优化 CPU 时，10 到 100 毫秒对于任务来说也是可以的。然而，由于我的[估计的每个任务的 Tokio 开销](https://github.com/alamb/rust_tokio_overhead)在大约 10 纳秒的范围内，所以几乎不可能测量 10 毫秒任务的 Tokio 运行时开销。

第二，在单独的`Runtime`实例上运行任务。你是怎么做到的？很高兴你问了。

### 专门的执行者

下面是我们如何在 InfluxDB IOx 中的独立 Tokio 运行时上运行任务的简化版本。(完整版本可在[我们的报告](https://github.com/influxdata/influxdb_iox/blob/fe155e15fb2ad166aee66b0458e63c24a8128dd4/query/src/exec/task.rs#L101-L118)中找到，并具有干净关闭和加入的附加逻辑。)

```
pub  struct  DedicatedExecutor  {
    state:  Arc<Mutex<State>>,                                                                                                          
}                                                                                                                                      

/// Runs futures (and any `tasks` that are `tokio::task::spawned` by 
/// them) on a separate Tokio Executor 
struct  State  {                                                                                                    
    /// Channel for requests -- the dedicated executor takes requests                                                                  
    /// from here and runs them. 
    requests:  Option<std::sync::mpsc::Sender<Task>>, 

    /// Thread which has a different Tokio runtime
    /// installed and spawns tasks there                                                                                            
    thread:  Option<std::thread::JoinHandle<()>>, 
} 

impl  DedicatedExecutor  { 
    /// Creates a new `DedicatedExecutor` with a dedicated Tokio 
    /// executor that is separate from the threadpool created via                                                                      
    /// `[tokio::main]`.                                                                                                    
    pub fn new(thread_name:  &str, num_threads: usize) -> Self {                                                                        
        let thread_name = thread_name.to_string(); 

        let  (tx,  rx)  =  std::sync::mpsc::channel::<Task>(); 

        let thread  =  std::thread::spawn(move  ||  {  
            // Create a new Runtime to run tasks                                                                                                                                                                                                                                
            let runtime  =  Tokio::runtime::Builder::new_multi_thread()                                                                  
                .enable_all()                                                                                                          
                .thread_name(&thread_name) 
                .worker_threads(num_threads)
                // Lower OS priority of worker threads to prioritize main runtime                                                                                                                                                          
.on_thread_start(move || set_current_thread_priority_low()) 
.build() 
                .expect("Creating Tokio runtime"); 

 // Pull task requests off the channel and send them to the executor 
 runtime.block_on(async  move  {                                                                                                        
                while let Ok(task)  =  rx.recv()  {                                                                                                                                                                                                                              
                    Tokio::task::spawn(async  move  {                                                                                    
                        task.run().await;                                                                                              
                    });                                                                                                                
                }                                                                

        let state  =  State  {                                                                                                            
            requests:  Some(tx),                                                                                                        
            thread:  Some(thread),                                                                                                      
        }; 

        Self  { 
            state:  Arc::new(Mutex::new(state)),                                                                                        
        }                                                                                                                              
    }                                                                                                                                  

```

这段代码创建了一个新的`std::thread`，它创建了一个独立的多线程 Tokio `Runtime`来运行任务，然后从一个`Channel`中读取任务`spawn`并将它们放到新的`Runtime`上。

注意:新线程是关键。如果你试图在主线程或者 Tokio 已经创建的一个线程上创建一个新的`Runtime`，你会得到一个错误，因为已经安装了一个`Runtime`。

下面是向这第二个`Runtime`发送任务的相应代码。

```
impl  DedicatedExecutor  { 

    /// Runs the specified Future (and any tasks it spawns) on the 
    /// `DedicatedExecutor`.                                                                        
    pub fn spawn<T>(&self, task: T) -> Job<T::Output>                                                                                  
    where                                                                                                                              
        T: Future + Send + 'static,                                                                                                    
T::Output: Send + 'static, 
    {                                                                                                                                  
        let (tx, rx) = tokio::sync::oneshot::channel();                                                                                

        let fut  =  Box::pin(async  move  {                                                                                                
            let task_output  =  task.await;                                                                                              
            tx.send(task_output).ok()                                                                                                                      
        });                                                                                                                            
        let mut state  =  self.state.lock(); 
        let task  =  Task  {                                                                                                              
            fut, 
        }; 

        if let Some(requests)  =  &mut state.requests {                                                                                  
            // would fail if someone has started shutdown                                                                              
            requests.send(task).ok();                                                                                                  
        }  else  { 
            warn!("tried to schedule task on an executor that was shutdown");                                                          
        }                                                                                                                              

        Job  {  rx,  cancel  } 
    }  
  }    

```

### 职位

上面的代码使用了一个包装器来包装名为`Job`的`Future`，该包装器处理将结果从专用执行器传输回主执行器，看起来像:

```
#[pin_project(PinnedDrop)] 
pub  struct  Job<T>  {                                                                                                  
    #[pin] 
    rx:  Receiver<T>, 
}                                                                                                                                      

impl<T>  Future  for  Job<T>  {                                                                                                            
    type Output  =  Result<T,  Error>;                                                                                                    

    fn poll( 
        self:  Pin<&mut Self>,                                                                                                          
cx: &mut std::task::Context<'_>, 
) -> std::task::Poll<Self::Output> { 
        let this = self.project(); 
        this.rx.poll(cx) 
    }                                                                                                                                  
}            

```

就是这样！你可以在这个 [Github gist](https://gist.github.com/alamb/bd0e086448ef9b438aeebd6f550e23ed) 里找到所有的代码。

## 后续步骤

InfluxData 是开源的忠实信徒和支持者。InfluxDB IOx 充分利用了 Apache [Arrow](https://arrow.apache.org/) 列内存格式和 Apache Arrow [DataFusion](https://arrow.apache.org/datafusion) 查询引擎的 Rust 实现，并对其做出了贡献，后者使用 Tokio 来执行查询计划。

我们热爱社区贡献，包括文档和代码。DataFusion 和 Arrow 都有[充满活力的社区](https://arrow.apache.org/datafusion/community/communication.html)。请随意过来打个招呼。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>