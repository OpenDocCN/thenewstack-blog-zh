# GraphQL 是为联邦而构建的，但不要做错

> 原文：<https://thenewstack.io/graphql-is-built-for-federation-but-dont-do-it-wrong/>

[](https://www.linkedin.com/in/anantjhingran)

 [阿南特·金兰

阿南特是 StepZen 的创始人兼首席执行官，这是一家初创公司，致力于简化开发人员获取数据的方式，以增强数字体验。Anant 的职业生涯跨越了 IBM Fellow、IBM 信息管理部门的 CTO、Apigee 的 CTO 和 Google Cloud 的产品负责人，他的职业生涯一直处于数据库、机器学习和 API 创新的前沿。](https://www.linkedin.com/in/anantjhingran) [](https://www.linkedin.com/in/anantjhingran)

当组织发展到一定规模时，他们会围绕团队进行组织。团队通常有职能职责——营销、财务、工程等等。API 遵循相似的功能排列；我们看到提供营销功能(促销、产品描述等)的 API 集。)、电商功能(购物车等。)、财务功能(订单到现金等。).这些 API 通常由专门的开发团队独立开发，即使在组织上他们可能在同一个工程组织中。

随着组织在 API 之旅中的成熟，以及 GraphQL 作为下一波 API 技术被采用，他们意识到他们的 REST 投资必须被利用到 GraphQL APIs 中。关于将什么公开为 GraphQL 的决策可以集中进行，也可以在功能团队中进行。随着团队和组织变得越来越大，一个常见的模式是分散这些决策。因此，一个企业可能有一个营销 GraphQL 端点、一个电子商务 GraphQL 端点和一个财务 GraphQL 端点，每个端点都由各自的团队负责。

## 统一 GraphQL 层的注意事项

 [丹·德布鲁纳

Dan 是 StepZen 的一名软件工程师，也是 IBM 数据管理部门的高级技术人员(STSM)和 Cloudscape 数据库引擎的架构师。Dan 指导 Cloudscape 从一家初创公司发展到部署在 IBM 的产品和中间件中，最终 IBM 在 2004 年将 Cloudscape 代码作为 Derby 贡献给 Apache。](https://www.linkedin.com/in/dan-debrunner-1025287/) 

然而，现代数字体验并不仅仅建立在一个功能性的 GraphQL API 上。例如，一个电子商务网站可能会结合营销、电子商务和物流 GraphQL APIs 等等。如何将这些不同的 GraphQL APIs 整合到一个统一的 GraphQL 层中，从而构建这些数字体验？

对于这些功能性的 GraphQL APIs 如何组合成一个统一的层，有各种各样的术语:模式拼接和联邦是最常见的。其中一些术语已经与特定的实现相关联，比如[阿波罗联盟](https://www.apollographql.com/docs/federation/)。让我们首先阐明构建这个统一的 GraphQL API 需要什么，然后我们将讨论各种方法。

*   这一层不应该有业务逻辑。它应该主要是一个路由和组装层。换句话说，就计算机科学而言，这一层有责任将请求分散到正确的功能性 GraphQL APIs，并收集结果以返回答案。
*   GraphQL 层必须调用具有正确身份验证和授权的功能性 GraphQL API。毕竟，不同的功能可以选择实现自己的机制。
*   它必须能够处理常见错误，包括无响应。

当您考虑上述因素时，这一层的需求和构建任何一个功能性 GraphQL APIs 的需求之间只有一个区别。也就是说，虽然功能性 GraphQL APIs 的后端可以是任何东西——REST、SOAP、数据库——但这一层的后端只能是 GraphQL。就是这样！功能 API 和统一 GraphQL 层都需要将多个后端连接在一起的能力。两者都需要在前台和后台处理身份验证和授权。两者都需要处理错误和性能问题。

现在问问自己:如果声明式方法适合这一层，为什么它不适合函数式 API？如果它适用于功能 API，为什么同样的方法不适用于这一层呢？

## 功能 API 和 GraphQL 层采用相同的方法

您可能会得出这样的结论:从技能和维护的角度来看，脱离函数式 GraphQL APIs 进行编程，并为该层使用声明性方法(如 Apollo 所提议的)是非常复杂的。我们认为声明性方法更好，应该用于功能 API 和这一层的[。](https://www.stepzen.com/developers/videos/federation)

例如，在 StepZen 中，任何开发人员——无论是构建功能性 GraphQL APIs 还是在这一层中——都使用四个概念:

*   每个后端公开一个迷你 GraphQL 子图。这个子图可以通过自省自动生成，从一些预制的公共端点中选择，和/或通过将@rest、@dbquery 和@graphql 构造添加到手工创作的 graphql 模式文件(SDL)中来创作。
*   通过使用@materializer 构造将一个子图中的查询/变异与另一个子图中产生的数据连接起来，可以将这些子图连接在一起。
*   一个 YAML 配置文件，包括对 API 和后端数据源的访问控制。这个文件与上面的图是分开的。
*   API 和配置交给 StepZen 来运行，系统以标准的方式进行优化、缓存、错误处理等。不需要运行或管理基础设施，我们保证您的 API 有 99.99%的可用性。

使用这四个概念，开发人员可以利用现有 API 和基础设施中的所有先前投资。同时，组织和前端团队获得了所有 API 使用一个 GraphQL API 的所有额外好处。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>