# Aporeto 的 Kubernetes 安全平台提供多区域集群支持、服务网格集成

> 原文：<https://thenewstack.io/aporetos-kubernetes-security-platform-now-offers-multiregion-cluster-support-service-mesh-integration/>

零信任云安全公司 [Aporeto](https://www.aporeto.com/) 已经扩展了其 Kubernetes 安全托管软件集，以包括多集群和多区域部署，并为多服务网格集成铺平了道路。

这项服务提供了网络层 4-7 支持，这“允许用户在性能开销和安全需求之间取得平衡。”Aporeto 联合创始人兼首席技术官 [Dimitri Stiliadis](https://www.linkedin.com/in/stiliadis/) 在一封电子邮件中写道。这些网络层的添加提供了所需的可见性和粒度。

“在大多数情况下，Kubernetes 群集中通过网络策略实现的网络安全是 L3 安全。这显然是有限的，因为在这一层没有多少信息可用。Aporeto 解决方案将网络安全扩展到 L4-L7 层，为集群中正在发生的安全操作提供了真正的可见性，”Stiliadis 写道。“只需点击一下，运营商就可以在所有 Kubernetes 集群上部署 MTL，而无需担心详细的网络政策。工作负载将使用负载平衡器或服务网格，Aporeto 解决方案为所有这些实施提供了统一的身份和安全框架。除了通过我们自己的数据平台支持安全实施之外，我们还使用 Envoy 代理支持跨服务网格实施的安全实施。”

升级还包括支持运行多个服务网格。通过使用 Envoy 代理，Aporeto 现在可以混合和匹配各种服务网格。Aporeto 适用于所有容器网络接口架构和服务网格，以及所有 Kubernetes 格式，包括 AWS EKS、谷歌 GKE、微软 Azure AKS、IBM Cloud Kubernetes，以及 Red Hat OpenShift、kubeadm 和 Heptio 等本地安装。Stiliadis 说这是 Aporeto 方法的核心。

“自动化和可扩展性是平台的核心，”Stiliadis 写道。“借助我们嵌入平台的功能即服务功能，运营商可以通过基于安全或测量事件调用的可编程功能框架，自动执行重复的安全任务、报警和警报。本质上，该平台提供了一个可扩展性框架，可在任何环境下定制操作。”

当新堆栈[在 2016 年首次写下关于 Aporeto 的](/aporeto-secures-kubernetes-workloads-network-policy-labeling/)时，该公司专注于 [Trireme](https://www.aporeto.com/opensource/) ，这是一种“可以轻松部署到每台主机上以站在 TCP/IP 堆栈前面的用户域进程、容器或【Kubernetes】DaemonSet”，它将使用“一种元数据机制来取代 IP 地址的使用，这种机制专门将应用程序标识为集体 pods 的成员，并且不是通过 VxLAN 或 Docker 插件，而是通过一种松散耦合的标签系统来弥合它们之间的差距。”

现在，Aporeto 继续采用基于应用程序身份，而不是基于 IP 地址的安全和策略管理。正是通过这种方法，该公司现在表示，它可以处理更复杂的 Kubernetes 环境。目前，Aporeto 使用 [SPIFFE 证书](https://thenewstack.io/scytale-launches-spiffe-based-service-identity-management/)或完全兼容的 OAUTH/OIDC 证书来实现这一点，工作负载可以使用这些证书安全地对第三方服务和应用进行身份验证和授权，而无需使用机密。

Stiliadis 告诉新堆栈，向多集群 Kubernetes 部署的迁移使得传统的基于 IP 的方法难以为继。他写道，Aporeto 的方法不仅超越了有问题的基于 IP 的方法，而且将安全控制平面与 Kubernetes 控制平面完全分离，提供了端到端的安全性，而没有理解和管理复杂网络拓扑的开销。

“至少可以说，在这样的多集群环境中提供哪怕是简单的网络安全也是一项挑战。通过依赖工作负载身份和端到端身份验证和授权，Aporeto 平台支持网络安全的多集群和多区域部署，”Stiliadis 写道。“在多集群 Kubernetes 中，网络拓扑非常复杂。不同的集群可以有不同的 IP 地址范围，这些范围通常是重叠的。NAT 网关、负载平衡器等。在群集之间修改 IP 地址。这使得使用基于 IP 地址的技术来实现网络安全变得极其复杂。”

来自 Pixabay 的 Reimund Bertrams 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>