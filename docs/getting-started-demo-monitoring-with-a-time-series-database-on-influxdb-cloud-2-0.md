# 入门演示:在 InfluxDB Cloud 2.0 上使用时序数据库进行监控

> 原文：<https://thenewstack.io/getting-started-demo-monitoring-with-a-time-series-database-on-influxdb-cloud-2-0/>

[InfluxData](https://www.influxdata.com/) 赞助了这次演示。

[https://www.youtube.com/embed/zr5V3IhOuUA?feature=oembed](https://www.youtube.com/embed/zr5V3IhOuUA?feature=oembed)

视频

创建和管理时间序列数据库，以及一般的数据库，仍然经常被认为是一件非常困难和复杂的事情。但是 [InfluxData](https://www.influxdata.com/) 并不这么看——事实上，在这个演示中，InfluxData 的产品营销总监 [Chris Churilo](https://www.linkedin.com/in/chrischurilo) 展示了如何开始设置新发布的 InfluxDB Cloud 2.0，这是一个无服务器时间序列平台即服务(PaaS)，只需点击几下鼠标。

其概念是，通过 InfluxData 的 [Chronograf](https://www.influxdata.com/time-series-platform/chronograf/) [](https://www.influxdata.com/time-series-platform/chronograf/)仪表盘和 [Telegraf](/monitoring-windows-services-with-grafana-influxdb-%E2%80%8Eand-telegraf/) 插件，InfluxDB Cloud 2.0 以及 InfluxDB 可以让您在家庭使用环境中监控、跟踪和分析此类数据点，如电力消耗或室温。在很大程度上，该平台的力量还可以应用于根据世界银行每秒可能需要的数千万个数据点来监控和预测趋势。具体到 InfluxDB Cloud 2.0，该平台是无服务器的，这意味着用户可以部署它，而不必设置和管理存储或担心管理服务器基础架构。使用模式是现收现付，但要开始，你可以免费试用一下，不需要信用卡。

Churilo 通过点击 Get InfluxDB 下的[云图标](https://www.influxdata.com/get-influxdb/)来浏览 InfluxData 的网站。添加您的信息后(无需输入信用卡信息。对于免费版)，您可以设置名为 buckets、dashboards 和 alerts 的数据库。

一个推荐且有趣的开始方式是使用 InfluxDB Cloud 2.0 来收集和监控您的笔记本电脑的性能数据。正如 Churilo 在演示中展示的，你点击 Load Your Data 图标，系统会提示你设置 Telegraf 插件。如果您不熟悉 Telegraf，或者不熟悉其中的任何流程，屏幕上会提供文档和进一步阅读的相关链接以及简短提示。

“好的方面是团队确实做得很好，确保文档分散在整个用户界面中，”Churilo 说。“因此，如果我真的不知道什么是 Telegraf，我可以很容易地进入并查看这个小提示，或者我可以开始深入了解有关 Telegraf 的指南。”

InfluxDB Cloud 2.0 的一个关键特性是平台的底层 [Flux 编程语言](https://github.com/influxdata/flux) InfluxData 发布，为用户提供更多自由来定制平台的分析功能以满足他们的特定需求。主要基于 JavaScript，熟悉 JavaScript 的用户应该能够在几分钟内掌握它的基本命令。

通过 UI，当平台通过脚本编辑器执行查询时，还可以访问实时使用的相关通量代码。丘里洛说，这个选项可以让你“实际看到通量的样子”。“对我来说，这是一种更容易学习的方式，”因为你可以实时跟随图形用户界面下的所有 Flux 命令，“丘里洛说。

虽然这个演示涉及一个相对简单的应用程序，但如上所述，DevOps 可以利用该平台来构建大东西，无论是监控与桥梁结构数据相关的数据还是主要大都市地区的用电情况。

“它的本质是，我们希望确保开发人员能够尽快启动并运行和使用对他们的开发工作非常重要的工具，”Churilo 说。“我们不希望人们不得不担心所有这些配置文件，并试图找出如何开始。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>