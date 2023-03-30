# GraphQL 不太可能的旅程

> 原文：<https://thenewstack.io/the-unlikely-journey-of-graphql/>

MongoDB 之所以出名，是因为它专注于开发人员的偏好，认为 JSON 是表示数据的自然方式，而 [JSON](https://thenewstack.io/an-introduction-to-json/) query 是访问数据的直观方式。但是当涉及到访问移动数据时， [MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) [通过](https://www.mongodb.com/docs/realm/graphql/)[收购 Realm](https://www.mongodb.com/press/mongodb-strengthens-mobile-offerings-with-acquisition-of-realm) ，采用新的协议 [GraphQL](https://graphql.org/) 作为查询移动数据的更方便的方式，寻找不同的途径来访问 JSON。

GraphQL 最初是作为一种更具声明性的数据查询方法出现在脸书，它提供了一种用于在应用程序之间交换数据的数据访问 API，这种 API 可以继承事实上的标准 REST API 的不足。GraphQL 正在成为一个小 API。

## 休息打开了大门

早在 2015 年，脸书就对 GraphQL 进行了开源，自此 graph QL 开始了一段令人惊讶的旅程，到了一个快速增长的生态系统的地步。GraphQL 的出现反映了应用程序交换数据的 API 的主导作用，它的成功完全是因为它可能会补充而不是取代 REST 的 API。

REST 作为一种向应用程序提供数据的标准、简单、直接的方式出现。这是对第一代面向服务的体系结构的复杂性的一种回应，它将握手集中在业务逻辑层。它让微服务的世界最终变得可以想象。作为对前辈(如 [SOAP](https://thenewstack.io/solo-io-adds-legacy-soap-integration-for-gloo-edge-1-8-release/) )要求应用程序在进程级握手以交换数据的回答，REST 将这一切简化为通过 HTTP 向特定端点发送 GET 命令的相对简单的事情。只需获取数据，并让应用程序处理逻辑。

毫不奇怪，在过去的十年中，REST 成为应用程序嵌入逻辑*和*交换数据的默认方法。它已经在无数的应用程序中根深蒂固，对于开发人员来说，编写代码非常简单。REST 是一种必不可少的方法，适用于静态环境，在这种环境中，客户端请求一组特定的信息。

但是 REST 有一个问题:调用很简单，但是实现可能会变得复杂，尤其是在涉及多个后端点(数据源)的情况下。满足 REST 调用可能需要处理身份验证、持久性和负载平衡的来回消息链。在微服务的世界里，输出通常包括从多个来源收集信息。结果是 REST 变得非常冗长，而这种冗长会导致延迟。当你使用移动设备时，延迟是你的敌人。

## 微服务为 GraphQL 创造了机会

GraphQL 引起了人们的关注，因为应用程序重构或现代化为微服务正在将 REST 推向极限。作为信息消费者，我们对我们使用的数字平台有着更高的期望。购买产品时，我们还会希望找到评论、竞争报价、自动填充关键字搜索以及其他可能的选项。单一的应用程序在负载下会崩溃，出于类似的原因，同样的命运可能会发生在 REST 上，这需要对特定的端点发出精确的命令。对于复杂的查询，有许多精确的请求。

脸书的开发人员创建了 GraphQL 作为客户端规范，以缓解从多语言数据源获取数据到各种 web 和移动客户端时日益出现的瓶颈。使用 REST，开发人员必须知道所有的端点。相比之下，使用 GraphQL，这种方法是声明性的:指定您需要什么数据，而不是如何产生它。REST 是命令式的，而 GraphQL 是声明式的。繁重的工作由底层的知识图来完成，这些知识图已经映射了数据及其类型，其结果是信息通常可以在一次传递中被检索到。

GraphQL 最初在你预期的地方获得了牵引力——大型目的地在线服务，如脸书、Shopify、Expedia、GitHub 等。它已经成为 JavaScript 开发人员的最爱。当然，任何新兴技术都存在争议:[为什么使用 GraphQL](https://www.apollographql.com/blog/graphql/basics/why-use-graphql/) 和[为什么不使用 GraphQL](https://wundergraph.com/blog/why_not_use_graphql) 。

虽然 GraphQL 的简单性在于执行，但是构建这些图的细节却是魔鬼。虽然脸书有一个相对单一的图，但对于大多数组织来说，答案可能是多个图的联合。

当我们谈到图形的话题时，让我们打破一个神话:尽管有这个名字，GraphQL 不是图形数据库的查询语言，尽管[它可以这样使用](https://neo4j.com/developer/graphql/)。

这里有一些商业背景。脸书专门为自己的数据源图创建了最初的客户端，所以在脸书之外，API 需要通用化。 [Apollo GraphQL](https://thenewstack.io/apollo-introduces-a-graphql-platform-for-shared-data-graphs/) 创建了一个 Apache 授权的开源客户端来填补空白；这是目前市场上可以买到的一些产品中的一种。他们添加了一个传输层，可以将客户端与一个联邦视图连接起来，这个联邦视图可能是代表不同数据源的多个知识图。除此之外，Apollo 还添加了自己的闭源[弹性许可](https://www.apollographql.com/docs/resources/elastic-license-v2-faq/)治理层和一个麻省理工学院许可的服务器，该服务器连接到 REST 和其他数据源的 API。

GraphQL 有许多很酷的特性使它很有吸引力。首先，由于底层的图，GraphQL 查询可以指定理解这些对象之间的关系所必需的确切数据实体。强类型有助于确保结果以正确的形式出现。如上所述，命令更加紧凑，避免了 REST 调用的繁琐。

还有弹性的问题。由于端点的脆弱性，它经常改变，REST APIs 需要版本化。相比之下，GraphQL APIs 更有弹性，因为版本控制被保留在底层知识图中；虽然这不是一张免于牢狱之灾的卡片，但比更新所有这些 API 要简单得多。此外，如果到数据点的一些后端连接中断，GraphQL 仍然可以返回部分答案。

## 最好竖起那些护栏

像任何 API 一样，GraphQL 的用处取决于它周围的防护栏。例如，虽然 GraphQL 可以聚合来自许多来源的数据，但它本身并不是一个数据虚拟化或数据联合工具。为此，需要规范化管理到数据源的连接，更不用说管理安全性和授权了。缺少捆绑 GraphQL 的工具、ide 或应用程序，使用原始 API 可能会因为它的强大而出现问题。例如，在构建底层图表时，将需要治理，以便交付给美国某人的答案不包含不能离开德国的数据。或者，当映射数据源之间的所有连接时，结果会烧掉宝贵的云计算周期吗？所有这些都是商业 GraphQL 工具正在寻求解决的问题。

知道数据来源呢？对于开发人员来说，保护 RESTful API 要简单得多，因为数据源是定义好的，而对于 GraphQL 调用来说，开发人员可能并不清楚命中了哪些数据源。这就是对身份验证、授权、速率限制等问题的关注。

正如我们前面提到的，GraphQL 将补充而不是取代 REST 或其他数据访问 API。它严格适用于获取快速答案，包括获取多条事实。它不是为支持长时间运行的查询而设置的。不可否认，我们可以实现缓存层，但是既然有更简单的替代方法，比如 REST，为什么还要费心呢？

## GraphQL 病毒式传播

GraphQL 已经建立了一个相当大的技术格局。在 [API 管理](https://azure.microsoft.com/en-us/services/api-management/)中有[通常的嫌疑人](https://wso2.com/api-manager/)，其中 GraphQL 只是最新加入名单的一个。如上所述，Apollo 扩展了最初的脸书 GraphQL 客户端，希望成为下一代数据联邦系统。然后是[Hasura](https://hasura.com/),它试图让传统世界(如关系数据库和 RESTful APIs)对 GraphQL 友好。Hasura 刚刚为关系数据库添加了一个理所当然的特性，即进行连接的能力。但是这一次，它不是跨关系表本身，而是独立的 GraphQL 实例。

还有其他类似于 [Wundergaph](https://wundergraph.com/) 的，它采取了相反的策略——一个服务器端 GraphQL 后端框架，它爬行数据库，生成模式，并处理基于角色的访问控制、缓存和状态管理。越来越多的数据库，从 [Neo4J](https://neo4j.com/developer/graphql/) 到 [DataStax](https://docs.datastax.com/en/astra/docs/using-the-astra-graphql-api.html) 、[arrangeodb](https://www.arangodb.com/2017/10/auto-generate-graphql-arangodb/)等，都可以通过 GraphQL 公开数据。同时，一旦开发了 GraphQL 模式，专门的引擎如 [Dgraph](https://dgraph.io/) 将自动生成一个持久数据库。你也可以顺便用哈苏拉[和尤加比特](https://blog.yugabyte.com/yugabyte-and-hasura-make-it-easier-to-build-complex-global-applications/)做同样的事情。

GraphQL 的灵活性是所有这些可扩展性的秘密。像任何 API 一样，它需要护栏——甚至比 REST 更需要护栏，至少在 REST 中，数据源是硬编码的。GraphQL 和 REST 都涉及到复杂性，只是 GraphQL 的复杂性被隐藏了起来。如上所述，随着 GraphQL 作为联邦查询引擎的野心越来越大，它将需要更复杂的内置防护和治理。对于高度管控的行业，可能需要详细的数据谱系来生成审计跟踪，记录只有适当的数据出现，没有任何禁止的违规行为。相比之下，在 REST 中这样做要简单得多，因为连接是由开发人员编码的，而不是由引擎生成的。

如上所述，GraphQL 不会取代 REST。这不仅是因为 REST 已经在现代应用程序堆栈中根深蒂固，而且它更适合高度复杂、长时间运行的查询。凭借其多功能性，我们预计 GraphQL 将成为运营数据库的对等产品，专为使用微服务运行的云原生环境而构建，在这种环境中，对简单、快速答案的需求需要隐藏在幕后的复杂性。GraphQL API 从它在脸书的不起眼的开端，最终出现在聚光灯下。这是一次多么漫长而奇怪的旅行啊。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>