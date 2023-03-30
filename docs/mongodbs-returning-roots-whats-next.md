# MongoDB 回归其数据管理的根基

> 原文：<https://thenewstack.io/mongodbs-returning-roots-whats-next/>

当 MongoDB Inc 年前在纽约成立时，最初的计划是创建一个完整的数据管理平台，但随着时间的推移，它将重点放在了 NoSQL 的数据库上。现在它又回到了最初的愿景。

首席技术官兼联合创始人埃利奥特·霍洛维茨在一次采访中说:“这就像我们休息了八年。”。****

[总裁兼首席执行官 Dev Ittycheria](https://www.linkedin.com/in/dittycheria/) 在芝加哥举行的 [MongoDB World 2017](https://www.mongodb.com/world17) 开幕式[主题演讲中概述了公司的成就，公司领导层还阐述了他们如何设想最初的想法，包括近期和长期。](https://explore.mongodb.com/vidyard-all-players/dev-ittycheria)

该公司宣布了其后端即服务(backend-as-a-service)计划，旨在处理日常开发任务，其数据库即服务(database-as-a-service)Atlas 在 Azure 和谷歌云以及 AWS 上得到支持。

它还展示了图表，这是 3.6 版本中的一个可视化特性，不需要[展平 JSON 数据](https://docs.snowflake.net/manuals/user-guide/querying-semistructured.html#using-the-flatten-function-to-parse-arrays)来使其看起来更有关系。图表将允许开发人员直接从连接到文档存储的基于 Web 的界面上探索他们的数据。

## MongoDB 3.6

Horowitz 概述了将于 11 月发布的 3.6 中的其他[功能，包括:](https://explore.mongodb.com/vidyard-all-players/eliot-horowitz)

一月份更新到 2.0 的 [BI 连接器](https://www.mongodb.com/blog/post/introducing-the-mongodb-connector-for-bi-20)将在今年晚些时候添加到 Ops Manager 中。这个特性允许您将 MongoDB 用作基于 SQL 的商业智能和分析平台的数据源。最近发布的 Tableau 10.3 包括一个[按钮](http://sdtimes.com/tableau-10-3-adds-data-driven-alerting-smart-recommendation-engine-expands-data-connections/)直接连接到 MongoDB。

它还让用户能够对子查询进行更多种类的连接，并以可视化的方式构建聚合管道。

它超越了 3.2 版本中引入的名为 [$lookup](https://docs.mongodb.com/manual/reference/operator/aggregation/lookup/) 的连接。

Horowitz 以一份产品目录为例，其中包括一件 t 恤和一块电池，他解释道:

“假设我们想要显示一个包含每个行项目的订单的网页，并显示每个订单的平均评分。现在，您必须对每个行项目进行查询，计算平均评分。完全有可能，但是你要对数据库进行 n+1 次调用。在 3.6 中，您可以通过一个数据库调用来完成。我们扩展了美元查找运算符，您可以创建子管道查找，因此您可以在聚合管道中作为单个查询执行任何类型的连接、任何类型的子查询。”

这个案例涉及到将 orders 集合与 reviews 集合连接起来，对于每个行项目，计算平均评分并将其全部放回到原始文档中。

第二个变化涉及使用 Update 操作符更新数组:

“假设你搞砸了一个订单，你想给这个用户订购的每件商品打八折。在 3.2 和 3.4 中，你必须对每个行项目进行更新。或者你不得不调用文档，修改它，然后把它放回去。如果用一个查询就能做到这一点，那不是很好吗？所以在 3.6 中你可以。在这里，我们将订单中每个行项目的价格乘以 0.8，得到 20%的折扣。如果我们只想更新一些元素呢？如果我们只想更新尚未发货的商品，该怎么办？我们也可以这样做。”

他说，无论你的文档嵌套有多深，它还提供了轻松更新的能力。

[文档验证](https://docs.mongodb.com/manual/core/document-validation/)特性将增加 [JSON 模式](http://json-schema.org/)支持，这将加强对必须更加一致结构化的集合的控制。他解释说，它可以让你说“这个文档必须看起来完全像这样，没有偏差”或“这个文档必须有这些字段，但它也可以有其他字段”。

在出现网络错误或其他中断的情况下，通过“可重试写入”,驱动程序和服务器进行协调，以便每个操作都有一个 ID，并且驱动程序可以安全地重试任何操作，保证它只发生一次。

为了防止用户在互联网上意外暴露数据——该公司因一些人所谓的“[松散的默认配置](http://searchsecurity.techtarget.com/answer/What-MongoDB-security-issues-are-still-unresolved)”导致暴露而受到指责——在 3.6 版本中，你将只能从本地主机连接。你将不得不添加一个标志，说，“打开这个到互联网上。”

它还支持新的变更流 API，允许您在数据库发生变更时实时提取数据。您可以订阅对集合的更改或更改子集。您可以查看分片集群上的数据子集。

3.6 的测试程序将在几个月内开始，尽管该公司尚未宣布具体时间。

Horowitz 告诉 Datanami 公司，从长远来看，该公司正在考虑开发一个并行查询执行引擎和一个列存储，主要的分析关系数据库使用它来加速分析。他说，专栏商店还有一两年的时间。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>