# Linkerd 的小秘密:一个闪电般的速度，服务网格集中的 Rust 网络代理

> 原文：<https://thenewstack.io/linkerds-little-secret-a-lightning-fast-service-mesh-focused-rust-network-proxy/>

[KubeCon + CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 赞助了这篇文章，期待 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 于 8 月 17 日至 20 日发布。

 [威廉·摩根

William 是 bound 的联合创始人兼首席执行官，该公司是开源服务网格项目 Conduit 和 Linkerd 的创始人。在 Ruby 之前，他是 Twitter 的基础设施工程师，在那里他帮助 Twitter 从一个失败的单片 Ruby on Rails 应用程序转移到一个高度分布式的容错微服务架构。他是 Powerset、微软和 Adap.tv 的软件工程师，MITRE 的研究科学家，拥有斯坦福大学计算机科学硕士学位。](https://www.linkedin.com/in/wmorgan/) 

像 [Linkerd](https://linkerd.io/) 这样的服务网格可以提供关键功能，如透明相互 TLS、gRPC 负载平衡、蓝绿部署和黄金指标。但是像所有的抽象一样，这些特性是有代价的。这些成本中的一部分是人的成本:服务网络越复杂，成功运营它所需的努力就越多。一些成本是**系统**成本:服务网格消耗 CPU 和内存，并给应用程序带来延迟。

Linkerd 的目标是通过成为 Kubernetes 最小、最快的服务网络来最大限度地降低这一成本(这一说法[已经得到第三方](https://kinvolk.io/blog/2019/05/performance-benchmark-analysis-of-istio-and-linkerd/)的证实)。但它是如何实现这一壮举的呢？在这篇文章中，我们揭示了 Linkerd 的秘密武器:一个闪电般快速的 Rust 代理，简称为 *Linkerd2-proxy* 。与 Envoy、NGINX 和 haproxy 等通用代理不同，开源的 Linkerd2-proxy 被设计为只做一件事，而且做得比任何人都好:成为一个服务网格 sidecar 代理。

事实上，我们相信 Linkerd2-proxy 代表了安全、现代网络编程的最新水平。它是完全异步的，用现代类型安全和内存安全的语言编写。它充分利用了现代 Rust 网络生态系统，与亚马逊的鞭炮等项目共享基础。它具有对 gRPC 等现代网络协议的本机支持，可以基于实时延迟对请求进行负载平衡，并针对零配置使用进行*协议检测*。它是完全开源的，经过审计和大规模的广泛测试。

但是事情并不总是这样。事实上，Linkerd2-proxy 一开始是一场赌博。2018 年，Linkerd 团队做出了一个艰难的决定，即重写 Linkerd，并在 Linkerd 1.x 中摆脱基于 JVM 的 Scala、Netty 和 Finagle 的“Twitter 堆栈”。很明显，控制平面应该用 Kubernetes 生态系统的通用语言 Go 编写。但是代理呢？Linkerd 2.0 是否应该建立在 Envoy 之上？NGINX？还有别的吗？

当我们评估这些选项时，我们最终走向了一个不同的、风险更大的方向:我们决定，如果我们真的想构建最快、最小的服务网格，这些选项都不行。我们真正需要的是一个新的代理，特定于服务网格用例。它应该是用铁锈建造的。

我们选择这条道路有三个原因:

1.  1.  **安全。**服务网格数据平面的安全性至关重要。我们知道代理将负责高度敏感的信息，例如客户 PII 和 HIPAA 主题数据以及 PCI 主题数据。Rust 对内存安全的保证让我们避免了一整类常见的漏洞和 CVE，否则它们可能会导致重大的安全漏洞。
    2.  **最小的占地面积，最高的性能。**性能和资源成本至关重要，仅次于安全性。我们需要尽一切努力来减少 Linkerd 数据平面的延迟、内存和 CPU 使用。我们知道，为服务网格用例专门编写一个代理*将允许我们尽可能地保持精简。*
    **   **简约。**降低系统的复杂性不仅仅是一件好事，它还是运营服务网络的人力成本的核心决定因素。我们需要 Linkerd“正常工作”,这意味着避免所有的配置、调优和操作复杂性，这些都是通用代理的重要组成部分。*

 *尤其是选择不使用 Envoy 是一个艰难的决定——特别是考虑到 Envoy 在 Kubernetes 社区的受欢迎程度。然而，最终，Linkerd 对资源占用和安全性的要求对 Envoy 来说过于严格，成为不现实的选择。特使是一把瑞士军刀，而我们需要的是一根针。

今天，Linkerd2-proxy 已经为世界各地的组织提供了数十亿个请求。它以优异的成绩通过了由 CNCF 赞助的第三方安全审计，并位于每个 Linkerd 安装的核心——通常有几兆的内存和亚毫秒 p99 延迟！也许最有趣的是，Linkerd2-proxy 的神奇之处是看不见的:就像一个好的实现细节一样，绝大多数 Linkerd 用户部署了大量的 Linkerd2-proxy 实例，却几乎不知道它们在那里。

在接下来的几周里，我们将分享更多关于 Linkerd2-proxy 的内部工作方式，以及我们在开发一个现代的、安全的、基于 Rust 的网络代理的过程中所学到的一些经验。

*要了解更多关于服务网格和其他云原生技术的信息，请考虑参加 8 月 17 日至 20 日的 KubeCon + CloudNativeCon EU 虚拟会议。*

![](img/75815f6c9d934e86ec6fa33b77909e39.png)

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*