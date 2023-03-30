# 在 Kubernetes 上运行有状态服务的蓝图

> 原文：<https://thenewstack.io/a-blueprint-for-running-stateful-services-on-kubernetes/>

[](https://www.linkedin.com/in/rcstaatz/)

[Ryan Staatz](https://www.linkedin.com/in/rcstaatz/)

[Ryan Staatz 是 LogDNA 的 DevOps 主管，他将公司的基础架构从虚拟机迁移到 Kubernetes。他的团队与 IBM 等大型企业合作，建立跨部署的稳定性，扩展 LogDNA 的合规性库，并提高大规模的可观察性。Ryan 经常介绍 Kubernetes 上的伸缩弹性搜索、利用多云基础架构应对挑战、在裸机上运行 Kubernetes 以及管理数十个独立的生产环境。在加入 LogDNA 之前，Ryan 曾在 WhatsApp 等企业公司工作，并一直热衷于为初创公司做出贡献。Ryan 拥有斯坦福大学的人类生物学学士学位。](https://www.linkedin.com/in/rcstaatz/)

[](https://www.linkedin.com/in/rcstaatz/)[](https://www.linkedin.com/in/rcstaatz/)

早在 Kubernetes 问世之前，管理有状态应用程序对于工程和运营团队来说一直是一个挑战。在这篇文章中，我们将探讨您在 Kubernetes 上部署有状态应用程序的所有方面，从底层硬件到 Pod 更新策略，并深入了解 LogDNA 如何使用有状态 Kubernetes 来构建世界上最快的日志管理平台之一。

首先，我们将描述“有状态的”和“状态”在云本地上下文中的含义。

“状态”是指应用程序在特定时间点所处的状况。有状态应用程序根据以前的事务改变其行为；换句话说，它保持着对过去的记忆。有状态应用程序的例子包括数据库、缓存和内容管理系统(CMS ),比如 WordPress。对于有状态的应用程序，应用程序必须有一个可以将其状态存储为数据的位置。这些数据需要在应用程序的整个生命周期中对其可用。在一个基本的单服务器、单实例应用程序中，这可能与将数据直接存储在主机文件系统上一样简单。

然而，当将应用程序扩展到多个实例和节点时，会出现一些操作上的挑战。例如，应用程序的每个实例要么独立于其他实例维护自己的数据集，要么与其他实例同时访问相同的数据。对于 Kubernetes 来说，这与容器短暂性的观点相反。容器被设计为在整个集群中是可替换的和可重新安排的，但是当容器具有与之相关联的数据时，该数据必须在部署时附加到容器。Kubernetes 支持这种行为，但是它需要额外的配置步骤。

在 Kubernetes 上运行有状态服务的有效性始于您的基础设施。集群设计影响从性能到可靠性的方方面面。需要考虑的事项包括集群是托管还是非托管的、节点运行的硬件、用于存储应用程序状态和多云部署以及数据驻留的存储类型。

一旦设计并优化了基础设施，下一步就是将有状态服务部署到 Kubernetes。Kubernetes 的最新版本提供了原生 API 对象，使这个过程变得更加容易，特别是 [StatefulSets](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) 。 [StatefulSets](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) 对于管理有状态 pod 的部署非常有用，非常类似于无状态 pod 的[部署](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)。StatefulSets 提供额外的功能来帮助管理有状态的应用程序，包括:

*   为每个 Pod 分配一个持久的、唯一的和有序的标识符。
*   通过本机服务启用每个 pod 的内部 DNS 查找。
*   按顺序部署、更新和终止 pod。
*   通过 volumeClaimTemplates 动态配置磁盘。

StatefulSet 中的每个 Pod 都分配有一个[序号索引](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/#pod-identity)，它是一个“0 索引”整数值，既作为唯一标识符，也作为部署、更新或终止 Pod 的顺序。该索引与状态集名称一起也用于创建唯一的网络标识。LogDNA 将此用于服务发现和跨多个 pod 的负载平衡请求。

Kubernetes 最初可能不是为有状态应用程序设计的，但是最近的版本提供了高度的支持。StatefulSets 的发布使得以更安全、更灵活的方式部署和扩展有状态应用程序变得更加容易。最近的 Kubernetes 版本也增加了额外的有用特性，包括[动态磁盘供应](https://kubernetes.io/docs/concepts/storage/dynamic-provisioning/)。

尽管无状态应用程序和有状态应用程序之间存在根本差异，但 Kubernetes 仍然提供了高度的灵活性和自动化，无论是运行在裸机上还是托管平台上。Kubernetes 允许我们在多个环境中自动化我们的有状态应用程序，同时保持闪电般的性能和高度的可用性。

*如果你想了解 LogDNA 如何利用 Kubernetes 开发有状态应用，你可以[观看由](https://go.logdna.com/running-stateful-services-on-kubernetes) [LogDNA](https://logdna.com/) 举办的网络研讨会。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>