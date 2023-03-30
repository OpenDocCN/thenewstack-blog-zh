# MongoDB 发布了用于 MongoDB Atlas 的托管 GraphQL

> 原文：<https://thenewstack.io/mongodb-unveils-managed-graphql-for-mongodb-atlas/>

NoSQL 数据库提供商 [MongoDB](https://www.mongodb.com/) 已经启动了对其托管云数据库 [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) 的基于 [GraphQL](https://graphql.org/) API 的查询语言的支持，作为与 [MongoDB Stitch](https://www.mongodb.com/cloud/stitch) 的集成，后者充当 GraphQL 客户端和服务器，发送、接收和处理请求。

GraphQL 提供了广泛使用的 REST API 的替代方案，与 REST 的方法不同，graph QL 通过 API 提供声明性查询功能，REST 的方法使用完整的信息负载来响应查询，而不是请求特定的数据。因此，GraphQL 允许更小的负载、更快的响应和更高效的代码，这是该公司在介绍该功能的博客帖子中强调的。

然而，在谈到此次发布时，MongoDB 首席技术官兼联合创始人 [Eliot Horowitz](https://www.linkedin.com/in/eliothorowitz) 将重点放在了开发者体验和最终结果上，而不是阴谋诡计。

“开发人员不想管理基础设施。他们希望有清晰的抽象概念，使其易于扩展，并易于思考他们的应用程序中会发生什么，”Horowitz 说。“像这样的服务是一种方式，可以说，我可以完全卸载什么，这样我就不必考虑它、维护它、监控它、为它做安全补丁，它就是有效的。开发人员关心的一切是上市时间，他们构建应用程序的速度，他们创新的速度。随着应用程序变得越来越复杂，一切都是为了让它变得越来越简单。”

Horowitz 表示，结合 MongoDB [在 2019 年](https://www.mongodb.com/press/mongodb-strengthens-mobile-offerings-with-acquisition-of-realm)收购的 [Realm](https://realm.io/) 移动数据库和数据同步技术，增加的 GraphQL 功能将使 MongoDB 用户比以往任何时候都更容易构建跨多种设备运行的 web 应用程序。GraphQL 支持是通过 Stitch 提供的，Stitch 处理后端功能，如用户身份验证和字段级安全性，而 Realm 处理移动数据同步，MongoDB 作为数据层中心的共同标准。

“Stitch 是 MongoDB 上非常薄的一层，旨在使构建 web 应用程序变得非常容易。今天的大多数应用程序都是 web 应用程序。Horowitz 说:“现在的趋势是开发单页的 React 应用程序，这些应用程序拥有某种 API，可以返回到数据和第三方服务。“Stitch 就是在 MongoDB 之上放一个层，处理诸如身份验证、字段级安全性、谁可以访问什么、围绕数据身份验证的复杂规则等等。Realm 基本上将同样的功能引入了移动领域。”

就使用 MongoDB 构建这样一个应用程序而言，该公司表示“不需要几分钟就能完成”基本要求，它列出了这些要求:

*   必须在 MongoDB Atlas 集群中创建一个数据库和至少一个集合。
*   必须创建一个 MongoDB Stitch 应用程序并链接到集群。
*   必须为 Stitch 中的数据库和集合定义用户规则。
*   必须定义缝合方案。

随着上述需求的满足，GraphQL 作为托管服务提供，消除了自己构建和维护 GraphQL 后端的需要，这是 Horowitz 强调的一点。需要注意的重要一点是，这种托管 GraphQL 支持仅在 MongoDB Atlas 中提供，而不是社区版本。

“通常，如果使用不带 Stitch 的 GraphQL，您需要遵循一些步骤来设置 GraphQL 服务器。从那里，开发人员需要从他们的数据创建一个模式，然后才能查询它，”Horowitz 说。“Stitch 处理所有这一切，因此开发人员可以真正不费吹灰之力地开始使用 GraphQL。Stitch 会自动为您生成模式。从这里开始，只需在 Stitch 中点击启用 GraphQL 服务，然后您就可以开始在服务上/针对单个端点进行查询了。”

随着 GraphQL 支持减少到定义数据模型和规则，Horowitz 说他希望看到 GraphQL 的采用继续其上升趋势。

“我对越来越多的 Mongo 开发人员不必编写后端感到特别兴奋。这可能会在 Mongo 社区内推动 GraphQL 的大量采用，这有望在更广泛的社区中推动更多的 GraphQL 采用，”他说。

MongoDB 是新堆栈的赞助商。

由 Pixabay 的 Dean Moriarty 制作的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>