# InfluxDB 迁移到云原生架构

> 原文：<https://thenewstack.io/influxdb-moves-to-cloud-native-architecture/>

InfluxData 是一家提供 InfluxDB 时序数据库的公司，该公司专注于将其 TICK 堆栈(Telegraf、InfluxDB、Chronograf 和 Kapacitor)引入云原生架构，即运行在临时容器上的架构。

首席技术官和联合创始人[保罗·迪克斯](https://www.linkedin.com/in/pauldix/)、 [InfluxData](https://www.influxdata.com/) 说，他们的客户使用 TICK 作为服务，这种变化是必要的。这就产生了对多租户系统的需求，在这种系统中，工作负载可以从一个用户隔离到另一个用户。设置利用率限制和内存利用率限制的能力允许跨多个租户隔离工作负载。

“集装箱化的架构非常非常适合这种模式，”迪克斯在电话采访中说。

他说，InfluxDB 的 1.x 版本看起来像一个整体系统，实际上几乎所有数据库都是这样实现的。但是设计团队 2.0 从底层开始被容器化，使用 Kubernetes 作为基础设施。

迪克斯说，栈运行在亚马逊网络服务上。Kubernetes 是基础层，etcd 存储元数据，Kafka 用来写数据。其他一切都是 Kubernetes 内部创建的不同微服务。所有的特性都将是开源的，除了高可用性和扩展集群的代码，它们将在商业上可用。

## 什么是扁虱？

InfluxDB 创建于 2012 年，是一个用于实时指标和监控的 SaaS 应用程序。但是用户对基础设施更感兴趣，所以该公司开源了代码库，并随着时间的推移将其他组件构建到堆栈中。

Dix 说，数据库系统是 TICK Stack 的一个组件，TICK Stack 是一个处理时间序列数据的平台，旨在解决一些常见的数据问题。命名，收集，存储和查询，处理和监控，可视化。

这些组件是:

> T= [Telegraf](https://www.influxdata.com/time-series-platform/telegraf/) 一个时间序列数据收集器代理，用于收集和报告指标和数据。这是一个运行在所有服务器上的二进制程序。
> 
> I= InfluxDB，时间序列数据库片段。
> 
> C = [Chronograf](https://www.influxdata.com/time-series-platform/chronograf/) 是用于监控和仪表板的可视化部件。它包含处理堆栈组件的部分，包括监控和警报规则。
> 
> K = [Kapacitor](https://www.influxdata.com/time-series-platform/kapacitor/) 是实时流数据处理引擎。它提供基本的 ETL、异常检测、监控和警报。它适用于流和批处理模式监控，并向大约 20 个不同的系统发送警报，包括 Slack 和 PagerDuty。

## 去耦合是关键

Dix [在去年的一次播客中告诉 TNS](https://thenewstack.io/the-technical-architecture-behind-tick-a-time-series-analysis-platform-using-influxdb/) ,架构中的组件解耦是关键。设计团队为堆栈的不同部分创建了不同的服务，并将写入管道从索引管道、查询处理管道和监控管道中分离出来，从而允许每一个管道独立扩展。用户界面需要高速度，bug 搜索不需要那么多。

InfluxDB 的广泛用途带来了相应的各种工作负载需求。例如，查询处理。他们的许多用户在工作时都有实时仪表盘，但是一天下来会发生什么呢？停机时启动服务器是一种浪费。“将处理层与数据存储层分离意味着你可以拥有廉价的数据存储和非常灵活的短暂处理，”他解释道。

## 两种数据

迪克斯解释说，有两种时间序列数据。常规数据发生在固定的时间点，如传感器数据、服务器监控数据或 CPU 读数。不规则数据是事件驱动的，例如对股票市场中的 API 交易的单个请求。“我们希望我们的堆栈能够很好地处理常规和非常规数据，”Dix 说。

还有另一个维度需要考虑:冷热数据。热数据是在内存中和快速但昂贵的固态硬盘上易于查询的数据。另一方面，冷数据不太可能被访问，因此可以存储在较便宜的介质上，如亚马逊网络服务 S3 对象存储。

InfluxDB API 的工作原理是跨热数据和冷数据无缝提取数据。迪克斯说，如果你从冷存储中提取数据，可能需要更长的时间，但你不必编写代码来获取数据。

## Flux:新的查询语言

传统的数据库平台并不是 InfluxData 重新思考的唯一问题。Dix 花了一年时间编写 Flux，这是一种与 InfluxDB 配合使用的新查询语言。“我不认为处理数据的最佳语言是在 70 年代发明的，也不认为除了 SQL 之外还有什么更好的语言，”迪克斯说。

他承认，学习一门新语言需要时间，但代价是开发人员的生产率。他专门编写了 Flux 来管理时序数据。SQL 因返回最简单的时间驱动数据所需的代码量而臭名昭著。

“我们可以在语言中做一些事情，实际上使它变得更优雅，更容易使用，如果你试图编写一堆 SQL 查询的话，”迪克斯说。

他说，Flux 的结构使得开发者很容易向语言中添加新的功能。

他希望看到更多的查询工作负载在数据库本身中完成。例如，对于数据科学家来说，从数据库中查询数据，将其拉回本地机器，对其进行一些处理，然后将数据加载回来是很常见的。拥有一种真正的脚本语言是简化这一过程的一个步骤。

InfluxData 是新堆栈的赞助商。

由[科林·卡特](https://unsplash.com/photos/w1g2o4J_4Dg?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/search/photos/influx?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>