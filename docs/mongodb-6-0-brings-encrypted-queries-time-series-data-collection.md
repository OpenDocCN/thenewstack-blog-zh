# MongoDB 6.0 带来了加密查询、时序数据收集

> 原文：<https://thenewstack.io/mongodb-6-0-brings-encrypted-queries-time-series-data-collection/>

开源软件 [MongoDB](https://www.mongodb.com/try/download/community) 和它的商业服务对手 [MongoDB Atlas](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) 背后的开发人员一直忙于让文档数据库更容易被开发人员使用。

“开发人员生活中最难的部分就是与政府打交道，”MongoDB 云产品副总裁安德鲁·戴维森(Andrew Davidson)说。MongoDB 最初的吸引力是为开发人员提供一种更简单的方法来存储、索引和检索作为对象的文档，而不是将这项工作转化为 SQL。戴维森认为，任何下一代开发平台都需要“在开发者所在的地方与他们见面”。

即将发布的 MongoDB 有许多直接针对提高开发效率的新特性。该公司将在本周于纽约举行的 MongoDB World 大会上讨论所有这些最新的增强功能。

以下 MongoDB 新特性旨在帮助解决这一问题。

预览版中提供的 Queryable Encryption 提供了查询加密数据的能力，并对整个查询事务进行加密——根据 MongoDB 的说法，这是业界首创。拥有大量敏感数据的组织(如银行、医疗保健机构和政府)会对该功能感兴趣。戴维森说，这消除了开发人员成为加密专家的需要。

这种端到端的客户端加密使用新颖的加密索引数据结构，被搜索的数据在数据库服务器上一直保持加密状态，包括在内存和 CPU 中。这些键永远不会离开应用程序，该公司坚持认为新功能不会影响查询速度和应用程序的整体性能。

MongoDB 现在还支持时间序列数据，这对于监控物理系统、快速移动的财务数据或其他面向时间的数据集非常重要。在 MongoDB 6.0 中，时间序列集合可以有关于度量的二级索引，并且数据库系统已经过优化，可以更快地对基于时间的数据进行排序。

戴维森认为，尽管有许多专门面向时间序列数据的数据库，如 [InfluxDB](https://www.influxdata.com/?utm_content=inline-mention) ，但许多组织可能不想为这一特定用途建立一个完整的数据库系统，一个在支持和专业知识方面花费更多的独立系统。

另一个特性是集群到集群的同步，它提供了跨环境的 MongoDB 集群的连续数据同步。它可以在私有云、内部或边缘环境中与 Atlas 协同工作。这为在多个地方使用数据进行测试、分析和备份奠定了基础。

还特别关注更好地支持分析。MongoDB 中的分析节点现在可以单独扩展，从而提供更好的配置。今年晚些时候将推出的一项功能是列存储索引，它可用于创建和维护专门构建的索引，以加快分析查询的速度，而无需更改文档结构或将数据复制到另一个系统。

## MongoDB 地图集

商业地图集本身也有所改进。

Atlas 的搜索功能——由开源软件 Apache Lucene 提供支持——已经得到了丰富，允许用户通过一个名为 Search Facets 的新功能更好地浏览和细化不同维度的结果，该功能实现了倒排索引技术。

名为 Atlas Device Sync 的新功能将 Atlas 中完全托管的后端数据库连接到流行的移动对象数据库[领域](https://realm.io/)，对同步到用户应用程序的数据进行精细控制。MongoDB [在 2019 年收购了](https://techcrunch.com/2019/04/24/mongodb-to-acquire-open-source-mobile-database-realm-startup-that-raised-40m/)领域。

虽然 MongoDB Atlas 的目标是通过云服务模型使数据库更容易管理，但该公司现在有了一个更简单的选择，Atlas Serverless，它现在已经正式上市，完全消除了数据库供应和扩展的任务。用户将按每台电脑付费。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>