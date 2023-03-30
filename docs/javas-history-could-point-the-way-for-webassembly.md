# Java 的历史可以为 WebAssembly 指明方向

> 原文：<https://thenewstack.io/javas-history-could-point-the-way-for-webassembly/>

很难相信，自 2001 年互联网大崩盘以来，已经过去了 20 多年。每当周期性科技走上下行之路，互联网大崩盘就继续成为潜在厄运的先兆。我清楚地记得，在 2001 年大崩盘后不久，我就和 IT 领域的失业者或未充分就业的人在一起。我们就是这么做的:消磨时间。

那段时间，有一天在纽约市的一个公园里，新泽西州蒙特克莱尔的布鲁克代尔公园，我的一个朋友正坐在公园的长椅上敲打着他的笔记本电脑，他说有一个非常酷的网站创建工具叫 Java。事实上，它已经存在很长时间了，但他描述说，你可以用 Java 代码编程并部署在网站上你想部署的地方，这是多么令人惊讶，他说。当然，与 20 世纪 90 年代 HTML 代码提供网站设计的主要元素相比，它在改变网站用户体验方面发挥了关键作用。当然，为什么不呢，我要去看看，我说。剩下的就是历史了，因为 Java 不仅在 web 开发中，而且在整个 IT 基础设施中都获得了历史地位。

快进到今天:有一个叫做 [WebAssembly 或 Wasm](https://thenewstack.io/what-makes-wasm-different/) 的东西，它提供了一个非常相似的声明。你在哪里[写一次，部署在任何地方](https://thenewstack.io/yes-webassembly-can-replace-kubernetes/)。不仅仅是为它最初创建的 web 应用程序，而是跨网络和在 CPU 上运行的任何东西。

让你想起了什么？

[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉新的堆栈:“Wasm 可能是 Java 的孙子，它遵循允许开发人员在任何设备上运行相同代码的广泛原则，但同时 Wasm 解决了阻止“任何设备上的 Java”的最初愿景成为现实的根本问题。”。

## 简单的例子

Wasm 已被证明在许多不同的硬件环境中非常有效，从服务器端到边缘部署和物联网设备，或者代码可以直接在 CPU 上运行的任何地方。代码捆绑在包装整齐的 Wasm 可执行文件中运行，可以与容器甚至迷你操作系统相比，后者运行时所需的代码和目标配置要少得多(如果有的话)。从本质上讲，无论代码部署在哪里，应用程序都远远超出了 web 浏览器环境的范围。因此，开发人员创建代码并部署它。事情真的可以这么简单，尤其是在使用 [PaaS 解决方案](https://thenewstack.io/should-webassembly-get-a-paas/)的时候。

Volk 指出，最重要的是，Wasm 实现了真正的“一次编码，随处部署”的能力，即相同的代码可以在任何支持的设备上运行，而无需重新编译。“Wasm 并不局限于一种开发语言，而是支持 Python 和许多其他流行语言。开发人员可以在服务器和其他设备上的共享环境中运行他们的代码，而不必担心底层的 Kubernetes 集群或虚拟机管理程序，”Volk 说。“他们还可以获得针对其微服务的统一日志记录和跟踪，开箱即用。与 Java 相比，这种简化的开发人员体验是另一大优势。”

在最近的 [KubeCon + CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 会议期间，[发表了一篇关于使用 Wasm 取代 Kafka 进行低延迟数据流传输的演讲](https://www.youtube.com/watch?v=EVW9hPdfRdY&ab_channel=InfinyOn)。与此同时，Java 继续被用于网络应用程序，即使替代方案可以提供更好的性能，但开发人员继续使用它，因为他们只是喜欢使用 Java。因此，如果 Wasm 的运行时性能不太好——事实确实如此——开发人员可能仍然会因为它的易用性而采用它。

“Wasm 的一大优势是开发人员很容易上手，只需部署一些代码并立即观察它的运行。这是一种价值主张，可能需要一段时间才能完全理解，但一旦你迷上了，你就不会再担心底层基础设施的细节了，”Volk 说。“然后你可以决定替换 Kafka 是否有意义，或者你只是想将其连接到你的 Wasm 应用程序。”

Java 的整个“编写一次，在任何地方运行”的承诺[与 WebAssembly](https://thenewstack.io/webassembly-5-predictions-for-2023/) 的[非常相似，Fermyon Technologies](https://www.fermyon.com/) 首席执行官[和联合创始人 Matt Butcher](https://www.linkedin.com/in/mattbutcher/) 告诉 New Stack:“事实上，Luke [Luke Wagner 是 WebAssembly 的原作者]曾经告诉我，他认为 Java 是 20 年来有用的研究，形成了如何编写下一代(例如 Wasm)的基础，”Butcher 说。

[https://www.youtube.com/embed/H6GfCJUJ-QU?feature=oembed](https://www.youtube.com/embed/H6GfCJUJ-QU?feature=oembed)

视频

## 还是不一样

Java 和 Wasm 之间有一个关键的区别:它们的安全姿态。

它的可移植性和一致性可以使安全性和合规性更容易管理(同样，它在 CPU 级别上以二进制格式运行)。此外，Wasm 在结构上的部分简单性意味着代码是在一个封闭的沙盒环境中发布的，几乎直接发布到端点。Java 的(以及。Butcher 说，NET 的默认安全姿态是“信任它正在运行的代码”，而 Java 授权代码访问文件系统、环境、进程和网络。

相比之下，Wasm 的默认安全姿态是不信任在语言运行时中运行的代码。对于 Fermyon(专注于云和边缘)，这是使 Wasm 成为云服务的良好候选人的关键特征，”Butcher 说。“因为它是容器和虚拟机采取的相同的安全姿态。这使得我们作为云供应商能够向用户销售服务，而无需审查或批准用户的代码。”

换句话说，在使用分布式容器化和微服务环境时，需要担心的攻击点数量会成倍增加。Volk 同意 Matt 的评估，因为依靠零信任原则允许基于相同技术的多租户，如 mTLS 和 jwt，这些技术已经用于 Kubernetes 上运行的应用程序容器，Volk 说。“这使得 Wasm 很容易在共享环境中安全地试用，这应该会降低入门的初始障碍，”Volk 说。

InfinyOn 的首席技术官 Sehyo Chang 告诉新的堆栈，Java 和 Wasm 之间的另一个巨大差异是，Java 需要 JVM，而不需要额外的资源，如垃圾收集器。“另一方面，Wasm 非常接近底层 CPU，不需要 GC 或其他大量粘合逻辑，”Chang 说。“这使得 Wasm 可以在非常低功耗的 CPU 上运行，适合在嵌入式设备或物联网传感器中运行，以在任何地方运行。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>