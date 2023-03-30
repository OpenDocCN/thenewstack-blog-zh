# Azure 上的 HashiCorp 咨询服务:第一个完全托管的服务网格

> 原文：<https://thenewstack.io/hashicorp-consul-service-on-azure-the-first-fully-managed-service-mesh/>

在微软的幕后帮助下， [HashiCorp](https://www.hashicorp.com/) 推出了它所谓的第一个完全托管的服务网格，[hashi corp consult Service(HCS)on Azure](https://www.hashicorp.com/products/consul/service-on-azure/)。

HashiCorp 联合创始人兼首席技术官 [Armon Dadgar](https://www.linkedin.com/in/armon-dadgar/) 在该公司本周在西雅图举行的年度 HashiConf 用户大会的开幕式上解释说，Azure 上的 HCS 现在处于私人测试阶段，它提供了一种连接服务的方式，无论这些服务是虚拟机还是 Kubernetes 环境。当用户从 Azure Marketplace 部署 Consul 时，HashiCorp 管理的 Consul 集群会在用户首选的 Azure 区域中被调用。然后，可以通过私有的 Azure 控制台或从外部公开的命令外壳来管理它。

这种基于[consult](https://www.consul.io/)的方法的真正好处是管理 Kubernetes 和非 Kubernetes 的混合资产，无论是在 Azure 上还是在其他云上，或者来自私有数据中心，微软杰出的工程师和 Kubernetes 的创始人之一 Brendan Burns[在后续采访中指出。](https://www.linkedin.com/in/brendan-burns-487aa590/)

“实际上连接 Kubernetes 并不困难，但是 Consul 最擅长的是将其他东西连接到基础设施中，”Burns 说。

## 网络控制平面

Consul 提供了一个网络控制平面，可用于将多个托管 Kubernetes、VM 和混合/本地环境连接在一起，实际上创建了一个平面网络拓扑，以支持多集群服务发现和请求路由等功能。它支持服务网格接口(SMI)与其他服务网格集成，根据博客的说法，“使用户能够在一个定制的 Kubernetes 资源中定义 Consul Connect 意图，该资源可以通过 kubectl 或 Helm 直接管理。”

HashiCorp 联合创始人 [Mitchell Hashimoto](https://www.linkedin.com/in/mitchellh/) 在后续采访中指出，由于 consult 可以与其他位置的其他 consult 实例以联合模式工作，因此不同云之间或云和私有数据中心之间的延迟可以保持在最低水平。

[![](img/c3e7504c3f0aa324b219346df697448e.png)](https://cdn.thenewstack.io/media/2019/09/e52f3f19-brendan_burns.jpg)

在一篇解释新服务的博客文章中，HashiCorp 列举了新服务的好处:

*   **服务发现**:提供集成健康检查的服务注册中心，使任何服务能够发现其他服务并被其他服务发现。
*   **服务网格**:通过将核心功能从集中式中间件转移到端点来简化服务网络。
*   **动态流量管理**:支持高级流量管理，支持不同的部署策略，提高应用弹性。
*   **服务分段**:通过相互 TLS 和本机 Envoy 集成，加密通信并控制跨服务的访问。
*   **可观察性**:支持网络指标收集，无需修改代码即可洞察应用行为和性能。
*   **Mesh Gateway** :在 Azure 区域、私有数据中心和运行时环境(如 AKS、Azure Stack 和 HashiCorp Nomad)之间透明、安全地路由流量。

## 哈希公司与微软合作

与微软合作有很多好处，特别是在计费和安全方面。所有的账单都是通过现有的 Azure 账户完成的，这可以极大地减少已经拥有 Azure 账户的用户的会计问题。提供服务所需的身份验证也完全由服务处理，通过利用现有的 Azure 帐户，消除了为每个新项目生成证书的混乱步骤。

伯恩斯解释说，这些功能来自微软最近的一项举措，即[托管应用平台](https://azure.microsoft.com/en-us/blog/azure-managed-applications/)，该平台是为 HashiCorp 等第三方软件提供商设计的，旨在基于 Azure 构建服务。这是一种不同于其他云提供商所采取的方法(阅读:Amazon Web Services ),通过使用相同的技术提供竞争服务来直接与开源软件发行版竞争。

Dadgar 说，当客户从市场上购买 Consul 时，“微软会在客户的帐户中生成一个特殊的子帐户，让我们在他们的帐户中有一个小口袋，我们可以为他们管理 Consul”。

Burns 说，面向 Azure 的 HCS 可以“对那些已经在媒体上阅读了服务网格并做了一点点实验的人来说是很棒的”，并希望推进更大规模的实现。“如果您一直在为混合连接而挣扎，这可能是一个非常好的解决方案。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>