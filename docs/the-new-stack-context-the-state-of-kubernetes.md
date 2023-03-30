# 新的堆栈上下文:Kubernetes 中的状态—首选方法

> 原文：<https://thenewstack.io/the-new-stack-context-the-state-of-kubernetes/>

欢迎来到[新的堆栈环境](https://thenewstack.io/podcasts/context)，在这个播客中，我们将讨论云计算领域的最新新闻和观点。本周，我们采访了 [LogDNA](https://logdna.com/) 的 DevOps 负责人 [Ryan Staatz](https://www.linkedin.com/in/rcstaatz/) ，讨论了在 Kubernetes 上运行有状态服务的[，这是我们关于 2020 年运行 Kubernetes 的挑战的系列文章和播客的一部分。](/different-approaches-for-building-stateful-kubernetes-applications/)

TNS 编辑和营销总监 Libby Clark 主持了这一集，旁边是 TNS 创始人兼出版商 Alex Williams 和 TNS 执行主编 Joab Jackson。

[第 106 集:瑞安·斯塔茨——库伯内特斯之国](https://thenewstack.simplecast.com/episodes/episode-106-ryan-staatz-the-state-of-kubernetes)

每个月在新一期杂志上，我们都会选择一个主题进行额外报道——那些我们听说对我们的读者来说很重要的问题。这个月，我们关注了 Kubernetes 围绕如何运行有状态应用程序正在面临的挑战之一。这是一个挑战，因为 Kubernetes 最初是为无状态应用程序设计的。

正如 Staatz 在他关于这个主题的帖子中雄辩地解释的那样，“在 Kubernetes 上运行有状态服务的蓝图”

*“状态”是指应用在特定时间点所处的状态。有状态应用程序根据以前的事务改变其行为；换句话说，它保持着对过去的记忆。有状态应用程序的例子包括数据库、缓存和内容管理系统(CMS ),比如 WordPress。对于有状态的应用程序，应用程序必须有一个可以将其状态存储为数据的位置。这些数据需要在应用程序的整个生命周期中对其可用。在一个基本的单服务器、单实例应用程序中，这可能与将数据直接存储在主机文件系统上一样简单。*

我们与 Staatz 讨论了他在 Kubernetes 上运行有状态应用程序的首选方法，以及 LogDNA 如何通过自己的日志服务支持这些架构。然后，在本节目的稍后部分，我们将讨论关于这个主题的其他一些最新帖子:分析师贾纳基兰·MSV 在他的帖子“构建有状态 Kubernetes 应用程序的不同方法”中揭示了为 K8s 提供有状态支持的许多不同方法。答[问&答:云计算原生计算基金会 Kubernetes 存储特别兴趣小组主席 Saad Ali](https://thenewstack.io/qa-kubernetes-storage-sig-chair-on-the-state-of-state-in-k8s/) 讨论了为简化有状态工作负载的运行所做的工作，以及仍然存在的挑战和未来的展望。

我们也来听听来自 InfluxData 的 Chris Churilo 的[新的 Stack Makers 播客](https://thenewstack.io/get-better-monitoring-with-a-time-series-database/)，他提供了一些关于为什么组织越来越依赖时间序列数据库来改进产品或服务的观点。

云计算原生计算社区和 LogDNA 是新堆栈的赞助商。

由来自 Pixabay 的 Thanasis 帕帕萨恰里亚斯特写图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>