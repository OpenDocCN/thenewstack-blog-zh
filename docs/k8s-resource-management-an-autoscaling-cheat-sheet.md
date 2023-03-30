# K8s 资源管理:自动缩放备忘单

> 原文：<https://thenewstack.io/k8s-resource-management-an-autoscaling-cheat-sheet/>

几乎每个运行 Kubernetes 基础设施的人都试图只使用他们需要的资源——不多也不少。因此，正在使用的资源必须能够在任一方向上扩展，以满足所需的需求。

幸运的是，Kubernetes 使我们能够自动执行开箱即用的扩展流程，从而避免了我们在每次需要时手动进行扩展和配置。它节省了时间和人力，也降低了成本。然而，配置这些自动缩放功能的众多控件可能会让人不知所措，即使对于经验丰富的专家来说也是如此。

这个备忘单旨在逐个资源地揭开 [Kubernetes 自动伸缩](https://thenewstack.io/reduce-kubernetes-costs-using-autoscaling-mechanisms/)的神秘面纱。让我们通过几个练习来探索可以自动缩放和工作的资源类型。

## 支持自动缩放的 Kubernetes 资源类型

在 Kubernetes 生态系统中，资源是我们创造的东西。以下所有资源都可以自动缩放:

*   Pod —部署的 Kubernetes 工作负载的最小单位
*   节点—一组单元
*   复制集—运行 pod 的多个实例以保持其数量稳定的过程
*   部署—管理副本集并以声明方式管理 pod 实例。所有复制副本实例共享单个卷和 PersisentVolumeClaim (PVC)。
*   StatefulSet —用于有状态应用程序(当部署用于无状态应用程序时)。StatefulSet 确保每个 pod 都有自己的卷和 PVC。
*   RAM 和 CPU 内核 Kubernetes 集群的内存和计算资源

值得注意的是，像 [DaemonSets](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/) 这样的一些资源是无法扩展的。通读这篇 StormForge [文章](https://www.stormforge.io/blog/understanding-kubernetes-resource-types/)，深入了解 Kubernetes 资源类型。

## 请求和限制

Kubernetes 允许我们指定对资源[请求和限制](https://www.stormforge.io/blog/kubernetes-requests-limits-demystified/)的控制和检查。

*   请求—指定必须为 pod 容器保留的资源。
*   限制—指定容器可以使用的最大允许资源数量。

在理想的 [Kubernetes 环境](https://thenewstack.io/how-to-make-the-most-of-kubernetes-environment-variables/)中，我们必须指定 CPU、内存和内存请求。否则，Kubernetes 会自动设置慷慨的默认请求，这会抬高成本。

## Pod 服务质量

Kubernetes 还使我们能够按照我们首选的优先级顺序为 pod 的服务质量(QoS)分配一个等级:

*   **有保证的 QoS 等级** —最高优先级的 pod。最高优先级的运输舱或运输舱中的所有集装箱可以被分配有保证的 QoS。

```
```
status:
qosClass:  Guaranteed
```

```

*   **尽力而为 QoS 等级** —最低优先级的 pod。优先级低的单元可以使用尽力服务质量。尽力而为单元中的容器没有 CPU 请求或内存限制。

```
```
status:
qosClass:  BestEffort
```

```

*   **突发 QoS 类别** —介于高优先级和低优先级之间的中等优先级 pod 可以使用突发 QoS 类别。pod 中的一个容器必须有 CPU 或内存限制或请求。

```
```
status:
qosClass:  Burstable
```

```

## 缩放对象和定义

*   自定义资源定义(CRD) —支持将唯一对象引入集群
*   HorizontalPodAutoscaler (HPA) —一个 CRD 对象，用于根据 CPU 利用率等指标增加 pod 的副本数量
*   VerticalPodAutoscaler(VPA)-用于设置容器中容器的请求和限制的 CRD 对象
*   水平扩展—增加单元数量以应对工作负载的增加。HPA 对此进行管理。
*   垂直扩展—向当前可用的单元添加更多内存或 CPU 容量，而不是添加更多单元

## 资源自动缩放的先决条件

1.  创建您的 [Kubernetes](https://kubernetes.io/docs/tutorials/kubernetes-basics/create-cluster/) 集群。
2.  可选但推荐:配置基于角色的访问控制( [RBAC](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) )。
3.  在您的工作站中安装 [kubectl](https://kubernetes.io/docs/tasks/tools/) 命令行工具，并连接到集群。
4.  确保您有一个为您的集群运行的[部署](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#creating-a-deployment)。本指南使用名为 python-hpa 的部署。
5.  可选:要基于自定义指标进行扩展，请将您的[指标服务器](https://docs.aws.amazon.com/eks/latest/userguide/metrics-server.html)部署到您的集群。

### 水平缩放

**1。创建 HPA。**

使用 kubectl autoscale 子命令。

```
bash
kubectl autoscale deployment python-hpa  --cpu-percent=50  --min=1  --max=10

```

ku bectl auto scale 命令为名为 python-hpa 的部署创建 HPA。

*   cpu-percent=50 将所有窗格的 cpu 使用率阈值设置为 50%。HPA 将增加或减少吊舱的数量以满足阈值。
*   min=1 和–max = 10 意味着副本的数量将保持在 1 到 10 之间。在本演示中，副本将由`python-hpa`部署控制。在运行`kubectl autoscale`子命令之前，替换您必须创建的任何其他部署。

**2。稳定窗口**

通常需要几分钟时间来稳定添加或删除的副本数量。将所有这些自动缩放在一起不是一蹴而就的。需要几分钟。

**3。特定指标的自动缩放**

您可以在创建的 HPA 的 YAML 中陈述特定的受监控指标。这支持基于您的监控或可观察性平台定义的指标进行扩展。

使用 autoscaling/v2 版本，通过以下命令获得 HPA 的 YAML:

```
```bash
kubectl get hpa php-apache  -o  yaml  >  /tmp/hpa-v2.yaml
```

```

然后，您可以添加以下格式的自定义指标:

```
```yaml
type:  Object
object:
  metric:
 name:  metric_name 
```

```

Prometheus 适配器的一个例子可能是这样的:

```
```yaml
spec:
  ...
  metrics:
  -  type:  Pods
 pods:
    metricName:  node_network_receive_bytes
    targetAverageValue:  100000m
```

```

**4。状态条件**

您应该检查您的自动缩放器是否可以缩放，或者是否有可能阻止它缩放的限制。您可以使用`kubectl describe hpa`子命令找到这些信息:

`kubectl describe hpa python-hpa`

这些条件位于命令行界面(CLI)输出的 status.conditions 字段中。

### 垂直缩放

**1。VPA 组件**

*   准入插件—为新单元设置正确的资源请求
*   推荐者—比较过去和现在的资源消耗率，以预测和推荐内存和 CPU 请求值
*   更新程序—检查哪些单元具有正确的资源，然后删除那些具有不正确资源的单元，以便更新的请求可以重新创建它们

**2。VPA 操作模式**

VPA 以以下四种模式运行:

*   重新创建—VPA 在创建 pod 时分配资源请求，并通过驱逐和重新创建来更新它们。当资源与建议大相径庭时，就会发生更新。
*   自动—根据建议重新创建窗格
*   关闭-VPA 仅提供建议，不自动更新请求。
*   initial-VPA 在创建 pod 时创建请求，但不会在以后更新它们。

**3。极限控制**

资源政策决定了 VPA 设定的限制。基本上，它在 YAML 定义的规格极限部分的[极限范围](https://kubernetes.io/docs/concepts/policy/limit-range/)的最小(min)和最大(max)值之间维持其建议值。

**4。设置 VPA 的命令及其参数**

对于本部分，您需要以下内容:

*   在您的工作站上安装和配置 Git
*   部署到集群的首选度量服务器
*   使用以下命令拆除 VPA 的早期版本(如果存在):

```
```bash
./hack/vpa-down.sh
```

```

**安装垂直吊舱自动定标器(VPA):**

下载 VPA 源代码:

```
```bash
git clone https://github.com/kubernetes/autoscaler.git
```

```

**设置 VPA:**

```
```bash
./hack/vpa-up.sh
```

```

**如果要停止运行 VPA，请将其拆除:**

```
```bash
./hack/vpa-down.sh
```

```

请注意，除非基于自定义指标进行扩展，否则 VPA 不应与 HPA 一起使用。有关如何使用 VPA 的更多信息，请参见[官方指南](https://github.com/kubernetes/autoscaler/tree/master/vertical-pod-autoscaler#prerequisites)。

**5。基于 Kubernetes 的事件驱动自动缩放器(KEDA)**

KEDA 是一个轻量级的工具，它可以帮助你通过要处理的事件数量来管理你的自动缩放。您可以将它添加到您的群集中，以扩展标准 HPA 和其他组件的功能。

*   KEDA 控制着 Kubernetes 的部署，以便将规模扩大到零事件。
*   KEDA 也是 Kubernetes 的度量服务器。

安装 KEDA 为您提供了以下四种自定义资源:

*   ScaledObject —描述事件源(如 RabbitMQ)和您的部署之间所需的映射
*   ScaledJob —描述事件源和您的 Kubernetes 作业之间的映射
*   TriggerAuthentications —包含用于监视 ScaledObject 的事件源的身份验证配置
*   ClusterTriggerAuthentications 包含用于监视 ScaledJob 的事件源的身份验证配置

**6。KEDA 事件**

KEDA 发出事件，例如 ScaledObject 第一次就绪时的 ScaledObjectReady 和 ScaledJob 删除时的 ScaledJobDeleted。查看 [KEDA 事件](https://keda.sh/docs/2.8/operate/events/)网页，查看 KEDA 发布的事件的详细列表。

## 结论

这个备忘单为在 Kubernetes 环境中使用和管理水平和垂直自动缩放提供了一个简明而全面的指南。有了这些信息，您就可以放心地在 Kubernetes 工作负载中实现自动伸缩了。

[StormForge](https://stormforge.io) 通过使用[机器学习](https://thenewstack.io/category/machine-learning/)来自动化管理和优化您的 Kubernetes 资源，包括充当 VPA 和调整您的 HPA 设置以提高效率，从而帮助您节省资金、时间和精力。与使用 HPA 或 VPA 单机版相比，使用 StormForge 这样的解决方案可以提高效率，并且它允许垂直和水平自动扩展协同工作而不会出现抖动。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>