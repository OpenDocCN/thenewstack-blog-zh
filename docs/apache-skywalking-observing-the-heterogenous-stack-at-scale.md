# 阿帕奇太空行走:观测大规模的异质堆栈

> 原文：<https://thenewstack.io/apache-skywalking-observing-the-heterogenous-stack-at-scale/>

[Tetrate](https://www.tetrate.io/) 赞助本帖。

 [泰瓦普拉特

Tevah 是 Tetrate 的内容作者，也是*天行者*的编辑。](https://www.linkedin.com/in/tevahp/) 

现代 DevOps 的可观察性问题是常见的:随着企业转向微服务、容器化、多语言 RPC 框架和服务网格，用户越来越需要了解高度复杂的分布式架构和应用程序之间的依赖关系。 [Apache SkyWalking](https://skywalking.apache.org/) ，一个应用性能监视器(APM)和可观察性平台，是一个解决这种需求的开源项目——有或没有服务网格。

像其他可观察性工具一样，Apache SkyWalking 允许系统管理员跟踪系统健康状况，并了解大量相互依赖的服务之间发生了什么。大型企业的内部系统通常会有许多运行数百项服务和数千个实例的子系统。SkyWalking 旨在帮助运营和维护团队确定请求缓慢的原因和位置，提醒他们异常的系统性能，提供跨应用程序的点对点、语言无关的指标，并有效监控整体系统健康状况。

 [周

李赞是四重奏的工程师和特使维护者。](https://www.linkedin.com/in/lizanzhou/) 

异构性使 SkyWalking 与众不同，它为收集、聚合和特定于域的查询系统提供了一个整体平台——不同系统的代理以及无缝集成服务网格的潜力。组织可能会选择使用 SkyWalking，这样他们可以保持一致性，并对传统和云原生架构使用相同的 APM 系统。

Apache SkyWalking 是吴声作为一个个人项目开始的，从那时起迅速发展，今天已经有 375 个贡献者。它以字面上的“可观察平台”命名，即大峡谷西部的玻璃桥天桥，它提供了自然地标的鸟瞰图。

它最初只是一个培训项目，旨在帮助同事了解分布式系统中出现的问题，后来从一个纯粹的跟踪系统发展成为一个功能齐全的 APM 系统和可观察性分析平台，目标是大规模运行在大型企业中的微服务和分布式服务。SkyWalking 是一个顶级的 Apache 项目，监控大型分布式系统，包括阿里巴巴、华为、腾讯、百度、中国电信以及各种银行和保险公司。在许多情况下，它每天收集和分析数十亿条带有指标的跟踪。

“空中行走保证了生产中高负荷条件下的可用性，”吴声说。“它的用户正在寻求数百亿级的常规处理能力、轻量级处理、可插拔性和易于定制。”

SkyWalking 的功能属于可观察性的[【三大支柱】](https://thenewstack.io/how-the-3-pillars-of-observability-miss-the-big-picture/):度量、日志和追踪。从根本上来说，SkyWalking 是一个致力于应用程序性能的 APM 工具，允许开发、运营和维护团队了解他们的系统和实际运营之间的关系。

指标为您提供了应用程序性能的汇总数据，例如服务数量、平均响应时间、吞吐量等。您还可以根据个人业务需求，向 SkyWalking UI 添加自定义指标。日志提供了事件或错误消息的记录。跟踪向您显示一段时间内的事件行为，以便您可以从头到尾跟踪一个请求，并识别系统缺陷和错误。

SkyWalking 的分布式拓扑图使用 STAM ( [流拓扑分析方法](https://wu-sheng.github.io/STAM/))，从显示无法从简单度量 SDK 中提取的关系的轨迹中分析拓扑。在服务网格中使用， [SkyWalking 可以通过 Envoy 的访问日志服务(ALS)支持可观察性](https://www.tetrate.io/blog/observe-service-mesh-with-skywalking-and-envoy-access-log-service/)——代理扩展通过 Envoy 发出所有请求的详细访问日志。SkyWalking 为您提供了各种使这些数据变得有用和可操作的方法:快速查看系统中慢点的延迟条形图列表视图，由用户指定的服务级别目标(SLO)阈值触发的警报，或定位性能问题边界的拓扑图，等等。

天行健的架构包括四个关键部分:

*   代理人；即提供度量和跟踪的其他项目的语言代理或协议。
*   可观测性分析平台(OAP)；一个高度模块化的轻量级分析程序，由一个接收器和用于流处理和查询的内核组成。
*   存储。
*   通过标准 GraphQL 协议查询和显示数据的 UI 模块。

最近的 SkyWalking 更新专注于使该项目越来越轻量级、可插拔和可定制，具有强大的可视化功能，并扩大了监控[其自身性能](https://www.tetrate.io/blog/skywalking8-1-release/)和(最近的)[浏览器数据](https://www.tetrate.io/blog/whats-new-with-apache-skywalking-8-2-browser-monitoring-and-more/)的范围。

对于网格采用者，Apache SkyWalking 与 Istio 和 Envoy 集成，并内置于服务网格管理平台 [Tetrate 服务桥](https://www.tetrate.io/tetrate-service-bridge/)。

关于空中漫步的更多信息，你可以尝试互动的[演示](http://skywalking.apache.org/)或者下载[的免费电子书](https://www.tetrate.io/apache-skywalking-ebook-tetrate/)、*空中漫步在行动中:你的大规模观测指南*。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>