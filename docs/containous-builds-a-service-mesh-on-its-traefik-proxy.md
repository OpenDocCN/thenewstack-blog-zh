# Containous 在其 Traefik 代理上构建了一个服务网格

> 原文：<https://thenewstack.io/containous-builds-a-service-mesh-on-its-traefik-proxy/>

[Containous](https://containo.us/) ，开源反向代理 [Traefik](https://traefik.io/) 和 [Traefik Enterprise Edition](https://containo.us/traefikee/) 背后的公司，已经随着 [Maesh](https://github.com/containous/maesh) 的发布进入了服务网格领域，这是一个新的开源服务网格，旨在方便开发者使用。Maesh 是使用 Traefik 构建的，以提供代理功能，Containous CEO [Emile Vauge](https://fr.linkedin.com/in/emilevauge) 在接受新堆栈采访时指出这是一个关键的区别。

“如果你使用一些传统的反向代理，如 HAproxy 或 NGNIX，你不应该动态地改变配置。如果你想增加一些路由或者动态地改变配置，你应该关闭代理并重启它，”Vauge 说。“Traefik 能够支持其配置的动态变化。最重要的是，它与每一个云本地 orchestrator 和工具完全集成。它能够连接到每一个云原生跟踪系统、每一个指标应用程序和每一个编排器——Kubernetes、Docker Swarm、Rancher、AWS 等等。所以基本上它是一个云原生反向代理。”

据该公司称，Maesh 基于 Traefik 的功能集提供了许多功能，包括使用 OpenTracing 的可观察性，对 HTTP 和 TCP 层的多协议支持，负载平衡、重试和故障转移等流量管理，断路器和速率限制，以及访问控制的安全性。除了这些特性之外，Vauge 说，Maesh 与其他服务网格的不同之处在于它易于实现和使用。

“我们希望做一些不同于其他服务网格的事情。我们想做一些简单而轻松的事情，就像 Traefik 一样。为此，我们决定使用不同的架构。使用 Istio，每个应用程序都有一个 Envoy 实例，当您想要部署数千个应用程序时，管理起来有点复杂，因为您将有数千个反向代理，”Vauge 说。“相反，我们希望使用轻量级架构，每个 Kubernetes 节点只有一个反向代理。与 Istio 相比，它更易于扩展，使用的资源也更少。”

Vauge 还比较了 Maesh 和 Linkerd，指出虽然 Linkerd 也是轻量级的，但它使用的 sidecar 代理与全功能的 Traefik 相比功能较少。Vauge 说，另一个比较点是安装，这是那些试图实现服务网格的人的一个常见问题。

“如果你想安装 Istio，安装起来真的很庞大——你必须下载 Istio，它超级重，然后它会在你的 Kubernetes 集群上安装大约 10 多个组件，并占用大量资源，”Vauge 说。“你要装 Maesh 的时候，它只下载 Traefik，超轻的，还有 Maesh 控制器，就是这样。您只需编写一行代码来安装它，仅此而已。所以真的超级简单。”

最后，Maesh 还推出了对 Traefik 版本 2 的完全支持，Vauge 表示该版本将很快推出，同时还完全符合[服务网格接口(SMI)](https://smi-spec.io/) 。

“这真的很重要，因为这个标准意味着每个人都已经知道我们是如何工作的。它与提供商无关，所以如果你想改变你的服务网络，很容易做到，”Vauge 说。“这意味着我们能够提供一些可观察性功能，一些流量管理功能，如金丝雀部署，以及一些安全功能，如访问控制，这非常重要。所有这些都归功于符合 SMI 标准。”

来自 Pixabay 的 xresch 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>