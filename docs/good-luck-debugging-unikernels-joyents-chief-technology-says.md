# Joyent 的技术总监认为，Unikernels 是无法调试的

> 原文：<https://thenewstack.io/good-luck-debugging-unikernels-joyents-chief-technology-says/>

云提供商 Joyent 的顶级技术专家指控说，uni nucles 不适合生产。

Joyent 首席技术官布莱恩·坎特里尔(Bryan Cantrill)在周五的博客文章《T2》中写道:它们部署复杂，安全性值得怀疑，而且几乎不可能调试。

因此，他们可能还没有准备好，也可能永远不会准备好生产工作负载，他认为。

坎特里尔是对多克公司周四宣布[已购买 Unikernel Systems](https://thenewstack.io/docker-buys-unikernel-systems-plans-bring-unikernels-data-center/) 一事所引发的兴奋做出回应的。

Docker [在 unikernels 中找到了希望](http://blog.docker.com/2016/01/unikernel/)，因为它们比容器更小，所以可以适应更紧密的计算机环境，攻击面更小。

单内核是一种应用程序，它被打包成完全在微处理器的特权模式下运行。坎特里尔解释说，它承担了以前由操作系统自己处理的所有“硬件接口责任”。

他警告称，这种方法将带来一些操作问题。

您现有的所有应用程序都需要移植到一个新的环境中。![Bryan-Cantrill-03](img/8c8dcf40035d18975fb906dcbc89fe2b.png)更糟糕的是，您将很难调试这些应用程序。

这位不相信的技术专家写道:“UNIX 内核中没有进程，所以如果你的应用程序依赖于这个(无处不在，已经有 40 年历史的)构造，你基本上就完蛋了。”。

没有流程，开发人员就不能使用许多常见的实用程序——如 [ps](https://en.wikipedia.org/wiki/Ps_(Unix)) 、 [htop](http://hisham.hm/htop/) 、 [strace](https://en.wikipedia.org/wiki/Strace) 、 [MDB](http://maxg.github.io/didit/debugging-with-mdb.html) 或[dt race](https://en.wikipedia.org/wiki/DTrace)——来跟踪他们行为不端时的程序进度。

“UNIX 内核是完全不可否认的，”他总结道。

坎特里尔本人是 [DTrace](http://dtrace.org/blogs/about/) 的作者，这是一款用于 Joyent 系统以及 Solaris、Mac OS X 和 FreeBSD 机器的强大调试工具。

坎特里尔警告说，甚至连 unikernels 所谓的性能和安全优势都值得怀疑。

单核可以通过消除跨越用户-内核边界的上下文跳跃来提高应用程序的性能，尽管这种增益对于现代处理器来说是最小的。

坎特里尔指出，单核可能很小，但因为它们作为客户操作系统运行，它们的主机服务器以不可更改的块为它们分配 DRAM 内存，工程师通常会慷慨地按比例分配内存，以避免内存不足的错误。因此，至少从单核中节省的一些空间会在服务器上损失掉。

Cantrill 认为，单核带来的安全好处也可能是虚幻的。

Cantrill 写道，Unikernels“经常运行新的或不同的软件(因此不容易受到 OpenSSL vuln-of-the-week 的攻击)，但这种通过模糊性实现安全性的论点可以用于运行任何新的、深奥的系统。

“安全争论似乎也忽略了单核非常依赖的保护边界:由底层虚拟机管理程序提供的来宾操作系统之间的保护边界，”他继续说道。

Docker 创始人兼首席技术官 Solomon Hykes[在接受新堆栈](https://thenewstack.io/docker-buys-unikernel-systems-plans-bring-unikernels-data-center/)采访时表示，Docker 计划做大量工作来为生产环境准备其 unikernel ready，包括将该技术集成到其支持软件堆栈的其余部分。

尽管有丰富的知识，Cantrill 本人并不是一个公正的观察者，当谈到 unikernels 时，他被定位为容器的替代品。Joyent 本身通过其 [Triton](https://www.joyent.com/blog/understanding-triton-containers) 云服务提供基于容器的基础设施托管。

无论如何，Cantrill 的帖子立即在[黑客新闻](https://news.ycombinator.com/item?id=10953766)和其他科技论坛上引发了大量讨论。

一位黑客新闻读者[断言](https://news.ycombinator.com/item?id=10955007)，指出 Cantrill 淡化了单核可能带来的性能提升。

1 月 27 日星期三，当 Unikernel Systems 的 Amir Chaudhry 和 Richard Mortier 将进一步讨论他们的技术时，Cantrill 的担忧可能会在 Docker Online 会议上得到进一步解决。

Docker 和 Joyent 以及新堆栈的赞助商

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>