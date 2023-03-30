# Supabase 瞄准 Firebase，推出可扩展的 Postgres 服务

> 原文：<https://thenewstack.io/supabase-takes-aim-at-firebase-with-a-scalable-postgres-service/>

谷歌的 [Firebase](https://firebase.google.com/) 已经成为网络和移动开发者快速入门的一种流行方式，它提供了一套处理后端的工具，这样他们就可以专注于前端的功能。

然而，根据[保罗·科普斯通](https://github.com/kiwicopple)的说法，Firebase 有其局限性，他着手创建开源替代方案 [Supabase](https://github.com/supabase/supabase) 来解决他遇到的问题。

“我在之前的创业中使用 Firebase，遇到了一些扩展问题。因此，我将系统的这一部分迁移到了 Postgres，但 Postgres 没有一些功能，即 Firebase 拥有的实时数据流，”Copplestone 说。

Firebase 实时数据库[存储数据](https://thenewstack.io/google-firebase-trims-middle-tier-faster-app-dev/)并与 NoSQL 云数据库同步。

“Firebase 有一个非常好的系统，你可以通过 websockets 监听数据库的变化。所以我在 Postgres 上使用服务器重新实现了它，然后我开源了它，”他说。

它开始获得关注，他和他的朋友安东尼·威尔逊聚在一起，两人决定用他们的开源版本建立一家公司。

## 基于 Postgres

虽然 Firebase 有 18 种不同的产品，但 Supabase 专注于其社区中最受欢迎的四种产品:Postgres 数据库、授权、大文件存储和自动生成的 API。它仍在构建相当于 Firebase 的功能。

Copplestone 指出，Supabase 不是 Firebase 的一对一克隆。

“值得称赞的是，Firebase 是一种非凡的开发体验。这可能是世界上开始一个新项目的最好工具。但是当你的项目开始扩大规模时，有时会遇到一些困难。这就是我们想要解决的问题，我们通过提供这个成熟的 Postgres 数据库来解决这个问题，”他说。“当然，Postgres 是高度可扩展的，它已经经受了 30 多年的战斗考验。”

尽管年代久远，Postgres 在最近几年经历了受欢迎程度的复苏，系统倡议的联合创始人 Adam Jacob 将其总结为:“其他数据库为特定领域提供了更好的模型，但没有什么能如此优雅地扭曲成你需要的任何形状。”

Supabase 在 Postgres 中使用了很多不同的部分，例如安全层，特别是授权层，以及 OAuth 和 magic 链接。

不是将授权放在中间件中，而是放在数据库级，使用 Postgres 健壮的行级安全功能。行级安全性使得开发人员可以很容易地逐行限制对特定组或部门的访问。

Supabase 还引入了其他开源工具。

除了 Postgres 数据库，它还利用 [PostgREST](https://postgrest.org/en/v7.0.0/) 来生成 API。它采用了 Netlify 开发的 API 服务 [Go True](https://github.com/netlify/gotrue) ，用于处理 Jamstack 项目的用户注册和认证。If 提供一个存储服务器，用于管理 S3 桶或其他 S3 兼容系统中的文件，并使用 API 网关[孔](https://github.com/Kong/kong)。

其目标是 [Jamstack](https://thenewstack.io/predictions-for-the-jamstack-in-2022/) 开发人群。

## 快速增长

在最近的发布中，Supabase 开源了它的[仪表盘](https://supabase.com/blog/2021/11/30/supabase-studio)，其中包括一个内置的 SQL 编辑器和类似 Airtable 的表格视图。

它宣布收购 Logflare，该公司在仪表板中增加了可搜索的 Supabase API 和数据库日志。现在，行级安全性与实时服务器一起工作，因此可以为每个用户设置行级策略，以便实时生效。它仍然在 GraphQL 上工作，但是构建了一个 Postgres 扩展来解决数据库上的 GraphQL 查询。

虽然官方支持 JavaScript 和 TypeScript，但开源社区正在构建许多客户端库，包括 TypeScript、Python、C#和 Swift。

[https://www.youtube.com/embed/QAm1x7KaLq4?feature=oembed](https://www.youtube.com/embed/QAm1x7KaLq4?feature=oembed)

视频

该项目发展迅速。它已经连续五个季度成为 GitHub 上增长最快的创业公司之一。它拥有超过 25，000 名明星，大约 45，000 名开发者注册了该平台。

它不是 Firebase 唯一的开源竞争对手。还有瑞典的开源后端即服务(BaaS) [Nhost](https://nhost.io/) 和 [Etebase](https://www.etebase.com/) ，专注于端到端加密，其开源 SDK 和[后端即服务平台](https://thenewstack.io/guide-serverless-technologies-functions-backends-service/)。

Hasura 是一个开源的实时 GraphQL API 引擎，为 GraphQL 或 REST APIs 提供内置授权。它支持 Postgres、BigQuery、MS SQL Server 等。

然后是 [Skygear](https://skygear.io/) ，一个用 Go 编程语言构建的 BaaS，有一个支持关系数据类型和实时数据同步的数据库。以及 [AppWrite](https://thenewstack.io/appwrite-a-cloud-native-backend-as-a-service/) ，它在一组集成的 REST APIs 中提供包括数据库、存储和授权在内的云能力。

[Parse](https://parseplatform.org/) 提供了一个为 Node.js 应用开发的后端服务器，可以使用环境变量在任何地方运行。它向基于 PostgreSQL 或 MongoDB 的核心添加了一个 GraphQL 接口、一个文件系统和一个通知框架。

[Back4App](https://www.back4app.com/) ，基于 Parse 平台，提供了一个可以用 GraphQL 和 REST 访问的低代码后端。

与此同时，微软拥有。基于. NET 的移动应用平台 [Xamarin](https://dotnet.microsoft.com/en-us/apps/xamarin) ，AWS 提供 BAAS [Amplify](https://aws.amazon.com/amplify/) 和[gameparks](https://aws.amazon.com/blogs/gametech/amazon-gamesparks-is-coming/)，旨在简化网络游戏的后端构建，但仍然拥有与 Firebase 相关的专有锁定。还有一些 Firebase [组件](https://opensource.google/projects/firebase-sdk)是开源的，但不是全部。

## 远程工作

虽然 Copplestone 和 Wilson 的总部在新加坡，但其大约 25 人的团队却分布在世界各地，完全处于偏远地区。2020 年夏天，它加入了 YCombinator 的第一个完全远程课堂。在 2020 年 6 月推出 alpha 版后，它于 2020 年 12 月宣布测试版。

它的客户包括印度尼西亚支付网关 [Xendit](https://www.xendit.co/en/) 、无代码网络监控和整合网站 [Monitoro](https://www.monitoro.co/) 和无代码网站建设者 [TAYFA](https://supabase.com/blog/2020/12/02/case-study-tayfa) 等公司。

继 2020 年 12 月宣布的 600 万美元融资后，它于去年 9 月筹集了 3000 万美元的 A 轮融资。

Copplestone 说，该公司将把资金集中在托管平台上，确保它是健壮的，企业就绪的，并继续扩展。

[https://www.youtube.com/embed/WiwfiVdfRIc?feature=oembed](https://www.youtube.com/embed/WiwfiVdfRIc?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>