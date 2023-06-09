# Kubernetes 探针(以及它们对自动缩放的重要性)

> 原文：<https://thenewstack.io/kubernetes-probes-and-why-they-matter-for-autoscaling/>

验证我们的[工作负载](https://kubernetes.io/docs/concepts/workloads/)——在 Kubernetes 上运行的应用程序——的健康状况对他们的成功至关重要。为了管理工作负载的健康状况，我们依赖遥测信息和诊断，这些信息通常通过系统和应用组件捕获，然后发送到监控工具。一旦传输完毕，系统管理员、开发运维团队和站点可靠性工程师(SREs)将会以指标的形式共享这些数据，以帮助确定我们必须采取的措施。

收集遥测信息的一种方法是使用探头。这个过程是一个诊断检查，通过这个过程，一个健康探测从一个负载平衡器发送到它定义的端点，比如一个 web 服务器场，以验证应用程序是否可用和运行。如果端点没有响应，负载平衡器(在这种情况下)将绕过端点，而不是将用户发送到可能失败的网站。这意味着探头出现故障。

我们可以使用 [Kubernetes 探测器](https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/#container-probes)在 Kubernetes 内部执行这些检查。kubelet 定期在我们的容器上执行探测，kube let 是运行在每个 Kubernetes 节点服务器上的主要节点代理。Kubernetes 探测器允许我们验证集群中运行的 pod 的状态。除了验证我们的[工作负载的健康](https://thenewstack.io/5-best-practices-for-configuring-kubernetes-pods-running-in-production/)和功能，我们还可以使用 Kubernetes 探针来监控和收集影响容器的其他事件的信息，比如自动伸缩。

本文将解释不同类型的探针以及每种探针的重要性。我们将讨论它们如何工作，特别是它们如何支持[自动缩放](https://thenewstack.io/getting-started-with-kubernetes-autoscaling/)。然后，我们将强调为什么找到正确的探头设置是至关重要的，以及为什么实验是优化探头设置的关键。

## 有效使用 Kubernetes 探针

有许多因素有助于 Kubernetes 探针的有效使用，也有许多相关的好处。让我们探讨一下 Kubernetes 探针是什么，强调一下它们的好处，并讨论如何最大限度地利用它们。

## 不同种类的 Kubernetes 探针

在我们探索如何有效地使用 Kubernetes 探针之前，我们必须熟悉三种 Kubernetes 探针:启动、就绪和活动。

在运行时序列中，探测器的使用流程如下:

![](img/8e82e459b1122b0e15a0c483027e3a13.png)

### 启动

**启动探测器**第一个启动，并告诉 kubelet 容器内的应用程序已经成功启动。其他两个探测器将被禁用，直到启动探测器处于成功状态。

启动探测器很有帮助的一个例子是监视启动缓慢的容器。如果活性探测器改为监视这些容器，容器可能会过早终止，因为没有一个应用程序会成功启动。

### 准备就绪

**就绪探测器**通知 Kubernetes 集群容器已经准备好接受请求，比如允许用户连接到 web 应用程序的请求。如果准备就绪探测器处于失败状态，则不会向 pod 发送 IP 地址。因此，pod 从相应的服务中移除。

就绪探测器可以保证在容器中运行的应用程序 100%准备好可以使用。然而，在某些情况下，就绪探测器不能做到这一点。例如，想象一下死锁的情况，其中应用程序进程继续运行，但不再为请求提供服务。就绪探测器不会检测未服务的请求，因为它假设应用程序运行良好。这种情况反映了必须同时使用就绪性和活性探测的情况。

您可能还想知道是否总是需要活跃度和就绪性探测。答案是，这取决于容器化应用程序的性质。由于就绪探测主要用于确认容器准备好接受网络请求，如果我们的应用程序不依赖于网络请求，例如，如果它正在容器内运行一个内部进程，不需要网络交互，我们可以省略它。

### 活性

**活性探测器**确认容器是否正在运行。如果来自探测器的信号指示一个非运行状态，kubelet 就拾取这个信号并终止容器进程。通常这将导致容器重新启动，除非它被不同地配置。

但是，即使活性探测器确认容器正在运行，也不能保证容器的应用程序正在运行。pod 可能已经准备好了，但这并不意味着应用程序可以处理请求。

想象一下，一个 web 应用程序因为无法连接到后端数据库而显示 HTTP 503 错误页面，后端数据库允许它检索信息。从活跃度探测器的角度来看，容器正在运行，因为 web 组件运行起来就像 web 页面是活动的一样。然而，应用程序并未处于成功状态，因为网页无法连接到数据库。

## Kubernetes 探针和自动缩放

如前所述，Kubernetes 探针不仅仅帮助我们了解应用程序的健康状况。它们还支持基于健康指标的精心规划的有效自动伸缩。

当自动添加单元以支持不断扩展的应用程序工作负载时，通常是当对 CPU、内存或其他关键资源的需求增加时，就会实现水平单元自动扩展。此外，每当需求减少时，水平单元自动缩放会自动停止并移除不必要的单元。作为对扩大或缩小计算需求的类似响应，当用更大或更小的资源量重新配置单元时，实现垂直单元自动扩展。

> 启动、活动和就绪探测器的正确使用和配置对于促进自动缩放事件的完成至关重要。

Kubernetes 自动缩放不需要探针。但是，正确使用它们可以通知自动缩放过程，并验证受影响的容器实际上已经启动或关闭。该序列将更快更有效地成功完成自动缩放事件。正确使用和配置启动、活动和就绪探测器对于促进这些自动缩放事件的完成至关重要。为什么？如果探测器设置在合理的时间内没有返回成功的响应，则可能会添加或删除额外的单元以满足自动缩放的需要，而实际上，一旦探测器成功返回并将第一组单元标记为就绪，可能就不再需要这些单元了。

## 定义参数和探头配置

Kubernetes 为启动、就绪和活性探针提供了几个参数，可以通过调整这些参数来微调探针配置。

每个参数都有一个默认值，但是我们环境中的特定情况可能要求我们使用不同的参数值。例如，探测器收集的参数默认值可能无法提供足够具体的信息来理解应用程序启动缓慢的原因。或者，默认值可能捕获并生成太多信息，从而难以得出有用的结论。

我们可以配置下面列出的所有参数，每个参数对所有三种 Kubernetes 探针类型都有效。

### 超时秒数

`timeoutSeconds`表示探头超时的秒数。默认值设置为一秒钟，这意味着容器有一秒钟的时间来响应探测请求。

假设我们的容器或应用程序探测器上的`timeoutSeconds`参数默认设置为 1 秒。在这种情况下，较慢的容器可能没有足够的时间响应，这可能导致容器终止。这个参数的值可能需要增加(可能增加到几秒钟)，因为在我们将一个没有响应的容器标记为“失败”之前，我们可能需要等待比平常更长的时间

### 周期秒

`periodSeconds`反映执行探测检查的频率(以秒为单位)。与`timeoutSeconds`参数一样，精确配置`periodSeconds`参数也很重要。如果探测检查过于频繁，该进程可能会使应用程序的工作负载饱和。然而，如果检查发生得不够频繁，我们可能不知道应用程序正在失败。

### 失败阈值

`failureThreshold`反映失败的请求或响应的数量。默认阈值是三，这意味着当一个容器错过三个连续的探测时，它将被标记为失败，假设`timeoutSeconds`和`periodSeconds`配置了它们的默认值。

### 初始延迟秒

`initialDelaySeconds`反映了容器成功启动后，探测器开始发出信号所需的时间。缺省值为零，这意味着探测器会在成功启动容器后立即发送信号。

对于启动较慢的容器或应用程序，最好将此延迟设置为较高的值。最初，Kubernetes 只提供就绪性和活性探测。虽然这通常工作得很好，但也有因为应用程序尚未准备好而导致探测器产生错误的情况，即使容器运行得很好。这也是引入启动探测器的原因:验证容器是否启动，而不立即检查应用程序本身的健康状况。

### 成功阈值

`successThreshold`反映了确保容器处于成功状态所需的阳性探测信号的数量。缺省值为 1，这意味着必须至少有一个来自探测器的肯定信号，才能将容器状态指定为成功。如果我们不想仅仅依靠来自探头的单个脉冲来确认容器的健康状态，我们可以将该值更改为一个更大的数字。

## 探索实验的价值

考虑到管理和运行 Kubernetes 容器的复杂性，为上述参数确定“绝对正确”的值是一个挑战。我们必须了解我们的应用程序启动的速度以及它在负载下的表现，以决定各种探头设置应该是什么，从而满足[SLA 或 SLOs](https://thenewstack.io/sre-fundamentals-differences-between-sli-vs-slo-vs-sla/) 。必须考虑参数和设置的组合以及它们之间的相互作用，这意味着探头调谐不是一门精确的科学。

> 探针实验使我们能够验证不同的参数设置，并了解它们如何影响 Kubernetes pods 的行为。

这就是实验发挥作用的地方。通常在测试环境中进行，探针实验使我们能够验证不同的参数设置，并了解它们如何影响 Kubernetes pods 的行为。它还帮助我们了解容器、应用程序和集群的整体健康状况。

通过使用探针实验过程跨不同场景运行多个测试，我们可以提高探针参数设置的准确性。

## 在 Kubernetes 中配置探针

探测器及其相应的参数都是通过 Kubernetes YAML 文件配置的，类似于其他 Kubernetes 资源的部署方式。

下面是一个 YAML 文件的例子:

```
  apiVersion:  v1
  kind:  Pod
  metadata:
  labels:
 test:  readiness
 name:  readiness-demo
    spec:
 containers:
      -  name:  probe-app
        image:  registry.k8s.io/alpine
        ports:  
containerPort:  8080
        readinessProbe:
          httpGet::
            path:  /health:
            port:  8080

 initialDelaySeconds:  5
 timeoutSeconds:  1
  livenessProbe:
 httpGet:exec:
            path:  /health
            port:  8080
 initialDelaySeconds:  15
 timeoutSeconds:  1

```

在这个例子中，容器监听端口 8080，并在 web 应用程序中内置了一个用于健康检查的`/health`端点。它有助于验证应用程序的就绪性和活动状态。

就绪探测器向该端点发送一个 HTTP GET 请求，初始延迟为 5 秒，超时为 1 秒。如果端点在给定时间内返回成功的响应(HTTP 200 ),则认为容器准备好了。

活跃度探测器的工作方式类似，但它用于检查容器是否仍在运行并响应请求。在本例中，它有 15 秒的初始延迟和 1 秒的超时。如果活性探测失败，Kubernetes 将重新启动容器，尝试恢复它。

就绪和活性探测都有助于确保我们的应用程序正常运行，并能够处理来自 Kubernetes 集群其他部分的请求。

## 基于机器学习的实验的价值

在为这些探头设置选择正确的参数或参数值时，没有什么金科玉律。我们可以使用手动方法开始调优和测试不同的探针值，验证对容器行为的影响以及基于探针运行容器的自动伸缩方面。

然而，这种手动方法将是一个乏味、耗时且潜在昂贵的过程。此外，我们很可能无法在合理的时间内收集足够的数据点来提供准确的配置决策。

做出这些自信的配置决策的关键是利用自动化和基于 ML 的实验工具，使我们能够收集足够的支持数据点，以了解各种配置组合如何影响和实现所需的探针行为。StormForge Optimize Pro 等工具将实验时间缩短了几个数量级，同时收集了更多的数据点，帮助我们了解如何收敛到我们想要的行为。

## 结论

在本文中，我们探讨了健康检查对于验证容器的重要作用，以及 Kubernetes 探针如何使我们能够执行这些检查。它们包括启动探针，用于验证容器工作负载的启动序列，以及准备就绪和活性探针，用于定期执行诊断测试，以帮助我们了解正在运行的容器和应用程序的健康状况。

为了有效地使用 Kubernetes 探头，我们需要试验不同的探头参数，并进行多项测试，这些测试考虑了真实世界的应用或容器环境条件，包括峰值负载、缓慢启动和尺寸缩小。我们对探针参数调得越精确，我们的探针检查、自动伸缩能力和整体 Kubernetes 应用程序性能就越好。然而，手动实验既繁琐又耗时。在当今复杂的应用环境中，利用自动化和基于 ML 的实验工具将帮助我们更快、更准确地找到正确的探头设置。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>