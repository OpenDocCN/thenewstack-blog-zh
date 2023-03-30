# 充分利用 Kubernetes 自动缩放功能

> 原文：<https://thenewstack.io/getting-the-most-from-kubernetes-autoscaling/>

在云计算中，自动伸缩是根据需求或工作负载的变化动态调整实例或资源数量的过程。这一过程提高了资源利用率，降低了成本，同时提高了应用程序的可靠性、可用性和可伸缩性。

水平自动伸缩是一个过程，通过该过程，服务或应用程序的运行实例的数量会自动增加或减少(分别为“向外扩展”和“向内扩展”)。同时，垂直自动扩展涉及动态调整分配给实例的资源，如内存、CPU 或磁盘存储量。

Kubernetes 实现了两个主要的自动缩放器:[水平 Pod 自动缩放器](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/) (HPA)和[垂直 Pod 自动缩放器](https://github.com/kubernetes/autoscaler/tree/master/vertical-pod-autoscaler) (VPA)。两者都有助于确保[应用拥有满足需求所需的资源](https://thenewstack.io/k8s-resource-management-an-autoscaling-cheat-sheet/)，同时避免过度供应并降低成本。

本文将探讨如何有效地利用 HPA 和 VPA 来实现[最佳自动伸缩功能](https://thenewstack.io/getting-started-with-kubernetes-autoscaling/)。我们还将讨论为什么只有 HPA 是不够的，以及 HPA 和 VPA 是如何相互补充的。

## 理解水平和垂直 Pod 自动缩放的复杂性

HPA 根据观察到的 CPU 使用情况和其他指标(如内存和传入网络流量)动态调整副本数量，从而横向扩展群集容量。

VPA 是一个独立的控制器，运行在集群中，观察工作负载如何响应请求。然而，当 pod 资源达到某一极限时，VPA 的反应不同于 HPA。Kubernetes VPA 不是向我们的工作负载添加更多副本，而是通过向现有的 pod 分配更多 CPU 或内存资源来垂直扩展集群容量。

HPA 和 VPA 要求我们使用 Kubernetes Metrics 服务器或其他实现 Kubernetes metrics API 的资源。度量服务器从我们的集群中聚集容器资源度量，并为 Kubernetes 自动伸缩管道公开它们。

## HPA 和 VPA 如何工作

Kubernetes 的 HPA 通过自动增加或减少 pod 的副本数量来调整集群的大小。但是 HPA 必须在所有资源消耗完之前行动。这就是为什么 HPA 使用一些指标配置来了解应该在哪个点添加更多复制副本。例如，当一个 pod 的内存利用率达到指标中定义的百分比时，它会增加集群中运行的 pod 的数量。

除了内存之外，我们还可以配置 CPU 使用率，以便在需要时触发 HPA 扩展。

然而，即使有了 HPA 和 VPA，活动的突然增加(称为负载激增)也会超出我们配置的指标，并中断我们的系统。因此，我们需要设置我们的指标级别，以便 HPA 和 VPA 能够足够快地横向扩展，让我们的 pod 能够处理增加的负载。否则，应用程序用户可能会注意到服务的降级或不可用。

如果使用量低于目标，我们的 pod 可能有太多的 CPU 和内存来处理当前的工作负载。然后，Kubernetes VPA 可以缩减我们的工作负载，减少 CPU 或内存。

Kubernetes 自动伸缩策略是根据特定的指标定义的，如 CPU 利用率、内存使用量或传入的网络流量。这些设置的策略触发实例的[添加](https://thenewstack.io/how-to-optimize-database-efficiency-in-kubernetes/)或移除，或者相应地调整资源。

在 Kubernetes，我们可以将 Kubernetes VPA 和 HPA 用于不同的目的。与 HPA 相比，具有可变且不可预测的资源需求的应用从 VPA 中获益更多，因为 VPA 可以调整单个 pod 的资源请求，如 CPU 或内存，并对资源分配提供更细粒度的控制。

另一方面，对资源有可预测和一致需求的应用程序从 HPA 中受益更多，因为它扩展了单元副本的数量，从而在多个单元和节点之间平衡了负载。

简单地添加更多的单元(水平扩展)并不总是理想的。与拥有额外的可用实例(水平扩展)相比，直接拥有更多可用资源(垂直扩展)会让某些应用程序受益更多。

一般来说，垂直扩展对于具有高资源需求和需要实时服务的大量用户的应用程序是有益的，比如一个[数据库](https://thenewstack.io/how-to-optimize-database-efficiency-in-kubernetes/)服务器。

另一方面，当我们的应用程序被分成更小的、可以并行运行的独立部分时，水平伸缩通常是有益的。这种类型的伸缩通常用于处理许多请求的应用程序，因为它允许更好的负载平衡和改进的可靠性。向许多用户提供静态内容的 web 服务器就是这种情况。

垂直和水平扩展各有利弊，最佳方法可能因应用程序的特定要求而异。为了实现最佳性能和可靠性，有必要将这两种扩展技术结合起来。

## 同时使用 HPA 和 VPA

通常建议不要在同一个 Kubernetes 部署中使用 VPA 和 HPA。据库伯内特[自述](https://github.com/kubernetes/autoscaler/blob/master/vertical-pod-autoscaler/README.md):

此时，垂直 Pod 自动缩放器不应与 CPU 或内存上的[水平 Pod 自动缩放器](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/#support-for-resource-metrics) (HPA)一起使用。但是，我们可以在自定义和外部指标上使用 VPA 和[HPA](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/#scaling-on-custom-metrics)

自定义指标和外部指标之间的根本区别在于，产生指标的应用程序是运行在我们的 Kubernetes 集群内部还是外部。我们的集群提供的自定义指标示例包括每秒读取数、每秒写入数和网络性能。外部指标可以是来自集群外部应用程序的发布/订阅队列中未送达消息的数量。

研究表明，与 Kubernetes 中的 VPA 相比，大多数组织更喜欢 HPA，因为 HPA 更容易设置和使用，对扩展过程提供更多控制，并与 Kubernetes 的其他功能(如自定义和外部指标)更好地集成。

根据 [Datadog](https://web.archive.org/web/20220330233349/https://www.datadoghq.com/container-report/) 从 2021 年 10 月开始的研究，40%在生产中运行 Kubernetes 的组织使用 HPA。同时，只有不到 1%的组织使用 VPA。简而言之，对于大多数公司来说，要么是 HPA，要么什么都没有。除了这些组织的云预算超支之外，生产中大量未充分利用的容器也造成了云浪费。

幸运的是，可以配置 HPA 和 VPA 一起工作。这个过程需要分离触发自动缩放的事件，这样它们就不会同时被触发。如果是这样的话，可能会导致纵向和横向的扩展，潜在地导致不必要的 pod(横向)或资源的过度分配(纵向)。

以前，我们必须在垂直或水平扩展我们的 Kubernetes 集群之间做出选择。但是，当 StormForge 推出带有 StormForge Optimize Live 的二维 Kubernetes pod 自动缩放功能时，情况发生了变化。

### StormForge 优化 Live 的二维自动缩放

StormForge Optimize Live 支持同步垂直和水平 pod 自动缩放。与配置 HPA 和 VPA 协同工作的典型过程相比，这是一种更简单、更有效的方法。

StormForge Optimize Live 根据实时资源利用率和需求，将[机器学习(ML)算法](https://finance.yahoo.com/news/stormforge-optimize-live-uses-machine-135800765.html)应用于应用的遥测数据。它决定了 pod 的理想 CPU、内存和群集中 pod 副本的最佳数量。

StormForge Optimize Live 还可以检测 HPA 是否打开，并建议我们的缩放点应该位于 HPA 配置的哪个位置。这确保我们始终非常接近使用曲线，以保持最佳性能和可靠性，同时减少云浪费和成本。借助 Optimize Live，我们可以自动优化资源使用并最大限度地减少过度配置，而无需手动调整、调整和配置我们的系统。

Optimize Live 分析捕获的可观察性数据，并基于容器实时推荐 CPU 和内存的优化配置。

## 在自动缩放之前了解您的应用

了解应用程序的要求对于选择最佳自动缩放选项至关重要，因为这有助于确保系统能够高效地处理应用程序不断变化的需求。要考虑的一些关键点包括流量模式、资源使用、性能目标和成本限制。

清楚了解这些要求后，我们可以选择最佳的自动扩展策略，无论是水平扩展、垂直扩展还是两者的组合，并相应地配置系统。

## 结论

Kubernetes 的自动伸缩机制允许我们的集群自动响应资源需求的变化。Kubernetes HPA 通过根据配置阈值调整集群大小来水平调整集群，以获得适当数量的单元。相比之下，VPA 通过添加或删除内存或 CPU 容量来垂直调整 pod。问题是，大多数组织只进行横向自动扩展，而 VPA 却没有得到充分利用。结果，许多资源被浪费了。

HPA 和 VPA 是在 Kubernetes 集群中有效管理资源的基本技术。HPA 确保您有足够的资源来处理流量高峰，同时在低流量期间降低成本。VPA 允许您确保您的应用程序有最佳数量的资源运行，同时最大限度地降低成本。HPA 和 VPA 相结合，可以帮助您实现更高效的资源利用、降低成本并提高应用程序的性能和可扩展性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>