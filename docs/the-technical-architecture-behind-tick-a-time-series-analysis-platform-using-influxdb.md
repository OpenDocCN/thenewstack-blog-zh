# 使用 InfluxDB 的时序分析平台 TICK 背后的技术架构

> 原文：<https://thenewstack.io/the-technical-architecture-behind-tick-a-time-series-analysis-platform-using-influxdb/>

[TICK 背后的技术架构，一个使用 InfluxDB](https://thenewstack.simplecast.com/episodes/the-technical-architecture-behind-tick-a-time-series-analysis-platform-using-influxdb) 的时间序列分析平台

TICK 是一个时间序列分析平台，可以积累、分析和处理时间序列数据，它是新一集 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客的焦点，该播客由 [Paul Dix](https://www.linkedin.com/in/pauldix) 、 [InfluxData](https://www.influxdata.com/) 联合创始人兼首席技术官主讲。

[TICK 栈](https://www.influxdata.com/time-series-platform/)由 [Telegraf](https://github.com/influxdata/telegraf) 、 [InfluxDB](https://www.influxdata.com/time-series-platform/influxdb/) 、 [Chronograf](https://www.influxdata.com/time-series-platform/chronograf/) 和 [Kapacitor](https://github.com/influxdata/kapacitor) 组成，从底层开始设计用于处理指标和事件。“服务器监控和应用性能监控是一个很大的使用案例。人们用它进行实时分析。我们已经看到财务人员构建实时风险仪表板。另一个是物联网的传感器数据，”迪克斯说。

应用程序开发人员将代码发送到 InfluxDB 进行监控。迪克斯指出，手工购物平台 Etsy 的流量体现了所需的指标跟踪。  InfluxDB 本身是用 [Go](https://golang.org/) 编写的，大量使用了它的剖析特性。

“围棋太棒了。他们的每个版本都改进了垃圾收集器，提高了性能，”Dix 补充道。

在商业方面，InfluxData 推出了一款横向扩展集群产品。InfluxData 还提供其数据库的企业版，使用户能够拥有无限数量的数据节点来处理和存储查询。

[https://www.youtube.com/embed/Yx8U8x6YKk4?feature=oembed](https://www.youtube.com/embed/Yx8U8x6YKk4?feature=oembed)

视频

### 在这个版本中:

[0:37:](https://thenewstack.simplecast.com/episodes/the-technical-architecture-behind-tick-a-time-series-analysis-platform-using-influxdb?t=0:37) 对 InfluxData 的介绍。
[3:29:](https://thenewstack.simplecast.com/episodes/the-technical-architecture-behind-tick-a-time-series-analysis-platform-using-influxdb?t=3:29) 用时序指标查询电报中的 TICK 栈。
[4:21:](https://thenewstack.simplecast.com/episodes/the-technical-architecture-behind-tick-a-time-series-analysis-platform-using-influxdb?t=4:21) 探索 InfluxDB 和 TICK stack 用例。
[9:38:](https://thenewstack.simplecast.com/episodes/the-technical-architecture-behind-tick-a-time-series-analysis-platform-using-influxdb?t=9:38)TICK 栈的技术架构。
[11:33:](https://thenewstack.simplecast.com/episodes/the-technical-architecture-behind-tick-a-time-series-analysis-platform-using-influxdb?t=11:33) 为什么解耦是扩展的关键。
[13:28:](https://thenewstack.simplecast.com/episodes/the-technical-architecture-behind-tick-a-time-series-analysis-platform-using-influxdb?t=13:28) 时序数据如何对基于事件的架构有好处。

InfluxData 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>