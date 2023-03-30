# Google Kubernetes 引擎提供多种发布渠道，扩展对 Windows 的支持

> 原文：<https://thenewstack.io/google-kubernetes-engine-offers-multiple-release-channels-extends-support-to-windows/>

寻求使[谷歌 Kubernetes 引擎(GKE)](https://cloud.google.com/kubernetes-engine/) 更加灵活和功能丰富，谷歌云将从下个月开始让组织选择 GKE 的发布渠道，云服务在 [KubeCon + CloudNativeCon](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2019/) 期间透露。

遵循与其他开源提供商类似的系统，GKE 的发布渠道选项将包括“快速”、“常规”和“稳定”这将允许组织选择 alpha 版本作为“快速”选项的一部分，“常规”版本作为标准版本的需要，而“稳定”版本作为经过测试的版本。

当然，组织内的不同团队可以为 GKE 选择不同的发布渠道。例如，一个测试团队可能想要自动的 alpha 版本，而一个业务模型关键的部署可能需要“稳定版本”

“快速”频道还将提供与 Windows 应用程序容器兼容的 GKE 1.14。在 Kubernetes 1.14 中，谷歌云表示，开源社区已经为运行在[微软 Windows Server 2019](https://www.microsoft.com/en-us/cloud-platform/windows-server) 上的 Windows 节点和应用程序提供了支持。谷歌云表示，GKE 1.14 将于 6 月开始容纳 Windows 服务器容器。

Google Cloud 还引入了一个 stack driver Kubernetes monitoring，它提供了 Kubernetes 对日志、事件和元数据的可观察性，并且还与 GKE 进行了预集成。谷歌云表示，通过这种方式，它可以用来提高 GKE 上运行的服务的可靠性，无论是 Kubernetes 云和本地部署。

在 KubeCon + CloudNativeCon 期间，谷歌产品管理总监 Aparna Sinha 告诉新的堆栈，在客户对“我们看到的一些问题”的反馈后，谷歌选择为 GKE 版本增加更多灵活性。

“我们以前想引入新功能，一些用户想使用这些新功能，但后来出现了他们不想使用的集群，”Sinha 说。“所以，我们说，‘好吧，这样做的方法是提供不同的火车:你有慢车、快车和动车——你选择适合你的选项。’"

Sinha 说，组织现在可以更加灵活地只使用“最新和最棒的 GKE 功能，直到他们通过大量测试”。Sinha 说:“你知道，即使是同一个客户，有时也会有一些应用程序希望在开发测试中运行，而其他应用程序也在运行。

Sinha 说，虽然 Google Cloud 只在其“快速”发布通道选项中提供对 Windows 服务器容器的 GKE 支持，作为白名单功能，但社区对广泛的 Windows 支持有明显的兴趣。“我们有很多客户对在 Kubernetes 上运行基于 windows 的应用程序感兴趣，”Sinha 说。"你可以想象，许多人都有一个运行在 Windows 操作系统上的应用程序."

如上所述，谷歌云的 GKE 发布选项结构在软件世界中并不少见。然而，对于许多使用 GKE 的组织来说，它应该是一个受欢迎的选择， [Chris McClimans](https://www.linkedin.com/in/hippiehacker) ，又名“嬉皮士黑客”，是新西兰开源技术公司 ii.coop 的首席执行官和创始人

除此之外，发布渠道允许组织更好地“设定他们对什么是稳定的期望”，McClimans 说。“渠道版本允许[组织]策划平台体验。“这就像说，‘如果我是保守的，我不想被更新——我想成为最后一个人，一个每个人都已经经历过戏剧性事件的人。”。或者，他们可能会选择更接近他们感到超级自信的地方，不会有任何不匹配的期望…然后是测试版，就像这样，“所以我们的东西的这种配置，不是每个人都做过，但你不是第一个——这可能就像，“抓住你的帽子，它可能会在 30 天内被拆除”。"

KubeCon + CloudNativeCon 是新堆栈的赞助商。

Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>