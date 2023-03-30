# Kubernetes 能低到什么程度？牧场主，武装小组去找

> 原文：<https://thenewstack.io/how-low-can-kubernetes-go-rancher-arm-team-to-find-out/>

[Rancher Labs](http://www.rancher.com/) 已经与 [Arm](https://www.arm.com/) 合作，为运行在边缘和数据中心节点上的基于 Arm 的集群带来 Kubernetes 管理。Rancher Labs 首席执行官兼联合创始人[盛亮](https://www.linkedin.com/in/shengliang/)表示，这基本上是一个弄清楚 Kubernetes 能做到多小的问题。

此举将 Rancher Kubernetes Engine (RKE)和 RancherOS 与基于 Arm Neoverse 的服务器相结合，为企业提供了一种在 x86 集群中管理 Kubernetes 及其物联网部署的单一方式。两家公司正致力于为中国的[智能城市项目](https://govinsider.asia/security/five-chinese-smart-cities-leading-way/)提供基于 Kubernetes 的解决方案。

物联网项目通常涉及运行在相机或空调系统中的低功耗边缘设备。5 到 8 千兆字节的边缘节点充当物联网控制器，进行大量数据处理，以减少发送回数据中心的数据量。用户向这些节点发送应用程序，这些节点的更新相当频繁。梁说，他们在这些数据聚合和数据摄取应用程序上运行 Kubernetes，然后他们在数据中心运行更大的 Kubernetes 集群。

Rancher Kubernetes Engine (RKE)是一个轻量级安装程序，它将 Kubernetes 打包到 Docker 容器中。它消除了标准安装程序对底层基础架构的依赖性，使安装和升级集群变得快速而简单。

Arm 服务器重组的最大挑战是边缘节点通常没有稳定的网络连接。除非节点彼此紧邻，否则它们无法形成集群。梁说，它们通常不是紧挨着的，所以它们最终成为单节点集群。

“Kubernetes 被设计成一个相当紧密耦合的系统。如果它在一段时间内(10 分钟、20 分钟)没有收到某个节点的消息，它会尝试让该节点重新运行。我们试图关闭所有这些东西，但最终意识到将所有这些作为单节点集群运行实际上更容易。我认为我们正在挑战极限，看看库伯内特能缩小到什么程度，”他说。

这项工作正在为物联网的使用而进行。它涉及到资源优化，比如去掉面向数据中心的特性，比如负载平衡。

“老实说，Kubernetes 在低于 8gb 的任何节点上都很吃力，”他说。“如果你有 8g 的内存，运行 Kubernetes 需要 2 GB，那么你还有 6 GB 的内存。但是，如果您从 4gb 开始，在部署任何有用的工作负载之前，一半的资源都在使用中。所以我们正在缩小足迹。”

基于 Rancher Kubernetes 的物联网和边缘节点平台，包括 Rancher 2.1 的 Arm 端口、2018 年 10 月推出的和 RancherOS 1.5，将于 2019 年初全面上市。11 月，该公司宣布其 Kubernetes 平台在中国三大云提供商[的可用。](/rancher-takes-kubernetes-management-to-china/)

据梁介绍，Rancher 还开发了多租户监控工具 Prometheus T5，这是客户一年多来一直要求的。

“如果多个人[或团体]共享一个 Kubernetes 集群，Prometheus 本身实际上是单租户。所以如果你登录普罗米修斯，我就能看到你所有的东西。人们不喜欢这样，”他说。“许多人让每个人开始他们自己的 Prometheus 部署，这带来了挑战—需要管理这些东西。这是浪费。这造成了大量的重复。这是非常非常耗费资源的。

“所以我们在普罗米修斯面前创建了一个安全代理。我们没有从根本上改变 Prometheus，使其成为多租户，但我们能够将所有查询捕获到 Prometheus 的时间序列数据库中，然后根据它所针对的人或项目，我们能够检测这些查询，以便如果我属于[某些]名称空间，我将只能看到这些名称空间的指标。"

它是这样工作的:

*   牧场主在每个新集群中部署一个普罗米修斯操作员。
*   集群范围的 Prometheus 部署用于存储集群级指标，如节点 CPU 和内存消耗，以及从单个用户部署的应用程序收集的项目级指标。
*   项目级 Grafana 通过一个安全代理与 Prometheus 对话，该代理检测 PromQL 语句以确保查询中只包含属于用户项目的名称空间。

在 7 月的《新堆栈制造商》的一集中，Rancher Labs 的联合创始人 Shannon Williams 讨论了该公司“全 Kubernetes”的决定。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>