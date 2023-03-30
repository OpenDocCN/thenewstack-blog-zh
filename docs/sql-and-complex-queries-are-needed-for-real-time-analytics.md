# 实时分析需要 SQL 和复杂查询

> 原文：<https://thenewstack.io/sql-and-complex-queries-are-needed-for-real-time-analytics/>

[](https://www.linkedin.com/in/dhruba)

[Dhruba Borthakur](https://www.linkedin.com/in/dhruba)

[Dhruba 是 Rockset 的 CTO 兼联合创始人，负责公司的技术方向。他是脸书大学数据库团队的工程师，也是 RocksDB 数据存储的创始工程师。此前在雅虎，他是 Hadoop 分布式文件系统的创始工程师之一。他也是开源 Apache HBase 项目的贡献者。](https://www.linkedin.com/in/dhruba)

[](https://www.linkedin.com/in/dhruba)[](https://www.linkedin.com/in/dhruba)

*注:本文是*[*设计下一代实时分析数据系统*](https://rockset.com/blog/why-mutability-is-essential-for-real-time-data-analytics/) *系列文章的第四篇*

当今的数据驱动型企业不仅需要从最新数据中获得快速答案，还必须执行复杂的查询来解决复杂的业务问题。

例如，客户个性化系统需要将历史数据集与实时数据流结合起来，以便立即向客户提供最相关的产品推荐。运营分析系统也必须提供任务关键型实时业务可观察性，例如一家在线支付提供商需要监控其全球交易，以发现可能预示金融欺诈的异常情况。

或者想象一下[一个电子学习平台](https://rockset.com/blog/case-study-real-time-insights-help-propel-10x-growth-at-e-learning-provider/)需要为学区客户和内部面向客户的团队提供关于学生和教师使用情况的最新见解。或者是需要监控并确保其金融客户在狭窄的盈利交易窗口内获得准确、相关的更新的市场新闻提供商。

## NoSQL 的局限性

SQL 支持复杂的查询，因为它是一种非常有表现力的、[成熟的](https://blog.sqlizer.io/posts/sql-43/)语言。复杂的 SQL 查询在商业智能(BI)中早已司空见惯。当 Hadoop 和 Hive 等系统出现时，它第一次将复杂的查询与大数据结合起来。Hive 在 Hadoop 的原生 MapReduce 编程范式上实现了一个 SQL 层。这些第一代基于 SQL 的大数据系统的代价是，它们以更高的查询延迟为代价提高了数据处理吞吐量。结果，用例牢牢地保持在批处理模式中。

当键值和文档存储等 NoSQL 数据库出现时，这种情况发生了变化。设计目标是低延迟和低规模。现在，公司可以获取大量数据，将其组织成简单的键值或文档对，并立即执行查找和其他简单的查询。这些大规模、可伸缩的键值存储或文档数据库的设计者认为，只有当查询本质上很简单时，规模和速度才是可能的。在键值存储中查找值可以变得非常快。相比之下，由于过滤器、排序和聚合的内在复杂性，SQL 查询在技术上太具挑战性，无法在大量数据上快速执行，他们决定。

### 不要注意窗帘后面的那个人

不幸的是，由于上述原因，当查询复杂、嵌套并且必须返回精确答案时，NoSQL 数据库往往会遇到问题。这不是他们的强项。他们的查询语言，无论是类似 SQL 的变体如 [CQL](https://cassandra.apache.org/doc/latest/cassandra/cql/) (卡珊德拉)和[德鲁伊 SQL](https://druid.apache.org/docs//0.15.0-incubating/querying/sql.html) ，还是完全定制的语言如 [MQL](https://www.mongodb.com/blog/post/should-mongodb-use-sql-as-a-query-language) (MongoDB)，都很少支持 SQL 、*标准的连接和其他复杂查询命令[，如果它们支持的话。](https://towardsdatascience.com/mythbusting-the-venerable-sql-database-and-todays-real-time-analytics-a6abfa35728e)*

NoSQL 数据库的供应商就像绿野仙踪，用烟雾和镜子分散你的注意力，并谈论速度，这样你就不会注意到 NoSQL 数据库在实时分析方面的实际弱点。使用 NoSQL 数据库的开发人员最终被迫在自己的应用程序代码中嵌入连接和其他数据逻辑——从从单独的表中获取数据到进行连接优化和其他分析工作。

虽然走 NoSQL 路是可行的，但它既麻烦又慢。以个人申请抵押贷款为例。为了分析他们的信用度，你可以创建一个数据应用程序来处理数据，比如这个人的信用记录、未偿贷款和还款记录。为此，您需要组合几个数据表，其中一些可能是[规范化的](https://machinelearningmastery.com/normalize-standardize-machine-learning-data-weka/#:~:text=Data%20normalization%20is%20the%20process,the%20smallest%20value%20is%200.&text=You%20can%20normalize%20all%20of,applying%20it%20to%20your%20dataset.)，另一些则不是。你也可以分析当前和历史抵押贷款利率，以确定提供什么利率。

使用 SQL，您可以简单地将信用历史和贷款支付的表连接在一起，并聚合大规模的历史数据集，如每日抵押贷款利率。然而，与 SQL 相比，使用 Python 或 Java 之类的东西来手动重新创建连接和聚合会使应用程序中的代码行数增加几十甚至一百倍。

更多的应用程序代码不仅需要更多的时间来创建，而且几乎总是导致更慢的查询。如果不能访问基于 SQL 的查询优化器，加速查询将非常困难和耗时，因为应用程序中的业务逻辑和应用程序使用的基于查询的数据访问路径之间没有界限。像[中间连接表](https://www.codecademy.com/learn/paths/data-science/tracks/sql-intermediate/modules/dspath-sql-multiple-tables/cheatsheet)这样普通的 SQL 可以高效优雅地处理的东西，在其他语言中会变成臃肿的内存猪。

最后，用应用程序代码编写的查询也更加脆弱，需要不断的维护和测试，如果数据量发生变化，还可能需要重写。大多数开发人员缺乏时间和专业知识来执行这种持续的维护。

我认为只有一个 NoSQL 系统能够胜任复杂查询:GraphQL。GraphQL 系统可以将数据类型与特定的数据字段相关联，并提供检索文档中选定字段的功能。它的查询 API 支持复杂的操作，比如基于一组匹配的字段过滤文档，并从匹配的文档中有选择地返回字段的子集。GraphQL 的主要分析缺点是缺乏表达能力，无法根据两个数据集中特定字段的值连接两个不同的数据集。大多数分析查询都需要这种在查询时连接多个数据源的能力。

## 为工作选择最佳工具——SQL

在科技领域和生活中，每一项工作都有一个最适合它的工具。对于复杂的分析查询，SQL 无疑是最好的工具。半个世纪以来，SQL 开发了一套丰富而强大的命令。创建查询很容易，为了加速结果、缩小中间表和降低查询成本，调整和优化查询甚至更容易。

关于 SQL 数据库有一些[神话，但是它们是基于 20 世纪 90 年代遗留的关系系统。事实是，现代云原生 SQL 数据库支持](https://rockset.com/blog/busting-myths-about-the-SQL-database-and-real-time-analytics/)[实时分析](https://rockset.com/blog/busting-myths-about-the-SQL-database-and-real-time-analytics/)所需的所有关键特性，包括:

*   可变数据，以令人难以置信的速度接收数据并平稳处理迟到的事件。
*   灵活的模式，可以根据输入流数据的结构自动调整。
*   即时纵向扩展数据写入或查询，以处理数据突发。

SQL 仍然非常受欢迎，是所有编程语言中最受欢迎的。正如我们所见，它支持复杂的查询，这是现代实时数据分析的要求。相比之下，NoSQL 数据库在执行连接和其他复杂的查询命令方面比较弱。此外，寻找一个不太知名的定制查询语言的专家可能既费时又费钱。

底线是，你可以毫无问题地找到熟练的数据工程师和数据操作人员，他们了解 SQL 及其处理复杂查询的能力。他们将能够利用这些知识和能力，推动您的组织从批量分析向实时分析的飞跃。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>