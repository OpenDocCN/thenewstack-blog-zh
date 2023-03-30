# InfluxDB 现在扩展到云上的“随规模付费”模式

> 原文：<https://thenewstack.io/influxdb-now-extends-to-a-pay-as-you-scale-model-on-the-cloud/>

[InfluxData](https://www.influxdata.com/) 赞助了这个播客。

曾经主要为金融行业保留的时间序列数据库正日益成为许多组织的必备工具。例如，传统的 SQL 数据库不是为每秒处理数千或(在许多情况下)数百万个数据点而设计的。但是时间序列数据库可以监控、跟踪、分析和吸收这些数据，用于预测应用、实时分析和商业智能。这些用例通常包括应用、服务器或网络监控，或者针对工业或物联网数据。

然而，许多组织面临着无法负担时间序列数据分析所需硬件基础设施的难题。或者他们的大部分操作都是基于云的，他们面临着缺乏可行的替代方案。作为解决方案，InfluxData 推出了 InfluxDB Cloud 2.0，这是首个无服务器时间序列平台即服务(PaaS)。

在本期 New Stack Makers 播客中， [InfluxData](https://www.influxdata.com/) 的联合创始人兼首席技术官[保罗·迪克斯](https://www.linkedin.com/in/pauldix)讨论了 InfluxDB Cloud 2.0 以及时序数据库如何发展到需要基于云的替代方案的地步。

[influx db 现在如何扩展到云上的“按需付费”模式](https://thenewstack.simplecast.com/episodes/how-influxdb-now-extends-to-a-pay-as-you-scale-model-on-the-cloud)

在许多方面，InfluxDB Cloud 2.0 是正在进行的时序数据库故事中的重要一章。对于许多组织来说，编写出了名的困难的 SQL 数据库服务器的日子已经一去不复返了。时间序列数据平台不仅变得更加强大，而且更加易于使用。例如，今天，一个人使用 InfluxDB 和 [Grafana](https://grafana.com/) 仪表盘和 [Telegraf](https://thenewstack.io/monitoring-windows-services-with-grafana-influxdb-%E2%80%8Eand-telegraf/) 可以相对容易地跟踪[家庭监控数据](https://thenewstack.io/how-i-created-a-telegraf-plugin-to-monitor-solar-panels/)，其准确度可以达到一家大型银行监控和预测数百万个数据点以做出衍生预测的水平。基于云的选项使该平台更加易于访问。

InfluxDB Cloud 2.0 是 InfluxData 在过去六年的开发工作中推出的无服务器选项。InfluxData 一直致力于解决数据收集、存储、可视化和监测的挑战，将时间序列数据处理到单一平台中。“使用 InfluxDB 2.0，我们希望将堆栈折叠成一个内聚的整体，作为一个易于使用的 API，”Dix 说。

对于传统的时序平台，DevOps 必须预先选择并投资于内存和 CPU、服务器、磁盘空间和其他基础架构，并确定“我如何支付所有这些费用？”迪克斯说。“无服务器模式的好处是[他们]实际上只为[他们使用的]东西付费。这就是我们希望 InfluxDB Cloud 2.0 实现的目标。我们想让人们不必预先考虑他们需要什么样的规模，而是能够(根据需要)进行扩展。”

InfluxData 随 InfluxDB Cloud 2.0 发布的一个关键特性是 [Flux 编程语言](https://github.com/influxdata/flux)。迪克斯说，创建 Flux 是“我们的一项重大努力”，它“最初是一种查询语言，因为我们意识到人们希望将更复杂的分析和数据分析推送到平台上，”迪克斯说。“我们需要一个完整的东西……并且能够定义各种定制逻辑。我们希望实现的另一件事是让人们能够连接到第三方系统，要么将数据拉入他们的时间序列数据分析，要么将数据推出，”迪克斯说。“所以我们创造了一种叫做 Flux 的新语言。这是整个 2.0 产品的核心组成部分。”

Dix 说，由于它以 JavaScript 为基础，以前写过 JavaScript 的人可以在 15 分钟内学会 Flux 的语言结构。“我们早期对[Flux]语言和整个平台的目标之一是，我们希望用户能够进入并能够使用平台，而不必实际学习 Flux，”迪克斯说。Dix 说，这个想法是为了让用户“只需点击鼠标”就能从他们的数据中获取情报。“然后，如果他们想要更高级的功能，那么他们可以使用其他更高级的工具[掌握] Flux，”迪克斯说。

Dix 说，InfluxDB Cloud 2.0 的主要想法是创建一个平台，“开箱即用，拥有你需要的所有组件，因此[你]不必处理将它们捆绑在一起的问题”。“无服务器部分实际上就是这样一个想法，你可以定义一个 Flux 脚本，你可以告诉平台运行它，”迪克斯说。“你不必担心我将它部署到多少台服务器上，或者我如何[扩展它]，”迪克斯说。

### 在这个版本中:

[1:02:](https://thenewstack.simplecast.com/episodes/how-influxdb-now-extends-to-a-pay-as-you-scale-model-on-the-cloud?t=1:02)  什么是时间序列数据，在过去几年中，这些类型的平台在哪里、如何以及为什么发挥作用？
[6:02:](https://thenewstack.simplecast.com/episodes/how-influxdb-now-extends-to-a-pay-as-you-scale-model-on-the-cloud?t=6:02) 您能解释一下最近发布的 InfluxDB Cloud 2.0 如何解决了其中的一些问题，以及有什么新功能吗？
[8:31:](https://thenewstack.simplecast.com/episodes/how-influxdb-now-extends-to-a-pay-as-you-scale-model-on-the-cloud?t=8:31) 你能再给我一些关于 Flux 的信息吗？词根是什么——也许它与其他语言有相似之处？
[16:58:](https://thenewstack.simplecast.com/episodes/how-influxdb-now-extends-to-a-pay-as-you-scale-model-on-the-cloud?t=16:58) 单二进制配置如何发挥作用？这有什么重要的？
[21:29:](https://thenewstack.simplecast.com/episodes/how-influxdb-now-extends-to-a-pay-as-you-scale-model-on-the-cloud?t=21:29) 开源组件，协作——这个版本的输入是什么，如果有的话？
[24:50:](https://thenewstack.simplecast.com/episodes/how-influxdb-now-extends-to-a-pay-as-you-scale-model-on-the-cloud?t=24:50) 有没有一个新兴的用例场景，在 InfluxDB 2.0 云的帮助下变得可能，而这在三年前是不可能的，现在已经出现了？

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>