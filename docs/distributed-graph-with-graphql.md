# 带 GraphQL 的分布式图

> 原文：<https://thenewstack.io/distributed-graph-with-graphql/>

在创建网飞的广告管理系统 Monet 时，其营销技术团队在使用传统的 REST APIs 时遇到了网络瓶颈。

即使是简单的页面也需要来自各种来源的数据，但是检索到的数据远远超过所需的数量。通过建立一个 GraphQL 层，它实现了 8 倍的性能提升。通过能够更具体地获取所需的数据，以前检索 10MB 数据的页面现在可以获得大约 200KB

根据一篇博客文章，该团队还发现了帮助其更快添加功能的其他好处，包括可重用的抽象和查询包装器来管理网络请求的逻辑。

GraphQL 的日益流行促使 Linux 基金会在去年 11 月成立了 [GraphQL 基金会](/graphql-gets-its-own-foundation/)，围绕 API(应用程序编程接口)的查询语言建立一个厂商中立的社区。脸书在 2012 年开发了这项技术，并于 2015 年在[开源。](https://code.fb.com/core-data/graphql-a-data-query-language/)

[https://www.youtube.com/embed/783ccP__No8?feature=oembed](https://www.youtube.com/embed/783ccP__No8?feature=oembed)

视频

[Apollo GraphQL](https://www.apollographql.com/) 最近发布了 [Apollo Federation](https://blog.apollographql.com/apollo-federation-f260cf525d21?_ga=2.21296306.847777793.1561456928-364483517.1560335808) ，这是一个用于组合多个 GraphQL 服务的架构，它将不同团队的部分缝合成一个整体，称为 graph。

Apollo 的首席执行官 Geoff Schmidt 解释说:[在建立网站时，某处有一个网络服务器与一个或两个数据库通信。](https://twitter.com/GeoffQL)

“但我们正在走向一个更加复杂的应用世界。许多不同平台上的许多不同频道。iOS 和 Android，可能还有 Apple Watch 和 home assistant……这不是一台服务器与一个数据库对话，他们正在将不同的微服务和数据库缝合在一起，可能是第三方 API。一个应用程序可能有 100 个片段，”他说。

除了作为外部服务的前端，查询语言[还为功能即服务提供了一个简单的接口](/serverless-graphql-perfect-match-new-cloud-paradigm/)，为无服务器和微服务提供了更复杂的业务逻辑。

“你必须将数据来自云中的所有地方——所有不同的微服务和数据库——连接在一起，以获得该应用程序屏幕上的特定数据组合。你最终会遇到 N 乘 N 的问题，试图覆盖你的应用程序使用的所有数据组合。”

他说，以前的方法是 REST APIs，这是一项已经有 20 年历史的技术。

“它是为一个非常不同的世界设计的。REST 的问题在于它是点对点的。它基于这样一个想法，即你要预先协商你需要从后端获得的每一种数据组合。

他说，你必须构建大量样板粘合代码，只是为了获取应用程序中每个功能和每个屏幕的数据。

“这不仅浪费了开发人员的时间，而且您构建的所有代码都是对安全性和性能敏感的。“这真的很难维持，”他补充说。你不仅浪费了大量的时间来构建代码，还花费了大量的时间在前端团队和后端团队之间进行协调。前端团队必须乞求帮助才能完成工作。"

相反，它促进了数据图的创建，这是一个位于设备和云之间的层，提供了云中所有数据和服务及其相互关系的地图。GraphQL 是它的查询语言。

它旨在取代模式拼接，并解决诸如协调、关注点分离和脆弱的网关代码等问题。

“超过 10 或 20 个开发人员，人们希望联合他们的图形。他们希望有许多团队都在构建自己的一小部分图表。也许目录服务可以跟踪产品，运输服务可以跟踪运输，评论和推荐服务……，”他说。

然而，就像去亚马逊一样，你可以把不同供应商的产品放进一个购物车。

客户机将它们的请求发送到 Apollo Gateway，它包含一个分布式查询规划器。它将一个可能涉及多个服务的查询分解成需要到达每个服务的片段或子查询。它了解这些服务之间的相互关系。它可以在所有这些后端上执行查询，然后将所有这些片段组合成一个结果提供给客户端。

这就像 SQL 查询规划器将来自多个表的数据组合在一起，但它不是从多个磁盘驱动器中提取数据，而是从多个微服务和构建这些微服务的多个团队中提取数据。

联盟基于以下核心原则:

*   **构建一个图应该是声明性的。**您可以从模式中声明性地构建一个图，而不是编写命令性的模式拼接代码。
*   代码应该通过关注点来分离，而不是通过类型。
*   **图表应该简单，便于客户消费。**
*   **它只是 GraphQL，只使用该语言符合规范的特性。**不仅仅是 JavaScript，任何语言都可以实现联邦。

对于复杂的环境，联合包括用户指定的主键、显式查询计划和跨服务边界使用非规范化数据的灵活方式等特性。

频谱讨论的早期用户对此有很多问题，顾问 Ben Awad 在 YouTube 视频中想知道它是否涵盖了所有可能的问题。

“如果我需要在网关级别定制某个查询，会是什么样子？”他问道。

Apollo 最近有了第一个百万下载周，在过去一年中总共有 2500 万次下载，并且刚刚在第一轮风险投资中筹集了 2200 万美元。

同时， [FaunaDB](/faunadb-harnesses-serverless-cloud/) 最近增加了一个 [GraphQL API](https://fauna.com/blog/the-worlds-best-serverless-database-now-with-native-graphql) 并且 [Postman](https://blog.getpostman.com/2019/06/18/postman-v7-2-supports-graphql/) API 开发环境在 7.2 版本中也增加了支持。

总部位于西雅图的威猛公司也发布了 [urql(通用反应查询库)](https://formidable.com/blog/2019/urql-2019/)，它宣称这是一种极简、更简单的 GraphQL 入门方式。根据[2018 JavaScript State 调查](https://2018.stateofjs.com/data-layer/graphql/)，它解决了关于 GraphQL 的头号抱怨:它臃肿而复杂。

Linux 基金会是新堆栈的赞助商。

专题图片: [I G](https://www.flickr.com/photos/qubodup/) 拍摄的:[南瓜子——微距，无闪光灯，塑料盒稳定#1](https://www.flickr.com/photos/qubodup/5016819309/in/photolist-8DjvAD-cPzn5f-ebiH4u-4T9SQH-f9whv7-9wjdg9-sbUyQj-76X1cY-9UndAh-7J82U4-cPznoy-aRkZ7V-cPznAo-cssu4C-9e2tfK-rnivhX-cPzjBu-8QZTin-MUjTHQ-cPzgvf-cPzecY-dSm6dQ-ikyZrn-cPzhVs-s2R8N-6PDw6N-9fz8Sd-57BDNQ-aEVhNi-boPDxm-97GD84-jHiGUg-bpZKjS-9qWiCe-okwFHx-in6U7u-8o6YNr-7LqyYx-KdTxs-9sK1dA-cCy7eJ-ca3dTQ-bmigsn-6MZbiG-egFws6-4TMadV-2Q4wPh-bhAgBc-dSrc8W-dVi8WX) 。公共领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>