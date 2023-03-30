# 蜂巢度量:如何在监控和可观察性之间架起桥梁

> 原文：<https://thenewstack.io/honeycomb-metrics-how-to-bridge-the-gap-between-monitoring-and-observability/>

新的[蜂巢](https://www.honeycomb.io/?utm_content=inline-mention)度量可观测性平台提供了一个单一的界面，在传统监测和[现代可观测性](https://thenewstack.io/monitoring-and-observability-whats-the-difference-and-why-does-it-matter/)之间架起了一座桥梁。

Honeycomb 的主要开发者倡导者、OpenTelemetry 的治理委员会成员 [Liz Fong-Jones](https://www.linkedin.com/in/efong) 将可观测性定义为一种“社会技术能力”，描述了 Honeycomb 的可观测性平台以前如何局限于通过基于事件的模型提供可观测性，使用本地格式的跟踪和日志，但要求用户将时间序列指标转换为事件。

Fong-Jones 在接受新堆栈采访时表示:“客户一直表示，除了应用程序跟踪，他们还希望在一个屏幕上获得系统指标的可见性。“这就是我们在这个最新版本中所做的事情，我们围绕什么是可观察性的信息没有改变。相反，它可以为人们提供一套更好的功能，将多种技术集成在一起。”

Honeycomb Metrics 今天在 Honeycomb 的用户大会上推出，目前正在面向 Honeycomb 企业客户进行公测。

除了结合可观察性数据和系统检查的监控指标，Honeycomb Metrics 还提供了 Honeycomb CTO 和联合创始人 [Charity Majors](https://www.linkedin.com/in/charity-majors) 在一次采访中所描述的“通往过去的桥梁”。

“现在，人们已经积累了 20 到 30 年的关于他们系统的度量数据，并且已经为理解像度量这样的事情建立了工具，”Majors 说。“许多人在开始时不想从头开始，他们想引进他们熟悉的东西，使用他们熟悉的术语。这是通向更好的基于事件的世界的一座非常好的桥梁……”

[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉新堆栈，桥接系统度量和可观察性可能有助于减轻特别明显的痛点。

“Honeycomb 新的可观察性方法旨在将软件开发人员从他们日常生活中最悲惨和低效的部分中解放出来:需要在基础设施指标和他们的应用程序代码之间建立联系，”他说。“从堆积如山的不相关基础设施事件和警报中剔除，以确定特定基础设施问题和新生产代码之间有意义的关联，这通常会严重浪费开发人员的时间。这种无法轻松地将代码与性能和可用性指标联系起来的能力，也是软件开发人员不愿采用公司同事使用的可观察性平台的核心原因。”

与其他替代方案相比，Honeycomb 使开发人员能够以一种概念上不同的方式来观察可观测性。Honeycomb Metrics 是面向服务级别对象(SLO)的，因为它提供基于预设参数的信息，这些参数指示应用程序在构建和后期部署过程中是否符合 SLO 标准。因此，如果云服务器上出现内存泄漏或其他基础设施问题，系统不会发送警报，但它会确定应用程序何时以及为什么不符合 SLO 参数。

关于 SLO，Fong-Jones 说，“我们已经用蜂巢矩阵定义了测试客户的成功标准”。在用户会议上的一次演示中，当使用一个新的查询功能时，Fong-Jones 设置了 SLO，以便在不到两秒钟的时间内返回一个 API 数据查询。“如果返回结果的时间超过两秒，这对[用户]来说是一种糟糕的体验，我们希望将这些查询与他们的错误逻辑相比较——慢是新的下降趋势。”

然而，衡量系统和基础设施性能的指标当然不会过时。例如，Honeycomb 产品营销高级总监 George Miranda 说，度量标准“适合你关心基础设施中发生的事情，但只是因为它影响了你的代码[执行]的方式”。

“我们在产品中构建指标的方式只是一种快速关联机制，我们从用户那里发现的是，他们仍然希望获得可观察性体验，并希望专注于影响他们用户的因素，”米兰达说。“因此，我们不再需要查看传统的指标和监控工具来确定是否存在基础架构问题，现在我们可以在产品内部向他们展示这一点，因此他们现在没有理由继续使用那些传统的监控系统来涵盖该使用情形。”

虽然过去 DevOps 团队成员可以使用特殊的技术和变通方法收集一些指标，以便将它们放入 Honeycomb 的可观测性平台，但 Honeycomb Metrics 现在支持直接接收它们。它通过不同的标准做到这一点，并且还将用于调试目的的指标集成到用户界面(UI)中。有了 OpenTelemetry——一个[云本地计算基金会(CNCF)](https://cncf.io/?utm_content=inline-mention) 供应商中立的框架，提供不同工具之间的互操作性——Honeycomb Metrics 可以直接从 open telemetry 或从其他来源收集指标数据，如[亚马逊网络服务(AWS)](https://aws.amazon.com/?utm_content=inline-mention) [CloudWatch](https://aws.amazon.com/fr/cloudwatch/) 、 [StatsD](https://github.com/statsd/statsd) 和 [Prometheus](https://prometheus.io/) 。

在 hnycon 的主要主题演讲中，Fong-Jones 演示了如何使用 OpenTelemetry，用户可以添加自定义工具来跟踪所有单个函数调用的跨度。除了现有的跟踪功能来了解应用程序的行为之外，Honeycomb Metrics 还允许用户快速查看有关运行这些应用程序的底层系统的数据，而在此之前需要花费时间和人力来收集这些数据。Fong-Jones 说，这是“除了我们对每一个请求都使用自动仪器之外的补充”。通过让工程团队在他们的系统级度量数据旁边看到应用级可观测性数据，Honeycomb 现在帮助他们确保新的应用特性是生产就绪的。

“这意味着我有足够的遥测技术，因此我知道我的生产服务行为如何变化，以及哪些用户受到影响，”Fong-Jones 说。“如果他们的性能因为任何原因受到负面影响，我需要知道我在产品代码中寻找什么。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>