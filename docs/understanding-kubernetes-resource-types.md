# 了解 Kubernetes 资源类型

> 原文：<https://thenewstack.io/understanding-kubernetes-resource-types/>

*注意:这是包含 Kubernetes 资源管理和优化的五部分系列的第一部分。我们从描述 Kubernetes 资源类型开始。*

 [欧文·达里娅

欧文是 StormForge 的首席销售工程师。在担任构建和领导基础架构团队的角色后，Erwin 已经过渡到供应商方面，在 Tintri 和 Juniper Networks 等公司的销售、营销和产品角色中服务并取得成功。](https://www.linkedin.com/in/erwindaria/) 

在我们深入 Kubernetes 资源之前，让我们澄清一下术语“资源”在这里指的是什么。我们在 Kubernetes 集群中创建的任何东西都被认为是一种资源:部署、pod、服务等等。对于本教程，我们将重点关注 CPU 和内存等主要资源，以及其他资源类型，如短暂存储和扩展资源。

集群管理的一个方面是将这些资源自动分配给在 pods 中运行的容器，这样，在理想情况下，每个容器都有它需要的资源，但不会更多。

在本文中，我们将强调运行在集群上的容器的逻辑资源。我们将分解开发人员日常使用的四种常见 Kubernetes 资源:CPU、内存、短暂存储和扩展资源。对于每种资源，我们将探索如何在 Kubernetes 中对其进行测量，回顾如何监控每种特定的资源，并强调一些优化资源使用的最佳实践。

让我们深入探讨一下每一种主要的 Kubernetes 资源类型。然后，让我们通过一些代码示例来看看这些资源类型的运行情况。

## 中央处理器

Kubernetes 集群通常运行在多台机器上，每台机器都有多个 CPU 内核。它们加起来就是可用核心的总数，比如四台机器乘以四个核心，总共是 16 个。

我们不需要使用整数个内核。我们可以以 1/1000 的增量指定 CPU 内核的任何部分(例如，半个内核或 500 个 CPU)。

Kubernetes 容器运行在 Linux 内核上，它允许指定 cgroups 来限制资源。Linux 调度程序将使用的 CPU 时间(由内部时间片定义)与定义的限制进行比较，以决定是否在下一个时间片运行容器。我们可以用 kubectl top 命令查询 CPU 资源，为一个 pod 或节点调用它。

我们可以通过改进算法和编码，或者通过编译器优化，使运行在容器中的程序更加高效，从而优化处理器时间的使用。集群用户对预编译容器的速度或效率没有太大影响。

## 记忆

Kubernetes 集群中的每台机器都有内存，这也是集群的总内存。例如，4 台机器乘以 32 [GiB](https://www.redhat.com/sysadmin/bits-vs-bytes) 就是 128 GiB。

内核级控制主内存，类似于 cgroups 的 CPU 时间。如果容器中的某个例程请求的内存分配超过了硬限制，它会发出内存不足的错误信号。

优化资源使用在很大程度上取决于应用程序的开发工作。一个步骤是提高垃圾收集频率，防止基于堆的映像分配超过硬限制的内存。同样，kubectl top 命令可以提供关于内存使用的信息。

## 探索 CPU 和内存

作为我们的第一个深入示例，让我们将流行的 web 服务器 NGINX 的三个复制容器部署到本地 Kubernetes 安装中。我们在笔记本电脑上运行一个单节点“集群”,它只有两个内核和 2gb 内存。

下面的代码定义了这样一个 pod 部署，并为三个 NGINX 容器中的每一个提供了十分之一的内核(100 毫 CPU)和 100 MiB 的主内存。下面的代码也将它们的使用限制为请求值的两倍。

```
apiVersion:  apps/v1
kind:  Deployment
metadata:
  name:  nginx-deployment
  labels:
    app:  nginx
spec:
  replicas:  3
  selector:
    matchLabels:
    app:  nginx
  template:
    metadata:
      labels:
        app:  nginx
spec:
  containers:
    -  name:  nginx
    image:  nginx
    resources:
      requests:
        cpu:  "100m"
        memory:  "100Mi"
      limits:
        cpu:  "200m"
        memory:  "200Mi"
    ports:
    -  containerPort:  80

```

我们可以像这样部署到默认名称空间:

```
kubectl apply  -f  nginx.yaml

```

本地集群只有一个节点。使用此命令返回关于它的详细信息:

```
kubectl describe nodes docker-desktop

```

在裁剪了大部分输出之后，我们可以检查一些关于资源使用的信息:

```
[...]

Namespace Name CPU.  Requests  CPU Limits Memory Requests Memory  Limits  Age

---------  ----  ------------  ----------  ---------------  -------------  ---

default nginx-deployment-585bd9cc5f-djql8  100m  (5%) 200m  (10%)  100Mi  (5%) 200Mi (10%) 66s

default nginx-deployment-585bd9cc5f-gz98r  100m  (5%) 200m  (10%)  100Mi  (5%) 200Mi (10%) 66s

default nginx-deployment-585bd9cc5f-vmdnc  100m  (5%) 200m  (10%)  100Mi  (5%) 200Mi (10%) 66s

[...]

Resource            Requests    Limits

--------  --------  ------

cpu  1150m (57%)  600m  (30%)

memory  540Mi        (28%)  940Mi  (49%)

ephemeral-storage  0  (0%)    0 (0%)

hugepages-1Gi  0 (0%)    0 (0%)

hugepages-2Mi  0 (0%)    0 (0%)

[...]

```

该信息显示了 CPU 和内存使用请求和限制，正如我们的部署对象所指定的那样。它还将这些值显示为最大可能分配量的百分比。

接下来是该节点的当前总数，同样以绝对值和百分比的形式列出。这些数字包括在 kube-system 名称空间中运行的一些其他容器，我们没有在这里显示，所以会有上面的输出没有涵盖的差异。

上面代码片段的最后三行表示 CPU 和内存之外的其他类型的资源，在本例中没有设置请求或限制。

## 短暂储存

Kubernetes 的另一种资源类型是临时存储。这是无法在 pod 生命周期中存活的挂载存储。Kubernetes 经常使用临时存储来缓存或记录日志，但从不使用它来存储重要数据，如用户记录。我们可以请求或限制像主内存这样的短暂存储，但它通常不是一种有限的资源。

那么上面代码片段中的 hugepages-1Gi 和 hugepages-2Mi 是什么意思呢？大页面是 Linux 内核的一个现代内存特性，它可以为进程分配可配置大小的大内存页面。我们这样做是为了提高效率。

Kubernetes 支持将如此大的页面分配给容器。这些构成了我们可以单独请求的每个页面大小的资源类型。

当指定请求或限制时，我们设置内存总量，而不是页面数量。

```
limits:
hugepages-2Mi:  "100Mi"
hugepages-1Gi:  "2Gi"Here,  we limit the number of  2  MiB pages to  50  and the number of  1  GiB pages to  2.

```

## 扩展资源

群集用户还可以使用扩展资源类型定义他们自己的资源类型(每个群集或节点)。一旦我们定义了类型并指定了可用单元，我们就可以使用请求和限制，就像我们到目前为止使用的内置资源一样。

一个例子是:

```
limits:
cpu:  "200m"
myproject.com/handles:  100

```

这个设置将容器限制为一个核心的 20%和我们项目的 100 个句柄。

## 资源请求和限制

请注意，资源请求和限制是我们讨论短暂存储和扩展资源的关键。这是因为最终用户可以在应用程序的部署清单中指定资源请求和限制，这就强加了一些关于 Kubernetes 应该如何处理容器或 pod 的规则。

请求表明一个容器应该拥有多少资源。它们帮助调度程序根据请求的资源量和节点上的可用资源将 pod 分配给节点。

限制用于指示容器可以使用多少资源的硬性上限，在操作系统级别强制实施。请求和限制是可选的，但是如果我们不指定限制，容器可以使用节点的大部分资源，这可能会产生负面的成本或性能影响。所以，一定要谨慎。

请记住，虽然一个 pod 可以包含多个容器，但通常每个 pod 只有一个容器。我们将资源分配给容器，但是 pod 的所有容器都从节点级别的公共资源池中提取。

在本系列教程的第二部分中，我们将深入 Kubernetes 请求和限制的世界。

## 考虑服务质量

到目前为止，我们描述的资源系统是管理计算资源的一种相当简单的方式。Kubernetes 在此基础上提供了一个简单的服务质量(QoS)系统。

QoS 描述了在给定硬件限制的情况下，技术系统在保持最佳整体质量的同时提供不同服务级别的方法。Kubernetes QoS 系统为一个 pod 分配三个级别中的一个:有保证、可突发和尽最大努力。参考 [Kubernetes 文档](https://kubernetes.io/docs/tasks/configure-pod-container/quality-service-pod/)了解如何分配这些级别以及它们如何影响 pod 调度。

保证级别在 pod 的生命周期内准确地提供所请求的有限资源，适合在恒定负载下运行的监控系统等应用。

可突发服务级别适用于具有基本使用配置文件的 pod，这些配置文件有时会因需求增加而超过基线。这个级别非常适合数据库或 web 服务器，它们的负载取决于传入请求的数量。

最后，BestEffort 不保证资源可用性。因此，它最适合需要时可以重复的批处理作业等应用程序，或者非关键任务的暂存环境。

## 结论

Kubernetes 集群维护硬件资源，如 CPU 时间、内存、临时存储和扩展资源，并将它们分配给正在运行的容器。通过一个请求和限制系统，操作人员可以根据单个容器调整资源分配，然后让 Kubernetes 系统将它们适当地分配给节点。

扩展资源使我们能够定义自己的资源类型，并以类似的方式使用它们。Kubernetes 还根据请求和限制为 pod 指定服务质量。然后，它使用这些指定来做出调度和终止决定。

Kubernetes 资源优化对于平衡成本和最终用户体验至关重要。然而，使用本文的方法手动分配参数可能非常耗时、昂贵并且难以扩展。

我们宁愿把时间花在创造令人兴奋的新功能上，这些新功能可以推动竞争优势或改善用户体验，而不是担心优化和资源使用。StormForge 平台使用机器学习来自动管理和优化您的 Kubernetes 资源，根据我们的成本和性能目标找到最佳配置。

[要了解更多关于 StormForge 如何工作的](https://www.stormforge.io/how-stormforge-works/)，[看看这个演示。](https://www.stormforge.io/request-a-demo/)

*敬请关注未来的文章，我们将解释资源请求和限制，如何设定优化目标，以及如何应对一些最困难的优化挑战。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>