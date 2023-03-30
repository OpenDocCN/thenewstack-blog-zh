# 配置 Kubernetes Pods 在生产中运行的 5 个最佳实践

> 原文：<https://thenewstack.io/5-best-practices-for-configuring-kubernetes-pods-running-in-production/>

编者按:贾纳基拉姆·MSV 的网络研讨会系列“机器智能和现代基础设施(MI2)”提供了涵盖前沿技术的信息丰富、见解深刻的会议。注册参加即将举办的 MI2 网络研讨会，网址为

[http://mi2.live](http://mi2.live)

.

Kubernetes 中的 pod 代表基本部署单元。它可能包含一个或多个作为逻辑实体打包和部署的容器。在 Kubernetes 中运行的云原生应用可能包含映射到每个微服务的多个 pods。豆荚也是 Kubernetes 的缩放单位。

这里是在 Kubernetes 中部署 pod 之前要遵循的五个最佳实践。尽管可能会应用其他配置，但这些是为云原生应用程序带来基本健康的最基本实践。

## 1)选择最合适的 Kubernetes 控制器

虽然将容器映像作为通用 pod 来部署和运行可能很诱人，但是您应该根据工作负载特征选择正确的控制器类型。Kubernetes 有一个称为控制器的原语，它与工作负载的关键特征一致。 [Deployment、](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) [StatefulSet](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) 和 [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/) 是 Kubernetes 中最常用的控制器。

部署无状态 pod 时，请始终使用部署控制器。这通过扩展、部署历史和回滚特性为 pod 带来了类似 PaaS 的功能。当一个部署被配置为最小副本数为 2 时，Kubernetes 确保至少有两个 pod 始终运行，这带来了容错能力。即使在部署只有一个副本的 pod 时，也强烈建议您使用部署控制器，而不是普通的 pod 规范。

对于数据库集群之类的工作负载，StatefulSet 控制器将创建一组具有可预测命名约定的高可用性 pod。需要高度可用的有状态工作负载(如 Cassandra、Kafka、ZooKeeper 和 SQL Server)被部署为 Kubernetes 中的有状态集。

当您需要在集群的每个节点上运行 pod 时，您应该使用 DaemonSet 控制器。由于 Kubernetes 会在新配置的工作节点中自动调度 DaemonSet，因此它成为配置和准备工作负载节点的理想选择。例如，如果您希望在部署工作负载之前在节点上挂载现有的 NFS 或 Gluster 文件共享，请将 pod 打包并作为 DaemonSet 部署。

确保在部署 pod 之前选择最合适的控制器类型。

## **2)为 pod 配置健康检查**

默认情况下，所有正在运行的 pod 都将重启策略设置为 always，这意味着当容器遇到错误时，在一个节点中运行的 kubelet 将自动重启一个 pod。

健康检查通过[容器探测器](https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/#container-probes)的概念扩展了 kubelet 的这种能力。可以为每个 pod 配置三种探测器—就绪、活动和启动。

您可能会遇到这样的情况:pod 处于运行状态，但“就绪”列显示 0/1。这表示 pod 未准备好接受请求。准备就绪探测确保在启动 pod 之前满足先决条件。例如，服务于机器学习模型的 pod 需要在服务于推理之前下载模型的最新版本。在将 pod 移至就绪状态之前，就绪探测器将不断检查文件是否存在。类似地，CMS pod 中的就绪探测器将确保数据存储区已装载且可访问。

活性探测器将定期检查容器的健康状况，并向 kubelet 报告。当此运行状况检查失败时，pod 将不会接收流量。该服务将忽略该 pod，直到活动探测报告一个肯定的状态。例如，MySQL pod 可能包含一个持续检查数据库引擎状态的活动探测器。

从版本 1.16 开始，启动探测器仍然处于 alpha 阶段，它允许容器在将健康检查移交给活性探测器之前等待更长的时间。这在将遗留应用程序移植到 Kubernetes 时很有帮助，因为这会花费不寻常的启动时间。

以上所有健康检查都可以用命令、HTTP 探测和 TCP 探测来配置。

关于配置健康检查的步骤，请参考 Kubernetes [文档](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/)。

## 3)利用 Init 容器来准备 Pod

有些情况下，容器在准备就绪之前需要初始化。在 pod 进入就绪状态之前，可以将初始化转移到另一个容器来做基础工作。一个 [init 容器](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/)可以用来下载文件、创建目录、更改文件权限等等。

init 容器甚至可以用来确保 pod 以特定的顺序启动。例如，在启动 WordPress pod 之前，Init 容器会一直等到 MySQL pod 可用。

一个 pod 可以包含多个 init 容器，每个容器执行一个特定的初始化任务。

## 4)应用节点/单元关联性和反关联性规则

Kubernetes scheduler 很好地根据 pod 的资源需求和集群中的资源消耗将 pod 放置在相关的节点上。但是，可能需要控制 pod 在节点上的调度方式。Kubernetes 提供了两种机制— [节点亲和/反亲和](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#affinity-and-anti-affinity)和 [pod 亲和/反亲和](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#affinity-and-anti-affinity)。

节点关联性扩展了已经非常强大的 nodeSelector 规则，以涵盖更多的场景。就像 Kubernetes 注释使标签/选择器更具表现力和可扩展性一样，节点相似性通过附加规则使 nodeSelector 更具表现力。节点关联性将确保在满足特定标准的节点上调度 pod。例如，可以强制将有状态数据库 pod 安排在连接了 SSD 的节点上。类似地，节点反亲缘性将有助于避免在节点上调度可能导致问题的 pod。

虽然节点关联在 pod 和节点之间进行匹配，但可能会出现需要将 pod 放在同一位置以实现性能或合规性的情况。Pod 关联将帮助我们放置需要共享同一个节点的 pod。例如，Nginx web 服务器 pod 必须安排在具有 Redis pod 的同一节点上。这将确保 web 应用程序和缓存之间的低延迟。在其他情况下，您可能希望避免在同一个节点上运行两个 pod。在部署 HA 工作负载时，您可能希望强制同一 pod 的两个实例不在同一节点上运行。Pod 反亲缘关系将强制实施防止这种可能性的规则。

分析您的工作负载，以评估您是否需要利用节点和单元关联性策略来进行部署。

## 5)利用自动缩放器

Amazon Web Services、Microsoft Azure 和 Google Cloud Platform 等超大规模云平台具有内置的自动扩展引擎，可以根据平均资源消耗或外部指标来扩展和扩展虚拟机群。

Kubernetes 以[水平机架自动缩放器](https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/) (HPA)、[垂直机架自动缩放器](https://github.com/kubernetes/autoscaler/tree/master/vertical-pod-autoscaler#install-command) (VPA)和[集群自动缩放器](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler)的形式为部署提供类似的自动缩放能力。

Horizontal pod autoscaler 根据观察到的 CPU 利用率，自动扩展复制控制器、部署、副本集或有状态集中的单元数量。HPA 在 Kubernetes 中被表示为一个对象，这意味着它可以通过一个 YAML 文件来声明，该文件通过 kubectl CLI 来控制。与 IaaS 自动扩展引擎类似，HPA 支持定义 CPU 阈值、pod 的最小和最大实例、冷却时间，甚至自定义指标。

垂直单元自动扩展消除了在定义单元的 CPU 和内存配置时的猜测。该自动缩放器能够为 CPU 和内存请求和限制推荐适当的值，或者可以自动更新这些值。自动更新标志将决定现有的 pod 是被驱逐还是继续使用旧配置运行。查询 VPA 对象将通过上限和下限显示最优的 CPU 和内存请求。

当 HPA 和 VPA 扩展部署和单元时， [Cluster Autoscaler](https://github.com/kubernetes/autoscaler) 将扩展和收缩工作节点池的大小。它是一个独立的工具，可以根据当前的利用率调整 Kubernetes 集群的大小。当存在由于资源不足而无法在任何当前节点上进行调度的 pod 时，或者当添加新节点会增加群集资源的整体可用性时，群集自动缩放会增加群集的大小。在后台，集群自动缩放器与底层 IaaS 提供者协商添加或删除节点。将 HPA 与集群自动扩展相结合，可实现工作负载的最高性能和可用性。

在接下来的教程中，我将通过用例及场景详细介绍每个最佳实践。敬请关注。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>