# 本周节目:你能感觉到燃烧吗？

> 原文：<https://thenewstack.io/this-week-in-programming-can-you-feel-the-burn/>

本周编程界的一个大标题来自一个统计数据:根据 Haystack Analytics 的一项研究，83%的开发人员饱受倦怠之苦。

作为一名开发人员，您可能不会对这个统计数据感到惊讶——除非，从统计角度来说，您属于那 17%感觉不错的人。不出所料，同样多的受访者(81%)表示，新冠肺炎·疫情对这种倦怠的增加负有部分责任，主要原因是“工作量增加”。

去年，当世界上许多知识工作者突然远离网络时，我怀疑通勤和办公室会议并不是唯一突然消失的东西。相反，随着休闲时间和活动融入日常生活，长达一小时的午餐和更严格的工作时间界限也消失了。面对这种突然远离的员工，我自己的直觉是，公司会想方设法确保他们得到同样的回报，推动他们的员工不断验证他们确实在工作。

作为一个在过去十年的大部分时间里都在远程工作的人，我亲眼目睹了围绕远程工作和责任的拉锯战，一些公司要求我使用时间跟踪应用程序对每天的每一分钟负责。朋友们讲述的公司跟踪他们的远程员工，确保他们的在线头像永不闲置的故事很常见，我只能想象这种行为在去年有所增加。嘿，如果你没有通勤时间，你可以做更多的事情！

那么，有人真的对开发者感到精疲力竭感到惊讶吗？我知道我不是。

