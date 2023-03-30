# 可观察性、分布式跟踪和 Kubernetes 管理

> 原文：<https://thenewstack.io/observability-distributed-tracing-and-kubernetes-management/>

可观测性和分布式跟踪与日益分布的系统的可靠性有着内在的联系。可观察性驱动的开发使用数据和工具来观察系统的状态和行为，以了解更多关于其弱点的模式。分布式跟踪提供了度量和日志，允许深入单个请求并更接近问题。在这种强大的配对中，可观察性发生在事件级别，这驱动您的问题，而跟踪发生在请求级别，这有助于回答这些问题。

在本期[新堆栈制造商](https://thenewstack.io/podcasts/makers)播客中，出版商 Alex Williams 采访了[首席执行官兼联合创始人](https://www.linkedin.com/in/radutt/) [Grafana Labs](https://grafana.com/) 的 Raj Dutt ，Grafana 是开源观察平台 Grafana 的提供商。他们谈到在不同的数据类型和开源项目中，在可观察性、跟踪、度量和日志之间创建一个更加无缝的过渡。

“你有大量的集装箱。这些容器正在以越来越快的速度发射遥测信号。这些集装箱来来往往。所以它们在同一时间非常多变。所以这非常复杂。Dutt 说:“要全面了解您的基础设施和应用程序的状况，真的很难。"可观察性实际上是对系统行为的深入了解."

这一集讲述了六岁的 Grafana 的开源历史，以及它如何发展到支持 50 种不同的数据源，包括度量、日志和跟踪。以及它如何从内部部署发展为云产品。Dutt 说，总是开源的好处在于人们可以在任何他们想去的地方运行它。

[可观察性、分布式跟踪和 Kubernetes 管理，带有 Grafana 的 Raj Dutt](https://thenewstack.simplecast.com/episodes/observability-distributed-tracing-and-kubernetes-management-w-raj-dutt-of-grafana)

当 Grafana Labs 在 2017 年推出时，它发布了基于 Kubernetes 构建的 Grafana 托管版本，实现了跨云部署。Dutt 表示，这种托管的 Kubernetes 产品“真正允许我们将开发人员的创新集中在 Kubernetes 之上的层，而不是必须自己运行它。”

Grafana 实验室堆栈还包括 Grafana 的高度定制版本，以及其新的[YAML-替代 Tanka](https://grafana.com/blog/2020/01/09/introducing-tanka-our-way-of-deploying-to-kubernetes/) ，该 Tanka 使用 [JSONit](https://github.com/voormedia/jsonit) 作为代码来自动化 Kubernetes 基础设施。

这种基础设施的发展也允许 Grafana 实验室团队创建 [Loki](https://grafana.com/oss/loki/) 。Loki 是一个多租户、廉价、大容量的日志聚合系统，专门设计用于 Kubernetes 和 Prometheus。它的成本更低，因为它只索引日志屏幕，而不像其他聚合器那样索引全文日志行。

对 Dutt 来说，可观测性不是一个尺寸。这是关于建立你自己的可观察性栈，根据你的预算需要。对于 Grafana Labs 团队来说，这意味着一个为高度分布式的异步远程团队服务的开源堆栈，它是更加分布式的、更大的开源世界的一部分。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>