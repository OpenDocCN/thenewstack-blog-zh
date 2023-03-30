# RapidAPI 的 RapidQL，一种用于 API 和数据库的开源查询语言

> 原文：<https://thenewstack.io/rapidapis-rapidql-an-open-source-query-language-for-apis-and-databases/>

当使用多个 API 时，您将需要处理许多身份验证方法、API 类型和端点。有了 [RapidAPI](https://rapidapi.com/) ，就有了一个单一的图形界面和超过 10，000 个 API 的市场可以使用，而不必担心单独的安全凭证或 API 类型。

最近几周，RapidAPI [增加了对 graph QL API](https://rapidapi.com/blog/graphql-api-support-added-to-rapidapi-marketplace/)的支持，它加入了 REST 和 SOAP，现在该公司[发布了](https://rapidapi.com/blog/introducing-rapidql/)一个名为 [RapidQL](https://github.com/RapidAPI/rapidql) 的开源项目，这是一种在单个查询中同时支持 API 和数据库的查询语言。

RapidAPI 开发人员关系负责人 Alex Walling 解释说，内部使用 GraphQL 使他们走上了创建 RapidQL 的道路。

“我们实际上在内部大量使用 GraphQL 来支持我们所有的市场，现在我们也支持基于它的 API。我们还发布了我们内部构建的开源工具 RapidQL，这就像是我们自己的副产品，使用了与 GraphQL 非常相似的语法，”Walling 告诉新堆栈。“我们喜欢这种思维方式和语法，所以我们将它引入到尚不支持它的 API 中，我们将查询现有 RESTful 或基于 SOAP 的 API 的能力，以及具有非常相似语法的数据库和其他数据源。”

在其核心，RapidAPI 是一个基于 web 的接口，使访问多个 API 及其端点变得简单，该接口抽象出了大部分复杂性，并在简单明了的地方展示了每个 API 的细节。此外，在选择了您想要使用的 API 之后，它提供了一种简单的方法来使用 web 表单测试 API，甚至可以自动生成代码，然后您可以将这些代码复制并粘贴到您自己的代码中。

RapidQL 是一种用 JavaScript 实现的类似 JSON 的查询语言，是 RapidAPI 生成代码的十几种语言之一。如下面的视频所示，RapidAPI 可以轻松地将单独的 API 连接到单个查询中，获取从第一个 API 返回的数据并将其传递给第二个 API，以及过滤掉 REST API 返回的所有不必要的数据。

[https://www.youtube.com/embed/-rBlFsHkF7U?feature=oembed](https://www.youtube.com/embed/-rBlFsHkF7U?feature=oembed)

视频

RapidQL 目前支持 MySQL、PostgreSQL 和 MongoDB 数据库，这意味着查询也可以将这些捆绑到单个查询中，以便更有效地同时使用许多 API。沃林解释说，WebSocket、GRPC 和 Kafka APIs 都在地平线上，因为 RapidAPI 正在努力成为 API 访问的中心点。

“我们真的希望成为找到、管理和连接所有 API 的单一来源，而不管 API 的类型如何。我们希望增加对许多不同类型的 API 的支持。“我们希望开发人员能够尽可能轻松地连接到他们的 API。RapidQL 将 REST APIs、SOAP APIs 和数据库查询抽象成一个类似 GraphQL 的查询，因此，以同样的方式，您可以定义希望在 GraphQL API 请求中返回什么属性和什么对象，您也可以用 RapidQL 做同样的事情。”

根据 Walling 的说法，虽然 RapidAPI 和 RapidQL 执行一些预处理来提供服务，但对服务的影响是极小的，范围只有几毫秒。RapidAPI 本身使用基于 NGINX 的代理，并以 Node.js 编写。在可伸缩性方面，Walling 表示，RapidAPI 目前每周处理数十亿个请求，并毫无问题地跟上了流量。

要开始使用 RapidQL，请查看 RapidQL Developer Hub for docs、入门指南和讨论板。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>