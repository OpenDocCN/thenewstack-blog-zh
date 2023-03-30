# 如何为 Kubernetes 构建合适的平台

> 原文：<https://thenewstack.io/kubernetes/kubernetes-infrastructure-architecture/>

Kubernetes 是一名管弦乐手。它是你如何部署、联网、负载平衡、扩展和维护容器化应用的方式。每种工作负载都有自己的体系结构，无论是有状态的还是无状态的，是容器化的整体，还是与服务网格、批处理作业或无服务器功能一起使用的微服务。

但是您还需要考虑您的 Kubernetes 基础设施本身的架构:您如何构建运行 Kubernetes 的平台。

Kubernetes 足够灵活，可以在几乎任何硬件上部署几乎任何类型的应用程序，不管是在云中还是在其他地方:为了既通用又强大，它具有极强的可配置性和可扩展性。这给你留下了很多架构选择。

这些选择包括您是否自己做出所有单独的配置选择，遵循像 [VMware Tanzu](https://tanzu.vmware.com?utm_content=inline-mention) 或 Azure Arc 这样的工具中的默认选项，这些工具提供了部署和管理基础架构的更加集成的方法，或者选择托管云 Kubernetes 服务，该服务仍然为您提供关于您部署的资源的选择，但将具有为[常见应用程序工作负载](https://cloud.google.com/architecture/distributed-load-testing-using-gke#architecture)设计的[、](https://aws.amazon.com/solutions/implementations/amazon-eks/) [参考架构](https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks/baseline-aks)和[蓝图](https://learn.microsoft.com/en-us/azure/architecture/framework/services/compute/azure-kubernetes-service/azure-kubernetes-service)。

## 规划 Kubernetes 资源

您的 Kubernetes 基础架构是一组物理或虚拟资源，Kubernetes 使用它们来运行容器化的应用程序(及其自己的服务)，以及您在指定和配置它们时所做的选择。

您需要根据 pod 和服务的工作负载和资源要求，决定控制面板服务器、集群服务、附加组件、集群、数据存储和网络组件需要哪些虚拟机(或裸机硬件)、集群上需要多少个节点以及它们应该具有哪些内存和 vCPU。

[自动扩展](https://thenewstack.io/getting-started-with-kubernetes-autoscaling/)允许您动态地上下调整容量，但您需要有可用的底层容量。您需要考虑托管您的 Kubernetes 集群的最佳平台:您自己的数据中心中的基础架构、边缘、托管提供商，或者公共、私有或混合云中的基础架构。

其中一些将由您的工作负载的需求决定:如果它们主要是无状态的(或者如果很容易将状态存储在外部)，您可以通过使用部署折扣但也可能突然中断的 spot 实例来降低云成本。您需要了解您计划运行的应用程序的大小、复杂性和可伸缩性，以及您需要的控制和定制程度，还要考虑您将使用的资源的性能、可用性和成本。

最初，Kubernetes 是基于这样的假设构建的，即它所运行的所有硬件在根本上是相似的，并且可以有效地互换，因为它是为了利用云基础设施即服务(IaaS)中常见的商用服务器而开发的。

但是即使在云中，不同的工作负载仍然需要非常不同的资源，Kubernetes 已经发展到支持更多的异构基础设施:不仅仅是 [Windows 节点](https://thenewstack.io/kubernetes-for-windows/)以及 Linux，而是 GPU 以及 CPU、Arm 处理器以及 x86。甚至可以选择使用某些类别的 Linux 设备作为节点。

如果您正在为您的 Kubernetes 虚拟机使用云 IaaS 或托管云 Kubernetes 服务，如 AKS 或 EKS，您可以为您的虚拟机选择合适的实例。如果您正在构建自己的 Kubernetes 基础设施[在边缘，](https://thenewstack.io/edge-computing/)您可能会选择 Arm 硬件或消费级英特尔 NUCs 来运行要求较低的 Kubernetes 发行版，如餐馆或零售店中的 k3s，在那里您没有数据中心级硬件的设施。

根据您选择的 Kubernetes 发行版，您可能还需要考虑您想要的主机操作系统以及您将使用哪个容器运行时。您将运行自己的容器注册中心还是只从公共注册中心获取图像？你会把秘密藏在哪里？使用 [HashiCorp Vault](https://www.hashicorp.com/?utm_content=inline-mention) 或云提供商的托管密钥库意味着您的部署管道中不会有可能泄露的凭证。

## 多集群 K8s 基础架构体系结构

您还需要考虑可能的故障:您是否需要运行关键控制平面组件的多个副本的[高可用性集群](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/high-availability/)或者您是否将运行多集群架构？

对于较小的 Kubernetes 基础设施，您可以使用名称空间来分隔不同的工作负载:逻辑分区允许您在一个集群上隔离和管理不同的应用程序、环境和项目。但是，您也可以使用一个 Kubernetes 控制平面来管理多个节点集群，将工作负载放在不同的集群上，以获得更好的安全性和性能。

如果您对可接受的延迟有法规要求或严格限制，需要实施不同的策略和权限，或者希望避免要求零宕机的应用出现单点故障，这使您可以在不同的位置(包括不同的云提供商)协调应用，但仍有一个位置可以访问该基础架构。这简化了应用程序在集群之间的迁移，无论是为了扩展还是灾难恢复，尽管它也带来了很大的复杂性。

## 联网您的 Kubernetes 基础设施

您还需要规划服务发现选项和网络拓扑，包括防火墙和 VPN 连接，以及网络插件、DNS 设置、负载平衡器和集群的入口控制器。

考虑访问管理:您将需要部署[基于角色的访问控制(RBAC)](https://thenewstack.io/three-realistic-approaches-to-kubernetes-rbac/) 来为您的用户和资源实施细粒度的权限和策略，并确保您的管理访问安全。但是您还需要为需要访问现有数据存储的工作负载管理机器身份。

本地 [Kubernetes 用户认证](https://kubernetes.io/docs/reference/access-authn-authz/authentication/#users-in-kubernetes)使用证书:如果您需要对用户访问进行集中控制和管理，您可能会希望使用您现有的身份提供者进行[认证。](https://thenewstack.io/how-do-authentication-and-authorization-differ/)

## 管理 Kubernetes 的架构师

由于 Kubernetes 旨在简化应用程序的伸缩，同时您可以手动更改各个设置，如活跃度和就绪性探测，因此它实际上是为声明式配置管理而设计的。你在 YAML 编写配置文件(或者使用一个工具为你发出这些文件)来告诉 Kubernetes 一个应用程序应该如何运行，Kubernetes 处理这些事情。

不要调整设置，您应该使用基础设施作为代码，专注于可重复性的自动化:将配置设置为版本控制、可审计的代码，并根据需要经常应用它(或者如果有问题就重启它)，每次都获得相同的系统。

可重复的、不可变的基础设施是 Kubernetes 的设计宗旨，在这种基础设施中，您将集群视为牲畜(而不是您单独命名、拥抱和关心的宠物)。为此做准备就是如何减少正在进行的管理和在生产中实际操作容器的工作量。

您可以使用带有 [Flux](https://fluxcd.io/) 或 [Argo CD](https://argoproj.github.io/argo-cd) 的 [GitOps](https://www.gitops.tech/) 工作流将此扩展到策略管理和治理以及应用交付，该工作流部署应用更新，并使集群从引导到配置更新一直保持在所需状态。您将希望收集指标并跟踪性能:大多数工作负载都会产生普罗米修斯指标，但是您还需要考虑一个[监控仪表板](https://thenewstack.io/kubernetes/kubernetes-dashboards/)以及您希望启用什么日志记录。

您需要监控您的容器基础设施的威胁和安全风险，并确保您的 VM 主机得到适当的加固。同样，在规划 Kubernetes 基础设施架构时，考虑一下您将为此使用的工具和流程，会更容易确保您不会遗漏任何东西。

## 了解库伯内特建筑

将所有这些放在一起并不简单，您可以从其他 Kubernetes 用户如何构建他们的基础架构中学到很多东西。

“你试图获得 Kubernetes 八年的开发成果，然后才能进行生产。这要求太过分了。你需要一本历书来帮助你导航和避开冰山，”前 Kubernetes 发布负责人兼指导委员会成员拉克伦·伊文森警告说。Evenson 与 Kubernetes 的联合创始人 Brendan Burns 共同撰写了[“Kubernetes 最佳实践”](https://www.oreilly.com/library/view/kubernetes-best-practices/9781492056461/)，试图提供一个指南来提供一些帮助。

但是，您仍然需要花费时间来找出最适合您的特定工作负载的基础架构，并获得运行它的专业知识。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>