# Yelp 开放了基于 GraphQL 的 API

> 原文：<https://thenewstack.io/yelp-opens-api-based-graphql/>

自从 [Yelp](https://www.yelp.com) 软件工程师 [Tomer Elmalem](https://twitter.com/zehtomer) 第一次开始使用 [GraphQL](http://graphql.org/) API 查询语言以来，才过了四个月，尽管时间很短，该公司还是在周三拉开了新 GraphQL API 的帷幕。

[新 API](https://yelp.com/developers/graphql/guides/intro) 利用 [GraphQL Python 库](https://github.com/graphql-python)在 Yelp 的数据架构内部实现了一个新的查询层。Elmalem 表示，之所以做出这些努力，是因为 GraphQL 使得访问存储在 Yelp 中许多 RESTful APIs 和系统上的数据变得更加容易，而不需要用户为每个单独的系统编写单独的查询。

“当我开始研究它时，它似乎可以解决我们在 API 方面的许多问题。使用 GraphQL，您可以得到您想要的。您进行查询并请求特定的数据。我们有很多向各种不同端点添加数据的请求。从维护和设计的角度来看，当我们的数据到处都是时，这是很困难的。Elmalem 说:“使用 GraphQL 进行构建可以让人们灵活地做自己想做的事情。

Elmalem 从实验到将 GraphQL 投入生产的速度既是 Yelp 内部工程文化的一个因素，也是 GraphQL 易于使用的一个因素。“我们的文化非常重视快速迭代和推动生产。我们不喜欢开发人员在开发过程中受阻，但是 GraphQL 设计本身让我们可以很容易地加入进来。这非常符合我们想要做的事情，”他说。

在内部，Yelp 已经使用了 [Swagger](https://thenewstack.io/swagger-3-0-release-approaching/) ，但是没有向外部开发者公开这些资产。“我们在内部经常使用 Swagger，但这将暂时与我们的常规 API 并行。我试图让常规 API 的特性更加接近对等。我唯一没有带来的是我们的自动完成支持。看起来 GraphQL 并不是最适合这一点的，”Elmalem 说，他指的是移动设备上自动完成使用的响应需求。

Elmalem 说他最喜欢 GraphQL 的部分是“它是多么的可重用。”

“真不错。我能够定义几个查询，并在这两个查询中重用模式，”他说。“在 rest APIs 中更难。我们试图在响应端创造可重用性，但这仍然有点困难。”

Elmalem 表示，他确实预计人们需要时间来充分发挥 GraphQL 的潜力。“我认为人们可能不会预先意识到 GraphQL 的全部潜力。这需要一些时间来适应，因为这需要学习曲线。进行查询很容易，但是使用片段和一次发送多个查询可能需要一些时间来适应。”

至于当前的 GraphQL 生态系统，Elmalem 表示，Python 库现在与 [JavaScript GraphQL 库](https://github.com/chentsulin/awesome-graphql#lib-js)不相上下。他说他希望看到将来添加一些查询白名单特性，但是现在，这些特性对于他的实现来说不是必需的。

他对 GraphQL 新用户的建议？“构建模式需要一点思考。您希望确保模式对尽可能多的可重用性有意义。底层数据模型很重要。对我们来说，这意味着添加一堆批量端点来取代一次只能产生一个请求的端点。”

Igor Ovsyannykov 通过 Unsplash 提供的特写图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>