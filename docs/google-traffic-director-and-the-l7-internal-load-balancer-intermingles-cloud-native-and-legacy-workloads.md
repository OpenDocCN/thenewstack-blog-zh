# Google Traffic Director 和 L7 内部负载平衡器混合了云本地和传统工作负载

> 原文：<https://thenewstack.io/google-traffic-director-and-the-l7-internal-load-balancer-intermingles-cloud-native-and-legacy-workloads/>

谷歌为其[谷歌云平台](https://cloud.google.com/) (GCP)发布了两个新工具，它们朝着一个主要目标努力——将企业带入应用架构的现代世界，而不必抛弃其遗留的应用。随着 [Traffic Director](https://cloud.google.com/traffic-director/) 和[第 7 层内部负载平衡器](https://cloud.google.com/load-balancing/docs/l7-internal/) (L7 ILB)的测试版的全面上市，使用谷歌 [Anthos](https://cloud.google.com/anthos/) 容器编排平台的企业现在可以为他们的云原生应用程序享受服务网格的好处，而 L7 ILB 为单片遗留应用程序提供类似的功能。

谷歌产品副总裁 Shailesh shuk la[表示，此次发布是谷歌现有多云战略的延伸，多云也包括这些内部的、单一的遗留应用程序。](https://www.linkedin.com/in/shailesh-shukla-005119)

Shukla 说:“最终，我们的目标是让企业以一种他们可以大规模实现的方式无缝、平稳地从传统环境迁移到混合和多云环境。“Anthos 战略的关键要素之一是消除与管理在不同点部署的各种微服务相关的部署复杂性。消除这种复杂性是谷歌多云和混合战略的核心。"

Traffic Director 为 Anthos 用户提供了一个托管服务网格，根据一篇博客文章，“使用开放 API 为 Envoy 或数据平面中的类似代理提供配置、策略和智能，因此客户不会被锁定”，以及全局弹性、智能负载平衡和高级流量控制，如流量分流、故障注入和镜像。本质上，Traffic Director 是开源 Istio 服务网格的一种管理形式，尽管 Shukla 在他对该服务的解释中没有走那么远。

“交通总监是更广泛的 Istio 战略的重要组成部分。如果退一步讲，这归根结底是关于如何在多种环境中部署计算的问题。Shukla 说:“Traffic Director 是控制平面的托管服务，是 Anthos 战略的重要组成部分，也是 Istio 世界观的重要组成部分。“所以，从根本上说，我们无法将交通总监和 Istio 视为两件不同的事情。Traffic Director 是更广泛的 Istio 架构的一部分，它们都是构建服务网格控制平面的组件。”

与此同时，L7 ILB 为遗留应用程序带来了服务网格的好处，由于其整体架构，遗留应用程序不能与 Envoy sidecar 代理一起工作。

在一份公司声明中，[特使代理](https://www.envoyproxy.io/)的创建者[马特·克莱恩](https://twitter.com/mattklein123?lang=en)说:“L7 ILB 使企业部署现代负载平衡变得简单。“在引擎盖下，L7 ILB 由交通主管和特使提供支持，因此您只需将 L7 ILB 放在您的传统应用程序前面，就可以获得高级交通管理。”

交通总监为 L7 ILB 供电，Shukla 强调了一个设计决策，他说这可以防止两种产品之间的锁定。

舒克拉说:“通过使用开放的 API，如 XDS，将[交通主管]连接到数据平面，这是特使代理，你现在已经创建了一个定义开放的环境。“我们不想造成锁定，我们希望支持持续发生在本地应用程序部署中的 80%的支出和投资。我们希望能够为客户提供向现代世界转移的能力，而不必重新构建或只关注新应用。”

目前，L7 ILB 和流量总监负责虚拟机和容器的工作，无论是由谷歌 Kubernetes 引擎(GKE)编排的还是自我管理的，因为谷歌的整体战略是在不强迫企业改变任何事情的情况下将企业纳入进来，并能够以自己的速度与 Anthos 一起前进。总的来说，Shukla 总结了网络技术背景下的版本，实现了从传统架构到现代架构的转变。

“从大的方面来看，如果你考虑企业，我们已经以传统的整体方式进行了部署，并且正在向混合环境转移。网络技术实际上是从内部整体架构迁移到这种多云、微服务和 API 驱动的世界视图的推动者，”Shukla 说。“作为这个行业和这个社区的参与者，提供正确的迁移和流动对我们来说非常重要。”

特写图片由戴维斯桑切斯从 Pexels。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>