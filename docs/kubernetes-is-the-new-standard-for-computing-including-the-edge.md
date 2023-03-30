# Kubernetes 是计算的新标准，包括 Edge

> 原文：<https://thenewstack.io/kubernetes-is-the-new-standard-for-computing-including-the-edge/>

[](https://www.linkedin.com/in/shengliang/)

 [盛亮

盛亮是 Rancher Labs 的联合创始人兼首席执行官。在创办 Rancher 之前，盛是 Citrix Systems 收购后云平台集团的首席技术官，他是该公司的联合创始人兼首席执行官。Sheng 的职业生涯始于在 Sun Microsystems 担任 Java 软件工程师，在那里他开发了 Java 虚拟机(JVM)。盛拥有中国科学技术大学学士学位和耶鲁大学博士学位。](https://www.linkedin.com/in/shengliang/) [](https://www.linkedin.com/in/shengliang/)

KubeCon Europe 2020 定于 8 月 17 日至 20 日举行。KubeCon 的显著增长证明了 Kubernetes 的受欢迎程度，自五年前诞生以来，Kubernetes 在计算机行业掀起了一场风暴。

几年前，KubeCon 吸引的主要是 CNCF 项目的开发人员。我注意到，这些年来，最终用户与会者稳步增加，今年的活动中将会展示十几个最终用户案例研究。Kubernetes 正在迅速成为数据中心和云的无处不在的计算环境。根据 [451 研究](https://go.451research.com/2019-mi-kubernetes-cloud-native-mainstream.html)，到 2022 年，全球 76%的企业将在 Kubernetes 上实现标准化。在最近 Rancher Labs 对 25 个行业的 1000 多名 IT 专业人员的调查中，85%的受访者在生产中运行容器。91%的企业运行着多个集群，并健康地混合了内部部署和基于云的部署。

在早期，Kubernetes 很难建立和运营。虽然今天的 KubeCon 与会者仍然可以学习如何直接使用上游开源代码，但许多人会转而与提供 Kubernetes 即服务的云提供商交谈。有很多选择——针对 Kubernetes 的亚马逊弹性容器服务(EKS)、Azure Kubernetes 服务(AKS)、谷歌 Kubernetes 引擎(GKE ),或者使企业管理员能够在私有数据中心操作 Kubernetes 集群的 Kubernetes 发行版提供商。

## **Kubernetes 是新的计算标准**

标准在 IT 行业中扮演着重要的角色。以网络为例。还记得 TCP/IP 出现之前的日子吗？我们有多种不兼容的网络协议，如 Novell、令牌环和 DECnet。只有局域网上的计算机才能相互通信。但是随着 TCP/IP 成为网络标准，交换机和路由器能够连接不同的网络。像 HTTP 这样的应用协议运行在 TCP/IP 之上，于是互联网诞生了。

当今的计算行业面临着多种不兼容网络协议的挑战。IT 管理员和 DevOps 团队必须处理多个不兼容的 IaaS 云，这些云也不同于他们的内部基础架构。Kubernetes 带来了一致的映像格式、API 标准以及跨异构基础设施的统一安全和操作实践。

通过采用 Kubernetes 作为新的计算标准，IT 组织可以跨位于不同云和数据中心的多个 Kubernetes 集群部署其应用程序。在 2019 年 11 月在圣地亚哥举行的上一届 KubeCon 上，多集群管理已经是一个热门话题。Kubernetes 生态系统充满了将 Kubernetes 作为计算标准的创新。多集群管理将为我们带来激动人心的新优势，包括:

1.  云和数据中心之间的应用程序迁移。
2.  全球安全政策的定义和实施。
3.  跨多个地理位置分散的集群部署高度可用且可扩展的应用程序。

## **到边缘并超越**

TCP/IP 是为计算机网络设计的。今天，它可能在边缘和物联网设备中更受欢迎。Kubernetes 也在遵循同样的道路，并被用于边缘计算。

2018 年 7 月，快餐连锁店福乐鸡快餐店[使用牧场主 Kubernetes 引擎(RKE)](https://medium.com/@cfatechblog/bare-metal-k8s-clustering-at-chick-fil-a-scale-7b0607bd3541) 在其零售点部署 Kubernetes 集群。在 KubeCon Shanghai 2018 上，世界第三大风力涡轮机制造商金风公司展示了其[如何在偏远的风电场](https://kccncchina2018english.sched.com/event/FzEF/keynote-delivering-renewable-energy-with-kubernetes-wei-zhang-vp-technology-goldwind-smart-energy-sheng-liang-ceo-rancher-labs)运行 Kubernetes 集群。金风科技利用 Kubernetes 的力量部署了一个复杂的人工智能和分析软件堆栈，以处理在边缘收集的大量数据。

福乐鸡快餐店和金风的经历促使我们开发了 K3s，一个为边缘计算设计的轻量级 Kubernetes 发行版。K3s 采用了已经在数据中心和云中得到验证的 Kubernetes 技术，并使其适用于 Raspberry Pis、机顶盒和监控摄像机。自一年前推出以来，K3s 已经成为 Kubernetes 生态系统中最受欢迎的开源项目之一。今天 [K3s 被用于](https://searchitoperations.techtarget.com/news/252479295/Kubernetes-edge-computing-takes-shape-on-container-frontier)从南非的银行分行到伊拉克的偏远军事基地。

凭借来自所有主要云提供商的 Kubernetes 服务、来自领先供应商的 Kubernetes 发行版以及最新的 K3s，Kubernetes 已经成为从数据中心和公共云到边缘和更远的计算标准。如果您有兴趣了解 K3s 的最新发展，请参加在 KubeCon Europe 举办的 [Darren Shepherd 的演讲](https://kccnceu20.sched.com/event/Zeo7/running-k3s-lightweight-kubernetes-in-production-for-the-edge-and-beyond-darren-shepherd-rancher)(运行 K3s，轻量级 Kubernetes，生产中的边缘和超越)。

*要了解更多关于管理云原生技术的信息，请考虑参加 8 月 17 日至 20 日举办的 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 虚拟会议。*

[![](img/75815f6c9d934e86ec6fa33b77909e39.png)](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>