# 面向开发人员的 6 项云本地注意事项

> 原文：<https://thenewstack.io/6-cloud-native-dos-and-donts-for-developers/>

[Lightbend](https://www.lightbend.com/) 赞助了这篇文章。

 [克林·芬利

Klint Finley 是一名专业作家和分析师，专门研究企业计算和开发人员技术。他在《连线》杂志担任了近八年的特约撰稿人，报道了人工智能、云计算和数据科学等主题。他的作品也出现在读写网、TechCrunch 和 BoingBoing 上。Klint 位于俄勒冈州波特兰市。](https://www.linkedin.com/in/klintron/) 

世界各地的开发人员正在深入进行迄今为止最大的软件转型之一:从单片、单节点应用程序迁移到在分布式系统上运行的基于微服务的云原生应用程序。从穿孔卡片到人类可读编程语言的转变可能没有这么大，但这是事实。

Lightbend 最近完成了一项针对 1000 多名开发人员和其他 IT 决策者的[调查](https://info.lightbend.com/Cloud-Native-Adoption-Trends-Report.html?utm_source=website&utm_medium=resource-panel&utm_campaign=COLL-2020-Cloud-Native-Adoption-Trends-Report&utm_term=none&utm_content=none)，揭示了企业在这一转变过程中面临的挑战以及他们如何面对这些挑战。作为一名开发人员或软件工程师，你可以从这项研究中获得以下信息:

***不要*忘记*为什么*你要采用云原生技术。**

很容易陷入你正在使用什么技术的问题中，以至于你忘记了你最初为什么要使用它们。但是请记住，采用云基础设施——无论是您自己的数据中心中的 Kubernetes 集群，还是公共云中的无服务器 API 都不是我们的目标。目标是帮助您的组织构建更具可伸缩性和灵活性的应用程序，并且更快地完成。如果您在构建应用程序时没有真正考虑云基础架构的优势和劣势，那么您很有可能没有真正实现您组织的真正目标。

***Do* 设计云原生应用，处理无响应或损坏的组件。**

节点崩溃。网络失灵。远程 API 会产生意外的结果。云原生开发需要你优雅地处理这些问题。应用程序需要给用户某种响应，即使一个或几个组件损坏或没有响应。您还需要考虑一旦损坏或不可用的组件再次工作，如何进行恢复。查看[反应原则](https://principles.reactive.foundation/)以获得更多指导和入门技巧。

***不要忘记安全性和合规性。***

云原生应用具有独特的合规性和安全性挑战。接受调查采访的高管一次又一次地表示，他们希望开发人员能够提前更多地考虑这些问题。尽早将安全和法规遵从性团队引入开发过程的开发人员——并且愿意将工作投入到理解其行业的安全和法规遵从性需求中——不仅会在工作场所取得成功，而且还可能通过避免在开发周期中进一步重构功能或整个应用程序的需要来节省他们自己和他们团队的工作。

***尽快找到可以转移到微服务或无服务器的功能。***

 *云原生开发不是一个要么全有要么全无的命题。你不必一次扔掉所有的巨石。您可以构建面向微服务的全新应用程序，同时查看所有现有的整体应用程序，并考虑可以取消哪些功能。跨多个应用程序共享的功能，如支付处理，是一个很好的选择。CPU 密集型特性也会降低整个应用程序的速度。图像转换是最好在功能即服务(FaaS)平台上单独运行的一个经典例子。FaaS 不会强迫用户等待应用程序来调整他们上传的一些图像的大小，而是可以在应用程序的其余部分继续运行的同时处理这项任务。

***不要*认为更多可配置或可移植的解决方案是“银弹”**

依赖给开发人员提供大量选择并且完全可以从一个云移植到另一个云的框架是很诱人的。但是更多的选择和控制也意味着更多的复杂性和更多的维护责任。结果是您需要做更多的工作，而花更少的时间来构建提供商业价值的特性。当然，依赖云提供商的特殊功能会降低应用程序的可移植性。但是，如果您没有利用这些提供商提供的资源，您真的从云获得了全部可能的价值吗？有时候，最好牺牲一点控制来支持敏捷性和更专注于重要事情的能力。

***做*决定什么样的取舍是你的组织可以接受的。**

构建云原生应用程序需要权衡利弊。您需要了解这些权衡，并做出明智的决定，决定您的组织愿意牺牲什么，不愿意牺牲什么。这通常意味着与管理团队达成妥协。确保您的技术目标与他们的业务目标一致。

## 结论

向云原生环境的大规模转变将要求您放弃许多您熟悉的东西，从架构到开发流程再到框架。这也意味着放弃对应用程序某些部分的一定程度的控制。但是这种变化也将是解放性的，将您从开发工作的繁重任务中解放出来，因为您将注意力集中在更高层次的特性上。这种转变意味着你开始更多地关注最初让你对编程感兴趣的东西。

*下载您的* [*云原生采用趋势 2020-2021*](https://info.lightbend.com/Cloud-Native-Adoption-Trends-Report.html) *以探索开发人员和 IT 领导之间关于云原生迁移的最高优先级的持续紧张关系。*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*