# Kubernetes 自动缩放入门

> 原文：<https://thenewstack.io/getting-started-with-kubernetes-autoscaling/>

自动扩展是指动态分配资源，以满足应用不断变化的需求。这也是 Kubernetes 集群最具影响力的功能之一。

Kubernetes 具有内置的服务发现和自我修复功能，它可以跨数千个节点调度和分发您的应用程序。这意味着您的集群可以增加或减少可用节点的数量，以适应资源需求的变化。

在 Kubernetes 中实现自动伸缩时，我们必须优先考虑效率。如果实施不当，可能会导致从成本增加到停机的严重后果。所以，优化是关键。

本文将回顾 Kubernetes 自动缩放的工作原理，讨论 Kubernetes 提供的不同的[自动缩放](https://thenewstack.io/k8s-resource-management-an-autoscaling-cheat-sheet/)方法，并强调自动缩放过程中可能出现的潜在错误。然后，最重要的是，我们将探索如何解决它们。

## 有效使用 Kubernetes 自动缩放

为了有效地自动扩展，我们需要合理地分配资源。为此，我们需要了解我们的资源可用性和应用程序要求，并相应地分配资源限制。这些限制通常取决于工作负载波动，而工作负载波动通常是不可预测的，并且容易出现峰值。

最佳资源分配至关重要。太少的资源会导致停机、延迟和糟糕的用户体验，而过度分配则[成本高昂](https://thenewstack.io/how-to-gain-visibility-into-kubernetes-cost-allocation/)且效率低下，导致时间和资源的浪费。

这就是自动缩放发挥作用的地方。自动缩放使我们能够在激增时扩大组件，并在恢复正常时减少组件。Kubernetes 中的自动缩放通过指定最小和最大副本数的目标 CPU 百分比来工作，该百分比与实际 CPU 消耗进行比较。如果超过最大阈值，群集将增加副本的数量。如果 CPU 使用率低于最小值，副本的数量就会减少。否则就维持现状。

## Kubernetes 中的自动缩放方法

Kubernetes 提供了三种主要的内置自动缩放方法。在接下来的章节中，我们将解释每种方法及其工作原理，并强调使用这种自动缩放方法的好处。

### 使用水平窗格自动缩放

[水平 pod 自动缩放器](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/) (HPA)允许我们根据 CPU 使用情况或其他用户定义的指标来增加或减少给定资源的 Pod 副本数量。

HPA 的工作原理是定期监控指标工具或服务器的资源使用情况，并定期调整 pod 复制副本的数量以匹配观察到的指标。它的目标是将所有 pod 的平均 CPU 使用率百分比保持在一个指定的值。

例如，如果部署遇到高流量，Kubernetes 集群可以增加副本的数量来处理负载。

### 使用垂直窗格自动缩放

与 HPA 不同，[垂直机架自动缩放器(VPA)](https://github.com/kubernetes/autoscaler/tree/master/vertical-pod-autoscaler) 根据使用情况而不是机架数量向现有机架分配资源。VPA 通过跟踪应用程序的资源使用情况来推荐 pod 副本的目标值。

这种扩展方法旨在使资源分配与实际使用相匹配。例如，如果一个副本使用了太多的 CPU，Kubernetes 集群可以增加它的 CPU 限制来适应它。

VPA 有助于防止 Kubernetes 调度程序错误地假设 pod 将坚持其初始最小限制而不是最大阈值，从而过量使用资源。VPA 让我们能够使用实时数据而不是依靠猜测来设置资源上限。

### 使用集群自动缩放器

[集群自动缩放器](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler)监控并调整集群的节点数量和整体大小，以满足需求。它的工作原理是监视因资源不足而无法安排的 pod，并确定适当的响应，包括:

*   添加另一个节点以解除对 pod 的阻止。
*   增加节点池的大小。
*   将当前部署的单元重新分配到更少的节点中。
*   从被阻止的节点中逐出 pod 以将其完全删除。

值得注意的是，因为这种方法涉及添加和删除基础设施，所以我们必须确保任何凭证都得到充分保护。

## 配置 Kubernetes 自动缩放

虽然自动扩展是在工作负载波动期间提高效率的优秀解决方案，但它不是一个放手的过程。无论我们选择哪种方法，正确配置和调整 Kubernetes 资源分配以防止错误和资源浪费是至关重要的。

在自动伸缩过程中，管理资源使用的最佳方式是建立对 CPU 和内存的请求和限制。请求是容器需要的资源的最小数量，而限制是容器将消耗的资源的最大数量。

但是，我们必须根据实际使用情况仔细设置和调整我们的限制和要求。请记住，单台机器上的 CPU 和内存是有限的，集群中的每个活动工作负载都需要足够的资源。否则，它们会耗尽内存，导致集群故障和成本增加。

明智地使用请求和限制还可以让 Kubernetes 调度程序更好地了解我们的服务需求。调度器根据尽力服务质量(QoS)将节点放置在 pod 上。QoS 根据 pod 的资源阈值确定其优先级。创建时，会自动为 pod 分配三个可能的 QoS 类别之一。从最高优先级到最低优先级，这些包括:

*   担保
*   可爆发的
*   全力

尽力服务质量(Best-effort QoS)意味着当系统内存不足时，这些低优先级的单元将被销毁以释放资源，从而防止内存不足(OOM)错误和崩溃。正确配置请求和限制对于确保高 QoS 至关重要。

## Kubernetes 自动缩放的局限性

正如我们所见，有效的 Kubernetes 自动缩放需要大量的微调。然而，知道如何最好地设置配置选项并不总是直观或显而易见的。Kubernetes 的三种自动缩放方法都有挑战和限制，如果我们选择使用它们，我们需要注意这些挑战和限制。

例如，HPA 和 VPA 在进行计算时都没有将每秒输入/输出操作(IOPS)、网络或[存储](https://thenewstack.io/choosing-between-container-native-and-container-ready-storage/)考虑在内。这使得应用程序容易变慢或崩溃。VPA 也不允许我们更新活跃运行的 pod 上的资源限制，这意味着我们必须移除 pod 并创建新的 pod 来设置新的限制。

此外，集群自动缩放器与较新的第三方工具的兼容性有限，这意味着我们只能在 Kubernetes 支持的平台上使用它。集群自动缩放也只查看 pod 的请求来做出缩放决定，而不是评估实际使用情况。因此，它不能识别用户请求的备用资源。这可能导致低效、浪费的集群。

## 利用机器学习优化 Kubernetes 自动缩放

Kubernetes 自动缩放的资源效率低下通常始于不恰当的垂直缩放。然后，水平扩展加剧了这些问题，表现为高云成本，因为集群自动扩展会向已经过度请求的集群添加实例。

基于机器学习的优化解决方案，例如 [StormForge Optimize Live](https://www.stormforge.io/how-stormforge-optimize-live-works) ，可以通过自动化维护 Kubernetes 大规模资源效率的过程来应对这些挑战。使用来自可观察性解决方案和机器学习的数据，这些工具提供了关于修改 Kubernetes 默认配置之外的配置的更高级的建议。

像 StormForge 这样的优化解决方案本质上就像一个替代 VPA，为我们处理 pod 大小调整。此外，如果它检测到我们也在运行 HPA，它会推荐一个目标利用率设置，在不影响应用程序性能的情况下减少资源使用。

使用机器学习来优化 Kubernetes 环境和降低成本消除了自动化资源管理的猜测。因此，我们可以专注于创新，而不是故障排除。

## 结论

Kubernetes autoscaling 可确保您的应用程序始终充分利用现有资源，无论工作负载如何，从而节省时间和金钱。

当然，在 Kubernetes 中实现自动缩放时，有一些事情需要记住。正确的配置是高 QoS 和持续监控应用程序以确保其正确伸缩的关键。这种微调过程可能具有挑战性，因此转向像 [StormForge Optimize Live](https://www.stormforge.io/how-stormforge-optimize-live-works) 这样的解决方案可以帮助确保您的 CPU 和内存资源始终得到正确分配，以保持您的应用程序以最佳容量和低成本运行。

当利用 Kubernetes 中的自动缩放时，请确保您使用的是 Kubernetes 的最新版本，并且您已经定义了资源请求以避免自动缩放的误算。这样做可以确保您的自动缩放实现全面、高效，最重要的是准确。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>