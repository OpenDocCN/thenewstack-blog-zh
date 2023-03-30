# Xen 项目的 Lars Kurth 谈到了单核的前景(和调试)

> 原文：<https://thenewstack.io/qa-lars-kurth-unikernels/>

几周前，当 Docker 宣布收购 Unikernel Systems 时，它在容器社区引起了轩然大波，Unikernel Systems 是 uni kernel 操作系统的创造者。尽管码头工人[称赞](https://thenewstack.io/good-luck-debugging-unikernels-joyents-chief-technology-says/)unikernel 占地面积小、安全性高，但其他人[对该技术将如何用于生产提出了疑问](https://thenewstack.io/good-luck-debugging-unikernels-joyents-chief-technology-says/)。Joyent 的首席技术官 Bryan Cantrill 在一篇博客文章中抨击道:“单核不适合生产”，他认为，由于他们的设计，单核不能被调试。

为了了解更多关于 unikernels 的信息，我们采访了 Lars Kurth，他是 Xen 项目顾问委员会的主席。他非常熟悉关于 unikernels 的想法:MirageOS 是 Xen 的子项目。他还是 Citrix 开源解决方案的总监。

![LarsK](img/a4f2cd4d25ed74cbbd503caeb9d172db.png)

**TNS:** 首先，在一个非常高的层面上，什么是 unikernel，它与容器、虚拟机或成熟的操作系统有何不同？

实际上，这不是一个简单的问题，因为有几个不同种类的 unikernel。从根本上说，它是一个包装好的应用程序，目标是特定的运行时环境，如虚拟机。因此，您基本上是将虚拟机管理程序层用作操作系统。

一方面，我们有像 Xen 项目的 MirageOS 这样的项目，它是单语言单内核。在单内核堆栈的最底层，有一个单内核基础，这是一个非常小的薄层，直接与虚拟机管理程序或硬件交互。在 unikernel 基础之上，有一个非常小的语言运行时层，一个单独的应用程序在其上运行。

通常，单核也没有进程，在一个地址空间中运行。其他的 unikernels，如[rum run](https://github.com/rumpkernel/rumprun)，并不依赖于特定的语言。例如，RumpRun 允许 POSIX 风格的应用程序作为单内核运行。

从某种意义上说，单核有点像运行在 x86、ARM 或其他本机指令集上的 Java 虚拟机。

JVM 背后最初的设计思想之一是可移植性。Java ME 和它的前身最初是打算在裸机上运行的。因此在某种意义上，裸机环境的 J2ME 运行时非常类似于单内核基础。单核和 JVM 的另一个相似之处是，在 JVM 中，你也只有一个地址空间，内核和用户空间没有分离。当然，这个类比并不是 100%正确，但是它可能提供了另一种思考单核的方式。

**TNS:** 有意思。因此，在这方面，单核就像 JVM。

**Kurth:** 当然有一些相似之处，但是，当然，单核是不同的，存在于 Haskell、OCaml、Erlang、Java 等语言中，现在甚至有一个针对 C++11 的项目。使用 Haskell 和 OCaml 等语言，您还可以依靠编译器或链接器来消除所有死代码，这是使用更动态的语言所做不到的。

**TNS:** 数据中心运行单核需要什么？你需要某种形式的 Linux 和 Xen 吗？

运行一个单内核所需要的——这适用于所有的单内核——就是拥有一个单内核库。如前所述，这是一个非常薄的层，向语言运行时公开基本的硬件功能(通常是 I/O)。今天我们有两个用于 Xen 的单内核基础:一个是 [Mini-OS](http://wiki.xenproject.org/wiki/Mini-OS) ，另一个是 RumpRun。

其他人，比如 IBM，刚刚开始为 KVM 试验一个名为 [Solo5](https://github.com/djwillia/solo5) 的单核基础，但这都是很早的事情。存在一些挑战，例如启动速度，这可能不容易解决。但是这整个想法正在加速发展。

**TNS:** 您认为还有哪些用例对单核特别有益？[我们从 Docker 那里听说](https://thenewstack.io/docker-buys-unikernel-systems-plans-bring-unikernels-data-center/)有两种用例是针对非常小的嵌入式系统和非常大的分布式应用。

Kurth:我认为你说得很对。这对于这些类型的应用程序来说非常有趣，而且在应用程序由协作微服务构建的世界中也是如此。单核为构建这样的系统提供了一个额外的工具。

在我进入云计算领域之前，我已经在嵌入式环境中工作了很长一段时间，unikernels 背后的一些想法与传统的嵌入式软件开发并没有太大的不同。

然后，如果你把标准化的工具组合起来，比如 Docker 提供的，你会得到一个标准化的工具链，它有可能以类似的方式覆盖不同的细分市场。这是一个非常强大的想法。当然，这将完全取决于这将如何实现，以及它在实践中如何工作。但是潜力是存在的，它可以让许多用户和开发者的生活变得更加容易。它甚至可能打破不同行业传统上处理软件工程的方式之间的隔阂。

让我们来谈谈其中的一些权衡。比如，我听说你必须把你的应用移植到单核上。这怎么可能呢？

**Kurth:** 对于某些单核来说，你当然必须从头开始编写应用程序。然而，对于其他应用程序(如 RumpRun ),您基本上只需将现有的应用程序编译到一个新的 unikernel 上。根据开发者的说法，移植的最大任务是删除你不需要的功能。

第一步是选择一个典型的应用程序(例如 NGINX ),包括所有的依赖项。请注意，可能有数百个库依赖项。第二步，去掉不需要的功能。这在今天是一个手动过程，但很可能是自动化的。然后，当然，你要测试最终结果。

**TNS:** 调试怎么样？Joyent 的 Bryan Cantrill [说你不能调试单核](https://thenewstack.io/docker-buys-unikernel-systems-plans-bring-unikernels-data-center/) …

Kurth: 好的，我理解他的观点，Bryan 声称你必须有一个带进程的操作系统来支持调试。这是一种非常以桌面为中心的世界观，也不完全正确。

如果是，你就不能调试任何深度嵌入的东西或者任何物联网设备。然而，有很多例子表明你可以。您只需将正确的接口构建到要调试的应用程序中，然后远程连接到被调试的应用程序。

归根结底，这些都是可以做到的。你只需要想去做。这只是一个工程问题。实际上并没有那么复杂。回到 Java 的类比，您调试一个 Java 应用程序，它从您的桌面运行在您的手机上。您所需要做的就是将适当的 Java 调试代理构建到您的 Java 映像中。

此外，部署的大多数生产代码都禁用了调试功能，以最大限度地降低安全风险。因此，在生产环境中提供有限的调试支持并不罕见。

![larsk (2)](img/7f543ea8f307a1acdfe7b0e6ea6761cc.png)

**TNS:** 因此，就像任何新技术一样，这只是一个建立正确的调试工具的问题。

对于许多 unikernels 支持的语言来说，调试工具已经存在。如果你看看 Haskell，有一个远程调试器包，理论上，你应该能够通过网络连接使用它来调试单内核。它可能不能开箱即用，但是我相信在 unikernels 中缺少调试支持是可以克服的。

*马拉·克鲁克转录*

Docker、IBM 和 Joyent 是新堆栈的赞助商

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>