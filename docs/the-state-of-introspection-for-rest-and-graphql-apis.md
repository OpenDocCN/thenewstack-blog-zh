# REST 和 GraphQL APIs 的自省状态

> 原文：<https://thenewstack.io/the-state-of-introspection-for-rest-and-graphql-apis/>

[](https://www.linkedin.com/in/anantjhingran)

 [阿南特·金兰

阿南特是 StepZen 的创始人兼首席执行官，这是一家初创公司，致力于简化开发人员获取数据的方式，以增强数字体验。Anant 的职业生涯跨越了 IBM Fellow、IBM 信息管理部门的 CTO、Apigee 的 CTO 和 Google Cloud 的产品负责人，他的职业生涯一直处于数据库、机器学习和 API 创新的前沿。在 StepZen，Anant 正在享受创建一家公司，将他对这些技术的热爱结合在一起，以简化、加速和扩展前端开发。](https://www.linkedin.com/in/anantjhingran) [](https://www.linkedin.com/in/anantjhingran)

自省是一个沉重的词，但在系统架构中，它本质上意味着:“我将能够告诉你我可以通过编程来做什么。”

所以如果我是一个数据库，我可以告诉你我有哪些表，列和视图等等。如果我是 REST 后端，我可以告诉你你需要做的 cURL，可选的参数和我返回的响应，包括错误代码。如果我是 GraphQL 端点，我可以告诉你我支持的查询、变异和类型。

作为开发人员，可以随时看文档；进行 SQL、cURL 或 GraphQL 调用。并通过尝试学习后端功能。那为什么还要自省呢？因为自省是程序在其基础上构建非凡东西的唯一方式。它可以是一个像 [Swagger Docs](https://swagger.io/tools/swaggerhub/hosted-api-documentation/) 这样的创建文档的工具。它可以是像 [GraphiQL](https://github.com/graphql/graphiql) 这样的工具，让开发者提交查询并查看响应。它可能是一个试图自动创建索引的数据库优化程序。它可能是一个需要应用程序支持的下拉查询的 IDE。它可以是定期运行的变更管理工具，并确定后端变更对应用程序的影响。它可以是一个自主代理，通过开始了解系统的情况来引导自己。它可以是很多东西，但重要的是它不是一个人。

## REST APIs 的自省状态

目前描述 REST APIs 的黄金标准是 [OpenAPI](https://swagger.io/specification/) 。OpenAPI 3.0 是在捐赠给 OpenAPI Initiative 并于 2015 年从 Swagger 规范更名为 OpenAPI 规范后的第一个正式发布的规范。OpenAPI 是用 YAML 或 JSON 对后端功能的描述。例如，下面是 devto.io 的一个片段:

```
---
paths:
  /articles:
    get:
      description:  |
        ...
      parameters:
        -  $ref:  "#/components/parameters/pageParam"
        -  $ref:  "#/components/parameters/perPageParam30to1000"

```

如你所见，它指定 API 支持`GET /articles?pageParam`。

我不会在这里讨论确切的语法，有很多参考资料。OpenAPI 规范的伟大之处在于它解决了机器的文档问题；有了工具，也为人类解决了文档化问题。一石二鸟！

然而，为端点创建 OpenAPI 规范完全是自愿的。Twitter 不公布它的 OpenAPI 规范，HolidayAPI 的 OpenAPI 规范已经过时了！我估计在 100，000 多个公开可用的 API 中，只有不到 5%具有良好的、一致的和最新的 OpenAPI 规范。因此，剩下 95，000 个 API 没有 OpenAPI 规范，也没有任何编程访问它们的方法。

## GraphQL APIs 的自省状态

在过去几年中，GraphQL 已经成为前端开发人员获取和修改后端数据的首选范例。GraphQL 是直观和高性能的，围绕它可用的工具数量令人印象深刻。默认情况下，GraphQL 是自省的。这意味着 GraphQL 端点支持 GraphQL 查询(哇！)像这样:

```
{
  __schema  {
    queryType  {
      name
    }
  }
}

```

基本上，我们要求 GraphQL 端点使用 GraphQL 查询告诉我们它支持哪些查询(这让我想起了大多数数据库中的 SQL 内省！).这很方便，实际上很棒，并且允许一整套第三方工具针对任何 GraphQL 端点工作。

此外，如果 GraphQL 端点发生变化，自省查询将返回一个不同的(当前的或更新的)结果。因此，只要程序定期发出查询，API 端点的生产和使用就会保持最新。多棒啊。相比之下，在 OpenAPI 中，规范是一个单独的文档。因此，如果没有更新，端点会做一些事情，规范会说些别的。不好！

## “95%的 REST APIs 都没有 OpenAPI 规范”的问题

Postman 有一些工具来获取 Postman 集合并从中生成 OpenAPI 规范。然而，这是实验性的，并不一定有效。有些人针对他们喜欢的 API 创建了一些 OpenAPI 规范，但是同样，作为第三方的成果，它们通常是不完整的或者错误的。例如，人们可以获得 AccuWeather API 的一小部分的 OpenAPI 规范，但是它已经非常过时了。所以，本质上，如果 API 提供者不想提供，或者出于某种原因不提供 OpenAPI 规范，那么开发者基本上就不走运了。

然而，如果您使用 GraphQL API，您可以免费获得自省。您可以获得 GraphQL 的所有好处。所以毫不奇怪，开发人员越来越要求他们处理的 API 是图形化的。

如果一个 API 提供者决定图形化他们的 REST 端点，一些技巧有助于使投资物有所值:

1.  编写 OpenAPI 规范。然后就很简单了，用像 IBM 的 openapi-to-graphql 和 StepZen 的 OpenAPI introspection 这样的工具来创建一个 graphql 端点。因此，您一举两得:您为 REST API 消费者获得了一个 OpenAPI 规范，也为 GraphQL 消费者获得了一个出色的 GraphQL API。我们推荐这条路。
2.  利用现有的 cURL 和 Postman 集合，生成一个非常好的 GraphQL(使用 StepZen 之类的工具)。这样做的好处是，您可以通过简单的点击和响应获得 GraphQL。

## **总结**

在 REST 上已经有 20 年的投资，但是处理现代前端体验的 API 的未来主要是围绕 GraphQL 编写的。不幸的是，在 REST 中对自省的投入并没有跟上它的流行。与此同时，GraphQL 带有自动自省功能。

我们相信，API 提供商的一些有针对性的投资，以及使用越来越多的 REST->GraphQL 开源和供应商工具，将使过渡更加简单。来吧，让我们继续前进！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>