# Atlassian 为 Kubernetes 开发了一种快速自动定标器

> 原文：<https://thenewstack.io/atlassian-develops-a-speedy-auto-scaler-for-kubernetes/>

Atlassian 以保持软件开发人员和运营人员的组织性而闻名。传统上，该公司一直专注于跟踪 bug、客户投诉、文档和源代码的协作和信息管理工具。但是像任何优秀的软件工具提供商一样，Atlassian 正在幕后使用所有最热门的新技术。

这包括 [Kubernetes](https://kubernetes.io/) ，Atlassian 已经在其内部构建系统中广泛使用。然而，这导致了流行的容器编排平台的一个小问题:新节点的上线速度不够快，不符合 Atlassian 的口味。

正如一家大力推广 DevOps 工具的公司所期望的那样，Atlassian 的内部构建过程非常紧张，并且设计得很快。通过在一个构建中加入大量节点，Atlassian 可以快速向开发人员提供反馈循环，让他们在构建运行时保持低调并继续工作。

不幸的是，有些构建需要数百台服务器，并且仅在很短的时间内启动它们。Atlassian 的 Kubernetes 平台团队高级团队负责人 [Corey Johnston](https://www.linkedin.com/in/corey-johnston-88808299) 观察到，在一组节点启动时和 Kubernetes 内部的自动缩放算法能够满足需求时，团队看到了三到四分钟的时间窗口。

问题出在 Kubernetes 的自动缩放例程中。这些系统被设计得非常复杂，能够满足大量的扩展需求。因此，每次需要更多节点时，Kubernetes 内部的自动缩放器都会经历一个复杂的决策过程，精确计算可能需要什么，以及过去的使用情况会显示什么。

这种机械思维的结果是，当节点数量达到数百个时，节点配置过程会很慢。Atlassian 花了很长时间来考虑这个问题，并做出自己的决定:是应该将所需的优化添加到 Kubernetes 主线中，还是仅仅构建自己的项目？

最后选择了后者。Atlassian 的团队发现，他们真正的问题是 Kubernetes 自动缩放器对于他们的需求来说过于强大:Atlassian 团队有非常谨慎的大规模需求，这否定了内部 Kubernetes 决策树的有用性。于是，[扶梯](https://github.com/atlassian/escalator)诞生了。

自动扶梯是一个 Apache 许可的，用于 Kubernetes 的自动缩放器。“我们这里的工作负载是大量 CI/CD 工作负载，它们通过我们的集群运行。我们转移到自动扶梯的第一个工作量是我们在这里构建所有产品的构建工程。Johnston 说:“当我们加入这些人时，我们看到在我们遇到这些问题的规模下，我们的群集节点数从单个节点增加到每个群集数百个节点。

Johnston 说，使用自动扶梯为 Atlassian 团队节省了大量时间和金钱。“当你的高峰期结束时，你就会遇到这种情况，你将进入一个困难时期:你为之付费的一堆额外容量实际上并未得到利用。旧的自动缩放器在某些情况下需要长达 14 个小时才能使虚拟机完全离线。以我们的规模，这可能意味着严重的财务成本。自动扶梯取代了它。我们决定需要什么，支持用户工作负载，并相应地进行调整，”Johnston 说。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>