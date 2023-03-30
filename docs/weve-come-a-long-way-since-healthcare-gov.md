# 自 Healthcare.gov 会议以来，我们走过了漫长的道路

> 原文：<https://thenewstack.io/weve-come-a-long-way-since-healthcare-gov/>

本周，拜登政府[通过](https://www.whitehouse.gov/briefing-room/statements-releases/2022/01/14/fact-sheet-the-biden-administration-to-begin-distributing-at-home-rapid-covid-19-tests-to-americans-for-free/)[网站](https://special.usps.com/testkits)的[夫妇](https://www.covidtests.gov/)向公众提供家庭 COVID 测试，允许每个地址订购四项测试，由美国邮政署​(USPS)提供。总的来说，整个事件似乎是成功的。

这是一个成功，至少当你把它与八年前 Healthcare.gov 的推出相比较，并且把成功定义为“没有在交通浪潮中崩溃”的时候当然，如果你将成功定义为“能够在多租户联合体中从与他人相同的地址订购 COVID 测试”，那么，好吧…

现在，作为一名开发人员，你可能会认为这是一个技术上的失败。但是暂且把这个放在一边，我们可以惊讶于政府——这个效率低下和技术无能的庞然大物，有些人可能会说——如何在几周的时间内成功地建立了一个小网站，实际上支撑住了使用量的激增(一位 Reddit 用户记录的并发用户数一度接近 70 万，可能远远超过这个数字)。

这个故事来自软件工程师[保罗·史密斯](https://adhoc.team/about/our-team/paul-smith/)，在一篇博客文章中[研究了 covidtests.gov 架构](https://adhoc.team/2022/01/18/covidtests-usps-aws-managed-services/)，发现该网站是使用各种亚马逊网络服务(AWS)产品构建的，包括 Akamai 和 AWS CloudFront 内容交付网络(CDN)，AWS S3 对象存储，以及他怀疑是 Lambda 函数前面的 API 网关。

虽然史密斯使用一些基本的技术侦察收集了所有这些信息，但他也有一个独特的见解，他在另一篇文章中披露了这一点，在这篇文章中，他研究了为什么 COVIDtests.gov 在 Healthcare.gov 跌倒的地方工作。也就是说，他“是帮助 HealthCare.gov 扭转局面的团队的一员”，现在是医疗保险医疗补助服务中心在 HealthCare.gov 工作的承包商。根据史密斯的说法，一切进展顺利的部分原因是因为他们保持简单。

“这意味着该网站的设计完全采用了众所周知的组件，这些组件已被证明能够处理繁重的负载，”Smith 写道。“显然，管理此次发布的团队为超大的需求进行了规划，远远超出了典型政府网站的体验，并相应地做出了技术选择。”

他将这里使用的方法与 Healthcare.gov 进行了比较，写道“将这种方法与 2013 年和 HealthCare.gov 启动的时代进行对比，当时政府的最先进技术是管理私人数据中心的服务器，这些数据中心有许多移动部件和故障模式，没有资源和经验来处理强烈的公共需求和流量。”

当然，用户界面——以及在网站上所做的一切——远没有注册健康保险所需的过程复杂和苛刻。尽管如此，自 2013 年以来，政府似乎在网站建设方面吸取了一些教训。更重要的是，据许多人说，该网站甚至可以在任何设备或浏览器上运行，在新旧设备上都可以显示和运行。如果你因为这样或那样的原因不能在网站上订购(比如前面提到的多租户问题)，政府就会转向另一种技术形式:电话。

如果所有这些都没有给你留下深刻的印象，还有最后一件事，正如[指出的，一个机敏的 Redditor](https://www.reddit.com/r/sysadmin/comments/s74sv6/comment/ht91uet/?utm_source=reddit&utm_medium=web2x&context=3) 发现了一个小复活节彩蛋。作为来自海外的游客，他们收到一个错误:

```
{
    "error":  "QWNjZXNzIG1haW4gcHJvZ3JhbS4gQWNjZXNzIG1haW4gc2VjdXJpdHkuIEFjY2VzcyBtYWluIHByb2dyYW0gZ3JpZC4="
}

```

从 base64 解码时，错误信息翻译为“访问主程序”。进入主安全系统。访问主程序网格。

[https://www.youtube.com/embed/RfiQYRn7fBg?feature=oembed](https://www.youtube.com/embed/RfiQYRn7fBg?feature=oembed)

视频

## 本周的节目中

*   **在 Go 1.18 中开始使用泛型&Fuzzing:**Go 1.18 即将推出，上个月[发布了测试版](https://go.dev/blog/go1.18beta1)，随之而来的是两个新特性:泛型和 Fuzzing。虽然你现在可以出去安装测试版并开始玩这两个功能，但有一点指导可能会有所帮助，所以 go 团队已经发布了[两个针对 Go 1.18](https://go.dev/blog/tutorials-go1.18) 的新教程，专注于这些新功能。首先，[关于泛型的教程](https://go.dev/doc/tutorial/generics)将指导你创建一个可以处理多种类型的泛型函数，从你的代码中调用它，然后讨论类型约束以及如何为你的函数编写它们。要了解更多信息，你也可以看看 GopherCon 关于泛型的演讲。接下来，[fuzzing 教程](https://go.dev/doc/tutorial/fuzz)将带您完成使用 fuzzing 诊断和修复问题的过程，让您编写一些有错误的代码，并使用 go 命令使用 fuzzing 来查找、修复和验证错误。
*   **Faker，js 重获新生:**上周，我们为您带来了[一个开发者的故事](https://thenewstack.io/is-open-source-really-free-if-we-arent-allowed-to-break-it/)，他决定打破他非常依赖的 JavaScript 包 faker.js 和 colors.js，以挑战这个人和传播阴谋论的名义。本周，看起来一群开发人员已经放弃了 Faker，并将它作为一个社区控制的项目重新启动。关于所有细节，你可以查看来自新团队本身的[更新，它涵盖了自分叉项目以来它所采取的各种步骤，包括组装](https://fakerjs.dev/update.html)[新的 GitHub repo](https://github.com/faker-js/faker) ，发布[文档](https://fakerjs.dev/)，以及进行“大量的问题分类和许多许多的公关审查”至于 colors.js，看起来并没有组织类似的努力，但似乎 npm 继续提供该库的还原版本，原始开发者仍然无法访问它。

*   **Vue 3 即将成为默认:**流行的 [Vue](https://vuejs.org/) JavaScript 框架[将在几周内转换到 Vue 3](https://blog.vuejs.org/posts/vue-3-as-the-new-default.html) ，对于所有 Vue 开发者来说，有一些变化需要注意。更换定于 2022 年 2 月 7 日星期一进行，可能包括一些[潜在的必要措施](https://blog.vuejs.org/posts/vue-3-as-the-new-default.html#potential-required-actions)以避免破损，所以请务必阅读。在这篇博文中，Vue 的创建者[尤雨溪](https://www.linkedin.com/in/evanyou)讨论了 Vue 是如何从“仅仅是一个运行时库”演变成“一个包含许多子项目的框架”的，这是“唯一可能的，因为 Vue 是一个社区驱动的项目。”虽然 Vue 3 的试运行时间比预期的要长一点，但你写道“在 Vue 核心之外，我们几乎改进了框架的每个方面。”新的 Vue 3，除了帖子中详细介绍的新功能之外，还带有新的文档和新的 vuejs.org“将为不同背景的用户提供更新的框架概述和建议，灵活的学习路径，在指南和示例中在选项 API 和组合 API 之间切换的能力，以及许多新的深入章节。”对于那些使用 Vue 的人来说，这篇博文绝对是所有有趣和相关细节的必读之作。
*   **GitHub 自动化开源记分卡:** GitHub 本周宣布，它将通过 GitHub Actions 和 OpenSSF 记分卡 V4 帮助[降低开源软件的安全风险。开源安全基金会(OpenSSF)](https://github.blog/2022-01-19-reducing-security-risk-oss-actions-opensff-scorecards-v4/) [记分卡](https://github.com/ossf/scorecard)的最新版本 V4 为开源项目提供了一个自动化的安全工具，可以标记有风险的供应链实践。现在，GitHub 已经在 GitHub 用户界面和市场中添加了 [GitHub 操作](https://github.com/marketplace/actions/ossf-scorecard-action)和 [starter 工作流](https://github.com/actions/starter-workflows)，使用这些工具的项目将在存储库发生变化时自动运行记分卡操作，使用内置的代码扫描提醒开发人员注意有风险的供应链实践。结果将自动出现在项目的“安全性”选项卡下，显示项目是否实现了记分卡项目的最佳实践。公共存储库可以免费访问 CodeQL、代码扫描 API 和 1000 分钟的操作时间。
*   **作为开发人员使用 Wordle:**上周，一篇有趣的小博文讲述了[用应用函子](https://blog.ploeh.dk/2022/01/17/enumerate-wordle-combinations-with-an-applicative-functor/)枚举 Wordle 组合。马克·西曼的博客文章是“特别编程的例子”和“当你需要列举组合时，列表的应用性是如何有用的例子”本质上，在这种情况下，你如何使用 Haskell 来编写解决单词的过程？请继续阅读，找出一个这样的尝试。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>