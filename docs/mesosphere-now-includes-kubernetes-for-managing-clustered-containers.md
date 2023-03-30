# Mesosphere 现在包括用于管理集群容器的 Kubernetes

> 原文：<https://thenewstack.io/mesosphere-now-includes-kubernetes-for-managing-clustered-containers/>

迄今为止最有效和高效的数据中心调度和分配平台不仅将支持，而且实际上将包括谷歌用于管理集群 Linux 容器的系统。这是 Apache Mesos 项目的商业支持者 Mesosphere 根据去年 8 月与谷歌达成的协议采取行动的结果。

现在，Mesosphere 的数据中心操作系统(DCOS)——[的最新预览版可供早期注册者](https://mesosphere.com/product/)——为开发人员提供了围绕应用程序创建 Mesosphere pods 的方法，然后在大规模池化计算和存储环境中启动这些应用程序。

## DCOS 要去哪里

新堆栈的 [Alex Williams 在去年 12 月](https://thenewstack.io/mesosphere-develops-a-data-center-operating-system-and-raises-36m-from-khosla-ventures/)对 DCOS 进行了简介，此前 Mesosphere 筹集了大约 3600 万美元的风险资金。甚至从那时起，DCOS 的营销信息已经成熟，其粗糙的边缘已经被抚平。

[![IF](img/09c42e5845bdb00c8e943e7f88b5d726.png)](https://thenewstack.io/wp-content/uploads/2015/04/150420-VMware-microservices-04-Benjamin-Hindman.jpg)

本杰明·欣德曼

“DCOS 是一个软件层，它让我们能够将数据中心中的所有机器(无论是虚拟机还是物理机)组合在一起，就像一台大型计算机一样，”Mesosphere 的联合创始人兼 DCOS 首席架构师 Benjamin Hindman 在周一与 VMware 的战略简报会上解释道。“因此，运行您的应用程序更容易，管理您的应用程序也更容易，并且真正将开发人员视为数据中心中的一流实体。”

在与新堆栈的采访中，中间层高级副总裁马修特里费罗提供了进一步的细节。DCOS 的核心是 Apache Mesos，这是一种“反向虚拟化”系统，它将整个数据中心的物理资源进行池化，并通过抽象层将该池与应用程序分开。这样，应用程序可以从位于数据中心的任何位置请求资源，而不仅仅是在本地或物理联网的群集中。

特里费罗解释说，DCOS 服务实际上是写入 Mesos API 的调度程序，是对 DCOS 的扩展。调度器向 Mesos 请求资源，Mesos 通过分配可用资源来响应。然后，调度程序决定如何利用这些资源，使用他所描述的相当复杂的模型。

“人们为了运行终端用户应用程序而在 DCOS 之上构建的就是这些服务，”他说。马拉松是其中一种服务的名称，由 Mesosphere 设计，用于运行长时间运行的程序，如 Web 服务器。Marathon 与 Mesos 协调工作负载的调度，确定它如何将资源组合在一起，以及它如何建议 Mesos 如何最好地部署它们。

“Kubernetes 类似于马拉松，”他继续说道。“实际上，除了马拉松比赛之外，有人可能还想用它来代替马拉松比赛。DCOS 上的 Kubernetes 是整个 Kubernetes 调度程序，它与这个低级 API 对话，允许它调度 pod——这些协同定位的容器。Mesos 的神奇之处在于，它使得编写所有这些替代调度框架或服务成为可能。”

## "两者都用"

在周三的一篇博客文章中，谷歌产品经理 Craig McLuckie 将 Kubernetes 和 Marathon 在 DCOS 的同时推出描述为鱼和熊掌兼得。“两者都用，”麦克卢奇写道。之前， [Docker 将围绕可互换零件的道德规范](https://thenewstack.io/orchestration-toolkit-release-aims-prove-dockers-commitment-flexibility-community-ecosystem/)描述为“包含电池，但可拆卸。”

当然，在数据中心，系统分析师和架构师会选择性能最佳的工具。当性能差异变得清晰时，他们往往会选择相同的工具。那么，如果有明显的性能差异，为什么中间层会给 DCOS 用户一个选择呢？

我向中间层的特里费罗提出了这个问题，他回答说这个问题隐含着某种误解。

[![Matthew Trifiro (300 px)](img/115dab9a34cc9e864c7d575328432e9a.png)](https://thenewstack.io/wp-content/uploads/2015/04/Matthew-Trifiro-300-px.jpg)

马修·特里费罗

“当你在谷歌的云上运行 Kubernetes 时，你永远不会说，‘嗯，我是要运行 Kubernetes 还是谷歌容器引擎？’因为 Kubernetes 运行在谷歌容器引擎上，”特里费罗说，这样做阐明了这个新 DCOS 计划中的一个重要关系。

“当你在内部运行 Kubernetes，或者在另一个云中运行，甚至在 DCOS 上运行谷歌计算引擎时，你不会问这个问题，”他继续说道。“Kubernetes 有一些低级的调度功能，但这些功能并不复杂，也不像我们做的那样。当 Kubernetes 想要安排一些事情时，它实际上可以映射到 Mesos，Mesos 可以执行 pod 的实际调度。对于 Kubernetes 应用程序，它不知道区别。”

Trifiro 继续解释了一个开发环境，在这个环境中，Kubernetes 被用来对一个应用程序建模，这个应用程序可能是用 Go 或 Python 编写的，围绕着一个可管理的 pod。当该模型扩展到数据中心规模时，开发人员不希望对其进行改造。DCOS 提供了一种将 pod 集成到 Mesos 调度环境中的方法，在 Mesos 调度环境中，Mesos 提供了 pod 本来可以自己获取的资源。但是豆荚实际上不需要知道区别。

## 另一方面

然而，特里费罗后来承认，有一个非常关键的区别 pods 可能会很好地利用:大数据资源的可用性，DCOS 也在大规模管理。是的，你可能要考虑改造你的 Kubernetes 应用程序。

“一个现代的应用程序正在做很多事情，”特里费罗说。“例如，如果我在运营一个处理餐厅预订实时优惠券的网站，那么[我希望]根据我的客户所处的位置、可以提供的优惠、他们过去购买的东西以及我所了解的偏好，向他们提供结果。我不想在 Go 里写自己的大数据分析。我想使用类似火花的东西，甚至可能是火花流。让 Spark 在相同的集群、相同的网络和相同的机器上运行，并与 Kubernetes 弹性共享，这意味着我的 Kubernetes 应用程序可以产生 Spark 工作负载来获得这些实时分析。”

Trifiro 说，Mesosphere 编写的将 Kubernetes 集成到 DCOS 环境中的所有代码都被贡献给了 T2 Kubernetes 开源项目 T3 的核心。“这真的代表了一个重要的步骤，”他告诉我们，“我们双方(Mesosphere 和谷歌)都认识到我们的两项技术对新的数据中心堆栈有多么重要。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>