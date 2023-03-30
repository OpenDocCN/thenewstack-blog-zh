# Nirmata 3.0 发布，包含虚拟集群和工作负载策略

> 原文：<https://thenewstack.io/nirmata-3-0-launches-with-virtual-clusters-and-workload-policies/>

Nirmata 赞助了这篇文章。

 [里泰什·帕特尔

Ritesh 是 Nirmata 的创始人兼产品副总裁，NIR mata 是一个基于 Kubernetes 构建的云原生应用管理平台。Ritesh 拥有大约 20 年的企业软件开发经验，并领导过软件开发团队。在加入 Nirmata 之前，Ritesh 负责 Brocade 的私有云战略和业务开发。](https://www.linkedin.com/in/patelrit/) 

今天，Nirmata 宣布了它的下一个主要版本，包括几个旨在为企业简化 Kubernetes 的新特性。该版本还为集群运营商提供了高级多集群工作流和用例，以及支持多种开发人员体验的自由。

随着 Kubernetes 在企业中的采用加速，DevOps 团队正在超越最初的用例，并面临与第 2 天运营和管理相关的挑战。  正如新堆栈 最近对 Kubernetes 用户进行的 [调查所显示的，运营商体验和开发者体验仍然是 Kubernetes 采用的最大挑战。Nirmata 3.0 中发布的特性旨在解决这些挑战并促进高级用例。](https://thenewstack.io/ux-is-kubernetes-biggest-short-term-challenge/)

## **Nirmata 3.0 中的主要特性**

**虚拟集群:**自助式开发运维的承诺来了！运营商现在可以允许开发人员通过指定所需的资源和服务来请求虚拟集群，虚拟集群是物理 Kubernetes 集群的安全部分。然后会自动为开发人员提供一个虚拟集群，开发人员可以使用它以各种不同的方式部署和管理应用程序。集群操作员可以管理资源消耗，如果集群接近容量极限或任何共享服务未能按照配置的 SLA 运行，就会收到警报。开发人员可以根据需要为他们的应用程序请求额外的容量，而运营商可以批准该请求，以自动调整虚拟集群的容量限制。有关虚拟集群的更多背景信息，请参见 [虚拟 Kubernetes 集群案例。](https://thenewstack.io/the-case-for-virtual-kubernetes-clusters/)

**工作负载策略管理:**确保您的工作负载符合您的安全、资源、公司策略、网络和访问策略！今年早些时候，Nirmata 团队启动了一个开源项目， [Kyverno](https://kyverno.io/) ，旨在解决与 [工作负载策略管理](https://www.nirmata.com/2019/06/03/introducing-kyverno-kubernetes-native-policy-management/) 相关的挑战。Kyverno 是在 Nirmata 成熟的政策管理框架基础上构建的，在社区中得到了快速采用，并于最近宣布正式发布。Nirmata 完全集成和支持部署和管理 Kyverno 策略，并提供对任何策略违规的可见性。要了解如何在集群中使用 Kyverno，请参见 [10 Kubernetes 最佳实践，您可以轻松地将其应用到集群中](https://thenewstack.io/10-kubernetes-best-practices-you-can-easily-apply-to-your-clusters/)。

**Windows 支持:**今年早些时候，Kubernetes 中对 Windows 容器的支持已经全面发布。有大量工作负载在 Windows 上运行，现在它们可以从 Kubernetes 支持的自动化中受益。现在可以将 Windows 节点添加到 Nirmata 管理的集群中，并将 Windows 应用程序与集群中的其他应用程序一起部署。

**服务网格支持:**随着云原生采用的复杂性增加，企业开发人员正在探索服务网格，以便为其微服务风格的应用提供安全性和可见性。Nirmata 提供了多种服务网格选择，并支持单击部署服务网格(如 Istio)和高级工作流(如蓝绿色部署和流量分流)。

Helm 3.0: Helm 可以说是目前最流行的打包 Kubernetes 应用程序的工具。Helm 3.0 解决了困扰早期版本的安全性和复杂性问题。Nirmata 一直支持头盔包，现在扩展到头盔 3.0。Helm 存储库可以用作上游，直接将应用程序部署到集群。

以上所有功能都可以在 Nirmata 管理控制台上获得，不需要客户进行任何额外的集成工作。随着企业继续采用云原生技术，他们需要一个管理平台来消除运营复杂性，并减少最初的 Kubernetes 复杂性曲线。

Nirmata 3.0 版本进一步巩固了 Nirmata 作为市场上最直观、最灵活、最高效的 Kubernetes 管理平台的地位。如果您有兴趣了解 Nirmata 如何帮助加快您的云原生之旅，请联系 [请求演示](https://info.nirmata.com/nirmata-demo) 或通过[https://try . Nirmata . io](https://try.nirmata.io)免费探索 Nirmata。

Billy Huynh 在 [Unsplash](https://unsplash.com/s/photos/cluster?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>