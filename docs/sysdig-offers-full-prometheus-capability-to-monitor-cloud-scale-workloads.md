# Sysdig 提供完全的 Prometheus 兼容性，以监控云规模的工作负载

> 原文：<https://thenewstack.io/sysdig-offers-full-prometheus-capability-to-monitor-cloud-scale-workloads/>

云原生监控公司 [Sysdig](https://sysdig.com/about/) 已经扩展了其旗舰[安全 DevOps 平台](https://sysdig.com/platform/)，使其与 [Prometheus](https://prometheus.io/) 完全兼容，使该平台成为“唯一与开源云原生监控工具完全兼容的企业监控解决方案”。

尽管 Prometheus 广泛用于监控基于 Kubernetes 的云原生部署，但它本身无法扩展到单台服务器之外。Sysdig 产品管理副总裁 Payal Chakravarty 说:“Prometheus 服务器适合小型环境。

“今天，当开发人员和 DevOps 团队开始使用 Prometheus 时，当它只是一个或两个应用程序或几个集群时，管理起来很容易，但当他们试图在整个企业中对 Prometheus 进行标准化时，情况就完全不同了。Chakravarty 说:“你需要大量资源来了解如何联合可管理性，然后如何扩展它以实现长期数据保留，因为 Prometheus 服务器只能处理几周的数据。

相比之下，Sysdig 平台每秒可以处理超过 1 亿个指标，并保留 13 个月的数据——这是它已经为 IBM 云平台提供的功能。Sysdig 对用户的部分价值主张是[将监控和安全](/sysdig-update-provides-security-and-visibility-to-cloud-native-applications/)结合到单一平台中。同样，Chakravarty 解释说，普罗米修斯的支持进一步增加了可用的数据和由此产生的可能性。“代理收集这些指标，并远程写入我们的指标存储，这是一个收集所有这些指标的时序数据库。你根本不需要普罗米修斯服务器，”查克拉瓦蒂说。

通过增加对 Prometheus 查询语言 [PromQL](https://prometheus.io/docs/prometheus/latest/querying/basics/) 的支持，Sysdig 平台允许用户在 Sysdig 平台内创建仪表板、警报和指标分析，使用 Sysdig 的现成 Kubernetes 仪表板，并继续使用他们已经使用 PromQL 创建的仪表板和警报。

“无论是 Kubernetes 容量管理，还是基于 Prometheus 指标的异常检测，它都提供了更多洞察的可能性，我们可以在收集的指标基础上创建这些洞察。这些是我们在未来获得数据后会考虑做的事情，”Chakravarty 说。“今天，您实际上可以将 Prometheus 指标与 syscall 派生的指标结合起来，并且可以对指标进行计算。因此，如果你必须计算某些趋势或组合从不同来源收集的指标来进行比较或混搭或分割，你将能够做到这一点。”

可以肯定的是，Sysdig 并不是唯一一个试图将 Prometheus 扩展到单台服务器之外的组织。

几年前，Weaveworks [在 Prometheus](https://thenewstack.io/weaveworks-horizontal-scaling-prometheus/) 的 [Cortex](https://github.com/cortexproject/cortex) 中引入了水平伸缩，正如[云本地计算基金会](https://www.cncf.io/)的[灭霸项目](https://github.com/thanos-io/thanos)一样。Sysdig 声称，它的发布是第一个提供云级可伸缩性的商业产品。

“据我们所知，Cortex 产品的规模不足以支持整个云规模的实施。Sysdig 首席营销官詹妮特·松田隼说:“它不会可靠地上升到那个指标水平。“我们从客户那里了解到的事实是，尽管可能有 Cortex 或这些东西声称它们可以扩展，但事实是它对人们不起作用。”

除了 Prometheus 和 PromQL 支持之外，Sysdig 还推出了 PromCat，“这是一个经过审查的 Prometheus exporters、dashboard 和 alerts 的精选存储库，用于监控云中运行的任何基础设施、应用程序和服务”，该库在发布时托管了 Kubernetes 控制平面 Istio 和越来越多的 AWS 服务的集成。

云计算原生计算基金会是新堆栈的赞助商。

照片由来自 Pixabay 的 Larisa Koshkina 拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>