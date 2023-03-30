# 如何使以数据为中心的应用程序适应 Kubernetes 架构

> 原文：<https://thenewstack.io/how-to-adapt-data-centric-applications-to-a-kubernetes-architecture/>

Kubernetes 是一个按需编排平台，本质上是松散耦合的。术语“松散耦合”没有像微服务那样广泛使用，但是有类似的含义。在这两个方面，组件都是精简的，有一个单一的目的，并且很少依赖。微服务架构为每个服务提供了一种独立运行的方式，与紧密耦合的方法相反，其特点是相互依赖的系统、集成的软件和硬件以及在应用程序发生变化时更新起来可能更加复杂的代码。

在这个由 TNS 创始人兼出版商 [Alex Williams](/author/alex/) 主持的 [The New Stack Makers](/podcasts/makers) 播客中；嘉宾 [Nanda Vijaydev](https://www.linkedin.com/in/nanda-vijaydev-3638693) ，杰出的技术专家和首席数据科学家 [HPE](https://www.hpe.com/us/en/ezmeral.html?utm_content=inline-mention) ，讨论了松耦合架构的概念如何在 Kubernetes 上运行以数据为中心的应用程序。这是一种通过使用 Kubernetes 进行微服务开发而逐渐形成的演变——与过去在紧密耦合的整体架构上部署的以数据为中心的方法相反。

[HPE 的 Nanda Vijaydev 如何使以数据为中心的应用适应 Kubernetes 架构](https://thenewstack.simplecast.com/episodes/nanda-vijaydev-of-hpe-how-to-adapt-data-centric-applications-to-a-kubernetes-architecture)

作为将 Kubernetes 和以数据为中心的管理放在上下文中的一种方式，Vijaydev 依赖于经常被恰当使用的[宠物与牛的类比](/how-to-treat-your-kubernetes-clusters-like-cattle-not-pets/)来描述它们的相似性和差异。通过这种方式，Kubernetes 提供的大规模和高度分布的特征代表了牛，因为许多集群可以像牛一样被集中起来管理。

“当你谈论 Kubernetes 擅长什么或什么使 Kubernetes 受欢迎时，是一种一遍又一遍地淘汰相同类型的应用程序或部署的方式——这就是你想要部署单个 web 服务器的规模，然后你想要做同样的事情，10 次 10，000 次或 1，000 万次，”Vijaydev 说。Vijaydev 说，最终结果是可重复性和标准化已经完成，“就如何扩大规模而言”，所以“当你不需要它时，你就缩小它——所以这是及时的性质，也是这个框架提供的稳定性。”

随意扩展和缩减微服务是一项非常类似放牛的工作，而在这种松散耦合的环境中管理 Kubernetes 上以数据为中心的应用程序需要在许多方面更加小心和关注。

当以数据为中心的应用程序集成到 Kubernetes 中时，挑战开始于这样一个事实，“它不仅仅是一个牛型的应用程序，”Vijaydev 解释道。“你必须明白，有一个数据访问层和一个数据持久性框架，它们必须在相同的规模上工作，这实际上是为了能够容器化，能够按需供应，能够在不需要时减少占用空间，这样你就可以收回资源，”Vijaydev 说。

通过收购，HPE 增强了其帮助组织应对与耦合在 Kubernetes 上运行的以数据为中心的工作负载相关的挑战的能力。其中包括 HPE 对 MapR Technologies 的收购、T2 BlueData 和 T4 云技术合作伙伴的收购。Vijaydev 说:“有几家公司是这些领域的先驱，我们将它们聚集在一起。

HPE 已经开发并获得了创建一个软件平台的技术，该平台使用户能够将数据管理视为一个数据管理问题，而不仅仅是一个数据管理问题:“这是一个 Kubernetes 问题。这是一个存储问题。这是一个网络问题。“这就是 Kubernetes 目前所处的位置，因为从全局的角度来看，它们中的每一个都非常、非常不连贯。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>