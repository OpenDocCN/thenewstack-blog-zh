# 服务网格:云迁移的门户

> 原文：<https://thenewstack.io/when-you-need-or-dont-need-service-mesh/>

*This is the second part of a three-part series. You can read the first part [here](https://thenewstack.io/how-istio-is-built-to-boost-engineering-efficiency/).*

Aspen Mesh 赞助了这个播客，作为讨论服务网格如何帮助开发人员的一系列采访的一部分。听听其他部分关于[如何建造 Istio 来提高工程效率](https://thenewstack.io/how-istio-is-built-to-boost-engineering-efficiency/)和第三部分[这里](https://thenewstack.io/how-a-service-mesh-amplifies-business-value/)。

对于任何选择向 Kubernetes 平台转移的组织来说，采用服务网格越来越被视为一个重要的构建模块。由于服务网格为微服务管理提供了可观察性、连接性和安全性检查，因此 [Istio](https://istio.io/) 的底层功能和开发是其运营和最终标准化的关键组成部分。

在第二集[中，New Stack Makers](/podcasts/makers) 由三部分组成的播客系列介绍了 [Aspen Mesh](https://aspenmesh.io/) ，通讯员 [B. Cameron Gain](/author/bruce-gain/) 展开了关于服务 Mesh 真正做什么以及它如何与 Kubernetes 一起使用的技术模式的讨论。参与对话的还有创始人工程师扎克·布彻、Aspen Mesh 联合创始人兼首席技术官安德鲁·詹金斯。我们还将介绍 service mesh，尤其是 Istio，如何在整个应用程序生命周期中帮助团队更好地利用容器和 Kubernetes。

[当你需要(或不需要)服务网 w/ B .卡梅隆增益](https://thenewstack.simplecast.com/episodes/when-you-need-or-dont-need-service-mesh-w-b-cameron-gain)

服务网格可以帮助组织迁移到云原生环境，弥补云环境中内部数据中心部署与容器化云环境之间的管理差距。一旦实现，如果运行正常的话，服务网格应该会降低这个过程的巨大复杂性。事实上，对于许多 DevOps 团队成员来说，没有服务网格就无法实现向云原生环境和 Kubernetes 的转变。

Butcher 说，在内部服务器和多云部署之间划分的典型环境中，服务网格通过支持“那些需要跨这些不同环境进行通信的组件的通信”，提供了“公共基础”。

“这就是投资的身份和安全方面[涉及]执行一个组织的监管控制的地方，”他继续说。“我的所有环境都是一致的，我可以向审计员证明的环境也是一致的，这些环境都是强制执行的。”

Butcher 说:“服务网格为您提供的集中控制和一致性非常有用，有助于让这种分裂的基础架构世界、这种多云的本地世界变得理智。

Jenkins 解释说，最终，组织将服务网格作为“不仅仅是部署问题”的答案，而是在云原生之旅中“将所有部分集成在一起”的一种方式。

詹金斯说:“这是你想要的最终目标，通过让开发人员能够在更小的组件上快速移动来释放开发人员的效率，这些组件都被缝合成用户的集成体验——但无论你在哪里，你都必须从这里到达那里。”“因此，我们发现组织大量使用服务网格来帮助完成这一演进过程。这涉及到我们现在所处的位置，将一些部分转移到更多的云原生模型中，并开发新的云原生组件，但不要放弃您已经完成的一切。”

与此同时，组织正受益于服务网格以及 Istio 的成熟。例如，随着最近发布的 [1.6.4](https://istio.io/latest/news/releases/1.6.x/announcing-1.6.4/) 和 [Istio 1.6.3](https://istio.io/latest/news/releases/1.6.x/announcing-1.6.3/) ，最近的一个特性是“真的很无聊——这很好，”詹金斯说。

詹金斯解释说，例如，现在更容易“回过头来充实需求，确保我们采用组织的需求、政策和类似的东西”。“因此，这只是一个很好的例子，说明了这一方面相对于另一方面已经发展了几个版本，并且越来越成熟。”

詹金斯说，开发中的另一个主要新功能是“web assembly support”，作为一种扩展 Istio，特别是 sidecar Envoy 代理的方式，“以更可移植和快速发展的方式，而不是必须在系统中构建一些非常低级的组件”。“我认为这将非常棒，因为它将允许开发人员将某种能力扩展到服务网格，但所有这些都不必发生在这个拥挤的核心中，在这里稳定性是一个极其重要的问题，这可能是对创新的自然拖累。因此，这种能力打开了网络组装的大门，使我们能够做到这两点:稳定性和创新的大门。”

然而，尽管大肆宣传，仍然有一些不需要服务网格的情况。换句话说，服务网格并不是所有开发运维的终极解决方案。“我不认为说‘嘿，每个人都必须使用这个新东西’是诚实的，”詹金斯说。“实际上存在一些问题，例如，你不需要 Kubernetes，你可能根本不需要容器，或者如果你考虑无服务器的话。”

当组织考虑采用什么来促进他们的软件开发和部署目标时，现在有数百种开源工具和解决方案可供选择。詹金斯说:“你需要的东西总会有一个连续统一体。“毫无疑问，所有问题都可以通过服务网格来解决，并且都需要服务网格。”

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特(Twitter)或脸书(T2)与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[反馈@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>