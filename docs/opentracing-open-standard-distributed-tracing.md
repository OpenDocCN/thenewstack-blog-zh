# OpenTracing:分布式跟踪的开放标准

> 原文：<https://thenewstack.io/opentracing-open-standard-distributed-tracing/>

日志帮助您了解您的应用程序正在做什么。几乎每个应用程序都为托管它的服务器生成自己的日志。但是在现代分布式系统和微服务环境中，日志是不够的。

我们可以使用像 ElasticSearch 这样的服务来收集一个应用程序的所有日志，当你只处理一个应用程序时，这就足够简单了。但是现在，应用程序更像是服务的集合，每个服务都生成自己的日志。由于每个日志都记录了服务的动作和事件，我们如何跨越这些服务来深入了解应用程序呢？

像这样的问题证明了为什么分布式跟踪正成为有效监控的一个要求，促使人们需要一个跟踪标准。

## 理论上的开放追踪

 [吉安卢卡·阿尔贝扎诺

Gianluca 是旧金山 InfluxData 驻意大利的站点可靠性工程师。作为 Docker 队长，他热衷于帮助团队使用持续集成、自动化和现代工具来改善他们的开发环境，以便更好、更快地工作。他信奉 DevOps 文化，是开源贡献者、博客作者和演讲者。他用 PHP、Go、Javascript 等语言编写代码。](https://www.influxdata.com/) 

尽管随着进程数量的增加，跟踪提供了对应用程序的可见性，但是到目前为止，为系统提供跟踪工具仍然是劳动密集型和复杂的。OpenTracing 标准改变了这一点，以最小的努力实现了分布式跟踪应用程序的检测。

2016 年 10 月，OpenTracing 成为[云原生计算基金会](https://www.cncf.io/)指导下的项目。在 CNCF 的管理下，OpenTracing 的目标是成为一个开放的、厂商中立的分布式系统检测标准。它为开发人员提供了一种跟踪线索的方法——跨接触点从头到尾跟踪请求，并大规模地理解分布式系统。

在 OpenTracing 中，跟踪讲述了在分布式系统中传播的事务或工作流的故事。跟踪的概念借用了科学界的一种工具，称为 [*有向无环图*](http://users.monash.edu/~lloyd/tildeAlgDS/Graph/DAG/) (DAG)，它将一个过程的各个部分从清晰的开始阶段划分到清晰的结束阶段。某些步骤组或中间的*跨度*可能是可重复的，但决不会像没有退出条件的“do 循环”那样无限期。

因此，这个上下文中的跟踪是由跨度组成的 DAG 命名的定时操作，表示跟踪中连续的工作段。分布式跟踪中的每个组件将贡献其自己的跨度。

现在您已经有了一些背景知识，下面的定义应该更有意义:跟踪是共享一个公共根的一组跨度。对于 OpenTracing，通过收集共享 TraceId 的所有跨度来构建跟踪。[ *编者按:[关于如何以这种方式收集跨度，OpenTracing 社区内仍有公开讨论](https://github.com/opentracing/specification/issues/24)。* ]

在这种情况下，span 是对应于特定远程过程调用的一组注释。每个跨度代表一个时间单位，并有自己的日志。span 上下文是一个键/值存储，可附加到特定的 span，您可以登录到该存储，以便更好地理解 span 所涉及的事件。基本上，跟踪是关于范围、进程间传播和活动范围管理的。

## 为什么 OpenTracing 的采用在增长

在[微服务架构](/category/microservices/)中，有比以往更多的应用程序相互通信。虽然应用程序性能监控非常适合在单个应用程序中进行调试，但是随着系统扩展到多个服务，您如何了解每个服务花费的时间、异常发生的位置以及系统的整体健康状况？特别是，您如何衡量服务之间的网络延迟——例如一个请求从一个应用程序到另一个应用程序需要多长时间？

进入分布式跟踪检测。随着基于云的环境中服务的更高级分布，跟踪将成为支持这些服务的云基础设施的关键部分。

如果您曾经在开发中使用过 Firefox 浏览器，您会知道当您打开它的浏览器控制台(Ctrl + Shift + J)时，您可以看到缓存中当前正在执行的所有组件，以及它们当前的运行状态。从某种意义上说，那是一种痕迹。

希望服务器端服务对跟踪标准的需求和客户端对跟踪标准的需求一样明显。我们特别需要 OpenTracing，因为有不同的语言和不同的库，每一种都可能使用自己的工具，可能发送不同的数据，可能访问自己的数据库。所以你很难从任何一个单一的组件中找到单一的痕迹。这一事实导致了对应用程序代码、库代码和各种系统的通用语言的需求。

## OpenTracing 用例

OpenTracing 文档为跟踪提供了一个通用定义:“位于应用程序/库代码和各种使用跟踪和因果关系数据的系统之间的一个薄薄的标准化层。”作为描述系统行为的标准机制，OpenTracing 将为应用程序、库、服务和框架提供一种“在不了解底层 OpenTracing 实现的情况下描述和传播分布式跟踪”的方式。这就是它的价值所在。

正如 GitHub 上所讨论的，OpenTracing 的常见用例包括:

*   **微服务** —例如，重建事务通过微服务架构的旅程。
*   **缓存** —确定请求是否命中缓存的故障排除。
*   **仲裁** —例如，跟踪单个进程的完整历史，并确定当多个服务并行而不是顺序地联系它时它的行为。
*   **消息总线监控** —确定队列中消息的适当跨度和分布，以确保它们触发适当的事件序列，同时确保某些消息简短、离散，并且永远不会成为数据泄漏的源头。

## InfluxData 对 OpenTracing 做了什么

认识到简化微服务平台故障排除的需求后， [InfluxData 决定在其](https://www.influxdata.com/blog/tracing-the-journey-of-a-transaction-as-it-propagates-through-a-distributed-system/) [Zipkin Telegraf 插件](https://github.com/influxdata/telegraf/tree/master/plugins/inputs/zipkin)中增加追踪功能。Zipkin 是一个分布式跟踪系统，有助于收集解决微服务常见延迟问题所需的计时数据。

Zipkin 使用 Cassandra 作为其所有痕迹的背景。我们发现对于 Telegraf 来说，收集踪迹，然后将它们的数据存储到 InfluxDB(一个本地的[时间序列数据库](https://www.influxdata.com/time-series-database/)中是很有用的。因为这些跟踪都有时间戳，所以 InfluxDB 是存储它们的更好选择。它针对时间序列数据进行了优化，并针对指标和事件进行了全新构建。如果您已经在 InfluxDB 中存储了指标，那么在那里存储您的跟踪也是有意义的，特别是因为您可以使用 Kapacitor(influx data 的本机处理引擎)来操作/交叉分析跟踪和其他指标。

在 InfluxData，我们使用我们构建的东西。为了验证我们自己的理论，我们正在我们的 [InfluxCloud](https://cloud.influxdata.com/) 服务中实现 OpenTracing。我们将很快分享一些关于实现的细节，以及它如何帮助我们进行故障排除。

OpenTracing 正受到许多公司的关注，因为开发人员想知道他们的应用程序中发生了什么。通过 OpenTracing，开发人员能够了解每个请求从哪里开始，到哪里去，以及在整个过程中发生了什么。掌握更多的知识可以让他们采取适当的行动。

您可以通过观看最近的 InfluxData [OpenTracing 网络研讨会](https://youtu.be/Sm3hVADls1o)了解更多信息。

[https://www.youtube.com/embed/Sm3hVADls1o?feature=oembed](https://www.youtube.com/embed/Sm3hVADls1o?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>