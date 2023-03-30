# Box 的 Kubernetes 之旅的起起落落

> 原文：<https://thenewstack.io/the-ups-and-downs-of-boxs-kubernetes-journey/>

KubeCon+CloudNativeCon 赞助了这个播客，作为对 Kubernetes 终端用户的一系列采访的一部分。听听之前关于防火墙后的[维基百科的基础设施是什么样子的](/what-wikipedias-infrastructure-is-like-behind-the-firewall/)和【Conde Nast 如何创建统一的基础设施平台的故事。

在线存储管理公司 [Box](https://www.box.com/home) 是首批基于 Kubernetes 的公司之一。最初在 PHP 上创建平台时，Box 的架构仍然使用 PHP 架构的某些部分。今天，Box 作为一个软件平台的云原生之旅的案例研究。该公司还继续依赖其遗留的基础设施，这些基础设施可以追溯到 PHP 在其数据中心的裸机服务器上运行的时代。

在本期 [The New Stack Analysts](/podcasts/analysts) 播客中，Box 的工程总监 [Kunal Parmar](https://www.linkedin.com/in/kunalparmar) 与主持人 [Alex Williams](/author/alex/) 讨论了云内容管理提供商的云原生之旅的演变，Alex Williams 是新堆栈的创始人和发行人；[云原生计算基金会(CNCF)生态系统副总裁 Cheryl Hung](https://uk.linkedin.com/in/cheryljhung)；和[肯·欧文斯](https://www.linkedin.com/in/kenowens12/)，云原生工程副总裁，[万事达](https://www.mastercard.us/en-us.html)。

[一家云管理提供商 Kubernetes Journey w/Kunal Parmar of Box 的沉浮](https://thenewstack.simplecast.com/episodes/the-ups-and-downs-of-one-cloud-management-providers-kubernetes-journey-w-kunal-parmar-of-box)

Parmar 说，在 Box 采用 Kubernetes 之前，该公司寻求“在 monolith 之外创造更多服务，以便有效地扩大规模”的方法。他解释说，实现这一点的一个方法是将其传统的整体应用程序转变为微服务。

“对于任何已经(转向 Kubernetes)的人来说，他们会知道这是一个真正漫长而艰难的旅程。因此，与此同时，我们一直专注于将 Kubernetes 用于我们在 monolith 之外构建的所有新微服务，”Parmar 说。“今天，我们正处于这样一个时刻，我们实际上正在考虑开始将 monolith 迁移到 Kubernetes 上运行，以便我们可以利用 Kubernetes 带来的好处。”

Box 转向 Kubernetes 背后还有另一个激励因素，Parmar 说这可能代表了一种“不受欢迎的观点”。

“我实际上相信巨石柱可能永远不会完全消失，但它们的尺寸肯定会缩小，”他说。

“在某种程度上，继续打破一个庞然大物的投资回报率变得足够低，以至于在这个庞然大物上再花时间是没有意义的，”Parmar 说。“因此，尽早将巨石放在 Kubernetes 上可以让我们长期受益。”

一个关键问题是决定何时从单一应用或平台转换到微服务是否值得投资。决定性因素可以归结为“真正试图理解你想要解决的问题。”

在 Box 的案例中，采用 Kubernetes 和微服务是解决与创新相关的问题以及更快地为其应用程序和平台添加新功能的一种方式。在 Box 采用 Kubernetes 之前，可能需要几个月的时间才能将新的软件服务投入生产。

“我们最终投资 Kubernetes 的转折点是一个团队花了大约六个月的时间投入生产。这真的很糟糕，因为我们阻止了许多我们希望客户利用的创新，”Parmar 说。“如今，借助我们基于 Kubernetes 的平台，一项新的微服务投入生产通常只需不到一周的时间，平均而言，我认为需要几天的实际努力才能实现。”

与此同时，Box 对 Kubernetes 的采用和依赖是一个“不断发展的故事”

“我对社区中的创新数量感到非常惊讶，Kubernetes 只是冰山一角。CNCF 在培育创新社区方面做得很好，不仅是在 Kubernetes 一方，甚至对云原生生态系统的其他部分也是如此，”Parmar 说。“在我们这方面，在云原生前端，我们首先做的是微服务，我们今天非常倚重，我们希望尽可能多的新功能内置于整体架构之外的微服务中。”

云计算原生计算基金会是新堆栈的赞助商。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>