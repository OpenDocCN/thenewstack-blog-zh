# 正确解释和演示开放式遥测

> 原文：<https://thenewstack.io/opentelemetry-properly-explained-and-demoed/>

[OpenTelemetry](https://opentelemetry.io/) 项目提供供应商中立的集成点，帮助组织获得原材料——“遥测技术”——为现代可观测性工具提供燃料，并且在集成时花费最少的精力。但是 OpenTelemetry 对于那些使用他们最喜欢的可观测性工具但不完全理解它如何帮助他们的人来说意味着什么呢？OpenTelemetry 与 Kubernetes 的新手(过去几年中 KubeCon 的大多数与会者)和刚刚开始接触可观测性的人有什么关系？

[开启遥测正确讲解并演示](https://thenewstack.simplecast.com/episodes/opentelemetry-properly-explained-and-demoed)

[light step 开发人员关系负责人 Austin Parker](https://www.linkedin.com/in/austinlparker) 和 Splunk 产品管理总监 Morgan McLean 在本播客期间，在[kube con+CloudNativeCon 2022](https://events.linuxfoundation.org/gitopscon-north-america/)讨论 OpenTelemetry 项目如何创建演示服务，以帮助云原生社区成员更好地了解云原生开发实践并测试 OpenTelemetry 以及 Kubernetes、observability 软件等。

[https://www.youtube.com/embed/3avyfkSUMls](https://www.youtube.com/embed/3avyfkSUMls)

视频

在 DevOps 历史上的这一猜想中，围绕开发人员和运营团队的可观测性已经有了相当大的宣传，最近，人们更多地关注通过单个接口来帮助组合使用中的不同可观测性解决方案，为此，OpenTelemetry 已成为一个关键标准。

Parker 说，DevOps 团队今天需要 OpenTelemetry，因为他们通常使用许多不同的数据源进行可观测性过程。“如果你想要可观察性，你需要将数据转换并发送给任意数量的开源或商业解决方案，你需要一种通用语言来保持一致。每当我拥有主机、IP 地址或任何类型的元数据时，一致性都是关键，这就是 OpenTelemetry 所提供的。”

此外，作为一名开发人员或操作员，OpenTelemetry 用于为您的系统提供可观测性仪器，McLean 说。“OpenTelemetry 通过社区的力量来定义这些标准，并提供从人们使用的成千上万种不同的软件、硬件和基础设施组合中提取数据所需的组件，”McLean 说。

可观察性和 OpenTelemetry 虽然在概念上很简单，但使用起来确实需要一个学习曲线。为此，OpenTelemetry 项目发布了一个演示来提供帮助。它旨在更好地理解云本地开发实践，并测试 OpenTelemetry 以及 Kubernetes、observability 软件等。该项目的创建者说。

[OpenTelemetry Demo v1.0](https://github.com/open-telemetry/opentelemetry-demo/tree/v1.0.0) 通用版可在 GitHub 和 [OpenTelemetry 网站上获得。](https://opentelemetry.io/blog/2022/announcing-opentelemetry-demo-release/)该演示有助于学习如何向应用添加工具，以收集指标、日志和跟踪信息，从而实现可观察性。开源项目有很多指导，比如针对 Kubernetes 的 Prometheus 和针对分布式追踪的 [Jaeger](https://www.jaegertracing.io/) 。展示了如何熟悉 Grafana 等工具来创建仪表板。该演示还扩展到创建故障和使用 OpenTelemetry 数据进行故障排除和补救的场景。该演示是为初学者或中级用户设计的，可以设置为在 Docker 或 Kubernetes 上运行大约五分钟。

“演示是人们开始的一个很好的方式，”帕克说。“我们也看到我们的商业合作伙伴表现出了很大的热情，他们说‘我们将用它来展示我们的平台。’"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>