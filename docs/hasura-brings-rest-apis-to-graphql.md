# Hasura 将 REST APIs 引入 GraphQL

> 原文：<https://thenewstack.io/hasura-brings-rest-apis-to-graphql/>

如今，围绕应用编程接口(API)的一个常见说法是从 REST API 过渡到 GraphQL，但现实往往是一个中间地带，这种情况将持续多年。对于这一现实，像提供托管云和企业版 [Hasura GraphQL 引擎](https://github.com/hasura/graphql-engine)开源项目的 [Hasura](https://hasura.io/) 这样的公司，现在给组织一种享受两个世界的最佳方式。

Hasura 首席运营官兼联合创始人[拉乔希·戈什](https://www.linkedin.com/in/rajoshighosh/)解释说，Hasura 的主要目标是通过让 GraphQL APIs 更容易访问来解决它所说的“前端和全栈开发人员的数据访问瓶颈”，实现 GraphQL 的梦想。

## **对 GraphQL 感到兴奋**

“人们对 GraphQL 非常感兴趣，特别是前端和全栈开发人员，因为这里有一个美丽的生态系统。这基本上是一个梦。他们不需要等待别人为他们构建特定的 API，他们可以直接请求他们想要的东西，”Ghosh 说。“这是 GraphQL 的梦想，也是开发人员喜欢它的原因，但现实是，它只是一个规范。要获得 GraphQL 的美丽，你需要有人站起来或者向你展示它。”

Hasura 的首席执行官兼联合创始人 Tanmai Gopal 解释说，像 [Apollo GraphQL](https://apollographql.com/) 这样的工具提供了一个用来编写 GraphQL 服务器的库，但是“Hasura 采取了一种稍微不同的方法，并表示您不必构建 GraphQL 服务器并为其编写代码，”他说这项任务可能需要几周甚至几个月的时间。相反，开发人员可以在几分钟内声明性地配置 web 服务器并公开生产就绪的 API。

除了快速构建 GraphQL API，Hasura 还允许开发人员将多个数据源集成到该图形中，包括 SQL、PostgreSQL、YugaByte、scale 和 Google Big Query 等数据库。现在，该公司已经将 REST APIs 纳入数据源列表。

## **REST API 连接器和数据中枢**

今年早些时候，Hasura 通过 [Hasura 2.0](https://hasura.io/blog/announcing-hasura-graphql-engine-2-0/) 首次发布了一种类型的 [REST API 支持](https://hasura.io/docs/latest/graphql/core/api-reference/restified.html#restified-api-reference)，让其 GraphQL 客户能够在需要时提供对 REST 端点的访问。现在，该公司已经推出了双向 REST API 连接器和数据中心，这两个功能都旨在让组织更容易使用 GraphQL 访问现有的 REST API。

“到目前为止，我们所做的就是让引入数据库和其他 GraphQL 服务变得非常容易。我们现在所做的是，我们让引入现有的 rest APIs 变得非常容易，”Gopal 说。“Hasura 正在解决的问题是，通过解决转换问题，然后通过解决某些特定的 GraphQL 问题，如授权、缓存和 API 速率限制，使 REST APIs 更容易进入 GraphQL。”

虽然将 REST API 导入 GraphQL 的能力已经存在，但这里的部分吸引力仍然在于 Hasura 处理这方面的繁重工作，而不是要求后端开发人员构建到该 REST API 的 GraphQL 连接。

“通过 Hasura，我们所做的是建立一个转换引擎，它在声明式地将 REST 端点转换为 GraphQL 方面具有非常好的开发人员体验，这将与 GraphQL API 的其余部分很好地配合，”Gopal 说。“现在，您不必花时间编写代码，然后部署和维护这些代码，这部分工作已经大大简化了。”

## **集成第三方 REST API**

除了导入自己的 REST API，Hasura 用户还可以将第三方 REST API 与新的 REST API 连接器集成。在这一点上，Hasura 还创建了它的数据中心，这是一个预配置的第三方 REST APIs 的存储库，这些 API 来自 Contentful、Elastic、Fauna 和 IBM Open API 等服务。有了 Hasura Data Hub，用户不仅可以将外部 REST API 构建到自己的 GraphQL 端点中，而且整个社区也可以将自己的 REST API 贡献到数据 Hub 中，供他人使用。

除了围绕 REST 和 GraphQL 的这些特性，Hasura 还在其托管的 Hasura Cloud 产品上推出了对 Google Cloud 的测试版支持。用户现在可以选择自己的地区，并连接到他们在谷歌云上的现有数据源，消除了谷歌和 Hasura Cloud 之间的网络出口成本。

展望未来，Gopal 表示，Hasura 将专注于提供处理大量数据的 GraphQL 的功能，以及允许社区更容易地将他们喜欢的数据源贡献给开源 Hasura 项目。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>