# Rowy 通过低代码云协作挑战了 Airtable 的极限

> 原文：<https://thenewstack.io/rowy-takes-on-the-limits-of-airtable-with-low-code-cloud-collaboration/>

虽然低代码/无代码工具可以帮助初创公司快速起步，但用户很快就会达到这些平台的极限。

科技咨询公司 Thoughtworks 的全球技术主管[迈克·梅森](https://www.linkedin.com/in/mikemasonca)告诉《新堆栈》:“当你想做一些[低代码平台](https://thenewstack.io/does-low-code-mean-more-work-or-more-freedom-for-developers/)不支持的事情时，你要么与之斗争，要么就降级到普通代码。”。

![](img/ba6354f1aa3321a253bf13d61dce7310.png)

[Rowy](https://www.rowy.io/) ，一个[开源项目](https://github.com/rowyio/rowy)瞄准了 Airtable 云协作服务的局限性，建立在谷歌云平台的资源之上，以突破这些障碍。

根据 Rowy 联合创始人 [Harini Janakiraman](https://www.linkedin.com/in/harinijanakiraman/) 的说法，大多数低代码/无代码工具缺乏灵活性，有功能限制，不能很好地扩展，而且价格昂贵。

Janakiraman [在 Product Hunt](https://www.producthunt.com/posts/rowy-2)上写道:“Rowy 是建立在创始人自身的痛点之上的。

*   “无法在他们熟悉的界面(如电子表格)中与我们的队友共享数据库访问权限。
*   我们喜欢 Airtable 的数据协作体验，但它的可扩展性有限，无法与您的生产应用程序同步，存储有限，并且无法在粒度级别控制访问。
*   我们也喜欢 Firebase 快速构建应用程序的体验，但他们的原生云控制台很难使用，特别是对于非技术用户。
*   我们通过第三方应用反复构建自动化。
*   在云控制台中管理数百个云功能，通过 CLIs 在终端中部署它们，试图找出哪个云功能在何时被触发——简直是一场噩梦！老实说，我们不应该以这种方式做事……”

Janakiraman 描述道 [Rowy](https://news.ycombinator.com/item?id=28758598) 是一个熟悉的电子表格 UI。在引擎盖下，它是一个生产数据库，一个 Google Cloud Firestore 上的 noSQL 文档数据存储。

有常见的电子表格功能，如过滤、排序、批量导入/导出数据，以及邀请团队成员在表和字段级别进行粒度权限控制。

Rowy 还支持用户在浏览器中编写云函数；向 Algolia、Twilio、SendGrid、BigQuery 和 Slack 等工具添加自动化扩展；并使用任何 npm 包和 API。

使用 [react-data-grid](https://github.com/adazzle/react-data-grid) ，它只呈现正在查看的表格，以保持滚动体验的平滑。

“这是一个内聚的平台，允许你端到端地建立在 GCP 上，你可以访问数据库，你可以访问无服务器的云功能，存储秘密管理器，你可以编写代码，”Janakiraman 说。

[https://www.youtube.com/embed/SKF31EN9CEA?feature=oembed](https://www.youtube.com/embed/SKF31EN9CEA?feature=oembed)

视频

在一个使用电影表格的[“看什么”演示](https://demo.rowy.io/table/whatToWatch)中，如果你添加一行，然后键入电影名称，其他字段会自动填充，使用一个 [IMDb](https://www.imdb.com/) npm 包提取数据。

以下是一些其他的演示:

*   [演示 1](https://demo.rowy.io/table/learnWithJason) :输入一个单词，看到数据库自动生成图像和定义。
*   [演示 2](https://demo.rowy.io/table/translations) :输入一个单词，获得它的法语翻译和文本到音频。
*   [演示 3](https://demo.rowy.io/table/expenses) :添加收据图像，通过谷歌视觉 API 查看其文本，并通过 [GPT-3](https://en.wikipedia.org/wiki/GPT-3) 检测价格。

## 数据工程背景

Janakiraman 曾是贝莱德纽约和亚太数据工程团队的工程副总裁，后来成为早期风险投资公司鹿角的技术主管。她的联合创始人，Shams Mosowi，曾是鹿角公司的首席软件工程师。

这家初创公司是一个位于澳大利亚悉尼附近的五人团队。最近，红杉资本印度公司为东南亚和印度的女性创始人选择了 15 家创业公司作为新的[项目，名为红杉星火奖学金。](https://www.techinasia.com/sequoia-selects-15-startups-spark-fellowship-programs-first-batch)

Rowy 成立于去年年中。It [在三月份发布了 v2.4](https://twitter.com/RowyIO/status/1501209752608641029) 。根据 Runa Capital 每季度发布的[罗斯指数](https://runacap.com/ross-index/)，它是增长最快的开源创业公司之一。

用户包括日本购物网站乐天、福布斯、谷歌、优步和银行巨头汇丰银行。

## 不仅仅是电子表格

有大量的 [Airtable 竞争对手](https://www.trustradius.com/products/airtable/competitors)，甚至还有开源竞争对手，如 [NocoDB](https://github.com/nocodb/nocodb) ，它转换 MySQL/Postgres/SQLite 数据，以及基于 Postgres 的 [Baserow](https://baserow.io/) 。谷歌有自己的产品叫做[表格](https://tables.area120.google.com/about)，微软有[列表](https://techcommunity.microsoft.com/t5/microsoft-365-blog/announcing-microsoft-lists-your-smart-information-tracking-app/ba-p/1372233)。

根据 Janakiraman 的说法，这些工具允许你编写一些函数，这些函数更像是不同领域的组合公式。

“有很多类似 Airtable 的 UI 替代品，它们专注于给你一个谷歌表单，但有更多的类固醇，你可以有图像，不同类型的字段等等，”她说。

“我们认为自己与众不同的地方在于……我们不需要在 Visual Studio 代码中单独编写云功能，然后转到云控制台……您不仅可以在类似 Airtable 的用户界面中查看 Firestore 数据，还可以基于您的数据构建云功能、自动化和工作流，连接到任何第三方工具，直接在浏览器中使用 NPM 和 API，而没有 CLI、终端或本机控制台的麻烦。”

她说，其他后端即服务初创公司，如 [Supabase](https://thenewstack.io/supabase-takes-aim-at-firebase-with-a-scalable-postgres-service/) 和 [Canonic](https://thenewstack.io/low-code-backend-builder-canonic-starts-with-a-graph/) 更关注基础设施。他们正在与谷歌工程师竞争，试图建立一个更好的数据库或更好的云平台。

“我们在说，‘我们是这个界面，让你可以更好地访问你现有的云平台。因此，我们并不是要求开发人员从构建谷歌云转移到其他东西，或者其他数据库或其他云平台。我们只是对开发者说，‘你可以继续用你熟悉的代码在现有系统上构建。我们不是要求你学习一门新的语言。这是 JavaScript，使用通用框架，等等。但我们给了他们一种工具，可以提高他们的生产力，让他们发展得更快。”

该公司最近还发布了一个名为 [Feedback Fin](https://github.com/rowyio/feedbackfin) 的开源反馈小工具，允许你在任何应用程序中插入一个按钮来收集反馈。

[https://www.youtube.com/embed/8Ci7eLyxhBI?feature=oembed](https://www.youtube.com/embed/8Ci7eLyxhBI?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>