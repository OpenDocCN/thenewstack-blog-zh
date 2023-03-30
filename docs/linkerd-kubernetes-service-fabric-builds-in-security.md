# Linkerd Kubernetes 安全服务结构

> 原文：<https://thenewstack.io/linkerd-kubernetes-service-fabric-builds-in-security/>

我们都知道网络安全对我们的 [Kubernetes](https://kubernetes.io/) 部署至关重要，对吗？当然，没错。一个[服务网格](https://buoyant.io/service-mesh-manifesto/)通过添加一个专用的基础设施层来促进微服务之间的服务对服务通信，并平衡服务间的流量，从而提高网络安全性。它还可以帮助您智能地控制服务之间的流量和 API 调用。现在，在 [Linkerd 2.11](https://linkerd.io/2021/09/30/announcing-linkerd-2.11/) 中，开源的 [Linkerd](https://linkerd.io/) 已经加入了一个新的授权策略特性，让您可以细粒度地控制哪些服务可以相互通信。

在深入探讨之前，让我们先谈一谈 Linkerd。这是第一个 Kubernetes 服务网格和[云本地计算基础](https://cncf.io/?utm_content=inline-mention)服务网格。[威廉·摩根](https://www.linkedin.com/in/wmorgan/)Linkerd 的创建者之一想要提醒你的是——尽管你听到了相反的说法——[服务网格“在架构上相当简单](https://buoyant.io/service-mesh-manifesto/)。它只不过是一堆用户空间代理”和一些管理 API。就是这样。仅此而已。

代理构成服务网格的数据平面，而管理进程充当其控制平面。代理本身只是第 7 层感知的 TCP 代理，比如 [Envoy](https://envoyproxy.io/) 、 [HAProxy](http://www.haproxy.org/) 和 [NGINX](https://www.nginx.com/blog/nginx-plus-r25-released/) 。Linkerd 使用它自己的 Linkerd 专用的基于 Rust 的微代理， [Linkerd-proxy](https://github.com/linkerd/linkerd2-proxy) 。

在 2.11 中，Linkerd 的开发人员在网状网络中添加了一个新的身份验证和安全特性，称为“策略”该特性使您能够精确控制哪些服务可以相互通信。简单吧？

它是这样工作的。这些政策建立在 Linkerd 的[自动内置相互 TLS (mTLS)](https://linkerd.io/2.11/features/automatic-mtls/) 安全服务身份之上。MTLS 自动验证和加密所有节间网络。授权策略以一种可组合的、Kubernetes 本地的方式表达，只需要很少的配置，但它可以表达许多行为。

这个新的[策略控制器](https://github.com/linkerd/linkerd2/tree/cf683f8df54c710898b8f3b751d0ba2e48231cef/policy-controller)是用 Rust 编写的。它使用 [kube-rs](https://github.com/clux/kube-rs) 与 Kubernetes API 通信，并公开了一个用 [Tonic](https://github.com/hyperium/tonic/) 实现的 gRPC API。在此之前，Linkerd 已经将 Go 用于其控制平面组件。Linkerd 背后的公司 bubble 的首席技术官 Oliver Gould 解释说，这是“因为 Kubernetes 生态系统(及其 API 客户端等)非常倾向于使用”。由于 [u/clux](https://www.reddit.com/u/clux/) 在 kube-rs 上的出色工作，现在在 Rust 中实现控制器是可行的。这是 Linkerd 项目向前迈出的一大步，我们计划在整个项目推进过程中更多地使用 Rust。"

为什么这是一个进步？古尔德解释说，“Rust 的类型系统使得编写错误代码变得更加困难，代价是编译速度变慢。这需要一些时间来适应，但一旦你习惯了，就很难再回去了。此外，我们的 Rust 控制器占用的内存只有 Go 控制器的 20-30%。”

在这个新的策略控制器之上，Linkerd 2.11 引入了默认的授权策略，只需设置一个 Kubernetes 注释，就可以在集群、名称空间或 pod 级别应用这些策略。

其中包括:

*   all-authenticated(仅允许来自 mTLS 验证的服务的请求)；
*   all-未经身份验证(允许所有请求)
*   拒绝(拒绝所有请求)…等等。

为了使这一点更加有用，Linkerd 2.11 还添加了两个新的[CustomResourceDefinitions(CRDs)](https://kubernetes.io/docs/tasks/extend-kubernetes/custom-resources/custom-resource-definitions/):Server 和 ServerAuthorization。您可以一起使用这些来设置细粒度的策略，以应用于任意组的 pod。例如，服务器可以选择一个名称空间中所有 pod 上的所有管理端口，服务器授权可以允许从 [kubelet](https://kubernetes.io/docs/concepts/overview/components/) 或 mTLS 连接进行健康检查连接，以便收集指标。

综上所述，您可以轻松地为您的集群指定许多网络安全策略，从愚蠢的“允许所有流量”到“服务 Foo 上的端口 8080 只能接收来自使用 Bar 服务帐户的服务的 mTLS 流量”，等等。有关您可以做什么的更多详细信息，请参见 [Linkerd 认证策略](https://linkerd.io/2.11/features/server-policy/)。

除此之外，还有许多其他有用的新功能和改进。

例如，直到最近，为了使其网络更加健壮，出于性能原因，Linkerd 只允许对无主体请求(如 HTTP GETs)进行重试。现在，Linkerd 还可以使用主体重试失败的请求，包括最大主体大小为 64KB 的 [gRPC](https://grpc.io/) 请求。

为了避免竞争情况，默认情况下，Linkerd 2.11 现在确保 linkerd2-proxy 容器在 pod 中的任何其他容器初始化之前准备就绪。这是 Kubernetes 对容器启动订购缺乏控制的一种变通方法。希望您不会再遇到因为代理还没有准备好而导致应用程序容器连接失败的情况。

最后，和往常一样，Linkerd 2.11 团队希望保持 Linkerd 为 Kubernetes 的[最轻、最快的服务网格。为了确保这种情况仍然存在:](https://linkerd.io/2021/05/27/linkerd-vs-istio-benchmarks/)

*   控制平面减少到只有三个部署。
*   由于高度活跃的 Rust 网络生态系统，Linkerd 的数据平面“微代理”甚至更小、更快。
*   Kubernetes 的服务网格接口(SMI)功能已经从核心控制平面中移除，并转移到扩展中。
*   Linkerd 映像现在使用最少的“分布式”基础映像。

如果 Linkerd 工作人员添加的唯一内容是新的授权策略，那么这将是我认真考虑使用 Linkerd 的唯一理由。加上其他改进，我认为如果您发现自己需要一个服务网格来进行云原生部署，Linkerd 应该是您的首选。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>