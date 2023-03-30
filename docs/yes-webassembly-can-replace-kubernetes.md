# WebAssembly vs. Kubernetes

> 原文：<https://thenewstack.io/yes-webassembly-can-replace-kubernetes/>

是的，WebAssembly 可以解决 Kubernetes 的一些弊病。

WebAssembly，或 Wasm，被证明是一种在 web 浏览器上运行代码的非常实用的方法，可以充当某种编译器。它作为一种语言工作得非常好，以至于[万维网联盟(W3C)](https://thenewstack.io/this-week-in-programming-the-time-has-come-to-pay-attention-to-webassembly/) 在 2019 年将其命名为 web 标准，从而成为与 HTML、CSS 和 JavaScript 并列的第四个 Web 标准。

[https://www.youtube.com/embed/-DVcchn4T_Y](https://www.youtube.com/embed/-DVcchn4T_Y)

视频

主要的网络浏览器包括首先是 Mozilla，然后是 Chrome，Internet Explorer 等。由于 Wasm 在 web 浏览器上编写代码和创建应用程序的迅速发展，它与 Wasm 兼容。除了 web 主力 JavaScript 之外，Wasm 还支持其他语言，包括 Rust、Go、.NET，C++，Python，Java 和 PHP。

一个更有趣的用例是 [Adobe](https://www.adobe.com) 如何依靠 Wasm/ [WASI](https://wasi.dev/) 平台在浏览器上直接运行 C++代码。这使得用户可以直接在浏览器上运行 Adobe 的 Photoshop 和 Acrobat，从而不再需要将这些软件工具下载到用户的机器上来工作。

最终，开发人员意识到 Wasm 也可以在服务器操作系统上运行，并且它的使用现在已经扩展到了硬件平台。它已被证明在许多不同的硬件环境中非常有效，从服务器端到边缘部署和物联网设备，或者代码可以直接在 CPU 上运行的任何地方。代码捆绑在包装整齐的 Wasm 可执行文件中运行，可以与容器甚至迷你操作系统相比，后者运行时所需的代码和目标配置要少得多(如果有的话)。从本质上讲，无论代码部署在哪里，应用程序都远远超出了 web 浏览器环境的范围。

在许多方面，Wasm 的能力可以与多语言编译器相提并论，因为它可以容纳许多不同的语言。然而，与编译器的比较在很大程度上就到此为止了。这很大程度上是因为与编译器相比，wasm 的相同二进制可执行文件可以在多个平台上运行——无需配置 Wasm 上的代码和目标设备。

在这种情况下，Wasm 无疑是对编译器时代的一个改进，在编译器时代，可执行程序和目标环境主机上的代码必须完全重新配置。一个二进制可执行文件跨多个目标，而无需重新配置:这就是 Wasm 的美妙之处。

“Wasm 最终让我们能够在不涉及开发人员的情况下，在服务器、云和边缘设备之间移动代码。这将最终结束开发者不得不花费大量时间担心调整他们的代码，然后在不同的目标平台上支持这些代码的时代，”[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉新堆栈。" Wasm 的工作是为所有这些平台提供一个一致的运行时."

由于这些原因，在某些情况下，Wasm 可以为 Kubernetes 提供一个非常好的替代方案。与 Kubernetes 相比，主要优势在于:

**简朴。**在部署应用程序时，即使应用程序被分发给不同的最终目标，也明显缺少一些步骤。Cosmonic 的 PaaS 版本只需要很少的命令行就可以部署一个应用程序，大部分是图形界面。使用 [Fermyon](https://thenewstack.io/whats-next-in-webassembly/) ，以及 Fastly 的 Compute@Edge 时也是如此。

相反，正如开发人员和 DevOps 人员非常了解的那样，作为一名开发人员，学习如何使用 Kubernetes 是相当困难的。这需要一个相当长的学习曲线，并且通常涉及到配置 YAML 文件，以及确保代码在进入部署和管理操作之前经过许多步骤和过程。

相反，安装 Kubernetes 和部署第一个应用程序通常需要几个小时，Bindle maintainer 和 [Fermyon Technologies](https://www.fermyon.com/) 首席执行官兼联合创始人 [Matt Butcher](https://www.linkedin.com/in/mattbutcher/) 告诉新堆栈。布彻说，在大约 7 分钟内将 Fermyon 平台安装到 DigitalOcean、AWS 或 Azure 上，然后部署 WebAssembly 应用程序“而无需编写一行 YAML 代码”是可能的。

**安全。**在这个高度分布式的 Kubernetes 环境中，安全性是一个现实问题，并且将继续是一个现实问题，这里无法一一列举。微服务的互连性意味着攻击者可以访问的数百个入口点中的一个，可能会对组织的整个基础架构造成严重破坏。[秘密管理](https://thenewstack.io/kubernetes-secrets-management-3-approaches-9-best-practices/)是另一个问题，就像名字一样，在指定谁可以访问容器中的秘密方面存在困难。

Wasm 的可移植性和一致性可以使安全性和合规性更容易管理(同样，它在 CPU 级别上以二进制格式运行)。此外，Wasm 在结构上的部分简单性意味着代码是在一个封闭的沙盒环境中发布的，几乎直接发布到端点。这并不是说 Wasm 从来没有漏洞可利用。只是 Kubernetes 有相对更多的可能性和妥协的切入点。

## 但它们不是一回事

Wasm 提供了巨大的机会，并可能成为大规模部署应用程序的一种方式，我们将在未来几个月和几年内看到，随着供应商在用户如何利用它方面变得更具创造性。相比之下，那些预测 Wasm 最终将吃掉 Kubernetes 的午餐并将完全取代它的人可能没有抓住要点。很难说会发生什么，以及在云环境中部署和管理高度分布式应用程序的其他技术最终会取代 Kubernetes。但它极不可能是 Wasm。

这是因为 Kubernetes 永远有它的用途。它总是被用来编排微服务，当然还有容器。也可以认为 Wasm 将会在 Kubernetes 中运行，它的支持者已经表示 Wasm 非常适合在 Kubernetes 环境中运行。

“Wasm 是一个无服务器的运行时，开发人员可以在其中部署代码，而不必同时编写和维护大量的基础设施 YAML。Wasm 为应用程序代码提供了一组标准 API，用于一致访问关键的运行时服务，如 SQL 或 NoSQL、Kafka 消息传递或代码调试，”Volk 说。“但是 Wasm 依赖于一个资源编排层，它可以由 Kubernetes 或任何其他调度程序提供，以提供这些服务运行所需的基础设施资源。然后，这些资源可以以容器、虚拟机、裸机或一些目前还没有人想到的奇特未来技术的形式交付。”

然而，并不是所有人都认为 Kubernetes 的容器编排能力将永远是事实上的选择。Butcher 说，Wasm 领域的许多人都被 HashiCorp 的 Nomad 调度程序所吸引。事实上，Fermyon 已经放弃了 Krustlet (Wasm-on-Kubernetes ),转而选择 HashiCorp Nomad 作为其调度。“Nomad 在调度容器和 web 组装方面做得非常出色，我们认为这是云协调器的未来，”Butcher 说。“我认为我们可以想象一个库伯奈特人消失，游牧人取而代之的世界。”

Butcher 说，Nomad 提供了编排容器的能力，就像 Kubernetes 一样，但它还有一个重要的附加功能:它可以调度非容器工作负载。“在 Fermyon，我们能够让 Nomad 安排和执行 WebAssembly 应用程序，而无需编写一行定制代码。”

与此同时，Kubernetes 开发人员有责任在较低层次上接受 WebAssembly，并改变内置的、特定于容器的假设，Butcher 说。Butcher 说，微软是第一家真正接受这一概念的公司，它的 [runwasi](https://github.com/containerd/runwasi) 项目是如何在 Kubernetes 内部执行 WebAssembly 的一个例子。

“runwasi 项目只是第一步，如果 Kubernetes 要保持其在微服务/容器领域的霸主地位，它需要经历一系列的转变，”Butcher 说。“Kubernetes 肯定会输，但如果不想被 Nomad 和 Wasm 超越，它的开发者和维护者需要迅速采取行动。"

## 生存威胁

不过，Wasm 对 Docker、以及集装箱构成了存在性的[威胁。与 Kubernetes 的最高级类似，Wasm 在简单性、可移植性和安全性方面的优势至少使其成为弥补 Docker 缺点的良好候选，特别是对于 edge 和分布式应用程序。然而，Butcher 指出了 Docker 在为两种不同的应用程序提供环境方面的优势:](https://thenewstack.io/when-webassembly-replaces-docker/)

*   像数据库和消息队列这样的长时间运行的进程，它们具有很强的 I/O 和内存管理需求。
*   保留应用程序状态并大量使用线程的传统代码。

“我对 Docker 的看法是，它在市场上拥有强大且可防御的地位，Wasm 不太可能取代它，”Butcher 说。“但说到微服务和 web 应用后端，我认为 WebAssembly 将会蚕食 Docker 的使用。”

因此，作为某些用例的 Docker 和容器替代品，Wasm 可以取代 Docker，但使用 Wasm 来编排容器和微服务，就 Kubernetes 可以在高度分布式云和内部环境中完成的程度而言，肯定不行。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>