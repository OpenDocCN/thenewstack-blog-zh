# 特使网关提供标准化 Kubernetes 入口

> 原文：<https://thenewstack.io/envoy-gateway-offers-to-standardize-kubernetes-ingress/>

特使代理项目正在扩展，目的是建立一套标准化的、简化的 API 来与 T2 的 Kubernetes T3 一起工作。

本周，在 [KubeCon+CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe) 大会上，开源项目透露，他们正在开发一个扩展项目 [Envoy Gateway](https://github.com/envoyproxy/gateway) ，它将使 Envoy 反向代理成为一个网络网关，不仅可以引导内部[微服务](https://thenewstack.io/category/microservices/)流量，还可以管理进入网络的外部流量。Kubernetes 是最初的目标。

特使网关背后的想法是提供“一个简化的部署模型和 API 层，旨在更轻的用例，”[在一篇博客文章中解释道](https://blog.getambassador.io/introducing-envoy-gateway-5b3df54e5f9b)特使创造者 [Mat Klein](https://www.linkedin.com/in/mattklein123/) 。

Envoy 最初是为 Lyft 创建的，于 2016 年作为开源发布，主要用于构建服务网格(通常与 Istio，[另一个 CNCF 项目](https://thenewstack.io/istio-applies-to-join-cncf-why-now/))帮助云原生应用通过 sidecars 相互通信。

有趣的是，Lyft 本身首先将该软件用作 API 网关/边缘代理，这意味着它也可以轻松地用作内部路由外部流量的反向代理，提供相同级别的可观察性和[零信任安全性](https://thenewstack.io/what-is-zero-trust-security/)。

特使代理项目于 2017 年被[云原生计算基金会](https://cncf.io/?utm_content=inline-mention)采用，并已达到毕业项目成熟度级别。特使网关也将由 CNCF 主办，作为一个附带项目。

## Kubernetes 网关 API

根据 Klein 的说法，API 网关可以被认为是“Envoy 代理核心的包装器”，它不会对核心本身进行任何重大更改。它可以在各种使用情况下管理 L4/L7 流量。

对于管理员来说，该软件旨在提供一种更简单的方式来建立 Kubernetes 服务网格。克莱因自己也承认，特使本身并不容易管理。一点易用性可能有助于吸引更多用户，即那些拥有较小网络的用户，他们现在倾向于部署 [HAProxy](https://www.haproxy.com/?utm_content=inline-mention) 或 [Nginx](https://www.nginx.com?utm_content=inline-mention) 来代替 Kubernetes 的入口任务。

也许更重要的是，该项目希望看到开发人员和第三方工具供应商通过提供一个参考实现，将 Envoy 作为 K8s 集群的入口控制器来运行，从而决定使用 Envoy 网关来访问 Kubernetes。Klein 解释说，这个 API 将是“T4 Kubernetes 网关 API ，带有一些特使专用的扩展。

“选择这个 API 是因为在 Kubernetes 上部署一个入口控制器是该项目的最初重点，也因为这个 API 拥有广泛的行业认同，”他说。

使用 Kubernetes 网关进行配置将“从 API 中分离路由和管理”，Ambassador Labs 首席执行官 Richard Li 在博客文章中进一步解释道。Ambassador 与 Fidelity、 [Tetrate](https://www.tetrate.io/?utm_content=inline-mention) 和 VMware 都是该项目的赞助商。API 将隐藏开发人员和管理员必须处理的底层配置。

该项目将“致力于让个人应用开发人员或团队在其基础设施中使用和部署 Envoy 的体验变得极其简单和容易，”[Istio 贡献者和指导委员会成员 Zack Butcher 在推特上写道。](https://twitter.com/ZackButcher/status/1526244360475615232)

Butcher 还指出，在 Kubernetes Gateway API 上的融合将减少现在正在进行的构建竞争控制平面的重复工作的数量。

“控制飞机是*无聊*！它们的建造成本也很高，而且很难做好，”布彻指出。

Klein 认为，如果 Kubernetes 的用户群都同意部署这些 API，这将允许他们的供应商“轻松地提供替代的 SaaS 实现，如果用户超越了参考实现，想要额外的支持和功能等，这可能是更好的选择”。

然后，第三方软件开发人员可以向上移动堆栈，在标准化的、厂商中立的 Kubernetes Gateway API 上构建高级功能。

这并不是第一个解决 API 网关问题的 CNCF。但是最好的部分轮廓和大使的 T2 使者将会被融合到这个新的努力中，CNCF 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>