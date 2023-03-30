# Mongoose:将面向 JSON 的开发人员引入 Apache Cassandra

> 原文：<https://thenewstack.io/mongoose-bringing-json-oriented-developers-to-apache-cassandra/>

Apache Cassandra 正在成为处理 JSON 文档的最佳数据库。如果你是一名 Cassandra 开发人员，觉得这种说法具有挑衅性，请继续阅读。

在上一篇文章中，我们讨论了[使用数据 API 和数据建模](https://thenewstack.io/api-magic-building-data-services-with-apache-cassandra/)将 Cassandra 塑造成更符合开发人员思维方式的开发人员体验，从而提高开发人员的工作效率，同时保持合理的数据库性能和规模。这是一个很好的假设，需要在特定的开发者习语和开发者社区的环境中进行测试。

[mongose](https://mongoosejs.com/)，一个通常与 MongoDB 驱动一起使用的对象数据映射库，是一个开源项目，周围有一个重要的 JavaScript 开发人员社区。在 [Stargate 项目](https://stargate.io/)，为 Cassandra 设计的开源 API 数据网关，我们与 mongose 合作，我们正在开发即将发布的 [JSON API](https://github.com/stargate/jsonapi) ，它将与 mongose 的[版本一起发布，将通过 JSON API 连接到 Cassandra。这为 Mongoose 开发人员创建了一个完全开源的端到端堆栈。对于 Mongoose 开发者来说，这是改变游戏规则的一步，也为 Cassandra 开启了一个重要的新篇章。](https://github.com/stargate/stargate-mongoose)

在这篇文章中，我将讨论如何使用 Cassandra 和 Stargate 提供一个开发人员友好的 JSON 习语，以及我们如何为 Mongoose 开发人员做到这一点。

## JS 社区的金发女孩

2022 年 10 月，我们发布了新版本的星际之门。在新的[版本 2](https://stargate.io/2022/10/26/stargate-v2-ga.html) 中，独立的 API 不再嵌入到核心的星际之门协调器代码中，而是分离到独立的服务中。这提高了星门的操作效率；现在，单个 API 服务可以独立部署和扩展。这也使得新的 API 服务更容易开发。只要他们遵守服务边界，这些服务可以与核心星际之门开发工作并行开发，并且独立于核心星际之门开发工作。

然后，我们寻找一个真正地道的经验，我们可以交付给开发人员。拥有 1800 万开发人员的 JavaScript 是世界上最流行的编程语言，JSON 是 JavaScript 开发人员构造数据的标准方式。但是，1800 万人不是一个共同体；它是许多社区。我们需要 JavaScript 社区的“金发女孩”——大到足以引人注目，但小到足以引人注目。我们找到了围绕 Mongoose 构建的合适社区，Mongoose 是一个对象数据映射器库，用于连接到 MongoDB 的应用程序。猫鼬有几个重要特征:

*   它以 JavaScript 为中心
*   它被广泛采用，大约有 200 万个 GitHub 仓库将 Mongoose 列为依赖项
*   猫鼬创造者瓦列里·卡尔波夫的积极领导提供了一个清晰的焦点
*   这是一个开源项目，自从 MongoDB 决定使用其[服务器端公共许可证](https://www.mongodb.com/licensing/server-side-public-license/faq)转向共享源代码模型以来，它一直缺少一个开源数据库

开发人员实际上并不直接与数据库进行交互，而是与数据模型进行交互。在 Stargate 的原始文档 API 中，API 通过使 JSON 看起来像传统的 Cassandra 表来处理它。这给面向 JSON 的开发人员带来了考虑 Cassandra 数据结构的负担，也给 Cassandra 面向行的索引逻辑带来了负担，因为一个 JSON 文档分布在多行中。

我们新的 JSON API 背离了这个数据模型，而是依赖于一个我们称之为“超级粉碎”的数据模型你可以在 3 月 14 日的免费数字活动 [Cassandra Forward](https://dtsx.io/3YLMOQV) 的亚伦·莫顿演讲中了解更多关于超级粉碎的信息。简而言之，我们利用 Cassandra 的宽列特性，每行存储一个文档，因为 Cassandra 行甚至可以处理非常大的文档。该行中还有一组列，专门用于存储 JSON 文档的标准元数据特征。现在我们有了更容易索引的东西，以及保存和检索元数据的方法。

然后，我们将这个数据模型放在新的 JSON API 前面，使用 Mongoose 使用的相同的 [mQuery](https://www.npmjs.com/package/mquery) 规范作为 API 需要支持的调用的指导要求。完成后，这将使 200 多万个依赖 Mongoose 的应用程序中的任何一个都可以运行在开源 Cassandra 或 DataStax 托管的 Cassandra 服务 [Astra DB](https://dtsx.io/3ypXtG5) 上，只需更改配置。

有了 Mongoose 和新的 JSON API，我们将为面向 JSON 的 JavaScript 开发人员提供完全地道的体验，为他们提供 Cassandra 的[规模和性能，支撑一个真正的 JSON 数据模型。](https://thenewstack.io/an-apache-cassandra-breakthrough-acid-transactions-at-scale/)

mongose 创建者 Karpov 也将在 Cassandra Forward 活动上发言，演示一个简单的电子商务应用程序，该应用程序使用 mongose 的 Stargate 版本、开源 Stargate 和 DataStax Enterprise (DSE)版本的 Cassandra。你可以从 [GitHub](https://github.com/stargate/stargate-mongoose) 下载这个应用的工作代码和支持平台。虽然我们有足够的代码来运行这个应用程序，但我们还没有完成代码。例如，我们现在与 DSE 竞争，因为我们需要[存储附加索引](https://dtsx.io/3ZRhl0w) (SAI)，它与 DSE 一起工作，并计划在今年晚些时候在 Cassandra 5.0 中发布。

## 回馈给卡珊德拉

卡珊德拉不是一个静态的软件；这是一个充满活力和不断发展的开源项目。所以我们也在延续 Cassandra 的传统，使用出现在客户端的 SAI 等[特性来促进数据库端的变化。类似地，Stargate 的 mongose 工作促使 Cassandra 围绕全局排序和高级查询过滤提出了一系列建议，这些建议不仅会使 Stargate 的 JSON API 和 mongose 客户端更好，还会为 Cassandra 查询语言添加强大的新功能。这是一个很好的提醒，数据工程师和应用程序开发人员不是两个不同的社区，而是扩展的 Cassandra 社区的补充群体。](https://thenewstack.io/boost-cassandra-data-models-with-storage-attached-indexing/)

而 JSON 只是第一步。本质上，我们要做的是利用 Cassandra、Stargate 和一个合理有效的 Cassandra 数据模型的构建块，构建一个文档数据库，您可以通过 JSON API 与之交互。换句话说，我们使用超级粉碎创建了一个专门构建的数据库，更好地服务于 Mongoose 开发人员社区。

有了 [Stargate v2](https://devm.io/api/stargate-apache-cassandra) 的模块化架构，以及 Mongoose 惯用方法的证明点，我们已经准备好迎接围绕特定软件开发习语组织的新开发人员社区。我们为猫鼬驾驭卡珊德拉的过程是可重复的——也是我们将要重复的一个过程。通过这样做，我们极大地扩展了 Cassandra 可以解决的开发人员和用例的数量，这是开源项目值得追求的目标。

[*了解更多数据税务*](https://dtsx.io/41TOMBj) *。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>