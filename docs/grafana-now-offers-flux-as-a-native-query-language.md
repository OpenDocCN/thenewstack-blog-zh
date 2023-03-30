# Grafana 现在提供 Flux 作为本地查询语言

> 原文：<https://thenewstack.io/grafana-now-offers-flux-as-a-native-query-language/>

作为 6.0 版全面升级的一部分，开源的 Grafana 可视化分析软件现在支持时间序列数据的 Flux 查询语言，最初是作为一个插件，但很快就会成为 T2 influx db T3 时间序列数据库的默认查询语言。

Grafana 软件工程师 [Jacob Lisi](https://www.linkedin.com/in/jacob-lisi-26479993/) 上周在 InfluxData 的 [InfluxDays 活动](https://influxdays.com/new-york-2019/schedule/)上对一群人说:“Flux 非常强大，与当今市场上的其他时间序列数据库查询语言相比，它远远超过了它们。Flux 和 InfluxDB 都是由 InfluxData 管理的开源项目。"它的查询能力独树一帜。"

流行的可视化软件的认可有助于在一个长期由 SQL 主导的世界中刺激新的开源查询语言的采用。在他自己在 InfluxDays 的主题演讲中，InfluxData 首席执行官 [Evan Kaplan](https://www.linkedin.com/in/kaplanevan/) 指出，时序数据库是增长最快的数据库类别(其次是图形数据库)。然而，SQL 本身在描述时间序列数据方面存在困难，这正是 Flux——与 InfluxDB 没有太大联系——可以提供帮助的地方。

当 Grafana 安装在服务器上时，默认情况下会安装一些软件包。这些支持与第三方软件的连接，如 [Graphite](https://graphiteapp.org/) 和 [Prometheus](https://prometheus.io/) 监控工具。Flux 插件将是第一个可用的 InfluxDB 插件的扩展。如果没有这种本地支持，用户将不得不从插件目录中手动安装插件。

Grafana 对管理员来说很方便，因为它是少数几个可以轻松支持多个后端的监控程序之一，例如传统数据库以及 InfluxDB 等时序数据库。这对于从各种来源汇总运营数据非常有用。

Grafana 的用户已经安装了 Flux。在随后的采访中，Lisi 注意到很大比例的 Grafana 用户也在部署 InfluxDB，尽管大多数人仍然使用该数据库系统的原始查询语言。事实上，InfluxDB 最初流行的部分原因是其类似 SQL 的查询，数据库管理员和程序员很容易快速学会。Lisi 承认，Flux 有更多的学习曲线，但它提供的回报要多得多。

InfluxDB 的联合创始人 Paul Dix [去年解释说，influx db 创建 Flux 是为了将数据库查询过程与保存数据的后端存储解耦。](https://thenewstack.io/flux-influxdatas-new-language-for-time-series-data/)这样开发者就不用针对不同的数据源重复编写同一个查询了。它实际上是一种完全成形的[图灵完整的](https://stackoverflow.com/questions/7284/what-is-turing-complete)函数式编程语言，一种更像脚本语言而不是一组查询命令的语言。

“Flux 是一种非常强大和富有表现力的语言，”Lisi 在随后的采访中表示同意。Flux 超越了普通的查询，提供了进行数据转换或连接多个数据集的能力。函数可以链接在一起。Lisi 说，所有这些事情“在 SQL 中都不容易做到”。

在即将发布的版本中，Grafana 将把 Flux 作为 InfluxDB 的默认语言，尽管它也支持 InfluxDB 的原始语言以实现向后兼容。

Grafana 的 6.0 版本于上个月在开源项目的年度用户大会期间发布， [GrafanaCon 2019](https://www.grafanacon.org/) 。随着这一版本的发布，该项目正从简单的指标转向构建一个“完整的可观测性堆栈”，Grafana 的创建者 Torkel Odegaard 在[的主题演讲](https://www.youtube.com/watch?v=QIi0m2BGFiU&t=2106s)中解释道。该项目已经转移到一个新的、响应更快的面板架构和新的编辑界面(由于前端设计从 Angular.js 转移到 React.js)。

[https://www.youtube.com/embed/QIi0m2BGFiU?start=2106&feature=oembed](https://www.youtube.com/embed/QIi0m2BGFiU?start=2106&feature=oembed)

视频

InfluxData 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>