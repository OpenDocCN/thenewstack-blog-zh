# Netdata Cloud 现在可以免费实时监控 Kubernetes 集群

> 原文：<https://thenewstack.io/netdata-cloud-can-now-monitor-kubernetes-clusters-for-free-in-real-time/>

Netdata，开源、分布式、实时、性能和健康监控平台 [Netdata Cloud](https://www.netdata.cloud/) 背后的公司，已经扩展了其监控 [Kubernetes](https://thenewstack.io/category/kubernetes/) 的能力。想看看它能否帮助您掌握 Kubernetes 集群的最新情况吗？现在，你可以[使用其内置的舵轮图](https://www.netdata.cloud/blog/kubernetes-monitoring-troubleshooting/)实时免费监控和诊断无限数量的 Kubernetes 集群。

不，这不是打字错误，Netdata Cloud 也不是免费增值销售的诱饵。美中不足的是它通过使用代理来跟踪正在发生的事情，目前，它的大多数功能都局限于单个代理。游戏的名称是向您展示 Netdata 云对您的公司有多么重要，并且有一天，他们将提供付费的基础架构范围的功能。简而言之，像 GitHub 和 Zoom 一样，Netdata 希望扩大其客户群，希望你会发现免费服务非常有用，以至于你愿意付费让它变得更加有用。

从技术上来说， [Netdata](https://www.netdata.cloud/) CEO 兼创始人[Costas tsaouss](https://www.linkedin.com/in/costatsaousis/)解释说，这一切都始于 [Netdata 代理](https://www.netdata.cloud/agent/)。“我试图解决一个令人痛苦的现实问题:IT [基础设施监控工具在实时提供完整的粒度指标方面有所欠缺](https://www.netdata.cloud/blog/why-netdata-is-free/)。相信我，我并不缺少可供选择的工具，但是它们中的每一个都缺少一些东西，要么不能看到我需要的每一个指标，要么不能以所需的频率看到它。鸟瞰视图对于获得事情进展的总体感觉是很好的，但是不断地将我送回命令行进行故障排除。

因此，Tsaousis 发布了 Netdata 的第一个版本，作为 GPLv3 的免费开源软件。展望未来，该公司正在加大对使用 eBPF 的 Linux 内核跟踪、容器监控、通用 [Prometheus](https://prometheus.io/) OpenMetrics 收集器的投资，并可能支持 [OpenTelemetry](https://opentelemetry.io/) 。

专门针对 Kubernetes，Netdata 云用户现在可以轻松访问该平台的内置导航图，免费实时监控和排除[无限数量的 Kubernetes 集群](https://thenewstack.io/what-does-it-take-to-manage-hundreds-of-kubernetes-clusters/)的故障。这些数据通过 Netdata Cloud web 界面显示。

该公司在上周举行的 [KubeCon+CloudNativeCon EU](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 虚拟会议上宣布了这一新的监控技术增强。

Netdata 产品副总裁 Robin Schumacher 表示，使用其分布式数据架构，Netdata 云使 DevOps 团队能够通过自动发现和零配置轻松可视化其基础架构。这为用户提供了 Kubernetes 监控体验，满足了开发人员、站点可靠性工程师和系统管理员的需求。“简单的部署、精细的监控和提供对 IT 黑盒的全面了解都是有效故障排除的关键要素，尤其是在使用 Kubernetes 协调分布式系统时。Netdata 帮助每个人提高效率，发现 Kubernetes 部署中的问题。”

Netdata Kubernetes 的监控功能现在包括:

*   具有从节点本身、`kubelet/kube-proxy`、`pods/containers`以及任何容器化的服务或应用程序(如数据库和 web 服务器)中自动发现和收集指标的功能，然后在几分钟内自动配置可视化。
*   通过向开发人员、SRE 和系统管理员提供对其集群的完全可见性，消除了传统 Kubernetes 监控的黑盒感觉，允许他们在易于导航的可视化界面中对所有指标和活动进行分类，同时对异常进行故障排除。
*   简化了部署过程，使用户能够直观地了解从 CPU 使用到磁盘 IO 的容器内部情况，而无需手动设置图表或编写查询来检索数据。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>