# 低代码后端构建器 Canonic 从图开始

> 原文：<https://thenewstack.io/low-code-backend-builder-canonic-starts-with-a-graph/>

你已经厌倦了构建后端基本相似、只有前端有本质区别的应用程序。所有人都是。这就是为什么有这么多后端即服务提供商的原因。

然而，Canonic 的团队采取了[低代码](https://thenewstack.io/using-apis-with-low-code-tools-9-best-practices/)路线，让更广泛的用户——也许是销售和营销团队，他们不一定是开发人员——分享这种爱。

联合创始人 Pratham agr awal 离开了伊利诺伊大学厄巴纳-香槟分校，在印度开办了自己的设计和开发店，他发现自己花在重复性任务上的时间太多了。

“有些项目有非常相似的后端，只是稍有改动，前端却不同。我总是觉得，如果这种信息已经在后端构建好了，只需要构建前端，我就可以节省几个小时的精力，”他[告诉](https://www.theadreview.com/meet-pratham-agrawal/) AdReview。

同为联合创始人的 [Aditi Jain](https://www.linkedin.com/in/aditi-jain-001b766b/?originalSubdomain=in) 、 [Simranjot Singh](https://www.linkedin.com/in/iamsimranjot/?originalSubdomain=in) 和 [Kartik Grewal](https://www.linkedin.com/in/kartikgrewal/?originalSubdomain=in) 曾在聊天机器人供应商 Haptik 与 Awrawal 合作，他们有类似的经历，并于 2020 年 5 月开始创造一个更好的选择。

“Canonic 的诞生是出于让后端开发变得简单、可重用和强大的需求，”这家印度初创公司的贾恩说。“我们觉得有必要简化这一点，使产品工程不受编写代码的技术诀窍的限制，代码可以自动生成，同时保持最大限度定制的可能性，不管有没有代码。”

## 建立在图表上

该图是任何基于规范构建的项目的起点。它允许用户在层次结构中可视化地组织信息，显示不同组件之间的关系，并在几分钟内创建 REST 和 GraphQL APIs。

“把它想象成思维导图，”贾恩解释道。使用该图，用户可以直观地定义他们的 API 和表的核心结构，以及他们想要链接的任何集成

它允许您构建复杂的工作流，类似于 Zapier，允许数据从一个集成流向另一个集成。你基本上用图表定义了后端的中枢神经系统。根据该图，Canonic 部署了一个无服务器 API 以及一个数据库和任何相关服务，比如触发器或 webhooks。它完全没有服务器，由 AWS 提供支持。

它包括:

*   一个内容管理系统(CMS ),可动态适应您定义的数据。
*   CRUD APIs 以编程方式管理内容，并构建和集成应用程序。
*   用户创建的所有 API 的自动生成文档，以及触发和测试这些 API 的示例和平台。

“这个 API 是完全可扩展的，这意味着您可以轻松地以自定义端点的形式添加更多功能-我们有一个内置的代码编辑器-以及跨越数百个第三方集成的工作流。总的来说，你可以用最少的后端经验，通过一个基于网络的应用程序创建复杂的后端服务和 API。

Canonic 是一个 web app 在平台上创建的所有内容都保留在平台本身提供的数据库中。然而，用户可以选择项目将被部署的区域。

有一个 [SDK](https://canonic.dev/features/sdk/) 允许你将你的项目直接集成到你自己的代码编辑器中，尽管该团队将 Canonic 吹捧为一站式后端平台，使你能够在一个地方查看和做所有事情。

CMS 基于 AWS Cloudfront。数据在传输中和静态时都是加密的，基于角色的身份验证和治理包括基于最低特权访问的许可 API 密钥。

用户可以从 Microsoft SQL Server、Airtable、MongoDB、PostGres、MySQL 或 Google Sheets 导入数据，Canonic 将自动生成该数据库的模式模型。

通过与 Okta、Auth0 和 OneLogin 的集成提供无代码身份登录。

用户还可以安排触发器，例如发送每日报告、每月报告或其他提醒，而无需编写任何代码。

这项技术于去年 8 月发布，团队已经发展到 9 名员工。

[https://www.youtube.com/embed/MpInTJgGwmM?feature=oembed](https://www.youtube.com/embed/MpInTJgGwmM?feature=oembed)

视频

金融科技初创公司 smallcase 在为公司建立内部路线图工具时转向了 Canonic

“在探索了一些现有的工具后，我们意识到由于一些定制需求，我们遇到了障碍。因此，我们决定探索无代码/低代码平台。主要从事平台交易核心代码工作的前端工程师 Shivang Bhandari 说:“我们觉得没有必要只为后端或前端需求雇佣人员，这反过来会耗费我们大量的时间、金钱和精力。

“Canonic 的无服务器部署能力、平台的直观性和定价都非常合理。围绕路线图用例已经编写了一些指南和文档，这使得设置甚至构建初始 POC(概念验证)变得非常容易。)

“该产品使用起来非常直观，项目也易于部署。Canonic 团队在我遇到困难或想要更好地理解工作流程时会非常及时地提供帮助。”

## 拥挤的空间

在低代码/无代码开发领域有很多竞争者，包括 [Xano](https://www.xano.com/) 、 [Supabase](https://thenewstack.io/supabase-takes-aim-at-firebase-with-a-scalable-postgres-service/) 、 [Backendless](https://thenewstack.io/backendless-badass-baas) ，在那些加入前端的人中，还有 [Bubble](https://bubble.io/) 、 [AppSmith](https://thenewstack.io/appsmith-an-open-source-low-code-framework-to-build-internal-apps/) 和 [AppGyver](https://www.appgyver.com/) 。

贾恩说，Canonic 在三个方面脱颖而出:

1.  它是完全无服务器的，根据 API 调用的数量来定价。
2.  用户可以使用数百个集成在其数据库之上定义业务逻辑。
3.  图形用户界面在客户中大受欢迎。

展望未来，该公司希望在相关用例上加倍努力，使其更容易满足复杂的需求。

它还希望通过开放平台和创建市场来增加可用的构建模块的数量。

“用户的角色变成了作曲者。他们只是把已经完成的不同部分组合起来，在几个小时而不是几个月内完成真正复杂的东西，”贾恩说。

“我们希望关注的第三个方面是，当用户达到平台的极限时会发生什么。我们希望毕业是透明的、可靠的，并且与开发人员的交接一样。用户应该不必从头开始。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>