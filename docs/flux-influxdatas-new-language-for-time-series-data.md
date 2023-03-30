# Flux: InfluxData 时序数据的新语言

> 原文：<https://thenewstack.io/flux-influxdatas-new-language-for-time-series-data/>

那么，新的“东西”是一个为每个用例专门构建的数据库吗？这似乎就是亚马逊最近宣布的 [Timestream](https://aws.amazon.com/timestream/) 的情况，这是一个测试版的时间序列数据库，连同其区块链数据库 Quantum Ledger，也是测试版，使其[数据库的总组合达到 15 个](https://www.infoworld.com/article/3323385/database/aws-adds-blockchain-and-time-series-databases.html)。

时间序列数据库已经引起了市场新贵的特别关注，如 [TimescaleDB](https://thenewstack.io/timescaledb-focuses-query-power-scale/) ，Iguazio， [eXtremeDB](http://www.mcobject.com/ent) 和 [FaunaDB](https://thenewstack.io/faunadb-harnesses-serverless-cloud/) 。并且 [DB-Engines](https://db-engines.com/en/ranking/time+series+dbms) 将监控工具 [Prometheus](https://prometheus.io/) 列为最受欢迎的时间序列数据库。

在这些项目中，实现 SQL 伸缩一直是一项主要任务，旨在跟踪随时间的变化。Redmonk 分析师 [Rachel Stephens](https://redmonk.com/team/rachel-stephens/) 在一份关于时序数据库市场的[报告](https://redmonk.com/rstephens/2018/04/03/the-state-of-the-time-series-database-market/)中解释说，高数据量需要高性能的写入和高性能的读取。

她指出，时序数据库往往不擅长处理高基数数据，因此用户可能还需要深度调试或跟踪功能。此外，添加 Kafka 或 Spark 流媒体基础设施可以帮助用户从短暂的数据中提取额外的功能。

在努力为开发人员解决处理时间序列数据的难题时， [InfluxData](https://www.influxdata.com/) 创造了一种新的查询和脚本语言，叫做 [Flux](https://www.influxdata.com/blog/why-were-building-flux-a-new-data-scripting-and-query-language/) ，它将[查询](https://thenewstack.io/optimizing-data-queries-time-series-applications/)和存储解耦。

作为一种函数式语言，它允许用户通过一组对数据的函数转换来定义复杂的查询。它还允许用户用用户定义的函数重新组合部分查询函数，允许他们创建常用功能的快捷方式。

InfluxData 创始人兼首席技术官保罗·迪克斯(Paul Dix)在一篇博文中表示:“开发者一遍又一遍地创建相同的查询，效率非常低。”。“我们希望常见的查询和用例得到表达和共享，这样我们就不会在 InfluxDB 中重复创建每个单独的查询。因为我们有一个共同的数据收集器(Telegraf)和一个共同的模式，所以社区应该有可能建立可重复使用的查询和功能。”

## 不仅仅是一种查询语言

在接受新堆栈的采访时，迪克斯说 [Flux](https://thenewstack.io/influxdb-moves-to-cloud-native-architecture/) ，以前叫做 IFQL，不仅仅是一种查询语言。

“它更像一种脚本语言——这是与 SQL 的主要区别。这是一种声明式查询语言。你可以在语言中有更复杂的行为，允许你做更复杂的分析，数据修改，ETL 任务，所有这类事情，他说。

这实际上是两件不同的事情:语言本身和查询引擎。

“我们将语言从引擎中分离出来，因此添加其他语言支持也在我们的计划之中。该引擎只是将一个有向无环图作为 JSON 对象，它知道如何执行，”他说。

解析器将解析查询，它看起来像一种函数式脚本语言，定义了您希望如何处理时间序列数据，然后将它解析为 DAG，引擎将在任意数量的流入服务器上执行该 DAG。该公司计划让它能够查询与时间序列任务配对的其他服务器，因此潜在地，你可以将存储在 MongoDB、Postgres 或其他什么中的一些数据配对，并将它们与存储在 Influx 中的时间序列数据配对。

可视界面将代表一个数据流。

“在幕后，在引擎中，我们可能不会完全按照指定的方式运行它，因为我们希望进行优化，但我们不希望程序员不得不考虑如何构建查询以获得最佳性能。我们希望他们指定数据流，然后我们将保持它的语义，并尽可能快地优化它，”他说。

如果您想对一组数据进行三次或四次转换，虽然在 SQL 中可以做到，但向其他程序员表示可能并不容易，也不是可读性最好的方法。

[https://www.youtube.com/embed/f5gVpHHKfUM?start=2&feature=oembed](https://www.youtube.com/embed/f5gVpHHKfUM?start=2&feature=oembed)

视频

“…我们不是为了简洁而优化它。我们正在优化它的可读性。我们所有的东西都是用 Go 编写的，我认为 Go 编程语言最伟大的一点就是它为可读性做了优化。…作为一名程序员，你读的代码比你写的多 100 到 1000 倍，所以优化可读性实际上是让程序员在团队中更有生产力的最佳方式，”迪克斯说。

他说，Flux 的优势在于进行转换，比如在一组基础数据上开窗口。

“对于时间序列用例，你可以把数据窗口变得非常复杂。如果你想了解服务器性能，你可以说，看看从周一到周五开市到闭市的时间序列数据，然后进行计算。或者是过去一个月的周一至周五，当市场开放时，进行计算。那种开窗，我们就成了一等公民。有了 SQL，我相信你可以做到，但通常这类查询会变得非常非常困难，”迪克斯说。

Dix 说，该语言当时被称为 IFQL，一年前首次随开源 v. 1.4 一起发布，并根据社区的反馈进行了大量修改。虽然作为 InfluxDB 1.7 和 2.0 的一部分，Flux 也可以独立运行。

在最近一期的[节目中，新堆栈制造商](https://thenewstack.io/couchbases-ravi-mayuram-on-the-future-of-databases/)、[高级工程副总裁兼](https://www.linkedin.com/in/ravimayuram/) [Couchbase](https://www.couchbase.com/) 首席技术官 Ravi Mayuram 谈到了 Flux 与 SQL 的对比。

InfluxData 计划建立一个包含输入和输出插件的模型，因此除了能够从其他来源引入数据之外，您还可以将数据发送到其他地方。

“您可以获得查询结果，而不是将结果返回给用户，您可以将结果发送给第三方服务—发送给另一个数据库或消息队列，或者您可以将结果直接发送回 InfluxDB。这些是数据流问题，你可以在一些用例中看到，人们希望监控某样东西，然后基于此将输出发送给其他东西。输出插件将使语言中的函数能够调用它。，”迪克斯说。

Grafana 和 [Sensu](https://monitoringlove.sensu.io/influx) 监控插件已经上市。

TNS 执行主编 Joab Jackson 对本文有贡献。

InfluxData 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>