# 介绍 clone set:CRD 生产级 Kubernetes 部署

> 原文：<https://thenewstack.io/introducing-cloneset-production-grade-kubernetes-deployment-crd/>

许多人将 Kubernetes 称为新的 Linux，因为它是云计算的操作系统。从另一个角度来看，它们也非常相似:Kubernetes 就像 Linux 一样是分层的，并且允许在其上构建不同的库和实用程序。有时这些程序有重叠的功能。有时他们有依赖性。在 Kubernetes (K8s)中，这被称为自定义资源定义(CRDs)。

在本文中，我将介绍一个用于工作负载管理的开源 CRD CloneSet。

## 克鲁斯项目

 [石安迪

石安迪是阿里云的开发者拥护者。他致力于开源云本地平台技术。他热衷于让 DevOps 的任务更简单，平台更强大。](https://www.linkedin.com/in/shiandy/) 

克隆体 CRD 属于 CRDs 家族:Kruise。这是阿里巴巴开源努力的一部分。

阿里巴巴集团很早就在生产中采用了 K8s。它有一个世界上最大的集群正在运行。在 K8s 的迁移和运行过程中，上游 K8s 出现了许多问题。例如，部署不支持金丝雀滚动更新。Statefulset 通过使用分区更新做到了这一点。但是既然是 StatefulSet，就要一个一个的更新 pod。假设您有数百个 pod，更新它们需要多长时间？实际上，上游工作负载中可用的部署策略是有限的，并且在不同的工作负载中实现。这是可以理解的，因为 K8s 是一个框架，不能简单地满足所有用例。

另一个例子是部署给 pod 随机命名。但是这会在服务重启后产生监控问题。StatefulSets 确实执行严格的命名顺序。然而，它以串行形式一个接一个地启动/更新 pod，没有足够的灵活性。

于是，阿里云创建了开源项目 Kruise。在它下面有几个已经在实际生产环境中得到验证的 CRD。他们现在与每个人分享。而克隆集是具有代表性的工作负载 CRD，具有不少独特的特点。

## 什么是克隆集？

首先，我们来谈谈命名约定。

在 Kubernetes 中，有关于控制器/CRD 的命名约定。后缀“set”表明 CRD 直接在吊舱上工作，就像“StatefulSet”以同样的方式，CloneSet 在单个 pod 上工作。但是 StatefulSet 侧重于“有状态”工作负载，而 CloneSet 侧重于“无状态”工作负载。

就功能而言，CloneSet 是无状态 pod 的工作负载。它现在支持所有的上游 Kubernetes 部署策略。是的，这里支持所有其他上游工作负载中的所有部署策略。

下面是比较表:

除了部署策略，克隆集还提供了广泛的其他功能。让我们来看看其中的几个。

## 特征

### 就地更新

就地更新意味着更新时不会重新创建 pod。只有容器图像被更新。Pod 对象本身、IP、PVC 等。，都保持不变。因为 Kubernetes 工作在 Pod 而不是容器的粒度上。从 Kubernetes 的角度来看，豆荚是完整的。

如果一个 pod 中有多个容器，这是一个很酷的特性。尤其是当您想要更新的容器不是主容器时。例如，每次当您更新 Istio 时，主容器将随 sidecar 一起更新。你希望这样吗？

### 最大浪涌

maxSurge 是最新 0.5 版本中提供的新功能。用例是当您想要滚动更新您的 pod，同时保持副本数量稳定时。就像内存中的值交换，我们总是需要一个缓冲区。maxSurge 定义了换出旧 pod 和换入新 pod 时的缓冲区大小。例如，如果您的副本是 5 个，maxSurge 是 20%，那么您有一个 pod 作为缓冲区。

部署的 maxSurge 滚动更新策略仅适用于 maxUnavailable。

对于 CloneSet，maxSurge 策略可以与 Partition 和 maxUnavailable 结合在一起，甚至可以就地更新。这比部署更有力量。

### 选择性荚果缺失

当缩小发生时，用户可以指定首先移除哪个 pod。是的，和 *kubectl delete pod* 不一样。当按比例缩小时，Deployment 和 StatefulSet 都有自己的序列，用户无法控制。有了 CloneSet，您可以在其余部分开始工作之前，先选择要删除的部分。这里有一个例子:

```
apiVersion:  apps.kruise.io/v1alpha1

kind:  CloneSet

spec:

   # ...

   replicas:  4

   scaleStrategy:

      podsToDelete:

      -  sample-9m4hp

```

按比例缩小时，pod 样本-9m4hp 将首先被删除。此功能的使用情形是，当出于资源调度目的而缩减规模时，您希望耗尽一个或多个节点。它给了你压倒一切的力量。

## 每箱 PVC

克隆集提供每荚聚氯乙烯索赔。在 StatefulSet 中，每个 pod 都有一个与其名称匹配的卷。但是当然，你必须忍受这种状态。在部署中，所有单元将获得一个与其单元名称无关的随机卷名称。如果 pod 已更新，您将再也找不到该宗卷。每个 pod PVC 赋予每个 pod 存储有状态信息的能力，而无需声明自己是有状态集。

CloneSet 还有许多其他可用的特性。有关可用特性的详细列表，请查看 CRD 的 git repo。如果您有希望被添加的用例，请提交问题。这里有一个教程。

## 摘要

如上所述，Kruise 的需求来自真实世界的用例。只要你在生产中使用 K8s，我敢打赌你有上面提到的一些问题。所以试试吧！我们想听听你的故事。这里是项目 Kruise 的[链接。](https://github.com/openkruise/kruise)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>