# 中间层在 Kubernetes 上加倍，多集群管理

> 原文：<https://thenewstack.io/mesosphere-doubles-down-on-kubernetes-multicluster-management/>

当 GE Transportation 希望超越其以 Java 为中心的开发堆栈并尽可能多地将应用程序容器化时，它知道它希望使用 Kubernetes，但也知道它需要帮助。这是一家将中间层 DC/操作系统作为其 Kubernetes 转型门票的客户。

GE Transportation Digital Solutions 为开发人员和工程师提供云开发环境，为铁路、联运和采矿行业的客户开发应用程序。软件应用可以是云原生的、基于 Java 的本地应用和遗留应用的混合，其中一些已经有 20 年的历史了。

它需要一个以“容器即服务”为中心的平台，能够以更加自助的方式提供，以云无关和可移植的方式支持行业应用程序。团队编码的公司需要融合来自各种来源的数据，包括机车上的物联网设备。然后，这些数据将用于推动分析、网络优化和运输物流应用

“我们可以构建一个驻留在公共云环境中的应用程序，但如果我们的客户想要在内部运行它，我们希望确保他们能够以一种轻量级、经济高效的方式来实现，”通用电气运输数字解决方案首席技术官[韦斯利·穆凯](https://www.linkedin.com/in/wesleymukai/)在一个案例研究中说。

“我们为他们提供了一个参考设计，他们可以自己站起来。未来，我们的目标是创建一个更加混合的设置，具有跨不同云的可移植性和无缝的本地可移植性。这是中间层可以真正帮助我们的一个领域。”他补充说，该公司还在考虑更多的分析项目。

Mesosphere 是越来越多专注于帮助客户采用混合云(它定义为数据中心和云的混合)和多云(涉及多个公共云)的供应商之一。

它最近发布了带有 [Mesosphere Kubernetes 引擎(MKE)](https://mesosphere.com/blog/introducing-mesosphere-kubernetes-engine-mke/)的 meso sphere DC/OS 1.12 版本，使您能够在同一个物理 It 基础设施上部署多个 Kubernetes 集群。为了顺应使用其数据中心技术来管理跨不同云的资源的趋势，它还将 DC/OS 重新命名为分布式云操作系统。

继去年宣布除了自己的 Marathon container orchestrator 之外，它还将支持 Kubernetes 之后，今年 2 月，它增加了更深入的 Kubernetes 集成和增强功能，重点是 edge 和多云支持，以及针对[托管的 Kubernetes](/mesospheres-data-center-operating-system-will-offer-managed-kubernetes/)的计划。

DC/操作系统是基于 [Apache Mesos](http://mesos.apache.org/) ，一个运行任何类型的分布式系统的平台。DC 操作系统还支持 100 多种数据服务，包括 Kafka、Jenkins 和 Spark。

“我认为云提供商真正腾飞的原因不是因为他们擅长提供虚拟机和存储(这已经存在一段时间了)，而是这些服务正在成为云提供商的按需消费品。Mesosphere 的产品副总裁 [Ed Hsu](https://www.linkedin.com/in/edwardihsu/) 说:“我们在 Mesosphere 所做的就是为您提供相同水平的自动化和对这些服务的可访问性，只是我们基本上不依赖于云提供商。“任何这些服务，你都可以带到聚云。您可以通过统一的多云运营模式让它在不同的云提供商之间并行运行。”

在最近的一项调查中，Kubernetes 是 Mesosphere 上最常用的工作负载，其中 84%采用了容器/微服务架构。混合云是增长最快的部署场景。

DC/OS 1.12 包括云的通用安装程序、Kubernetes 的多区域部署和操作功能、改进的 LDAP 用户目录集成、通过 [Prometheus](https://prometheus.io/) 的指标等等。

该公司声称，客户可以通过 DC/OS 和 Mesosphere Kubernetes 引擎(MKE)削减 50%或更多的成本。它为云、数据中心和边缘提供单一控制平面；它称之为高密度多 Kubernetes 和改进的生命周期自动化，用于安全性和第 2 天操作。

单个控制平面允许用户跨多云环境、多个 AWS 区域、一个协同定位数据中心和 AWS 以及其他场景管理多个 Kubernetes 集群。

据 Mesopshere 的产品和营销经理 Chris Gaun 说，它提供了改进的集群配置和升级集群，“这是最难做的事情之一，从一个版本到下一个版本”，以及像从公共云提供商那里获得的自动化，但它是一种可以在任何地方运行的软件。

“如果一个节点出现故障，它会重新启动并运行，而无需任何操作人员的干预，”他说。“想象一下你的 Kubernetes 控制飞机坠毁了。在正常情况下，这应该是红色代码。每个人都必须在现场让它恢复正常运行，在此之前不会做任何其他工作。与中间层 Kubernetes 引擎，你不需要做任何事情。它将在几分钟内恢复运行。我们进行了大规模测试，整个控制面板花了几分钟才恢复运行。

对于传统的 Kubernetes，每个操作系统一个 Kubernetes 节点，如果您在虚拟化环境中，每个虚拟机一个 Kubernetes 节点；每个实例，如果你在公共云中；或者服务器，如果你是在裸机环境中这样做的话。公司通常由不同的团队运行多个 Kubernetes 部署，这些团队之间互不交流。这可能会导致蔓延。

通用运输公司的穆凯这样说道:

*“如果一个客户操作 30 个终端，那么它可能有 30 个本地应用程序实例在运行，这是非常低效的。…即使在内部，我们也希望软件得到更好的整合，更像私有云一样运行。比如说，当客户在其运营中增加第 31 个终端时，这样做可以大大提高可扩展性。”*

通过高密度的多个 Kubernetes，您可以在一个硬件上运行多个 Kubernetes 节点，比如一台服务器或一台虚拟机。Gaun 说，这意味着，如果你想在裸机环境中运行，你可以摆脱虚拟化，同时仍然可以在一台裸机服务器上运行多个 Kubernetes 组件。这意味着您可以使用更少的操作系统、更少的虚拟化、更少的管理开销—您不必为每个集群都配备一个集群管理器。

“如果你整合所有这些，并真正考虑所有的节省，它可能会大得多[超过 50]，”他说。

该公司还增加了对 Mesosphere [Jupyter](http://jupyter.org/) 服务测试版的支持，这使得数据科学团队更容易使用 Jupyter 笔记本分享文档和可视化

专题图片:fotolehrling 拍摄的“火车站 Gleise 货运列车”。根据 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>