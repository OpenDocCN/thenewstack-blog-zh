# 将日志和指标与 Grafana Labs 的 Loki 1.0 发布相结合

> 原文：<https://thenewstack.io/merging-logs-and-metrics-with-grafana-labs-loki-1-0-launch/>

Portworx 赞助了 New Stack 对 Kubecon+CloudNativeCon 北美 2019 的报道。

Grafana Labs 在今年的 [KubeCon+CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 上发布了开源 [Loki](https://grafana.com/oss/loki/) 日志聚合软件的 1.0 版本，称该工具已经普遍可用并准备好投入生产使用。虽然 Loki 是[在 KubeCon 2018 上首次发布的](/tns-context-grafana-loki-and-kubecon-takeaways/)，但 Grafana Labs 的产品副总裁 [Tom Wilkie](https://www.linkedin.com/in/tomwilkie/) 表示，这一发布非常早，自那以来已经走过了漫长的一年。

“这是一个非常早期的声明，很大程度上是一个原型。威尔基在接受 New Stack 采访时表示:“我们在过去的 12 个月里，以非常紧凑的发布周期，非常快速地对它进行了迭代，不断地进行部署，并在内部进行了尝试。“我们从用户那里得到了很多反馈，他们喜欢它，他们在开发、测试和试运行中使用它，但对 1.0 之前的产品有很多担忧。”

自从 Loki 首次发布以来，Grafana Labs 已经在生产中运行了八个月，该项目已经收到了来自近 200 名贡献者的 1000 多份贡献，Wilkie 说他们已经发布了至少五个小版本。除了表明 Loki 已准备好投入生产使用，Wilkie 还指出，LogQL 是一种“普罗米修斯风格的查询语言”，这是该团队希望在 1.0 版本中强调的内容。

“现在对 LogQL 来说还为时尚早。我们已经构建了一些基本功能，开始从日志中提取指标，并能够将它们与来自 Prometheus 的指标相结合。我们试图构建这种语言，使它尽可能地与 PromQL 相同，”Wilkie 说，他解释说 LogQL 可以用来引入和公开普罗米修斯之前的遗留系统的日志数据。

Grafana Labs 也是开源指标、分析和监控可视化工具 [Grafana](https://grafana.com/) 的幕后公司，并且在许多方面，指标和日志记录是同一枚硬币的两个不同面——例如，指标可以告诉你某项服务运行缓慢，而日志记录可以帮助诊断该服务运行缓慢的原因。Loki 与其他日志工具的不同之处在于，它不索引日志的全文，而是只索引元数据，同时使用与 Prometheus 相同的服务发现技术在 Kubernetes 环境中运行。Wilkie 解释说，Loki 将指标和日志结合在一起，因为 Loki 允许用户在指标和日志之间即时切换上下文。

“因为我们已经在您的指标和日志之间获得了这种系统一致的元数据，所以我们实际上可以自动化这一过程，我们可以自动从任何给定的基于指标的查询切换到日志查询，向您显示您正在查看的服务的相关日志。真的很厉害。这有助于大幅缩短事故的平均恢复时间。”

除了发布开源的 Loki 1.0，Grafan Labs 还推出了 [Grafana Cloud](https://grafana.com/products/cloud/) ，这是一个高度可扩展的托管 Loki 服务，根据使用情况定价，包括支持和培训。至于 Grafana Labs 的下一步是什么，Wilkie 说，该公司计划将最后一个领域添加到其度量和日志产品中——跟踪。

“分布式跟踪通常被称为可观测性的第三个支柱。一年前，我们在 Grafana 实验室开始了我们的伐木之旅，上周在 KubeCon，我们开始了我们的追踪之旅，”Wilkie 说。“我们已经在 Grafana 中添加了一些分布式追踪的集成，能够可视化 Jaeger 和 Zipkin 等工具的痕迹，在接下来的一年里，我希望能够发布一些令人兴奋的关于 Grafana 实验室各种追踪集成和项目的公告。”

云原生计算基金会和 KubeCon+CloudNativeCon 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>