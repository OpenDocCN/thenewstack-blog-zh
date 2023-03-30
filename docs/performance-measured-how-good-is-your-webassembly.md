# 性能测量:你的 WebAssembly 有多好？

> 原文：<https://thenewstack.io/performance-measured-how-good-is-your-webassembly/>

WebAssembly 采用率[正在激增](https://thenewstack.io/yes-webassembly-can-replace-kubernetes/)。几乎每周都有至少一家初创公司、SaaS 厂商或成熟的软件平台提供商开始提供 Wasm 工具，或者已经在其产品组合中引入了 Wasm 选项。但是如何比较所有不同产品的性能呢？

好消息是，鉴于 Wasm 的运行时简单性，至少在运行时的实际性能可以在不同的 WebAssembly 产品之间直接比较。当对在 Kubernetes、容器和微服务上运行的分布式应用程序进行基准测试时，这种直接比较肯定要容易得多。

这意味着，无论 Wasm 应用是在浏览器、边缘设备还是服务器上运行，Wasm 在每个实例中提供的计算优化都是端到端的，其运行时环境处于各种隧道中，显然有利于安全，并且不受运行环境的影响，因为它直接在 CPU 上的机器级别上运行。

从历史上看，Wasm 也有一段时间了，在 2019 年万维网联盟(W3C)将其命名为 web 标准，从而成为与 HTML、CSS 和 JavaScript 并列的第四个 Web 标准。但是，虽然 web 浏览器应用程序代表了 Wasm 的核心和历史用例，但重点是它被设计为在正确配置的 CPU 上的任何地方运行。

在 PaaS 或 SaaS 服务中，Wasm 用于优化计算性能，无论它是否在浏览器中运行，Wasm 在运行时提供的计算优化可以在不同选项之间直接衡量。

至少有一个应用程序正在被越来越多地采用，它可以用来对 Wasm 不同版本的不同运行时、编译器和 JIT 进行基准测试:[libna。](https://libsodium.org/)虽然是轶事，但作者已经联系了至少 10 家使用或知道它的公司。

lib 钠包含一个用于加密、解密、签名、密码散列和其他安全相关应用程序的库。它的维护者在文档中将它描述为一个可移植的、可交叉编译的、可安装的和可打包的 NaCl 分支，并带有一个扩展的 API 来提高可用性。

密码学工程师 Frank Denis 说，自推出以来，lib nasna 基准已被广泛用于衡量最佳运行时间。Denis 指出，libna包括 70 个测试，涵盖了代码生成器可以实现的大量优化。这些测试都不执行任何类型的 I/O(磁盘或网络),所以它们实际上是以独立于平台的方式测量编译器和运行时的实际效率。“运行时在本地笔记本电脑和云中服务器上的排名是一样的，”丹尼斯说。

事实上，lib 钠对于测试一些 Wasm 应用程序是值得的， [Fermyon Technologies](https://www.fermyon.com/) 首席执行官[和联合创始人 Matt Butcher](https://www.linkedin.com/in/mattbutcher/) 告诉 the New Stack。“任何好的基准测试工具都有三个可取的特征:它必须是可重复的、公平的(或者对特定的运行时没有偏见)，并且反映产品的使用情况，”Butcher 说。“libna 是基准测试的绝佳候选。不仅加密本身是一个合适的用例，而且加密中使用的算法将找出运行时的真正计算特征。”

[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉《新堆栈》说:“libna 对于测试一些 Wasm 环境也是值得的，因为它包括具有广泛不同需求特征的基准测试任务，一些用于探测原始 CPU 或内存性能，而另一些用于检查更细微的性能特征“目前的结果表明，该套件能够揭示不同运行时之间的显著性能差异，无论是编译语言还是解释语言，”沃尔克说将这与直接在操作系统上运行、中间没有 WASM 的应用的性能进行比较，为我们提供了一个关于这些运行时未来优化潜力的好主意。"

[https://www.youtube.com/embed/H6GfCJUJ-QU?feature=oembed](https://www.youtube.com/embed/H6GfCJUJ-QU?feature=oembed)

视频

## 真实规格

在一篇[博文中。](https://00f.net/2023/01/04/webassembly-benchmark-2023/) Denis 描述了在他完成的测试中不同 Wasm 应用的基准测试。其中包括:

*   Iwasm，它是 WAMR(“web assembly micro runtime”)包的一部分，是从其存储库中下载的预编译文件。
*   Wasm2c，包含在 Zig 源代码中，用于引导编译器。
*   Wasmer 3.0，使用他们网站上显示的命令安装。这三个后端已经过单独测试。
*   Wasmtime 4.0，编译自源码。
*   通过 Ubuntu 软件包安装的节点 18.7.0。
*   Bun 0.3.0，通过他们网站上的命令 show 安装。
*   Wazero 来自 git rev 796fca4689be6，编译自源代码。

哪一个在运行时测试中脱颖而出？根据 Denis 的结果，Iwasm 是 [WebAssembly 微运行时(WAMR)](https://github.com/bytecodealliance/wasm-micro-runtime) 的一部分。 [iwasm VM 内核](https://github.com/bytecodealliance/wasm-micro-runtime/blob/main/README.md#iwasm-vm-core)用于运行 wasm 应用程序。根据该项目的文档，它支持解释器模式、提前编译(AOT)模式和实时编译(JIT)模式、LLVM JIT 和快速 JIT。

这并不意味着 iwasm 赢得了简单易用的赞誉。丹尼斯写道:“与其他选择相比，(iwasm)令人生畏。”。"它感觉像一个厨房水槽，包括不同的组件."这些包括 IDE 集成、应用框架库的远程管理和 SDK ”,使其看起来像是简单问题的复杂解决方案。文档也有点乱，让人不知所措，”丹尼斯写道。

## 运行时不是一切

还存在其他基准来衡量不同 Wasm 备选方案之间的性能差异。Denis 传达的测试备选方案包括:

然而，基准运行时性能并不是所有 WebAssembly 应用程序的基本指标。Volk 指出，还存在其他测试方法来测试不同的 Wasm 运行时，这些运行时侧重于非常具体的任务，如计算斐波那契数列、对数据数组排序或对整数求和。Volk 说，还有其他更全面的基准，包括对整个用例的分析，如视频处理，PDF 编辑，甚至基于深度学习的对象识别。

“Wasm 具有提供近即时启动和可扩展性的潜力，因此可用于经济高效地提供和扩展网络带宽和功能，”Volk 说。“根据特定用例需求评估这种快速启动能力，可以显示 Wasm 运行时对最终用户体验的直接影响。”

一些 Wasm 应用程序用于网络以改善延迟。运行时性能当然很重要，但在这种情况下，延迟性能才是最重要的， [Sehyo Chang，](https://www.linkedin.com/in/sehyo) [InfinyOn，](https://infinyon.com/)的首席技术官说。Chang 说，这是因为在任何应用程序中，延迟在决定整体用户体验方面起着至关重要的作用。Chang 说:“缓慢的响应时间会极大地影响用户参与度，并导致用户不满，从而可能导致销售机会的丧失。”。

在最近的一次 KubeCon + CloudNativeCon 的会议上，Chang 给做了一个关于用 Wasm 代替 Kafka 的演讲。Chang 说，基于 Java 的流媒体技术，如 Kafka，由于垃圾收集和 JVM，可能会经历高延迟。Chang 说，然而，使用 WebAssembly (WASM)技术可以在没有这些损失的情况下进行流处理，从而显著减少了延迟，同时还提供了更多的灵活性和安全性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>