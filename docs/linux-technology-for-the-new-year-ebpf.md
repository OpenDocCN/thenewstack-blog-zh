# 新一年的 Linux 技术:eBPF

> 原文：<https://thenewstack.io/linux-technology-for-the-new-year-ebpf/>

在未来的一年中，我们将开始看到 Linux 内核架构的变化，因为一个新的组件 eBPF(扩展的 Berkeley 数据包过滤器)开始从各个内核模块接管更多的监控、安全和网络职责。

今年早些时候，SAP 实验室的开发者 Gaurav Gupta 在[的一次关于在哥本哈根 KubeCon 使用该技术进行低开销跟踪的演讲中说，eBPF 是“Linux 最新的超级力量”。](https://youtu.be/ug3lYZdN0Bk)

作为 Linux 内核的虚拟机，eBPF 可以为内核本身内部的高级、低开销跟踪奠定基础，提供对 I/O 和文件系统延迟、按进程划分的 CPU 使用情况、堆栈跟踪和其他对调试有用的指标的洞察。它还可以在系统安全方面发挥作用，有可能提供一种阻止 DDOS 攻击的方法，监控入侵检测，甚至取代 IPtables 作为加强防火墙的一种方法。它还提供了一个更干净的安装驱动程序的替代方法。

“在未来，你将会看到更多的 eBPF 程序，而不是内核模块，”网飞内核和性能工程师 [Brendan Gregg](http://www.brendangregg.com/) 在 10 月于北卡罗来纳州罗利举行的 [All Things Open](https://allthingsopen.org/) 会议上说道。"你将开始看到更多用 eBPF 编写的令人惊讶的东西."这是 Linux 向微内核模型迈进的一步，在微内核模型中，更多的功能是在用户空间而不是内核空间定义和运行的。

随着组织转向最新的 Linux 内核，他们可以享受这些新的好处。要运行 eBPF，您至少需要 Linux 内核版本 4.4，或者最好是 4.9。

最初被称为伯克利包过滤器的技术[最初是作为伯克利软件发行版(BSD)的](http://www.tcpdump.org/papers/bpf-usenix93.pdf) HTTP 包过滤器。Plumgrid 扩展了它在软件定义网络中的用途，为 Linux 内核提供了一种代表用户执行定制操作的方式。

这通常是模块的工作，尽管它们的使用需要在安装时重新编译内核，它们也可能使内核崩溃。eBPF 不仅仅是重定向数据包，它还可以附加到任何内核事件或任何套接字上。它可以运行简单的程序。它基本上是内核的沙箱，提供内置的安全性。eBPF 程序被编译成字节码，因此开发人员不必担心不同的底层架构。

Gregg 承认，编写原始 eBPF 代码很困难。它类似于汇编编程语言，没有循环和其他限制。幸运的是，一些软件包可以让编写程序更容易。有了 [LVMM](https://llvm.org/) ，开发人员可以用 c 语言创建 eBPF 程序。 [BPF 编译器集合](https://github.com/iovisor/bcc/blob/master/README.md) (BCC)工具包提供了 Python 和 Lua 环境，这对于构建复杂程序很有好处。

那些希望使用 eBPF 捕获指标的人应该看看由 [IOVisor Project](https://www.iovisor.org/) 启动的一个项目，名为 [bpftrace，](https://github.com/iovisor/bpftrace)一种针对 eBPF 的高级跟踪语言。“它将程序归结为仅仅是探针和逻辑，”Gregg 说，并指出 bfptrace 提供了与 [Dtrace](http://dtrace.org/blogs/about/) 为 Solaris 提供的相同的低开销、动态跟踪。Linux 并不缺少跟踪工具，尽管“让它们融入内核是一个挑战，”Gregg 承认，他指的是 [KTap](https://github.com/ktap/ktap) 和 [SystemTap](https://sourceware.org/systemtap/) 。

Gregg 设想更多的工程师在基础工具上开发新的图形用户界面。

在 2017 年的基础设施软件会议上，WeaveWorks 的 Alfonso Acosta [演示了](https://www.youtube.com/watch?v=k4jqTLtdrxQ&t=2854s)如何使用 eBPF 来监控通过 NGINX 服务器的所有流量，而无需向 NGINX 本身添加任何工具。

[https://www.youtube.com/embed/k4jqTLtdrxQ?start=2854&feature=oembed](https://www.youtube.com/embed/k4jqTLtdrxQ?start=2854&feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>