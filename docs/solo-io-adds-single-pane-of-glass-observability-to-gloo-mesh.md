# Solo.io 为 Gloo Mesh 增加了“单一窗口”的可观察性

> 原文：<https://thenewstack.io/solo-io-adds-single-pane-of-glass-observability-to-gloo-mesh/>

Solo.io 管理多个 Istio 服务网格的软件正在获得一个统一的界面，该公司声称可以跨多个集群查看。

带有 [Gloo Mesh](https://www.solo.io/products/gloo-mesh/) 的“单一窗格视图”多集群可观测性作为普罗米修斯监控工具和 Istio 顶部的附加层。Gloo Mesh 的可观察性功能收集在多个不同环境的多个集群上运行的微服务的指标、日志记录和跟踪。在网络层面，它旨在为数百种不同的微服务提供更统一的可观察性数据视图，以便更快地修复错误并帮助提高网络性能。

此前，许多 DevOps 团队都在与“可观察性孤岛”作斗争，[埃里克·弗里伯格](https://www.linkedin.com/in/efrieberg)， [solo.io](https://solo.io?utm_content=inline-mention) 的首席营销官告诉 New Stack。“我们所做的是将多星系团的所有可观测性集中在一起，以便看到所有的相互作用，”弗里伯格说。

这种单视图可观察性被视为解决与跨多个集群和不同环境部署微服务相关的日益增加的复杂性的一种方式。

“我们需要了解这些应用程序之间实际发生了什么，”全球首席技术官 Christian Posta 在本周举行的公司虚拟用户会议的主题演讲中说。“当我们转向微服务时，我们已经在服务之间转移了一些复杂性，我们需要观察和了解正在发生的事情，特别是当事情出错时，以便我们可以纠正它们。”

solo.io 的后端数据工程师 Harvey Xia 在他的演讲中详细描述了 Gloo Mesh 如何用于收集多个集群的遥测和日志数据。Gloo Mesh 集成了 Istio，以便配置 Envoy 代理，将 Gloo Mesh 代理视为度量和访问日志的同步。当特使代理发出度量时，它被发送到 Gloo 网格代理，该代理又将数据转发到 Gloo 网格服务器。“这个过程将所有的可观测性数据聚集到一个地方，”夏说。

夏还描述了 Gloo Mesh 的可观测性功能如何集成其他工具和接口，如广受欢迎的用于可视化的 [Grafana](https://grafana.com/) ，或用于收集运营指标的 [OpenTelemetry](https://opentelemetry.io/) 框架。指标被聚合到一个位置，以允许系统范围的多集群查询，并将聚合的数据源集成到用户界面(UI)中。

“因此，如果用户已经有了一个复杂的[普罗米修斯联盟设置]，他们想使用它，他们只需将其作为一个源插入，然后利用 Gloo Mesh 作为其用户界面，”夏说。“或者，如果用户已经有了自己喜欢的用户界面，如 [Datadog](https://www.datadoghq.com/) 或 Grafana，他们可以将 Gloo mesh 视为聚合指标的真实来源，并将其直接插入他们的用户界面。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>