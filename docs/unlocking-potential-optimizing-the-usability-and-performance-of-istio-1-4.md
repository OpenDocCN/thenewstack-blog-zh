# 释放潜力:优化 Istio 1.4 的可用性和性能

> 原文：<https://thenewstack.io/unlocking-potential-optimizing-the-usability-and-performance-of-istio-1-4/>

[](https://www.stackrox.com/)

 [凯伦·布鲁纳

凯伦·布鲁纳是 StackRox 的首席开发工程师，她在那里推动自动化并倡导产品的可操作化。此前，Karen 曾在 Clari、Ooyala、LinkedIn 和 Yahoo 担任开发运维及站点可靠性工程职位。她在好莱坞的数字特效行业开始了她的职业生涯，并在《互联网大盗》中出演了电影《宝贝》。她用业余时间渲染纱线中的双关语，学习晦涩的纤维工艺，以及被猫绊倒。](https://www.stackrox.com/) [](https://www.stackrox.com/)

[Istio service mesh](https://istio.io/) 不是一项低维护或易学的技术，但其最新版本包括几项升级，可提高可用性和性能，同时减少用户的维护工作量。Istio 已经成为 DevOps 工具箱中越来越重要的工具，尤其是对于 Kubernetes 部署。为了应对日益增长的用户需求，一个支持应用程序和技术的生态系统应运而生，以使 Istio 尽可能发挥作用，同时提供一个解决方案来解决 Kubernetes 中的一些差距。

Istio 工作组于 2019 年末先于 KubeCon + CloudNativeCon 北美发布了最新版本的 Istio，v1.4.0。最新的更新为管理、性能和安全性方面的许多改进奠定了基础，这将使生产用户受益匪浅。以下功能可以帮助您尽可能轻松地操作 Istio:

**对** **无混合器遥测技术的 Alpha 支持**:无混合器遥测技术使得在代理服务器侧柜中使用更少的 CPU 和内存资源变得更加容易，而不会降低网络服务或指标。以前，如果用户想要从[特使代理](https://www.envoyproxy.io/)收集连接遥测数据，istio-proxy sidecar 必须为其处理的每个连接建立到 istio 的 Mixer 遥测服务的连接。启用新的无混合器遥测技术后，连接指标在特使代理中处理，然后由 [Prometheus](https://prometheus.io/) 抓取。从代理的角度来看，通过使指标收集变得被动，代理上的簿记负载下降了。

**Istio 授权策略 API** :取代 Istio 的 RBAC 策略实现，在 Istio 1.4.0 中, [Istio 授权策略 API](https://istio.io/blog/2019/v1beta1-authorization-policy/) 升级为 beta。解决了 Istio RBAC 政策如何应用于工作负载而非服务的困惑，新的控制系统增加了对更多用例的支持，并简化了 Istio 的 UX。

**服务网格管理的集中工具**:**istioctl**命令增加了对 1.4.0 版本中安装和管理控制平面配置的支持，集中工具管理 Istio 服务网格。用户现在可以使用实验性的 **istioctl** analyze 命令对集群进行故障诊断，该命令检查实时集群或 YAML 清单来安装和配置 Istio。应用该命令有助于防止在实时 Kubernetes 集群上出现安装问题。

**特使代理**:特使代理现在支持额外的指标，并支持镜像用户指定的流量百分比，而不是提供全有或全无的选择。这些更新使得由特使代理提供动力的数据平面运行更加顺畅。

**自动 mTLS** :自动 mTLS 简化了从许可 mTLS 模式到 mTLS 实施的迁移，使得 Istio 及其安全特性的逐步采用更加容易。以前，当用户逐渐将 istio-proxy sidecar 添加到部署中时，他们必须创建 DestinationRule 资源。也有必要更新它们，以反映哪些上游目标具有可以支持 mTLS 连接的代理边车。借助自动 MTL，Istio 控制平面会跟踪哪些部署具有边盘，并根据需要更新网格的边盘代理，以连接到那些具有或不具有 MTL 的工作负载。

这些最新的 Istio 升级有助于组织确定其 Istio 部署的最佳使用案例。随着功能的扩展、性能和可用性的提高，Istio 的价值主张变得越来越清晰。此外，不断成熟的安全控制，如新的授权策略，将从根本上增强 Isitio 如何应用于[安全用例](https://www.stackrox.com/post/2019/08/istio-security-basics-running-microservices-on-zero-trust-networks/)，如入口/出口和网关支持，而不会增加复杂性。这些新特性应该被视为一个重要的跳板，它将规定 Istio 如何在更多的行业部署中使用，并巩固其作为领先的新兴服务网格技术之一的地位。

Kubecon + CloudNativeCon 是新堆栈的赞助商。

来自 Pixabay 的 Wokandapix 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>