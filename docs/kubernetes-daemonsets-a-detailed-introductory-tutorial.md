# Kubernetes DaemonSets:详细的入门教程

> 原文：<https://thenewstack.io/kubernetes-daemonsets-a-detailed-introductory-tutorial/>

Kubernetes 是最流行的容器编排系统之一。它受欢迎的原因之一是，在管理容器时，它卸载了许多维护任务。例如，Kubernetes 在规划部署微服务的位置时节省了时间。当确保所有单元在所有可用节点之间平均分布时，它还可以节省您的时间。

但是和所有事情一样，没有一个解决方案适合所有用例。因此，Kubernetes 有几种不同类型的部署策略。在这篇文章中，你将了解什么是 DaemonSets，它们带来了什么好处，以及何时使用它们。

## **什么是 Kubernetes 部署？**

 [达维德·齐奥尔科夫斯基

Dawid 有 10 年的经验，最初是网络/系统工程师，中间是 DevOps，最近是云原生工程师。他曾在一家 IT 外包公司、一家研究机构、电信公司、一家托管公司和一家咨询公司工作过，因此他从不同的角度收集了很多知识。如今，他正在帮助公司迁移到云计算和/或重新设计他们的基础设施，以实现更加云本地化的方法。](https://twitter.com/DavidZisky) 

在我们深入 DaemonSets 之前，让我们确保理解 Kubernetes 工作流的一般概念。 [Kubernetes](https://en.wikipedia.org/wiki/Kubernetes) 是一个相当复杂的系统，有很多组件和选项。

网络、存储、扩展等有多种选择。但是 Kubernetes 的核心功能是运行容器。因此，如果您想要指示 Kubernetes 运行一个容器(作为一个 [pod](https://kubernetes.io/docs/concepts/workloads/pods/) ，您需要创建一个工作流。

和 Kubernetes 上的其他东西一样，工作流有几个配置选项。最常见的工作流类型是部署。

创建一个部署意味着指示 Kubernetes，“请从这个 Docker 映像运行一个容器。”当然，这是一个非常简化的解释，但是你已经明白了。

要创建一个部署类型的工作流，您需要在您典型的 Kubernetes YAML 定义中包含它:

```
apiVersion:  apps/v1

kind:  Deployment

metadata:

(...)

spec:

(...)

```

### **行动部署**

那么，当您创建部署时会发生什么呢？Kubernetes 将首先找到合适的节点来运行您的 pod。“合适”的主要标准之一是节点上的负载。默认情况下，Kubernetes 会尝试将负载分布到所有节点上。例如，假设您有五个节点，其中四个节点上有 10 个 pod 在运行，而最后一个节点上只有八个。Kubernetes 很有可能会在最后一个节点上安排任何新的部署。此外，当其中一个节点由于某种原因变得不可用时，Kubernetes 会尝试将在该节点上运行的所有 pod 重新调度到剩余的节点，并且再次尝试将这些 pod 分发到所有节点。

所有这些关于在哪里安排集装箱的决策都是在幕后进行的，您不需要担心您的 pod 将被安排在哪里。这是 Kubernetes 的主要特点之一。每当集群饱和时，您只需添加新节点，Kubernetes 会为您完成所有管理工作。

### **不同类型的工作流程**

以上都只是 Kubernetes 的默认行为。当然，有时你实际上可能想要对计划过程有更多的控制。您可能希望在特定节点上安排一些微服务，这通常用于多个节点池。比如你可能想增加几个带高性能显卡的节点，在这些节点上专门调度一些 AI 处理微服务的大数据。这只是一个例子。除了默认的“在任何地方安排我的 pods”之外，您可能还需要更多来自 Kubernetes 的不同行为一个这样的用例是需要在每个节点上安排一个 pod 的副本。现在让我向你介绍达蒙塞特。

## **输入 DaemonSet**

那么，为什么要在每个节点上调度相同的容器呢？有很多可能的原因。最常见的是需要调度一个“守护程序”类型的应用程序，该应用程序需要在每个节点上执行一些操作。常见的例子是日志或指标收集守护进程。也可以不在所有节点上而是在它们的子集上安排一个 pod 的副本。这对于安排守护程序类型的 pod 非常有用，例如，仅在特定的节点池上。

例如，如果您想从每个节点获取指标(如 CPU 或 RAM 使用情况)，最好的选择是在每个节点上安排一个容器，从每个单独的节点收集这些指标。为什么不简单地调度一个容器来收集所有节点的指标呢？嗯，您可能会冒这样的风险:运行服务的节点由于某种原因而死亡，并且您会丢失整个集群的指标。当然，Kubernetes 会在另一个节点上重新部署该服务。但是根据集群的繁忙程度，这可能需要一段时间，因此，您可能会丢失一些数据。在度量的情况下，也许这没什么大不了的，但是想象一下在一瞬间丢失所有容器的日志。

但是除了这些常见的用例之外，对于任何特定于应用程序的用例，例如节点本地应用程序缓存，您可能只想在每个节点上都有一个相同容器的副本。

## **详细 DaemonSets**

既然我们已经理解了 DaemonSets 的必要性，那么让我们更详细地讨论它。我们已经知道 DaemonSet 的要点是确保所有节点都运行 pod 的副本。因此，与典型的 Kubernetes 部署不同，您不需要指定想要运行多少个 pods。Kubernetes 将自动运行您拥有的节点数。与正常部署的另一个不同之处是，如果从集群中删除一个节点，Kubernetes 不会将属于 DaemonSet 的 pod 移动到另一个节点，而是简单地销毁它。

那么如何用 DaemonSet 创建工作流呢？非常类似于正常部署。事实上，与任何其他 Kubernetes 定义一样，您需要准备一个带有`apiVersion`、`kind` 和`metadata` 字段的 YAML 定义。然而，在这种情况下，`kind` 值将是`DaemonSet`，而不是`Deployment`。因此，达蒙塞特 YAML 定义的一个例子可能是这样的:

```
apiVersion:  apps/v1
kind:  DaemonSet
metadata:
  name:  fluentd-daemon
spec:
  selector:
 matchLabels:
  name:  fluentd-daemon
  template:
 metadata:
  labels:
 name:  fluentd-daemon
 spec:
  containers:
 -  image:  fluent/fluentd
 name:  fluentd-daemon

```

根据 DaemonSet 的思想，上面的定义将在集群中的每个节点上部署一个`fluentd` pod。Kubernetes 将确保每个节点上只有一个 pod。例如，如果您有五个节点，您将有五个`fluentd`pod 在运行。如果其中一个节点变得不可用，您将有四个`fluentd`pod 在运行。

## **总结**

Kubernetes DaemonSets 一开始可能有点难以理解，因为它们似乎违背了开发 Kubernetes 的目的。但是就像任何其他事情一样，在一些用例中，看似奇怪的东西实际上是有用的。在 Kubernetes DaemonSets 的例子中，它们通常用于日志或监控。此外，不要忘记 Kubernetes 的主要优势是灵活性以及根据不同的公司和基础设施进行调整的能力。

当然，没有人会强迫你使用 DaemonSets。如果你觉得你不需要它们，不用它们是完全没问题的。但另一方面，当您确实需要类似守护进程的功能时，使用 DaemonSets 比试图用普通的 Kubernetes 部署实现同样的功能要好得多，也容易得多。如果你想了解更多关于 Kubernetes 的信息，请查看[这篇关于 Kubernetes pods 的高级概念的文章](https://releasehub.com/blog/kubernetes-pods-advanced-concepts-explained)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>