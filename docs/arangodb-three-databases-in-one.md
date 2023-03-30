# ArangoDB:三个数据库合二为一

> 原文：<https://thenewstack.io/arangodb-three-databases-in-one/>

在美国拓展业务的德国数据库 ArangoDB 在其同名数据库管理软件 3.5 版本中发布了新功能，使跨多种数据模型查询和搜索不断增长的数据集变得更加容易。

多模型数据库不仅要有效地使用以不同方式存储的数据，还要管理多个数据库，每个数据库都有自己的存储和操作需求，包括数据一致性。

使用 [ArangoDB](https://www.arangodb.com/) ，数据可以存储为键值对、图形或文档，并且可以使用一种声明式查询语言进行访问。您可以同时执行这两项操作—文档查询和图形查询。首席执行官[克劳迪斯·温伯格](https://twitter.com/weinberger?lang=en)解释说，这种结合提供了灵活性和性能优势。

他说，在数据库市场，规模并不重要。

“有图形数据库，有像 Elasticsearch 这样的全文搜索引擎，有像 Redis 这样的键值存储。工程和机器学习负责人[jrg Schad](https://www.linkedin.com/in/j%C3%B6rg-schad-945345a9/)说，不幸的是，在实践中，你通常拥有的用例并不简单地映射到这些数据存储中的一个。

“因此，大多数情况下，你不只是有一个图形问题。但是，举例来说，您可能会同时遇到文档存储问题和图形问题。”

他说，因此开发人员通常将 MongoDB 用于文档，将 Neo4j 之类的东西用于图形部分，然后在其上构建应用层。

“核心思想实际上是从同一个引擎提供所有这一切，并从一个数据库引擎提供所有相同的事务保证。你不必编写自定义代码来合并顶层数据，或者提供跨不同数据存储的事务保证，”他说。

阿兰戈还提供全文搜索，想象中有点像 Elasticsearch，来索引整个文本数据。

在[版本 3.5](https://www.arangodb.com/2019/08/multi-model-database-arangodb-3-5-released-distributed-joins-streaming-transactions-extended-graphdb-search-capabilities/) 的新特性中:

*   **[smart Joins](https://www.arangodb.com/arangodb-training-center/smart-joins-tutorial/)**，仅在 ArangoDB 的企业版中可用，允许您分片数据并在不同的机器上运行 joins。这使得在不适合单个节点的大型图上运行复杂查询更加有效。
*   **流事务 API** 允许用户从支持的语言驱动程序中执行和控制 ACID 事务，包括 Java Sync、Go、JavaScript 和 PHP。ArangoDB 仅支持单实例设置中多文档/多集合查询的完全 ACID 保证。
*   **可配置的分析器和分类索引**用于[搜索](https://www.arangodb.com/why-arangodb/full-text-search-engine-arangosearch/) 。据该公司称，这可以将查询性能提高 1，500 倍，并简化多租户环境中的管理。
*   **k 最短路径和剪枝:** [k 最短路径](https://www.arangodb.com/arangodb-training-center/graphs/k-shortest-paths-queries-in-aql/)使用户可以查询两个顶点之间的所有最短路径，并按路径长度或权重分析结果集。PRUNE 允许用户向他们的查询添加一个语法，以在特定条件下停止更深层次的搜索，这有助于减少开销和加快结果。
*   **[数据屏蔽](https://www.arangodb.com/arangodb-training-center/data-masking-tutorial/)** 对敏感数据(如信用卡和社会安全号码)进行匿名处理，以便在测试环境中使用生产数据。有预定义的组件，但您也可以进一步定义自己的组件。

“在欧洲这里，[GDPR]是一个大话题，”沙德说。“您必须小心，哪些数据可能会返回到您组织中的某些组。因此，我们想出了一种方法……轻松地屏蔽掉隐私数据等信息，但仍能返回有意义的结果。”

### 完全本土的

ArangoDB 于 2014 年在德国科隆成立，最近在旧金山设立了总部。今年 3 月，它获得了由 Bow Capital 牵头的 1000 万美元 A 轮融资，使其总融资额达到 1920 万美元。

创始人温伯格和弗兰克·塞勒一起工作了 20 多年。2004 年，他们成立了数据库咨询公司 triAgens，专注于 NoSQL 解决方案。

ArangoDB 提供开源[社区](https://github.com/arangodb/arangodb)版本和其商业企业版。它有一个测试版的托管服务。它的客户包括巴克莱、汤普森-路透和思科。

它在市场上有很多公司。在 [DB-Engines](https://db-engines.com/en/ranking) 排名中，前 10 个最受欢迎的数据库中有 7 个在 multimodel 中列出。它还与其他多模式开源数据库竞争，包括 OrientDB、Cassandra、Redis、Couchbase、YugaByte 等。

根据 Weinberger 的说法，不同之处在于，其中许多都有一个构建在文档或键值存储之上的图形层，而不是包含这三者的完全本机模型。****

### 三合一

[其核心](https://www.arangodb.com/arangodb-white-papers/white-paper-multi-model-database/)，用 C++编写，数据库软件是几个数据存储的组合，可以用一种类似于 SQL 的声明式查询语言 ArangoDB Query Language (AQL)访问。AQL 支持以各种方式组合的连接和遍历，并且您可以同时查询不同的数据存储。它被设计成独立于客户端——无论使用哪种编程语言，所有客户端的语言和语法都是相同的。

它将所有三种模型类型的数据存储为 JSON 文档。对于图形，它为每个顶点存储一个 JSON 文档，为每个边存储另一个文档。特殊的边集合确保每条边都有 _ *from* 和 _ *to* 属性，这些属性引用边的开始和结束顶点，允许对所有三种模型类型使用一种查询语言。

在后端，它使用 RocksDB 进行扩展。

它还使用了 [Foxx](https://www.arangodb.com/why-arangodb/foxx/) ，这是一个 JavaScript 框架，用于编写以数据为中心的 HTTP 微服务来扩展 API。使用 Foxx，开发人员可以将他们的数据访问和域逻辑编写为微服务，并通过对内存数据的本地访问直接在 ArangoDB 中运行。

Schad 说，展望未来，该公司将专注于运行更大集群的优化。如何在节点之间复制数据？管理员如何获得大规模调试问题所需的指标？对于适合单个节点的图，有效的备份和容错又如何呢？

它还在钻研机器学习，并使机器学习管道更有效。

专题图片:兰登·彼得森的《三》。根据 CC BY-SA 2.0 获得许可。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>