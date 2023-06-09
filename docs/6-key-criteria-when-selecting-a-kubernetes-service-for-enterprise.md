# 为企业选择 Kubernetes 服务时的 6 个关键标准

> 原文：<https://thenewstack.io/6-key-criteria-when-selecting-a-kubernetes-service-for-enterprise/>

[KubeCon + CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 赞助了这篇文章，期待于 8 月 13 日至 16 日在阿姆斯特丹举办 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 。

 [黛安·克莱

Diane Clay 是 Hitachi Vantara 云解决方案和服务产品营销高级经理，负责 SaaS 和 PaaS 云解决方案和服务组合的整体营销。她在开发和推出解决方案、服务和端到端产品方面发挥了重要作用，这些产品将推动我们客户的数字化转型。](https://www.linkedin.com/in/diane-clay-1531191/) 

如果您像大多数组织一样，在您的多云环境中越来越多地使用容器。原因很简单:集装箱是现代基础设施的组成部分。将应用程序从其环境中分离出来，可以让工作负载在任何地方持续安全地运行。凭借这一点，Kubernetes 已经成为云原生未来的最终基础。Kubernetes 的发展已经形成了一整套为互操作性和持久性而设计的开源工具集。创新是快速的，成千上万的组织每天都在利用创新带来的好处来建设适应力强、经得起未来考验的基础设施。

为什么是 Kubernetes？它是一个可靠的、开放的和非专有的应用程序，被广泛采用，但仍然提供了很大的灵活性和较低的成本。它协调多个主机上的容器，使公司能够实时扩展资源和应用程序，并允许他们通过更高效地使用硬件来优化基础设施资源，从而节省资金。

只有一个问题——许多采用 Kubernetes 的组织最终会有太多孤立的、单独管理的 Kubernetes 部署。这造成了大量的低效率和复杂性，给 IT 人员带来了更大的负担，并使安全和法规遵从性管理人员更加难以控制。组织应该期待并接受 Kubernetes 的广泛采用，但必须准备好解决围绕孤岛部署的管理、安全性和控制的问题——特别是当它们变得超出原始团队的处理能力时。如果没有一种整合且一致的方法来管理(甚至自动化)无中断升级、版本控制、高可用性、合规性、控制、监督以及一系列行政和管理功能，组织会发现他们提高速度和敏捷性的新方法是一种额外的负担。

Kubernetes 服务中有哪些神奇的成分？遗憾的是，对于您的企业 Kubernetes 部署，没有单一的完美算法，这里有六个关键标准，您应该在做出 Kubernetes 服务决策之前进行评估。

1.  **开放和混合多云**:不同的公有云和私有云有着明显的优势和劣势。为了确保您可以在需要时随时将应用放在您想要的位置，从而缓解锁定问题，请寻找一种不可知的开放式混合和多云解决方案，使您能够更新现有应用并构建新的应用。它应该为所有主要云提供商的企业级 Kubernetes 集群的部署、管理和监控提供可靠的服务。
2.  **集中的命令和控制**:寻找一个直观的、多云的仪表板和强大的 API 来管理您的 K8s 集群生命周期，不受操作环境的影响。它应该能够让您的开发人员和运营商获得所需的灵活性，以便在公共云、私有云以及内部环境等环境中高效运营。考虑集中的 RBAC 和访问管理的重要性，以及利用详细的审核日志功能查询活动的能力，这有助于改进管理决策和法规遵从性操作。您应该能够从直观的仪表板实时查看和调试应用程序日志。它应该支持您在主节点上调度工作负载的能力，以利用可用资源并提高较小环境中的效率。一致且集中的命令和控制将有助于加快关键应用程序的开发。
3.  **端到端部署**:寻找一种服务，通过内置的云无关、企业级 CNCF 认证的 Kubernetes 发行版，端到端地管理 Kubernetes 部署。它应该部署纯上游 Kubernetes，没有任何专有定制，并且支持最新的稳定版本，这样你就可以快速无缝地将其他工具集成到你的生态系统中。
4.  **高度可用的 Kubernetes 集群**:您的 K8s 服务应该允许并使您能够根据需要跨可用性区域提供高度可用的 Kubernetes 集群，只需点击几下鼠标，并提供集中的用户访问、控制和日志记录。部署的集群应支持自我修复、无中断升级，并根据需求进行伸缩；通过集成的智能自动扩展来降低企业运营的成本和停机时间。此外，该环境应与行业领先的云原生工具集成，包括 Prometheus、Calico、Istio 和 KNative。
5.  **治理和合规遵守**:确保您的 Kubernetes 服务整合了一个统一的仪表盘，支持集中管理和策略(治理)以及集中审计。控制应用和数据以及确定数据中心、地理位置或选定托管服务提供商的登陆区域的能力，意味着开发人员可以构建数据流管道，限制违反合规或监管要求的能力。您需要集中监控和警报，以便您的企业运营团队能够改善(缩短)响应时间和恢复时间。
6.  **其他关键功能**:寻找能够添加 GPU 实例、可抢占和现场实例的选项，以及在主节点上调度工作负载以利用可用资源的能力。执行滚动工作负载更新以确保最大正常运行时间的能力至关重要，从公共或私有容器注册中心无缝部署应用程序以及通过自动同步的 SSH 密钥管理控制对集群节点的访问的能力也是如此。

Kubernetes 成为企业级容器、集群和 DevOps 环境的事实上的标准有很多原因。您希望确保您选择的 Kubernetes 服务将帮助您的组织加快云原生基础架构的采用，在遵循行业最佳实践的同时充分实现您的多云战略。

它应该能够让您更好地控制您的云支出，优化现有资源，并为您的开发人员和运营商提供一个协作环境。它应该通过集中控制来提高您的效率，同时仍然支持单个部门的部署—通过强制只使用经批准的发布版本来提供一种确保安全性和法规遵从性的实用方法。

合适的 Kubernetes 服务将为您完成所有这些工作，并帮助您优化您的云原生未来，同时最大限度地减少甚至消除与管理整个企业的多个 K8s 集群相关的挑战。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>