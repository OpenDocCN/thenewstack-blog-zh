# Kubernetes 1.21 带来了新的内存管理器，更灵活的调度

> 原文：<https://thenewstack.io/kubernetes-1-21-brings-a-new-memory-manager-more-flexible-scheduling/>

开源的 Kubernetes 编排软件一直在发展。每一次新的迭代都会带来新的特性和改进，使容器管理变得更加简单和灵活。随着 Kubernetes 最新版本的发布，云原生开发者和管理员将会发现这一点。事实上， [Kubernetes](https://kubernetes.io/) 的 1.21 版本将于下周发布，它带来了 50 项增强功能(比 1.20 版本的 43 项和 1.19 版本的 34 项有所增加)，因此应该对几乎所有容器用户都有所帮助。

但是这些新的增强是什么呢？让我们深入研究一下，找出答案。

## 一个新的内存管理器

您的容器部署依赖于内存。这些部署必须明智地使用内存，否则，它们可能会耗尽您集群的宝贵资源和您企业的资金(请记住，在云托管的帐户上，您需要为您使用的内容付费)。

内存管理器是生态系统中的一项新功能，它为保证 QoS 类别中的 pod 启用了保证内存分配功能。通过此功能，您将发现两种不同的分配策略:

*   单 NUMA 适用于高性能和对性能敏感的应用。
*   多 NUMA 克服了单 NUMA 策略无法管理的情况(例如当一个 pod 所需的内存量超过单 NUMA 节点容量时)。

存储器管理器为每个 NUMA 节点(和各自的存储器类型)初始化存储器表集合，这产生存储器映射对象。内存表和内存映射是这样构建的:

```
type  MemoryTable  struct  {

            TotalMemSize uint64  `json:"total"`
            SystemReserved uint64  `json:"systemReserved"`
            Allocatable uint64  `json:"allocatable"`
            Reserved uint64  `json:"reserved"`
            Free uint64  `json:"free"`
}

type  NodeState  struct  {
          NumberOfAssignments int  `json:"numberOfAssignments"`
          MemoryMap map[v1.ResourceName]*MemoryTable  `json:"memoryMap"`
          Nodes  []int  `json:"nodes"`
}

type NodeMap map[int]*NodeState

```

从最初的 README.md 中找到更多关于新内存管理器的信息。

## 更灵活的调度程序

Kubernetes 的开发人员明白的一件事是，每个工作负载并不相同。随着 1.21 的发布，调度程序将获得两个新功能:

*   指定节点允许云本地开发人员使用 Pod 中的`.status.nominatedNodeName`字段定义首选节点。如果调度程序无法将传入的 pod 放入首选节点，它将尝试抢占优先级较低的 pod 以腾出空间。
*   Pod 关联性选择器允许开发人员在部署中定义节点关联性。此功能允许您限制将在哪些节点上安排 pod。

Pod 亲和力是这样定义的:

```
apiVersion:  v1
kind:  Deployment

…

spec:

…
affinity:
podAffinity:
requiredDuringSchedulingIgnoredDuringExecution:
nodeSelectorTerms:
-  matchExpressions:
-  key:  example-label
operator:  In
values:
-  label-value
namespaces:  […]
namespacesSelector:

```

## 复制集缩减

对于任何管理 Kubernetes 部署的人来说，您都知道自动伸缩可能是最重要的特性之一。困扰 Kubernetes 自动伸缩的一个问题是在负载峰值过后缩减规模。

随着 1.21 的发布，现在有两个新的缩减策略，这意味着您将不再需要手动检查何时缩减部署。这些战略是:

*   副本集上的随机 pod 选择缩减规模—使用`LogarithmicScaleDown`半随机选择 Pod(基于 Pod 时间戳的对数存储桶)来缩减规模。
*   使用`controller.kubernetes.io/pod-deletion-cost=X`(其中 X 是 0 到 10 之间的一个数字)，ReplicaSet 删除成本使您可以注释 pod。删除成本值较低的单元将首先被删除。

## 索引作业

对于索引作业，作业控制器将创建一个具有关联索引(作为注释添加)的 Pod，从–到。规格-完工-1。作业控制器将为还没有活动或成功窗格的最低索引创建窗格。如果一个索引有多个窗格，控制器将删除所有窗格，只留下一个。没有索引的活动窗格会被删除，没有索引的已完成窗格不会计入失败或成功(也不会被删除)。

## 网络策略端口范围

在 Kubernetes 1.21 之前，您必须为每个网络策略编写一个规则。现在，您可以编写一个定义整个端口范围的网络策略。这意味着您的部署工作更少，策略文件更少。使用 NetworkPolicyEndPort 特性门，您可以像这样定义一系列端口:

```
spec:
egress:
-  ports:
-  protocol:  TCP
port:  32000
endPort:  32768

```

## 结论

好了，Kubernetes 1.21 中的一些特性应该会让你对这个新版本感到兴奋。要了解更多 Kubernetes 1.21 即将(和将要)推出的内容，请务必查看完整的[变更日志](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.21.md)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>