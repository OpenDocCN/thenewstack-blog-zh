# 使用 Kubernetes 端点切片来分割您的 API，以解决集群网络瓶颈

> 原文：<https://thenewstack.io/slice-up-your-api-with-kubernetes-endpointslices-for-cluster-network-bottlenecks/>

Kubernetes 有很多锦囊妙计。事实上，这件衬衫是为章鱼量身定做的，所以它有六个袖子，每个袖子都充满了各种花样。每一个新版本都有新的特性让开发人员感到惊喜。

当然，伴随着这些众多的特性而来的是一种难度，这种难度是目前全球企业所采用的其他技术所没有的。Kubernetes 的开发人员明白他们的容器编排器是多么具有挑战性。此外，他们非常希望确保 Kubernetes 能够满足企业对 it 的一项要求——规模。为此，他们不遗余力地开发能够在大规模部署时缓解困难的功能。

一个这样的特性是端点切片。

## 什么是 EndpointSlices？

简单地说，EndpointSlices 使跟踪 Kubernetes 集群中的网络端点成为可能(也很简单)。

等一下。什么是端点？

在 Kubernetes 的领域中，端点是任何获得分配给它的各个 pod 的 IP 地址的对象。然后，Kubernetes 服务会引用该端点，这样该服务就会保存 pod 内部 IP 地址的记录，以便进行通信。pod 通过端点将自己暴露给服务。

为了使 Kubernetes 服务能够确保将流量分发到 pods，端点必须充当抽象层。

问题是，随着 Kubernetes 变得越来越复杂，它现在需要向后端 pod 发送越来越多的流量。随着这种演变的发生，最初的端点 API 的局限性已经暴露出来。最大的问题是伸缩性。

因为每个服务的所有网络端点都存储在一个端点中，这些资源可能会增长到不可接受的规模，这对 Kubernetes 的性能有负面影响。换句话说，随着您的网络终端越来越多，您扩展部署的能力受到了影响。

为了缓解这个问题，[端点切片](https://kubernetes.io/docs/concepts/services-networking/endpoint-slices/)应运而生。

## 有什么问题？

想想这个:你越是扩大规模，事情就越难。正如我们已经解释过的，Kubernetes 的一个不太好的方面是端点。但是假设您已经部署了一个位于大量 pod 之前的服务。您的服务包括一个端点对象，该对象包含每个 pod 的 IP 地址和端口号。

问题就出在这里:每次在服务中添加或删除 Pod 时，整个端点对象都会更新，并通过网络发送到每个节点。当端点对象扩展时，由此产生的流量会使这些节点承受巨大的负载。

这就是 EndpointSlices 发挥作用的地方。

从 Kubernetes v1.17 (beta)开始，它不再使用端点对象(包含不断增长的 IP 地址和端口号)，而是被分割成更小的部分(因此得名)。这些切片(本质上更小)有助于减轻由非常大的端点对象引起的负载。具体来说(至少从 1.17 版开始)，每个端点“切片”将容纳多达 100 个 pod 的网络详细信息。这是极限。

这在现实生活中是如何实现的？假设您的服务部署包含大量的 pod。如果您删除其中一个 Pod，Kubernetes 只会重新剪切包含该 Pod 详细信息的切片。当分片在网络上更新时，它将只包含多达 100 个 pod 的信息，所以集群网络不会阻塞。

最终，您的部署将享受到:

*   降低网络流量。
*   减少节点和控制平面的工作量。
*   更好的性能和可靠性。

## 如何实现 EndpointSlices

EndpointSlices 工作到您的清单中，使用如下的种类声明:

默认情况下，控制平面将确保每个 EndpointSlices 不超过 100 个端点。但是，您可以使用–max-endpoints-per-slice 标志(与 Kubernetes 控制器管理器守护程序一起使用)指定这个数量，最多 100 个端点。

一个示例 EndpointSlice 资源如下所示:

```
apiVersion:  discovery.k8s.io/v1beta1
kind:  EndpointSlice
metadata:
name:  testing
labels:
kubernetes.io/service-name:  endpointslicesample
addressType:  IPv4
ports:
-  name:  http
protocol:  TCP
port:  80
endpoints:
-  addresses:
-  "10.1.2.1"
conditions:
ready:  true
hostname:  podA
topology:
kubernetes.io/hostname:  nodeA
topology.kubernetes.io/zone:  us-west2-a

```

## 结论

如果你与 Kubernetes 大规模合作，端点切片可能是 Kubernetes 自面包片以来发生的最好的事情。但是，请记住，该功能仍处于测试阶段。如果你想了解更多关于这个令人兴奋的可扩展 Kubernetes 世界的信息，请查看[官方 EndpointSlices 信息页面](https://kubernetes.io/docs/concepts/services-networking/endpoint-slices/)。

在[未飞溅](https://unsplash.com/s/photos/slices?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)上通过[凸起](https://unsplash.com/@chuttersnap?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>