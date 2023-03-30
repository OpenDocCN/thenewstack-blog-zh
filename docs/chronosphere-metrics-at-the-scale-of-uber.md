# 超时空:优步尺度的度量

> 原文：<https://thenewstack.io/chronosphere-metrics-at-the-scale-of-uber/>

随着公司转向微服务架构，他们发现他们的系统创建的指标数量会爆炸式增长。优步在 2014 年末就是这种情况，当时它意识到它的石墨/碳监测堆栈跟不上。

后来，它尝试将 stat site 用于聚合，Cassandra 用于时间序列存储，ElasticSearch 用于索引，但发现这也是不够的。

这最终导致这家拼车公司建立了自己的指标平台，名为 [M3](https://github.com/m3db) ，并于 2018 年开源。现在，该项目的两位技术负责人，[罗布·斯基林顿](https://github.com/robskillington)和[马丁·毛](https://twitter.com/martin_c_mao?lang=en)，正在推动这项技术进入一家名为[超时空公司](https://chronosphere.io/)。

“随着的不断发展，我们不得不扩展基础设施，但与此同时，监控的复杂性也成倍增加，”Chronosphere 首席执行官毛表示。

“这些架构变化会带来什么，因为现在有这么多更小的组件。监控端会产生更多的数据。这些数据中有很多是高基数或高维数据。我们体验到，我们使用的开源工具没有一个能够真正扩展到所有新的数据量和现在产生的数据的高维度，实际上没有一个商业产品能够做到这一点”，Mao 说。

### 不断扩大规模

11 月，该公司宣布了由 Greylock Partners 牵头的 1100 万美元投资。

格雷洛克的[陈佳瑞](https://www.greylock.com/team/#jerry-chen)告诉新堆栈:

“可观察性，尤其是指标，已经成为各种规模的所有公司的必要脉搏。应用、基础设施和业务运营的指标现在对公司运营至关重要。

“在过去的几年里，随着公司转向云原生架构，他们看到了指标和高维度或高清指标数量的爆炸式增长。现在，每个应用事件都会产生大量数据，如时间戳、应用版本、操作系统版本、延迟等。现有系统无法以经济高效的方式处理高清指标。超时空团队在 M3 的优步大厦解决了这个问题，这个解决方案可以处理规模，但也有成本。

“Chronosphere 正在构建向各种规模的所有公司查询高维度指标的能力。借助 Chronosphere，客户现在可以从持续可靠的云服务中了解应用和基础架构的使用情况、应用或业务部门的成本消耗。”

毛将 M3DB 描述为专门为度量标准而构建的。他解释说，其他时间序列数据库——比如建立在 Postgres 基础上的[时标](/timescaledb-focuses-query-power-scale/);或者[蟑螂](/cockroachdb-unkillable-distributed-sql-database/)或 PingCAP 的 [TiDB](/tidb-brings-distributed-scalability-sql/) ，它们依赖于 RocksDB——它们的核心数据库不是为云原生世界中的数据量或复杂性而构建的。然而，他提到了 influx db，这是另一个从头开始为时序数据优化的工具。

他指出，Datadog 是其最接近的竞争对手，尽管它的目标客户群更广，他说，而 Chronosphere 高度专注于大企业的规模和高效监控。

Skillington 现在是 Chronosphere 的首席技术官，最初[将 M3](https://eng.uber.com/m3/) 描述为[普罗米修斯](https://prometheus.io/)的远程存储后端。

他说当它被开源时:

*发布于 2015 年，M3 现在拥有超过 66 亿个时间序列。M3 每秒聚合 5 亿个指标，每秒将 2000 万个指标保存到全局存储中(使用 M3DB)，使用仲裁写入将每个指标保存到一个区域的三个副本中。它还允许工程师制定指标策略，告诉 M3 以更短或更长的保留期(两天、一个月、六个月、一年、三年、五年等)存储某些指标。)和特定的粒度(一秒、十秒、一分钟、十分钟等)。这使得工程师和数据科学家能够使用与定义的存储策略相匹配的指标标记(标签)，在细粒度和粗粒度范围内智能地存储不同保留时间的时间序列。*

开源软件有三个主要组件:时间序列数据库、摄取管道和查询引擎。它没有任何仪表板，警报功能或异常检测功能，这些功能是 Chronosphere 团队内置于其 SaaS 产品中的。

它可以在公共云或内部运行。它支持公制摄取格式和语言，包括 SQL、Prometheus、Carbon、Graphite 等等。

### 控制成本

Chronosphere 让客户决定将不同类型的数据存储多长时间。

某个部署新服务的人可能想知道哪个特定的容器或哪个特定的 Kubernetes pod 导致了问题。但是在部署已经运行了一段时间之后，特定的 id 或特定的容器就不那么有用了。Chronosphere 允许用户指定将每个数据子集保留多长时间。

“例如，所有短暂的数据，如关于吊舱和容器的信息，如果你想，你可以选择只存储它们两个小时，如果你想，存储六个小时，这取决于你的使用情况，然后你只需为那段时间的资源使用付费，”毛说。

除了自动化仪表板和警报，因为它专注于大型组织，所以它一直在添加企业功能，如智能速率限制、细粒度访问控制和资源限制。

他指出，你可以实现开源的 M3 平台，但这就像公司里的每个人都使用一个工具，有能力踩在别人的脚趾上，或者一个人为每个人搞垮系统。它的新特性和路线图专注于在多租户组织中使用。

11 月，它增加了分布式跟踪功能，该功能已深度集成到现有的监控堆栈中。未来，它将建立在整合的基础上。例如，构建单击仪表板上任何指标数据点并直接转到其底层分布式跟踪之一的功能。

毛曾说过，可扩展性是推出新功能的决定性因素。

它希望为用户提供更多的可见性，让他们了解不同的团队如何使用产品，通过在他们接近预算极限时提供选项来控制他们的成本。

该技术仍处于私人测试阶段，尽管已经有客户在生产中运行 Chronosphere，毛说。它没有真正的时间表结束测试，但可能会达到 GA 在今年晚些时候。它计划继续与客户合作，让他们入职，而不是通过网页或其他方式使用自助服务。

专题图片: [depo17](https://www.flickr.com/photos/depo17/) 的[掌舵](https://www.flickr.com/photos/depo17/3242721269/in/photolist-5WxN4p-7sC1Rf-2ivkosE-7sDpYW-7vKuCX-7szsr2-7sDqeq-dLFvPH-7vKuDT-7sy3x4-7szs7g-7sC1Ts-7szsov-7sDq3s-7sC1S9-7szsPr-7sDqgS-7szrPX-7sDr2q-7vPjph-7szsnn-7sDqb5-7sGs2x-7sC1V3-7vKuDp-7sDr1q-7szrYg-7sC1Uh-7sDqf3-7t1xMh-7szs28-7vKuCn-7szrSn-7szs3V-7sDqYY-7sDq19-7sX4Nx-32JBNp-7szrYD-7sLpYy-7sLpXs-7sDqxb-7vPjpU-7sDquw-7szsdX-7sDqXY-7szsfH-7szsig-7szsj6-7sDqbN)。根据 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>