# STORK:面向 Kubernetes 的开源存储智能

> 原文：<https://thenewstack.io/stork-open-source-storage-intelligence-kubernetes/>

来自 Portworx 的一个新发布的以 Kubernetes 为中心的开源存储项目，名为 STORK(用于 Kubernetes 的 STorage Orchestrator Runtime)，专注于简化有状态应用程序的管理，如数据库、队列、在容器中运行的键值存储。

在 12 月的 KubeCon + CloudNativeCon 2017 上有一场关于存储的讨论，主要围绕着[容器存储接口](https://github.com/container-storage-interface/spec) (CSI)，这是一个跨行业的标准倡议，在 [Kubernetes 1.9](https://thenewstack.io/kubernetes-1-9-brings-stability-windows-support/) 中作为 alpha 功能发布。CSI 将使用户能够插入和更换 Kubernetes 集群的存储。

[云原生计算基础](https://www.cncf.io/kubecon-cloudnativecon-events/)也刚刚接手 [Rook](https://rook.io/) ，它可以作为[初始级项目](https://thenewstack.io/cncfs-rook-project-brings-storage-capability-cloud-native-workloads/)在各种类型的存储和需要它的应用程序之间架起一座桥梁。

对 CSI 的关注主要集中在存储资源调配上。Portworx 联合创始人兼首席技术官 Goutham "Gou" Rao 表示，STORK 更多的是在不使用标签的情况下促进应用程序本身的编排。

在新堆栈制造商播客的一集里，Rao 讨论了 Portworx 如何用容器为存储构建技术架构。

[集装箱集群存储的 Portworx 技术架构](https://thenewstack.simplecast.com/episodes/the-portworx-technical-architecture-for-storage-in-container-clusters)

“我们从大量大规模部署这些数据库的经验中学到了这个项目，”他说。“客户采用的一些方法，如添加标签或手动添加约束条件来促进这些应用程序的部署，在生产环境中变得有些困难。”

他解释说，在生产环境中，有许多动态变化——机器崩溃、磁盘故障、存储过度利用。“储物织物可能会有很多磨损。Rao 解释说:“这种智能需要反馈给 Kubernetes，这样它才能更有效地管理分布式、有状态的应用程序。

标签基本上是将应用程序绑定到哪种类型的节点。但是当你有数百台服务器和数千个容器时，就会变得非常混乱。你失去了对你的标签在哪里和它们在做什么的关注，他说。基本上，一个标签变成了你必须管理的另一件事。STORK 能够以自动化、自我驱动的方式提供所有这些优势。

在其初始形式中，STORK 使用 Portworx 使用的开放式存储框架，但该公司计划与其他供应商合作，提供一系列存储选项。用户也可以通过编写自己的插件来添加自己的驱动程序。

它是 Kubernetes 的自然扩展，位于 Kubernetes 集群上，有助于做出基于存储的决策，决定如何最好地调度和管理应用程序，例如应用程序应该在哪里运行。如果运行应用程序的服务器出现存储问题，会发生什么情况？

“这背后的目标是为操作员、系统管理员提供一个免提环境；他们不必担心耐用性或磨损对存储环境的影响。STORK 有点像自动驾驶仪，让你的应用程序运行，不管底层基础设施如何，”Rao 说。

它知道您的云环境或物理服务器(如果在本地运行的话)。

[STORK v1.0](https://portworx.com/blog/) 提供三个主要功能:

*   超融合，协同定位 pod 及其数据。STORK 将运行，以便每个容器的数据都是本地的。
*   调度程序可以决定存储是否有问题，并将容器重新定位到存储位于本地的其他节点。
*   通过 Kubernetes 创建卷快照，并通过 Kubernetes 将这些快照恢复到其他持久卷声明(PVC)。

除了扩展存储选项的范围之外，未来的增强功能还包括对可用性分区的支持，以便在确定节点优先级时考虑数据所在的分区和机架，并支持使用与快照相同的界面将备份保存到云中。

[云本地计算基金会](https://www.cncf.io/kubecon-cloudnativecon-events/)和 [Portworx](https://portworx.com/) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>