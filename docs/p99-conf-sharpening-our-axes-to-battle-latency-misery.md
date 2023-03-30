# P99 CONF:磨利我们的斧头来对抗潜在的痛苦

> 原文：<https://thenewstack.io/p99-conf-sharpening-our-axes-to-battle-latency-misery/>

[P99 CONF](https://www.p99conf.io/)——一个专注于开源社区的会议，面向痴迷于低延迟的工程师——以 [Gil Tene 的](https://www.linkedin.com/in/giltene/)关于“痛苦指标”的演讲拉开帷幕，并以一个关于 P99 延迟减少的西西弗式任务结束。在此期间，工程师们谈到了他们在基础设施工程、编程语言、甚至性能测量的艺术和科学方面经历的许多艰难的性能之战和经验教训。

参加 live 的数千名工程师花了很长时间来挖掘所有这些痛苦和不幸。毕竟，你还能在哪里在短短几个小时内磨砺你自己的消除延迟之斧——从顶级工程师应对地球上最艰难的性能挑战的经验中学到东西？只有在 P99 CONF，也就是现在可以点播狂看的。

通过精心设计的性能优化，Go 的速度能与 [Rust](https://thenewstack.io/adoption-of-rust-whos-using-it-and-how/) 匹敌吗？ [WebAssembly](https://thenewstack.io/the-latest-milestones-on-webassemblys-road-to-maturity/) 和 Rust 如何融入低延迟 C++项目？在 Linux 内核的网络堆栈和 [DPDK 之间的性能比较中，谁会胜出？](https://www.dpdk.org/)扩展的 Berkeley 包过滤(eBPF)和 io uring 的最新用例是什么？

像优步、Lyft 和 Square 这样的团队如何满足被吹嘘的两个、三个、四个甚至五个“九”？我们应该把我们的 9 分一起扔掉吗？

这些讨论都是会议的一部分。

以下是 P99 CONF 主题演讲，随后是 20 分钟的简短演讲，主题和演讲者都是新堆栈的读者非常熟悉的。

## 吉尔·特纳:痛苦的度量和后果

Tene 在 2014 年发表的如今颇具传奇色彩的[“oh sh * t”](https://www.youtube.com/watch?v=nP1aK4DLu-k)演讲促使许多工程师重新思考他们测量 P99 和类似延迟的方法。但是，在痴迷于如何改进性能测量十多年并看到分布式系统是如何发展的之后，他自己对该主题的方法也发生了变化。

从《奇爱博士》(Dr. Strangelove)到《黑客帝国》(The Matrix)，再到《献祭的山羊》(sacrificial goats)，Azul Systems 的联合创始人兼首席技术官 Tene 带领 P99 CONF 观众踏上了一段旅程，从高延迟峰值到测量绝望的低谷。他用“所有漂亮的图表”解构了我们真正在看的东西，更重要的是，我们错过了什么。

这个演讲会让你想知道在你看到的我们活动标识的图表背后到底发生了什么，并且可能会思考 P99 的想法。在似乎绝望的谷底，Tene 展示了一个相当可怕的例子，说明改善图表性能的行为如何会严重破坏最终用户体验。真不幸。

但是 Tene 仍然相信，事实上，克服我们公认的性能测量方法的缺点是可能的…只是不是以他最初认为我们可以的方式。苦难中有希望。隧道尽头的光。甚至是彩虹(也许是因为 Tene 从夏威夷加入我们)。事实证明，工程师可以通过学会热爱痛苦来避免痛苦。如果这对你来说还没有意义，是时候拿起红色药丸并观看他的会议了。

## Liz Rice:在纤毛中使用 eBPF 进行高性能联网

[Isovalent 的首席开源官 Liz Rice](https://www.linkedin.com/in/lizrice) 向与会者介绍了 Cilium([云本地计算基金会](https://cncf.io/?utm_content=inline-mention)的一部分)如何通过使用 [eBPF](https://thenewstack.io/ebpf-finds-a-home-with-a-new-foundation/) 绕过部分网络堆栈来提高吞吐量、释放 CPU 使用率并使 Kubernetes 网络更加高效。

使用 XDP(快速数据路径)， [Cilium](https://github.com/cilium/cilium) 可以在网络接口卡上运行 eBPF 程序，使您能够在网络数据包到达时立即利用 eBPF。例如，正如 Rice 所演示的，您可以使用 eBPF 作为一种快速有效的方法来识别和丢弃“死亡包”。值得注意的是，这种缓解可以动态加载，无需安装内核补丁或重启机器。这只是如何使用 eBPF 动态改变系统中网络行为的一个例子。

eBPF 也可以用于操纵数据包；例如为了负载平衡而改变包含在分组中的源地址和目的地址。当数据包到达时，eBPF XDP 程序可以确定将它发送到哪里——在该主机上还是发送到不同的机器上——而不需要内核的网络堆栈处理数据包。这实现了令人印象深刻的性能提升。(附录 A:阅读 Seznam.cz 如何通过运行基于 XDP 的负载均衡器与 IPVS 负载均衡器相比，实现了两倍以上的吞吐量，并节省了“难以置信的 CPU 使用量”[。)](https://cilium.io/blog/2022/04/12/cilium-standalone-L4LB-XDP/)

除了 XDP 之外，eBPF 程序可以附加到网络堆栈中的各种不同点，这在使用 Kubernetes 的复杂网络堆栈时特别有用。正如 Rice 的演示、火焰图和基准测试所示，这为吞吐量和 CPU 增益带来了更多机会。观看视频，亲自了解性能影响。

## 阿明·罗纳彻:克服可变有效载荷以优化性能

Sentry.io 的首席架构师阿明·罗纳切尔分享了他构建公司事件处理管道的经验，这尤其有趣(阅读:令人困惑的非平凡),因为有效载荷大小可能有多个数量级的差异，数据的复杂性会影响处理，并且数据流的可变容量是不可能预测的。

作为一个错误跟踪和监控产品，Sentry 根据共性对错误和事务事件进行分组。这需要在事件到来时进行快速而复杂的处理。可能需要多层处理来生成错误报告，包括堆栈跟踪、源代码、标签和示例屏幕截图。所有这一切都需要从海量的会话更新、事务事件、指标和许许多多的报告中几乎瞬间地推导出来。

这带来了相当多的挑战。一个是用户希望报告尽可能快地到达，但是一个单独的崩溃报告可能有很大的事件处理时间差异(从 1 毫秒到 30 分钟以上)。这种延迟取决于很多因素，这些因素通常无法立即看出。

另一个错综复杂的问题是:管道末端发生的事情会影响管道的开始。此外，为了确保管道可以越来越靠近用户，管道有两层:最内部的接收系统，加上一个客户中继(本地代理)来执行一些操作，如在数据离开客户的基础架构之前去除个人身份信息。数据来自许多不同的来源，对管道的任何更改——甚至是一个错误修复——都可能中断客户的工作流程。

毫不奇怪，应对这些复杂的挑战需要精心制定的多方面战略。观看视频，了解 Sentry 迄今为止是如何接近它的，以及它接下来计划如何优化它。

## Dor Laor:在 ScyllaDB 与 P99 延迟斗争了 8 年

八年来， [ScyllaDB，](https://www.scylladb.com/?utm_content=inline-mention)由 [Dor Laor 领导，](https://www.linkedin.com/in/dor-laor/)一直在与 P99 延迟作斗争，同时建立一个“全天候、全地形、高吞吐量、低延迟的数据库”有些人可能觉得这是一项永无止境的任务，但对于 Laor 和 ScyllaDB 的每个人来说，这是一项充满爱的工作。

Laor 在他的主题演讲中首先概述了延迟的三个主要来源。首先是速度不匹配，最常见的是磁盘速度和 CPU/内存速度之间的不匹配。如果出现这种不匹配——而系统的设计不能处理这种不匹配——就会碰壁，P99 延迟明显高于平均延迟和中值延迟。如果你在做文件系统或数据库之类的东西，这就意味着 P99 普遍较高。在深入研究了导致这种速度不匹配的各种 CPU 和 I/O 差异之后，Laor 概述了 ScyllaDB 如何解决这个问题。

第二个潜在的来源应该是任何一个有青少年的人都很熟悉的:缺乏对极限的尊重。ScyllaDB 和许多其他系统一样，有 CPU 和 I/O 调度器来调度多个任务。每个任务都有一个配额(我们的是半毫秒)。当一个任务的配额用完时，它应该为其他任务释放 CPU。

但是，如果你得到一个以自我为中心的任务，不让别人轮到你，P99 潜伏期会增加。在 ScyllaDB，我们通过一个阻塞检测器来解决这个问题，该检测器会提醒我们任务配额违规，甚至为我们提供任务停止时正在做什么的详细信息。我们发现的一些罪魁祸首包括大内存分配、内存分配器本身、缓存、I/O 系统，有时甚至在 Linux 内核中。

P99 延迟的第三个核心原因是隔离不完善。这在软件中很常见。ScyllaDB 采取了各种措施来隔离 CPU 和 I/O。例如，为了隔离 CPU，我们使用了一种[每核分片架构](https://www.scylladb.com/webinar/on-demand-webinar-under-the-hood-of-a-shard-per-core-database-architecture/)，这使我们免于锁定。此外，在每个 CPU 中，都有一个调度程序来提供任务之间的隔离，并确保它们遵守限制。

还有一个 I/O 调度器将磁盘加载到它的最佳点:磁盘吞吐量最大化的点，但 I/O 没有排队，延迟仍然很好。这是通过一个用户空间 I/O 调度器来完成的，该调度器对每个任务进行优先级排序:将要求低延迟的任务的优先级放在不太重要的重量级批处理任务(比如压缩)之上。

但后来 Laor 打破了它:“最臭名昭著的延迟来源是什么？到处都是。几乎所有东西都必须完美，才能有低 P99。”这包括文化、灾难恢复、操作系统、架构、磁盘、协议、客户端等等。观看视频，了解他对 P99 延迟的诸多影响，以及如何解决这些影响的示例。

## 慈善专业:从 SLOs 到“年度游戏”

[慈善专业，](https://www.linkedin.com/in/charity-majors)[honeycomb . io 的联合创始人兼首席技术官，](https://www.honeycomb.io/?utm_content=inline-mention)以其残酷而深刻的见解而闻名——她的 P99 CONF 主题演讲也不例外。注重延迟的工程师可以从游戏中学到很多东西，在游戏中，任何缺乏完美体验的东西都会破坏甚至是最具想象力的设计。这就是工具和遥测技术发挥作用的地方。

正如梅杰斯所说，“没有问题是不可能的。但是 T4 有可能在用户注意到之前发现并修复问题。你真的希望用户认为这是理所当然的。”

但是你如何衡量这种体验呢？吉尔·特内首先介绍了丑陋的 P99 现实，Nobl9 的亚历克斯·伊达尔戈[和 Optimizely](https://www.p99conf.io/session/throw-away-your-nines/) 的布赖恩·泰勒[也探讨了这一现实，梅杰斯宣称，“总体是虚假的，每个人的经历都很重要。任何一个可以登录的玩家都可以在论坛上发起一场风暴。”](https://www.p99conf.io/session/properly-understanding-latency-is-hard-what-we-learned-when-we-did-it-correctly/)

您的系统可能有四个 9，但仍然…

*   今天登录的每个人可能已经将他们的状态保存在一个没有响应的碎片上——并且认为你已经 100%停机了。
*   在某些地区，每个人的登录延迟可能会超时。
*   注册时付款的追加销售可能会失败。

有效的可观察性是工程体验和用户体验之间的隐性联系。

按照梅杰斯的说法，“没有可观性，你真的是在瞎开车。你没戴眼镜就在高速公路上飞驰。”

可观察性*应该*帮助你看到幕后发生的事情——你可以调试你的代码，重建任何用户的体验，甚至理解新的场景而不用发布新的代码。它应该能帮助你超越“这个坏了吗？”“这是如何工作的，我的用户体验如何？”你在这方面做得越好，你经历的破碎就越少。

但是，如何在游戏或其他复杂的高度分布式系统中实现这种独角兽级别的可观察性呢？

*   跨多个云、数据中心和区域部署。
*   由世界各地的众多团队设计和开发。
*   用于数千种设备类型。
*   容易出现巨大的并发问题和“雷群”

这是梅杰斯多年来一直在解决的问题，导致她最近在 Honeycomb.io 成为[一名“意外创业创始人”。](https://thenewstack.io/charity-majors-honeycomb-tech-founder-odyssey/)观看她的主题演讲，寻找明确的前进道路——分享她来之不易的经验教训，这样你就可以提供全是独角兽和彩虹的用户体验。

## 布莱恩·坎特里尔:工具制造的首要地位

工具——用来制造其他东西的东西——是我们人性的核心。但是尽管有制造东西的许可，工程师们还是经常被劝阻不要制造他们自己的工具。花在工具上的时间被认为是令人遗憾的分心，而不是必要的努力。知名软件工程师和权威人士布莱恩·坎特里尔不同意这种观点。

“老实说，软件历史上一些最重大的发展实际上是团队在为自己开发更好的工具，”他在 P99 CONF 上说。想要例子和引人入胜的故事？氧化物计算机公司的联合创始人兼首席技术官坎特里尔从不让人失望。

大约在 1969 年，他从 Unix 开始收集有影响力的工具制作示例(考虑到 Cantrill 自己的职业生涯是在 Sun Microsystems 开始的，他 9 岁的女儿怀疑那是一个微酿酒厂，这并不奇怪)。Unix 背后的团队看到美国电话电报公司·贝尔实验室确实需要一种更好的方法来排版他们的专利申请，他们最初将 Unix 作为文字处理系统。

但是很快就发现 Unix 除此之外还有相当多的用途。按照坎特里尔的说法，“工具变得比它创造的人工制品更有价值。这是投资工具的早期红利。”

下一个——也是更简洁的——例子诞生于[唐纳德·克努特](https://thenewstack.io/donald-knuth-on-machine-learning-and-the-meaning-of-life/)更新他的书《[计算机编程的艺术](https://en.wikipedia.org/wiki/The_Art_of_Computer_Programming)排版在第一版和第二版之间数字化了，Knuth 鄙视随之而来的排版。因此，Knuth 自己动手制作了排版他自己的书所需的工具: [TeX](https://www.saildart.org/TEX1%5B1,DEK%5D1) 。

Bryan 说:“TeX 和 LaTeX 对于编写全球技术文档变得非常重要。我们应该感到幸运的是，一位计算机科学家在更早的时候就遇到了这个问题，并且围绕编写一个工具有了这种时代精神、这种风气。”

Git 的前身 NSELite，Cantrill 的 baby DTrace(它极大地加速了 ZFS 等后来系统的开发)，Jenkins (née Hudson)，甚至 Rust 都是一些人试图更快更高效地完成自己工作的产物。即使工具制造商没有预料到长期的红利，Cantrill 丰富多彩的故事和收获肯定很容易被任何现代技术专业人士欣赏。

## Avi Kivity:从磁盘角度了解数据库操作的窗口

了解快速 NVMe 固态硬盘内部的情况是最大限度提高其性能的关键，尤其是在 IO 密集型工作负载的情况下。但是你如何窥视这个传统的黑箱呢？

这就是 ScyllaDB 的首席技术官兼联合创始人 [Avi Kivity 最近解决的问题。具体来说，他希望从新的 AWS EC2 I4i 实例](https://www.linkedin.com/in/avikivity/)中基于 [NVMe 的 Nitro SSDs 的角度，对 ScyllaDB——一个具有独特的接近硬件架构的 NoSQL 数据库——有一个新的了解。](https://aws.amazon.com/ec2/instance-types/i4i/)

Kivity 开始设想这一点，并与着迷的 P99 CONF 观众分享了他的方法。在解释了他如何使用开源 Python 和 Linux 工具创建一个进入磁盘的窗口后，Kivity 讲述并解释了 IO 的实时可视化:以颜色编码的读取和写入、随机 IO、顺序 IO 以及每个 IO 消耗的磁盘带宽的动态显示。可视化包括:

*   ScyllaDB 的每核分片架构如何反映在磁盘行为中。
*   顺序表写入与提交日志写入有何不同。
*   压缩如何响应读写工作负载而上升或下降。
*   数据库如何使用磁盘来避免锁争用。

接下来，Kivity 转向一个不同的视角:相同的数据库操作如何在监控仪表板中表现出来。一个度量接一个度量，他揭示了每个图表有趣趋势背后的数据库内部。

观看 Kivity 的演讲，体验这一迷人的系统可观测性之旅——并了解如何在自己的 IO 中获得这种水平的洞察力。

## 但是等等，还有呢！50 多场围绕核心低延迟主题的技术讲座

除了主题演讲之外，大会还有一系列深入的会议，可以让任何有延迟意识的工程师疯狂观看几个小时。这是冰山一角:

**Nobl9 的 Alex Hidalgo** 解释了为什么在设定服务可靠性目标时只考虑“9”可能会遇到问题，并探索了更好的数字来代替。阅读相关内容:[当 99%的服务水平目标被高估(并且过于昂贵)](https://thenewstack.io/when-99-service-level-objectives-are-overrated-and-too-expensive/)。

Optimizely 的布赖恩·泰勒讲述了他的组织如何应用 Gil Tene 的“oh sh*t”演讲的经验来理解在其数据管道中发现的令人惊讶的延迟来源。

**Square Engineering 的 Omar Elgabry** 分享了该公司如何在采用超时、回退和抖动三种技术后，将 DynamoDB 延迟从 10 秒以上减少到 500 毫秒左右。

**Lyft 的 Pavlo Stavytsky** 揭示了该组织如何测量 CPU 负载以提高应用性能——它收集哪些指标，以及它如何检索和计算这些指标。

**优步的克里斯蒂安·贝拉斯克斯**详细介绍了该公司如何通过实施大规模、半自动 Go 垃圾收集调优机制来降低计算能力的成本。

微软的 Daniele Salvatore Albano 展示了 cachegrand，这是一个 SIMD 加速的散列表，没有锁，也没有使用纤程、io_uring 等的忙等待循环。了解一下: [Cachegrand，一个面向数据开发的快速、可伸缩的密钥库](https://thenewstack.io/cachegrand-a-fast-scalable-keystore-for-data-oriented-development/)。

**[甲骨文公司的](https://developer.oracle.com/?utm_content=inline-mention) Ron Pressler** 研究了 Java 虚拟线程如何通过大幅增加服务器的请求能力，为每请求线程风格提供更高的吞吐量。

**[亚马逊网络服务的](https://aws.amazon.com/?utm_content=inline-mention)马克·理查兹**使用了一个 HTTP 基准来比较 Linux 内核网络堆栈和通过 DPDK 进行内核旁路的用户空间网络的性能。

**Google 的 Steve Rostedt** 分享了他关于使用跟踪来分析运行 KVM 的 Linux 主机的开销的内部见解。

**[Red Hat 的](https://www.openshift.com/try?utm_content=inline-mention)bartomiej p otka**解释了如何使用现代云的原生可观察性和工具来有效地发现和发现效率问题。

**ScyllaDB 的 Piotr Sarna** 解释了他如何以延迟友好的方式将 WebAssembly 和 Wasmtime 集成到 C++项目中，包括异步 Rust。

Percona 的彼得·扎依采夫探索了查询优化，如并行查询、异步查询和复杂工作排队，以充分利用数据库。

Vercel 的 Malte Ubl 讨论了在边缘环境中呈现网页的新范式的利弊，并研究了使其大放异彩的端到端架构。

秋田公司的马克·格里特解释了为什么他的团队逆潮流而动，坚持使用 Golang，而不是重写它在 Rust 中的应用。了解一下:[一个 Rust 重写真的值得吗？](https://thenewstack.io/is-a-rust-rewrite-really-worth-it/)

Hudson River Trading 的 Sabina Smajla 展示了如何利用编程语言的异步库，只需对现有代码做一些小的调整。了解一下:[异步编程的 3 种类型](https://thenewstack.io/3-types-of-asynchronous-programming/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>