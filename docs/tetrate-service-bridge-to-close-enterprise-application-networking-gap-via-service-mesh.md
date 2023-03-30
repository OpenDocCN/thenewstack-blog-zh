# 通过服务网格缩小企业应用网络差距的 Tetrate 服务桥

> 原文：<https://thenewstack.io/tetrate-service-bridge-to-close-enterprise-application-networking-gap-via-service-mesh/>

在某些时候，你必须停止生产你认为人们需要的东西，并开始在市场上进行测试。你必须去获得用户。大约四年前，谷歌 Istio 服务网的第一批工程师就是在这里发现自己的。但是，就像仍在兴起的云原生空间中的许多东西一样，第一反应是:嗯，这是什么？还有谁在用？

Zack Butcher 是第一批与 service mesh 合作的工程师之一，现在是 Istio 贡献者和指导委员会的成员，他说三年或更久以前，任何人都可能是第一个用户。现在我们知道 [Istio](https://thenewstack.io/what-is-istio-and-why-does-kubernetes-need-it/) 是一种机制，它不仅允许您连接服务，还允许您保护和观察每个服务，并控制它们如何相互通信。

有道理对吗？但是如果 Istio 只和 Kubernetes 合作呢？如果您的组织仍在从单一环境过渡，该怎么办？使用[多云还是混合云](https://thenewstack.io/stop-talking-about-multicloud-and-hybrid-cloud-and-start-talking-about-integration/)还是本地云——还是混合云？企业如何保护所有这些不同规模的分布式服务？

Butcher 和几个 Tetrate 的联合创始人建立了 [Tetrate Service Bridge](https://www.tetrate.io/tetrate-service-bridge/) 作为一个应用程序连接平台或技术桥梁，将您从那些传统环境带到那些现代环境，并提高可靠性和可用性。也称为 TSB，它旨在解决异构工作负载的网络问题。

Tetrate Service Bridge 构建于 Istio 之上，现已全面上市，它是针对企业级挑战的解决方案，这些挑战不能仅仅通过 Kubernetes 层抽象出来。Tetrate 团队已经围绕控制整个服务车队(从边缘到网格)的流量构建了一套核心功能。

Butcher 说，TSB 弥合了拥有服务网格能力和以安全的方式实际实现这些能力之间的差距。

他说，“这个服务网格很棒，但是我如何在我的企业中使用它呢？我如何改变我的过程来利用网格？实际上，改变流程非常昂贵，所以我怎么能不改变流程呢？”

这些企业流程也不简单。他们希望使用服务网格来加强安全性和合规性要求。或者获得对整个复杂基础架构的控制和可见性。如何在高度异构的环境中实施安全控制。

“服务网格解决了我的许多问题，但你却告诉我只能在 Kubernetes 使用它？我希望这些东西能帮助我从我的遗产到现代环境，而不是已经在那里，”布彻说。

TSB 帮助您管理所有计算，连接 Kubernetes 和传统基础设施。他给出了一些例子，你可以用它们来链接 Istio 和 Envoy，并开始组装你的应用网络。

> “Tetrate Service Bridge 是一个平台，应用程序可以安全、成功地进行通信，而不必进入其中的杂草中。”— Zack Butcher，Tetrate 的创始工程师

Butcher 说，然后是企业管理方面，团队需要能够证明他们正在正确和安全地使用服务网格。他说，TSB 使团队能够通过多租户和控制来划分他们的物理基础设施和基于云的环境，所以你可以使用服务网格“在运行时做很酷的事情”

连接工具不仅可以与 Istio 和[特使代理](https://www.envoyproxy.io/)一起工作，还可以与[阿帕奇天行者](https://skywalking.apache.org/)一起工作，实现整个系统的可观测性。

他们很清楚，虽然他们是一个方便使用这些开源工具的工具，整个 Tetrate 团队都是他们所依赖的开源项目的贡献者，但他们不是一个开放的核心公司。

“在我看来，在开放核心公司中存在着非常大的压力。如果我作为一名开发人员，我必须决定人们为之付费的项目或产品——他不想做出价值主张的决定，”Butcher 解释道。

他继续说道，“我们正在开源部分的基础上构建一个层。我们正在将这些开源部件组装成一个连贯的系统。”

这个决定的另一部分是，由于他们本质上仍然使用开源工具，企业可以通过 Tetrate 以相对便宜的方式这样做。

Butcher 指出了 TCB 这样的企业闭源产品和它所服务的开源项目之间的根本区别。

“功能以开源方式进入，然后你如何管理这些功能，以及你如何在一个组织内使用它们，这就是你放在产品中的东西，”他说。"

虽然他们在 4 月份才与 TSB 完全公开，但他们从一开始就与采纳者一起构建它。

Butcher 引用 Socrates 的话说，在经历了“采用 Istio 的痛苦——我们在一个没有用户的洞穴中”之后，他们决定与用户携手共建。

其中一个早期采用者是 FICO，该组织在美国创建了主要的信用风险评分。服务网格的一个新兴使用案例是传输中的加密，以确保符合 HIPAA 和 GDPR 不断变化的法规和标准，从而自动执行 [PCI-DSS 控制](https://www.securitymetrics.com/blog/what-are-12-requirements-pci-dss-compliance)。当金融机构仍在向微服务架构过渡时，这一点尤为重要。

FICO 自 2019 年以来一直在使用 Istio，但需要 Tetrate 来运营 Istio 以实现 PCI 合规性，该合规性要求所有数据在传输过程中加密，并且在数据库中“静止”时保持加密。

今年 3 月，Tetrate 还宣布获得了由 Sapphire Ventures 牵头的 4000 万美元 B 轮融资。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>