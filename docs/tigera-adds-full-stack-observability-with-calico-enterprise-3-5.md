# Tigera 通过 Calico Enterprise 3.5 增加了整个堆栈的可观察性

> 原文：<https://thenewstack.io/tigera-adds-full-stack-observability-with-calico-enterprise-3-5/>

Tigera 在本周的[kube con+CloudNativeCon Europe](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)上发布了最新版本的用于 Kubernetes 的 [Calico Enterprise](https://www.tigera.io/tigera-products/calico-enterprise/) SaaS 安全和可观测性平台，增加了一系列功能，为云原生应用程序开发人员和站点可靠性工程师(SREs)提供实时故障排除和全栈可观测性。

基于开源网络和网络安全 [Calico](https://docs.projectcalico.org/about/about-calico) 项目，Calico Enterprise 提供了扩展的企业级功能，Calico Enterprise 3.5 特别添加了几个功能，该公司称这些功能提供了“一个易于理解和面向行动的视图中的全栈可观察性，否则由于 Kubernetes 基础设施的抽象、短暂和分布式特性，这是非常困难和耗时的。”

[Tigera](https://www.linkedin.com/in/amitgupta1/)的业务开发和产品管理副总裁艾米特·加普塔描述了现在的全栈可观察性与应用程序更加静态时有什么不同。

“全栈可观察性实际上是为 DevOps 和 sre 提供从底层基础架构到应用栈的完整可观察性。这对于基于微服务的应用非常重要，因为它们是在分布式基础设施上运行的分布式应用，所以现在基础设施和应用之间的界限变得模糊了，”Gupta 说。您的应用程序可能存在性能问题，或者您的延迟可能会因为 DNS 请求花费太长时间而增加

为了提供这种全栈可观察性，Calico Enterprise 3.5 增加了四个不同的功能，可以跨任何多云基础设施运行，以帮助对分布式应用进行故障排除。

首先，动态服务图提供了名称空间、微服务和部署之间流量的点对点拓扑表示，Gupta 解释说，一旦达到一定的复杂程度，这将简化故障排除。

“一旦用户通过了大约 20 到 30 个在他们的 Kubernetes 集群中运行的微服务，他们就很难理解依赖图，”Gupta 说。“这非常重要，因为这是基本的起点，因为您要在应用中寻找性能问题或基础架构问题。

接下来，应用程序级的可观察性可以检测和防止异常行为，而域名系统(DNS)仪表板允许用户将 DNS 问题与应用程序问题区分开来。

“一种非常常见的情况是性能延迟上升，而真正的根本原因是更高的 DNS 延迟。当所有这些微服务通过网络进行通信时。这些不是库中的过程调用。因此，如果他们在网络上通信，DNS 性能的任何下降都会直接影响您的应用程序性能，”Gupta 说。“我们已经多次看到这种情况，所以我们为用户添加了一组功能，以便能够从应用程序响应时间一直到基础架构和 DNS 响应时间。”

最后，Calico Enterprise 3.5 增加了动态数据包捕获，自动检索 pcap 文件，并允许用户自定义数据包捕获的持续时间和数据包大小。

Gupta 解释说:“一旦 DevOps 工程师或 SRE 确定了性能热点或问题所在，他们就可以进行进一步的故障排除和诊断，就像捕获数据包以确定请求的有效负载一样简单，这样他们就可以确定性能问题是来自基础设施还是设计不佳的应用程序查询。”。“在 Kubernetes 的世界中，其中一些故障排除步骤可能会非常复杂，因为您需要能够访问底层基础设施才能生成此数据包捕获文件。我们实现了真正的无缝和 RBAC 驱动，因此平台工程师可以让服务团队以自助方式完成这项工作。”

Calico Enterprise 收集的所有数据既可以在服务的单一控制台中获得，也可以传输到特定的端点。例如，Calico Enterprise 可以配置为将数据发送到 Syslog 端点、Splunk、使用 FluentD 发送到 ElasticSearch 或由 Prometheus 收集，以及其他可能的使用案例。此外，可以在 Calico Enterprise 本身内部直接采取行动，也可以用来从外部触发事件。

展望未来，Gupta 表示，用户可以期待可观察性功能的进一步增强，基于机器学习的算法可以帮助执行问题的根本原因分析。他还说，他们将继续扩大收集和提供的数据类型。

Gupta 说:“我们在全栈可观测性方面取得了长足的进步，但用户可以期待看到越来越多的扩展数据集，因此对他们来说，解决应用程序的性能和可用性问题是非常理想的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>