更糟糕的是，New Stack 的 Lawrence Hecht 研究了这些数字，发现除了基本的标题之外，[年轻的女性开发人员甚至比她们的男性同事更容易倦怠](https://thenewstack.io/young-female-developers-burn-out-because-of-expectations/)，高达 16 个百分点，原因是“管理层的不切实际的要求”

与此同时，当诸如此类的头条新闻出现时，只需稍作等待，就会有一系列关于“如何战胜倦怠”的文章流传开来，同时还有一些提供技巧和应用程序作为解决方案的企业电子邮件。不要担心，正如公关人员[艾德·兹特龙](https://www.linkedin.com/in/edzitron)在他的博客文章中所提到的，关于倦怠对话是如何成为将你的痛苦转化为营销的工具。

“如果你所在的公司搞不清楚员工为什么会感到疲惫，让我来为你简化一下:疲惫是由看似无止境的工作造成的。这是疲惫的一种形式。“本质上，这不是一个心理健康问题——这是一个超负荷且无法从所述超负荷中喘息的问题，试图通过提供‘心理健康’、‘健康’和‘冥想’之类的东西来解决它是不真诚的，”齐特龙写道。他还写道，“他们想要一种能够处理问题的光学方法，让人们感觉好像他们在乎，而不是做他们实际上应该做的事情来应对倦怠——给人们更多的工资，雇佣更多的人，以便工作分散到更多的人身上，并积极主动地监管人们肩上的工作量。”

在那之前…祝你好运。

## 本周的节目中

*   今年早些时候，随着 [OpenSearch](https://opensearch.org/) 的首次发布，AWS [完成了其弹性搜索](https://thenewstack.io/this-week-in-programming-aws-completes-elasticsearch-fork-with-opensearch/)的分叉。如果你不明白，整件事有点像 AWS 和 Elastic 之间的拔河比赛，AWS 最终看起来占了上风。在 Elastic 改变了 ElasticSearch 的许可，试图阻止 AWS 出售基于当时开源项目的服务后，AWS 将该项目分叉为在 Apache 2.0 下发布 OpenSearch，有效地保留了其开源状态。现在，OpenSearch 已经[达到了 1.0](https://opensearch.org/blog/updates/2021/07/opensearch-general-availability-announcement/) ，AWS 表示，这不仅“标志着 OpenSearch 的第一个生产就绪版本”，还引入了“多个新的增强功能”，如数据流、跟踪分析跨度过滤、报告调度等。1.0 版本还涉及相当多的代码清理，删除专有代码和标记，并增加了从 ElasticSearch 升级到 OpenSearch 的能力，就像您正在执行 ElasticSearch 的正常升级一样。如果你对了解项目的进展感兴趣，请前往[公共路线图](https://github.com/orgs/opensearch-project/projects/1)了解更多信息。
*   继推出 64 位的 Visual Studio 2022 第一个预览版之后，微软发布了 [Visual Studio 2022 预览版 2](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-preview-2-is-out/) ，它表示该版本专注于“个人和团队生产力、现代发展和不断创新的主题”更具体地说，它带来了十多种语言的本地化，最新版本的 C++构建工具，特别是 XAML 和 web 应用程序的实时预览。在最后一点上，这意味着不再仅仅为了看到最小的视觉变化而重新编译——相反，您将实时看到差异。Preview 2 还在其热重载特性中增加了 C++支持，这同样意味着您可以编辑您的 C++和。NET 应用程序运行时。如需完整的功能列表，请查看[发布说明](https://docs.microsoft.com/en-us/visualstudio/releases/2022/release-notes-preview)和视频摘要。

[https://www.youtube.com/embed/eUk8cpQv9Eg?feature=oembed](https://www.youtube.com/embed/eUk8cpQv9Eg?feature=oembed)

视频

*   **无服务器 COBOL？**我必须承认，当我读到这个标题时，我短暂地笑了一下——只是想到了一种 60 年前的语言正在走向无服务器化——但当 AWS 谈到[无服务器 COBOL](https://aws.amazon.com/blogs/opensource/serverless-cobol-rejuvenating-legacy-code-with-open-source-software/) 及其使用 AWS Lambda 和 GnuCOBOL 更新遗留 COBOL 代码的方法时，它并不是在开玩笑。毕竟，去年我们看到了当你认为像 COBOL 这样的语言不再值得学习时会发生什么:[遗留的失业系统在疫情引发的裁员的重压下崩溃](https://thenewstack.io/u-s-unemployment-surge-highlights-dire-need-for-cobol-skills/)。也许无服务器 COBOL 在这里可以有所帮助？如果 COBOL 仍然在您的系统上运行，也许 AWS 关于无服务器语言的系列文章会有用。
*   **副驾驶的传奇还在继续:** GitHub 的“AI 配对程序员”[副驾驶](https://copilot.github.com/)现在才出来几周，它的背上就有一个巨大的靶子。这项服务还处于技术预览阶段，但是网络普通用户总是对基于人工智能的代码建议服务吹毛求疵。我们已经看到有多少[认为 Copilot 违反了 GPL 许可](https://thenewstack.io/this-week-in-programming-github-copilot-copyright-infringement-and-open-source-licensing/)，以及这种观点如何可能是开源开发者中的代沟的结果[，现在焦点是智能感知如何实际上](https://thenewstack.io/this-week-in-programming-github-copilot-and-the-generational-divide/)[编写错误代码](https://gist.github.com/0xabad1dea/be18e11beb2e12433d93475d72016902)。安全研究员 [Melissa Elliot](https://0xabad1dea.github.io/) ，又名 [0xabad1dea](https://twitter.com/0xabad1dea/status/1393381762697420802) ，花了一些时间与 Copilot 在一起，发现该服务在一定程度上定期提供不正确的代码。在 GitHub 的要点中，她提供了三个 Copilot 这样做的例子，写道它们“不需要任何哄骗；Copilot 很乐意根据对功能代码的直接要求来编写它们。不可避免的结论是，Copilot 可以并将定期编写安全漏洞，尤其是在内存不安全的语言中。”她猜测，问题的一部分在于，Copilot 的训练集包括了网站上的所有公共代码。“在这个模型中，专业制作的代码和初学者的家庭作业似乎没有任何系统的分离。神经网络见，神经网络做。“所以，在你给它打电话并依靠 Copilot 为你写代码之前…

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>