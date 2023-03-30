# Istio 和 Kubernetes 哪个先来？

> 原文：<https://thenewstack.io/which-comes-first-istio-or-kubernetes/>

我们对 Kubernetes 了解多少？这是一个原始的，张开的血盆大口。这不是我们大多数人想要的。需要什么？接触研磨的数字齿轮，这些齿轮构成了我们所知的分布式架构。

服务网络公司 [Tetrate](https://www.tetrate.io/?utm_content=inline-mention) 创始工程团队的成员 Zack Butcher 说，Istio 是 Kubernetes 管理层的一个例子。他与 Tetrate 的联合创始人 [Varun Talwar](https://www.linkedin.com/in/varuntalwar) 一起讨论了服务网格 Istio 及其在高度分布式网络管理中的作用，包括本期[新堆栈制作者](/podcasts/makers)播客中的 Kubernetes。《新书库》的创始人兼发行人亚历克斯·威廉姆斯主持了这一集。

[先造什么:Istio 还是 Kubernetes？](https://thenewstack.simplecast.com/episodes/what-to-build-first-istio-or-kubernetes)

服务网格越来越被视为任何组织从传统基础架构迁移到云原生和微服务环境的必要先决条件。根据云本地计算基金会(CNCF)的一项调查，在帮助管理分布式环境的服务网格中，Istio 暂时领先。CNCF 2020 年的调查显示，在生产中使用服务网格的所有组织中，有 47%使用 Istio，其次是 Linkerd 和 Consul，两者的市场份额分别为 41%(一个组织也可以使用多个网格)。

Istio 以及一般的服务网格可以被认为是网络和编程层之间的空间。通过这种方式，它有助于管理整个运营，而 Kubernetes 本质上只是网络的一部分。

“Kubernetes 纯粹是关于计算的——这就是为什么我们认为网格是一个更大的东西，也是为什么我们认为网格是你可以不用启动 Kubernetes 就可以启动的东西，”Butcher 说。“网格在体系结构上是应用程序的网络。这给了我们巨大的力量，这就是为什么网络如此引人注目。”

Tetrate 建议，人们可能会假设，首先部署一个 Kubernetes 环境，然后添加一个服务网格来管理这一切是明智的。然而，这种方法并不推荐，对于组织来说，通过同时实施 Kubernetes 和服务网格(如 Istio)来开始数字化转型也不是一个好主意。虽然它可能“与许多人的想法有点背道而驰，但我认为你应该从 Istio 开始，”Butcher 说。

“为什么你不应该同时做这两件事，也许最简短的答案是，当我们在州际公路上行驶时，很难同时改变汽车的发动机和轮胎，”Butcher 说。“要采用这两种技术中的任何一种，都需要大量的操作复杂性和组织学习。”

塔尔瓦说，与此同时，Istio“在本质上保持不变”。从一开始，Istio 就被创建来帮助连接、保护和观察服务。“Istio 仍然是一样的——它在单个 Kubernetes 集群中做了出色的工作，并将继续这样做，”塔尔瓦说项目的发展方向……是让它变得更可靠、更有用。所以所有的路线图项目更多的是围绕它所做的事情的可用性和可靠性。有一些工作[正在进行]扩展和一堆这样的事情，但在核心上，它是相同的。"

塔尔瓦说，最终，Istio 像任何成熟的技术一样，“应该变得无聊，消失在背景中”。“因此，应该发生的是您进行调配，这只是您基础架构的一部分。应用程序开发人员可以对他们的 API 进行编程，并可靠地获得他们想要的行为。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>