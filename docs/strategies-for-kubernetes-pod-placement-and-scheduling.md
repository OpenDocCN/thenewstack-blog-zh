# Kubernetes Pod 放置和调度策略

> 原文：<https://thenewstack.io/strategies-for-kubernetes-pod-placement-and-scheduling/>

Kubernetes 有一个最复杂的调度程序来处理 pod 放置策略。根据 pod 规范中提到的资源请求，Kubernetes 调度程序自动选择最合适的节点来运行 pod。

但是在某些情况下，我们可能需要干预调度过程，以便在 pod 和一个节点或两个特定的 pod 之间实现匹配。Kubernetes 提供了一个强大的机制来控制 pod 放置逻辑。

让我们探索一下 Kubernetes 中影响默认调度决策的关键技术。

## 节点关联性/反关联性

从一开始，Kubernetes 就依赖于使用标签和选择器来对资源进行分组。例如，服务使用选择器来过滤带有特定标签的包，这些包将有选择地接收流量。标签和选择器使用简单的基于等式的条件( *=* 和*！=* )来评估规则。同样的技术通过*节点选择器*特性扩展到节点，该特性将强制一个 pod 在特定节点上进行调度。

最终，标签和选择器开始支持基于集合的查询，这带来了基于 *in、notin、*和 *exists* 操作符的高级过滤技术。与基于平等的需求相结合，基于集合的需求提供了复杂的技术来过滤 Kubernetes 中的资源。

节点关联性/反关联性使用标签和注释的表达性基于集合的过滤技术来定义 pod 在特定节点上的放置逻辑。注释提供了没有向选择器公开的附加元数据，这意味着用于注释的键不能包含在查询和过滤资源中。但是节点关联使得在表达式中使用注释成为可能。反相似性确保 pod 不会被调度到与规则匹配的节点。

除了在查询中使用复杂逻辑的能力之外，节点亲合性/反亲合性可以对放置逻辑施加硬性和软性规则。一个硬规则强制执行一个严格的策略，该策略可以阻止将 pod 放置在不符合标准的节点上。软规则将首先检查是否有任何节点匹配指定的条件，如果不匹配，它将使用默认的调度模式来放置 pod。表达式*required duringschedulingignoredduringeexecution*和*preferred duringeexecution*分别执行硬规则和软规则。

下面是将节点关联/反关联与硬规则和软规则结合使用的示例。

```
affinity:
  nodeAffinity:
    preferredDuringSchedulingIgnoredDuringExecution:
      nodeSelectorTerms:
        -  matchExpressions:
          -  key:  "failure-domain.beta.kubernetes.io/zone"
            operator:  In
            values:  ["asia-south1-a"]

```

上述规则将指示 Kubernetes 调度程序尝试将 pod 放置在运行于 GKE 集群的“asia-south1-a”区域中的节点上。如果没有可用的节点，调度程序可以自由应用标准放置逻辑。

```
affinity:
  nodeAffinity:
    requiredDuringSchedulingIgnoredDuringExecution:
      nodeSelectorTerms:
        -  matchExpressions:
          -  key:  "failure-domain.beta.kubernetes.io/zone"
            operator:  NotIn
            values:  ["asia-south1-a"]

```

上面的规则通过使用 NotIn 操作符来施加反相似性。这是一个硬性规定，确保没有任何 pod 被放置在运行在亚洲-南亚 1a 区域中的 GKE 节点中。

### Pod 亲和力/反亲和力

虽然节点关联性/反关联性解决了 pod 和节点之间的匹配，但有些情况下我们需要确保 pod 位于同一位置，或者没有两个 pod 在同一个节点上运行。Pod 亲和/反亲和有助于我们应用实施粒度放置逻辑的规则。

类似于节点亲和/反亲和中的表达式，pod 亲和/反亲和可以通过*requiredduringschedulinggingnoredduringeexecution*和*preferred during schedulingignoredduringeexecution*来施加硬性和软性规则。还可以将节点关联与 pod 关联混合和匹配，以定义复杂的放置逻辑。

为了更好地理解这个概念，假设我们有一个 web 和缓存部署，每个部署有 3 个副本运行在一个三节点集群中。为了确保 web 和 cache pods 之间的低延迟，我们希望在同一个节点上运行它们。同时，我们希望避免在同一节点上运行多个缓存单元。这将加强运行 web pods 的策略，每个节点只有一个缓存 pod。

我们首先使用反关联性规则部署缓存，该规则防止在一个节点上运行多个 pod。

```
      affinity:
        podAntiAffinity:
          requiredDuringSchedulingIgnoredDuringExecution:
          -  labelSelector:
              matchExpressions:
              -  key:  app
                operator:  In
                values:
                -  redis
            topologyKey:  "kubernetes.io/hostname"

```

*topologyKey*使用附加到节点的默认标签来动态过滤节点名称。注意我们如何使用 *podAntiAffinity* 表达式和操作符中的*来应用规则。*

假设在集群的不同节点上安排了 3 个缓存单元，我们现在希望部署 web 单元，这些单元放置在具有缓存单元的相同节点上。我们将使用 *podAffinity* 来执行这个逻辑。

```
        podAffinity:
          requiredDuringSchedulingIgnoredDuringExecution:
          -  labelSelector:
              matchExpressions:
              -  key:  app
                operator:  In
                values:
                -  redis
            topologyKey:  "kubernetes.io/hostname"

```

上面的子句指示 Kubernetes scheduler 找到具有缓存 pod 的节点并部署 web pod。

除了节点和 pod 关联/反关联，我们还可以使用污点和容差来定义自定义放置逻辑。我们还可以编写自定义调度程序，从默认调度程序中接管调度逻辑。我们将在本系列的后续文章中探讨它们。

在本系列的下一部分中，我将向您介绍在生产场景中使用节点和 pod 关联的端到端教程。敬请期待！

*贾纳基拉姆·MSV 的网络研讨会系列“机器智能和现代基础设施(MI2)”提供了涵盖前沿技术的信息丰富、见解深刻的会议。在 [http://mi2.live](http://mi2.live) 注册参加即将举行的 MI2 网络研讨会。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>