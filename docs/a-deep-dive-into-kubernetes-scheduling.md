# 深入了解 Kubernetes 的日程安排

> 原文：<https://thenewstack.io/a-deep-dive-into-kubernetes-scheduling/>

[](https://granulate.io/)

 [罗恩·索博尔

罗恩·索博尔是云计算初创公司 grate 的研发负责人，致力于通过基础设施优化来实现企业责任，为各地的公司标准化减少数字碳足迹。Ron 之前在以色列国防部队的军事情报项目中服务了 7 年，在被提升为研发团队领导之前，他与软件工程团队密切合作。](https://granulate.io/) [](https://granulate.io/)

Kubernetes 调度程序是 Kubernetes 控制平面的核心组件之一。它在控制平面上运行，其默认行为是将 pod 分配给节点，同时平衡它们之间的资源利用率。当 pod 被分配给一个新节点时，在该节点上运行的 kubelet 从 Kubernetes API 中检索 pod 定义。然后，kubelet 根据节点上的 pod 规范创建资源和容器。换句话说，调度程序在控制平面内部运行，并将工作负载分配给 Kubernetes 集群。您可能从未检查过 Kubernetes Scheduler 的日志或配置参数，因为在大多数情况下，该工具对于大多数开发、测试和生产案例都工作得很好。

本文将深入探讨 Kubernetes 调度器，首先概述一般的调度和带有亲缘性和污点的调度驱逐。然后我们将讨论调度器的瓶颈和您在生产中可能遇到的问题。最后，我们将研究如何微调调度器的参数，以适合您定制的集群。

## 日程安排概述

Kubernetes 调度只是将 pod 分配给集群中匹配节点的过程。调度程序监视新创建的 pod，并为它们的分配找到最佳节点。它根据 Kubernetes 的调度原则和您的配置选项选择最佳节点。

最简单的配置选项是直接设置`podspec`中的**节点名**字段，如下:

```
apiVersion:  v1

kind:  Pod

metadata:

   name:  nginx

spec:

   containers:

   -  name:  nginx

      image:  nginx

   nodeName:  node-01

```

默认情况下，上面的 nginx pod 将在 node-01 上运行。但是， **nodeName** 有很多限制，导致非功能 pod，比如云中未知的节点名，资源节点外，以及间歇性网络问题的节点。因此，除了在测试或开发期间，您不应该在任何时候使用**节点名**。

如果您想在一组特定的节点上运行您的 pods，使用 **nodeSelector** 来确保这一点。您可以将**节点选择器**字段定义为‘pod spec’:
中的一组键值对

```
apiVersion:  v1

kind:  Pod

metadata:

   name:  nginx

spec:

   containers:

   -  name:  nginx

      image:  nginx

   nodeSelector:

      disktype:  ssd

```

对于上面的 nginx pod，Kubernetes 调度程序将找到一个带有 disktype: ssd 标签的节点。当然，节点可以有额外的标签，Kubernetes 已经为节点 kubernetes.io/arch 或 kubernetes.io/os.填充了公共标签。你可以在 Kubernetes 参考文档中查看标签的完整列表。

使用`nodeSelector`可以有效地约束 pod 在带有特定标签的节点上运行。但是，它的使用只受标签及其值的限制。Kubernetes 中有两个更全面的特性来表达更复杂的调度需求:**节点亲和度**，标记 pods 吸引它们到一组节点；和**污染和容忍**，标记节点以击退一组圆荚体。这些特性将在下面讨论。

## 节点关联性

节点关联性是在 pod 上定义的一组约束，用于确定哪些节点有资格进行调度。可以使用关联性规则来定义 pod 节点分配的硬性和软性要求。例如，您可以将 pod 配置为仅运行带有 GPU 的节点，最好是带有 NVIDIA_TESLA_V100 的节点，以满足您的深度学习工作负载。调度器评估规则，并试图在定义的约束内找到合适的节点。像`nodeSelectors`一样，节点关联性规则与节点标签一起工作；然而，他们比`nodeSelectors`更强大。

您可以向`podspec`添加四个关联性规则:

*   **要求执行**
*   **requiredduringschedulingrequiredduringeexecution**
*   **在 schedulingignoredduringeexecution 期间首选**
*   **在 schedulingrequiredduringeexecution 期间首选**

这四个规则包括两个标准:必需的或首选的，以及两个阶段:调度和执行。以 required 开头的规则描述了必须满足的硬性要求。以 preferred 开头的规则是软要求，将被强制执行，但不能保证。调度阶段指的是 pod 到节点的第一次分配。执行阶段适用于调度分配后节点标签发生变化的情况。

如果规则在执行期间被声明为**ignored，调度程序将不会在第一次赋值后检查其有效性。但是，如果用**requiredduringeexecution**指定规则，调度程序将通过将 pod 移动到合适的节点来确保规则的有效性。**

看看下面的例子来帮助你理解这些相似性

```
apiVersion:  v1
kind:  Pod

metadata:
   name:  nginx

spec:
   affinity:
      nodeAffinity:
         requiredDuringSchedulingIgnoredDuringExecution:
            nodeSelectorTerms:
            -  matchExpressions:
               -  key:  topology.kubernetes.io/region
                  operator:  In
                  values:
                  -  us-east

         preferredDuringSchedulingIgnoredDuringExecution:
         -  weight:  1
            preference:
               matchExpressions:
               -  key:  topology.kubernetes.io/zone
                  operator:  In
                  values:
                  -  us-east-1
            -  us-east-2

   containers:
   -  name:  nginx
      image:  nginx

```

上面的 nginx pod 有一个节点关联规则，指示 Kubernetes 调度程序应该只将 pod 放在美国东部地区的一个节点上。第二个规则表明美国东部 1 区或美国东部 2 区应该是首选。

使用关联性规则，您可以使 Kubernetes 的调度决策为您的定制需求服务。

## 污点和宽容

集群中并非所有的 Kubernetes 节点都是相同的。可以让节点具有特殊的硬件，如 GPU、磁盘或网络功能。同样，您可能需要将一些节点专用于测试、数据保护或用户组。可以将污点添加到节点中以排斥豆荚，如下例所示:

`kubectl taint nodes node1 test-environment=true:NoSchedule`

对于污点`test-environment=true:NoSchedule`，Kubernetes 调度器不会分配任何 pod，除非它在`podspec` :
中具有匹配的容差

```
apiVersion:  v1
kind:  Pod

metadata:
   name:  nginx

spec:
   containers:
   -  name:  nginx
      image:  nginx

   tolerations:
   -  key:  "test-environment"
      operator:  "Exists"
      effect:  "NoSchedule"

```

污点和容忍共同作用，使 Kubernetes 调度程序专用一些节点，只分配特定的 pod。

## 调度瓶颈

尽管 Kubernetes 调度器被设计为选择最佳节点，但是在 pods 开始运行之后,“最佳节点”可能会改变。因此，从长远来看，pod 的资源使用和节点分配存在潜在问题。

### 资源请求和限制:“吵闹的邻居”

“吵闹的邻居”并不是 Kubernetes 特有的。任何多租户系统都是他们的潜在居住地。例如，假设您有两个 pod，A 和 B，运行在同一个节点上。如果 pod B 试图通过消耗所有 CPU 或内存来制造噪音，pod A 就会有问题。幸运的是，为容器设置资源[请求和限制可以控制邻居。Kubernetes 将确保容器为其请求的资源进行调度，并且不会消耗超过其资源限制的资源。如果您在生产环境中运行 Kubernetes，您将希望设置资源请求和限制，以拥有一个可靠的系统。](https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/%23how-pods-with-resource-requests-are-scheduled)

### 系统进程资源不足

Kubernetes 节点大多是连接到 Kubernetes 控制平面的虚拟机。因此，这些节点也有自己的操作系统和相关进程在其上运行。如果 Kubernetes 工作负载消耗了所有资源，节点将无法运行，并会遇到问题。您需要在 kubelet 中用标志**–system-reserved**设置保留资源来防止这种情况。

### 抢先或预定的 pod

如果 Kubernetes Scheduler 不能将一个 pod 调度到一个可用的节点上，它可以从节点上抢占(驱逐)一些 pod 来分配资源。如果您看到 pod 在集群中移动，而没有特定的原因，请考虑使用优先级来定义它们。类似地，如果您的 pod 没有被调度并且正在等待其他 pod，您需要检查它们的优先级。

在下面的例子中，优先级类不会为自己抢占任何其他 pod:

```
apiVersion:  scheduling.k8s.io/v1
kind:  PriorityClass

metadata:
   name:  high-priority-nonpreempting

value:  100000
preemptionPolicy:  Never
globalDefault:  false

description:  "This priority class will not preempt other pods."

```

您可以通过以下方式为 podspec 中的 pod 分配优先级:

```
apiVersion:  v1
kind:  Pod

metadata:
   name:  nginx

spec:
   containers:
   -  name:  nginx
      image:  nginx

   priorityClassName:  high-priority-nonpreempting

```

## 调度框架

Kubernetes Scheduler 有一个可插入的调度框架架构，允许您向框架添加一组新的插件。插件实现插件 API，并被编译到调度程序中。在这一节中，我们将讨论调度框架的工作流、扩展点和插件 API。

### 工作流和扩展点

调度 pod 包括两个阶段:调度周期和绑定周期。在调度周期中，调度器找到一个可行的节点。然后，在绑定过程中，将决策应用于集群。

下图说明了阶段和扩展点的流程:

工作流中的以下点对插件扩展开放:

*   **队列排序**:对队列中的 pod 进行排序
*   **前置过滤器**:检查 pod 的调度周期的前提条件
*   **过滤**:过滤不适合 pod 的节点
*   **后置过滤器**:如果没有为 pod 找到可行的节点，则运行
*   **预评分**:运行预评分任务，为评分插件生成可共享状态
*   **评分**:通过调用各个评分插件，对过滤后的节点进行排名
*   **NormalizeScore** :结合分数，计算节点的最终排名
*   **预留**:选择绑定周期前预留的节点
*   **允许**:批准或拒绝调度周期结果
*   **预绑定**:执行任何先决条件工作，例如提供网络卷
*   **绑定**:将 pod 分配给 Kubernetes API 中的节点
*   **后绑定**:通知绑定循环的结果

插件扩展实现了插件 API，是 Kubernetes Scheduler 的一部分。您可以在 Kubernetes 存储库中检查该接口。一个插件应该用它的名字注册它自己，如下:

```
// Plugin is the parent type for all the scheduling framework plugins.

type  Plugin  interface  {

  Name()  string

}

```

插件也实现了相关的扩展点，如下图:

```
// QueueSortPlugin is an interface that must be implemented by "QueueSort" plugins.
// These plugins are used to sort pods in the scheduling queue. Only one queue sort plugin may be enabled at a time.

type  QueueSortPlugin  interface  {

  Plugin

  // Less are used to sort pods in the scheduling queue.

  Less(*QueuedPodInfo,  *QueuedPodInfo)  bool

}

```

## 调度程序性能调整

Kubernetes 调度程序有一个工作流来为 pods 查找和绑定一个可行的节点。当集群中的节点数量非常多时，调度程序的工作负载会呈指数级增长。在大型集群中，可能需要很长时间才能找到最佳节点。要微调调度程序的性能，需要在延迟和准确性之间找到一个平衡点。

**percentageOfNodesToScore** 设置了计算节点分数的节点数量限制。默认情况下，Kubernetes 为 100 个节点的集群设置了一个介于 50%和 5000 个节点的集群之间的线性阈值。默认值的最小值是 5%。它确保您的集群中至少有 5%的节点被考虑进行调度。

在下面的例子中，您可以看到如何通过性能调优 kube-scheduler 来手动设置阈值:

```
apiVersion:  kubescheduler.config.k8s.io/v1alpha1

kind:  KubeSchedulerConfiguration

algorithmSource:

   provider:  DefaultProvider

percentageOfNodesToScore:  50

```

如果您有一个大规模集群，并且您的 Kubernetes 工作负载无法承受 Kubernetes 调度程序造成的延迟，那么更改百分比是一个好主意。

## 摘要

本文涵盖了 Kubernetes 中调度的所有方面。我们从 pod 和节点的配置开始，包括节点选择器、相似性规则、污点和容忍度。然后，我们讨论了 Kubernetes Scheduler 的框架、扩展点和 API，以及可能出现的与资源相关的瓶颈。最后，我们介绍了该工具的性能调优设置。尽管 Kubernetes Scheduler 可以开箱即用地将 pod 分配给节点，但了解其动态并为可靠的生产级 Kubernetes 设置配置它们是非常重要的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>