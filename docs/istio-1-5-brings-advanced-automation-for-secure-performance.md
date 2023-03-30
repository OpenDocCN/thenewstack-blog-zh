# Istio 1.5 为安全性能带来先进的自动化

> 原文：<https://thenewstack.io/istio-1-5-brings-advanced-automation-for-secure-performance/>

Istio 已经成为最常用的服务网格技术之一，用于保护和控制容器和 Kubernetes 中的网络流量。其强大的功能集使其有助于解决用户在运行微服务时经常遇到的一些实际问题。在标准的三个月期限之后，Istio 1.4 发布了，Istio 1.5 引入了大量的改进，提高了自动化程度，并提供了工具来帮助进一步运营平台。

Istio 1.5 进行了重大的架构更改和几项 API 更新，提供了改进用户体验和平台功能的新功能。以下重点将帮助组织优化 Istio 的配置管理、架构支持和整体性能。

## 结构管理

 [凯伦·布鲁纳

Karen Bruner 是 StackRox 的技术布道者，她在那里推动自动化并倡导产品的可操作性。此前，Karen 曾在 Clari、Ooyala、LinkedIn 和 Yahoo 担任开发运维及站点可靠性工程职位。她在好莱坞的数字特效行业开始了她的职业生涯，并在《互联网大盗》中出演了电影《宝贝》。她用业余时间渲染纱线中的双关语，学习晦涩的纤维工艺，以及被猫绊倒。](https://www.stackrox.com/) 

**研究所**

Istio 1.5 增加了 Istio 安装的主要管理工具 **istioctl** 的功能和可靠性。通过 **istioctl** 安装现在已经升级到 beta。它可以从现有的概要文件直接将 Istio 安装到集群中，也可以生成一个可以应用于多个集群的清单以保持一致性。

**Istio 操作员**

在 Istio 1.5 中，IstioOperator API 替换了 Istio 操作符使用的 IstioControlPlane 自定义资源。虽然 operator 仍处于 alpha 版本，但它现在可以用于在集群中安装 Istio。它旨在支持在集群内安装和卸载 Istio，以实现无缝配置更新。

**诊断工具**

Istio 1.5 还引入了更多选项来使用 **istioctl** 验证安装和配置。从实验状态升级而来的, **istioctl** analyze 增加了额外的检查和资源，以确保配置正确。

## **建筑**

**Istiod**

Istio 1.5 对 Istio 的控制平面架构进行了相当大的结构性更改，最终缩减了微服务的数量，以换取单一的单片 Istio。在早期版本中，完整的 Istio 部署会在控制平面中部署六个主要服务。在 v1.5 中，这些被整合到一个 Istiod 部署中，一个容器运行一个应用程序进程。

**Web 组件扩展**

Istio 1.5 使用可移植指令格式 [WebAssembly](https://webassembly.org/) ，将其扩展模型与[特使](https://www.envoyproxy.io/)代理的扩展模型合并。在此变化之前，Istio 扩展利用了 Mixer 遥测和策略服务，这导致了较差的可伸缩性。sidecar 代理的每个服务到服务连接都需要连接 Mixer 以进行指标报告和授权检查，这为每个连接带来了延迟。与此同时，Envoy 扩展必须用 C++编写，然后编译成代理二进制文件，这对用户来说极具挑战性且非常耗时。

WebAssembly 支持许多不同的语言，其中许多来自于围绕该项目的不断增长的社区。然后扩展被编译成可移植的字节码格式。编译完成后，可以使用一个命令行将新过滤器部署到现有的 Istio 集群中。向通用扩展模型的转变简化了向 Istio 添加定制功能的能力，也减少了延迟。

## 其他改进

**可观察性**

Istio Telemetry v2 的发展仍在继续，它引入了非 HTTP TCP 连接的指标、gRPC 连接的状态代码报告以及遥测配置的 alpha 支持。早期基于 Mixer 的版本也遭受了每个连接延迟和 CPU 使用增加的问题，在 v2 中这两个问题都减少了一半。这个版本还支持为支持多个 Kubernetes 服务的工作负载设置规范服务，支持用户友好的数据聚合。

**交通管理**

Istio 1.5 以 Envoy 代理为中心，为流量管理提供了一种更加系统化、结构化和逻辑化的方法。为了减少网络流量和计算，特使代理现在支持从飞行员接收部分路由更新。它还引入了更可靠的健康检查。Istio 1.5 还为集群出口流量引入了对基于位置的负载平衡 HTTP 代理设置的支持。

**安全**

Istio 对云原生环境的安全性做出了巨大贡献，1.5 中的最新特性更进一步，增强了其自身和工作负载的安全性。在 Istio 1.5 中，Auto mTLS 升级到 beta 版，以帮助减轻采用 Istio 期间的工作负载迁移。此外，几个新的 API 也升级到了 beta，包括 **PeerAuthentication** 和 **RequestAuthentication** ，它们取代了 **AuthenticationPolicy** 和 **AuthorizationPolicy** API，后者现在支持 Deny 语义，以防止全局控件的本地覆盖。

Istio 1.5 现在还使用 Istio 秘密发现服务(SDS)作为默认服务，将 mTLS 证书传递给代理边车。该服务使用 API 将证书直接发送给 Envoy，而不是创建 Kubernetes 秘密，然后将秘密装载到代理容器中。这种方法要安全得多，它允许 Istio Citadel 颁发每个 pod 的证书，而不是每个工作负载的证书，并且支持证书的动态更新，而无需重新启动 Envoy。

自从推出 Istio 1.4 以来，Istio 团队肯定一直很忙。Istio 1.5 对组织使用 Istio 保护和控制网络流量的方式进行了重大更改，通过提高流量效率、配置管理和简化安装，显著增强了用户体验。Istio 继续在服务网格技术的开源领域处于领先地位，该版本在自动化、安全性和性能方面的改进清楚地表明，Istio 团队专注于创建一个用户友好的平台，这对于优化云原生投资将越来越重要。

来自 Pixabay 的 Maritime_Filming_UK 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>