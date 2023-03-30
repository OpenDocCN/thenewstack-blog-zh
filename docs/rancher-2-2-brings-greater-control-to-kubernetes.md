# 牧场主 2.2 给库伯内特带来了更大的控制

> 原文：<https://thenewstack.io/rancher-2-2-brings-greater-control-to-kubernetes/>

Rancher 2.2 现已全面推出，旨在为开发人员和 IT 人员简化 Kubernetes，并让他们对自己的应用程序有更多的控制权。

“2018 年，越来越多的公司通过 Kubernetes 从单纯的开发/测试转向生产。越来越多的人开始接受 Kubernetes 投入生产的想法。但是你是怎么做到的呢？你是怎么支持的？Rancher Labs 的产品管理负责人 Ankur Agarwal 说:“如何确保集群具有高可用性和多租户功能。

“我们看到了这种对高弹性集群、高可用性应用、多租户和可支持性的渴望。所以在 2.2 中，这就是我们要解决的问题。”

新版本的工作已经进行了一年多。之前的版本，牧场主 2.1，是[在 2018 年 10 月](https://www.businesswire.com/news/home/20181008005735/en/Rancher-Labs-Introduces-Rancher-2.1)推出的。

该公司此前宣布[支持多集群应用](https://thenewstack.io/rancher-supports-running-apps-across-multiple-kubernetes-clusters/)和普罗米修斯监控。

2.2 中的新特性包括:

*   **etcd 集群的灾难恢复。**用户可以从 Rancher UI、API 或 Kubernetes API 执行 etcd 的计划和临时快照，写入本地存储、挂载的共享存储或任何 S3 兼容的对象存储。

尽管是为恢复能力而设计的，但是如果停机次数过多，群集可能会变得无响应。现在只需几次点击，您就可以看到所有备份的历史，然后您可以决定使用哪个备份。您还可以计划备份。Agarwal 说:“你可以计划一下，然后忘掉它。”。

*   **全局 DNS** 通过自动将服务主机名编程为公共 DNS，为部署在多个集群或同一集群内的多个项目中的应用提供公共访问。此版本包括对 Route53 和 AliDNS 的支持，以及对 CloudFlare 的 alpha 支持。对其他提供程序的支持正在开发中。

假设您想要构建某种跨不同可用性区域的高可用性用例。如果你有同一个应用程序的副本在运行，你可以对你的 DNS 进行编程，让它只需点击几下就能指向这些应用程序。你可以在全局范围内做一次，让它为你管理和维护。

*   **多租户目录**支持用户按集群或项目隔离目录，提供粒度隔离，因此即使是应用名称也不能跨项目共享。

“Kubernetes 有一个目录的名称空间概念，这很好，但这不是纯粹的隔离，因为人们仍然可以看到其他项目，”Agarwal 说。

“有了所有这些掌舵图表的目录，你可以说你不希望这些团队看到彼此的申请，”他说。“如果您在一个集群中有一个目录，您可以决定它是否对其他集群可见。有了多租户目录，您可以在项目级别做到这一点，无论您为自己的项目创建了什么样的导航图。也可以只指向你有的一个舵库。”

Rancher Labs 最近一直在发布与 Kubernetes 相关的公告。最近它发布了 [Submariner](https://submariner.io/) ，这是一个开源项目，可以在不同的 Kubernetes 集群之间实现直接联网。

12 月，它宣布与 [Arm](https://www.arm.com/) 合作，将 Kubernetes 管理引入运行在 edge 和数据中心节点上的基于 Arm 的集群[。上个月，它发布了开源项目 k3s(T7)，这是一个轻量级的 Kubernetes 发行版，面向物联网安装等资源受限的环境。](https://thenewstack.io/how-low-can-kubernetes-go-rancher-arm-team-to-find-out/)

11 月，它宣布其 Kubernetes 平台可在中国三大云提供商上使用。

管理 Kubernetes 项目的云本地计算基金会是新堆栈的赞助商。

来自 Pixabay 的 Momentmal 特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>