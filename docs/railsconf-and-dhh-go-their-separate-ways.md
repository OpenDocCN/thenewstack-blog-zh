# 铁路和 DHH 分道扬镳

> 原文：<https://thenewstack.io/railsconf-and-dhh-go-their-separate-ways/>

本周的一篇[博客文章可能是一封电子邮件](https://twitter.com/konstantinhaase/status/1499524059792556035)来自 Ruby on Rails 的创造者[大卫·海涅迈尔·汉森](https://dhh.dk/)，也被称为 DHH。在一篇名为“ [No RailsConf](https://world.hey.com/dhh/no-railsconf-faa7935e) ”的博客文章中，DHH 花了近千字详细描述“2021 年对于 Ruby on Rails 来说是不可思议的一年”，以及他个人为这个项目所做的一切，然后分享了一封来自 RailsConf 组织者的简短电子邮件，详细描述了他们“开始与其他贡献者分享开幕主题演讲阶段”的决定

显然，这不是一个吸引 DHH 的想法。“这是一个真正的耻辱，这就是我们现在所处的世界，”他写道。“政治和意识形态的分歧如此之大，以至于我们甚至无法在一次会议上分享对 Ruby on Rails 的热爱，而不需要清算旧账。”

尽管博客文章中没有提到到底是什么样的问题，你可能还记得去年发生的一件事，当时 [Basecamp 试图阻止员工在工作中讨论政治](https://world.hey.com/dhh/basecamp-s-new-etiquette-regarding-societal-politics-at-work-b44bef69)，作为回应三分之一的员工[离开了公司。](https://www.theverge.com/2021/5/3/22418208/basecamp-all-hands-meeting-employee-resignations-buyouts-implosion)

虽然有些人准备和 DHH 一起寻找出路，但更多人的回应是:“不要让上帝把你劈开的那扇门撞到你。”或者像他们这些天在 internetz 上说的那样，“[好，好，好，如果不是我自己行为的后果。](https://www.youtube.com/watch?v=pmm3MBxfghU)

自从 DHH 的博客发布以来，一个特别的 Twitter 帖子一直在流传，Ruby 负责人 Brandon Weaver 将 DHH 的现状与 Scala 进行了比较。

在帖子中，他写道，Scala 社区在 2016 年允许一名“知名的奴隶制辩护士和种族主义者”在 LambdaConf 发言后，经历了一场分裂，并且“DHH 目前的思维方式很快就走上了那条道路，我已经看到了我期望从他的博客帖子中出现的那些圈子的语言。”

就 DHH 而言，尽管他就此话题发表了一篇博文，但他似乎对整个事件并不担心，声称他“有信心我们最终能够绕过已经泄露到我们程序中的难以驾驭的政治化。”

“我不相信这是大多数程序员或大多数公司最终想要的，”他继续说道。“但这是一个透露偏好的危险时刻，所以我完全理解为什么许多人选择回避。”

DHH 明年是否会被邀请回来还有待观察，但如果 Twitter 上的反应有任何迹象，似乎许多人在超过 15 年后没有他的主题演讲也很好。

## 本周的节目中

*   AWS Lambda 获得. NET 6 运行时:AWS 已经[为 AWS Lambda](https://aws.amazon.com/blogs/compute/introducing-the-net-6-runtime-for-aws-lambda/) 引入了. NET 6 运行时，这意味着开发者现在可以使用[。NET 6](https://dotnet.microsoft.com/en-us/download) 运行时在 x86 和 Arm/Graviton2 处理器上构建 [AWS Lambda](https://aws.amazon.com/lambda/) 函数。而。NET 6 有许多自己的新特性，AWS 写道，也有新特性添加到。开发人员可以用它来改进诊断和性能，并使用新的编码模式。此外，AWS 提供了作为开源项目的 [Lambda 运行时客户端](https://github.com/aws/aws-lambda-dotnet/tree/master/Libraries/src/Amazon.Lambda.RuntimeSupport)，提供它所说的“在所有环境中一致和透明的 Lambda 运行时客户端体验，无论是托管运行时、容器映像还是使用 Lambda 运行时客户端。NET 自定义运行时。了解有关迁移现有。NET Lambda 函数添加到新的。NET 6 运行时，去看看博客文章，或者读一读 Lambda 开发者指南。
*   Knative(终于)加入了 CNCF:等待终于结束了，Knative 本周加入了云计算本地计算基金会(CNCF)作为一个无服务器孵化项目。将 [Knative](https://knative.dev/docs/) 加入 CNCF 的可能性已经酝酿了很久，而[曾一度被宣布在可能性领域之外](https://thenewstack.io/knatives-independent-future-outside-a-foundation/)。但正如 IBM 现在所写的，“通过接受 Knative 作为孵化项目，CNCF 获得了一个扩展、简化和增强 Kubernetes 平台的项目，用于无服务器和事件驱动的工作负载。这是一个双赢的组合。”除了标准的祝贺性陈词滥调，IBM 关于此事的博客帖子提供了自己对 Knative 成为孵化项目之旅的看法，以及 IBM 目前正在改进的功能，如 Knative 的性能、异步调用和领导 Knative 运营商。如果你想了解更多，除了这篇博文，IBM 还邀请读者“参加(和/或在 3 月 8 日之前提交演讲)”2022 年 5 月在西班牙巴伦西亚举行的第一届 KnativeCon 。

*   围棋历史: [Golang Weekly](https://golangweekly.com/issues/402) 时事通讯用 [Go 强调了它所谓的“资源宝库”和“监管的壮举”:一部纪录片](https://golang.design/history/)，一份“来自围棋发展过程的问题、讨论、建议、CLs 和会谈”的列表，旨在提供围棋历史的全面参考事实上，全面也是一个恰当的描述，因为它提供了功能添加、语言设计等的完整时间表。想知道关于[仿制药](https://golang.design/history/#generics)添加的一切？这无疑是一个很好的起点。如果没有别的事，请前往查看[有趣的事实](https://golang.design/history/#fun-facts)部分。例如，你可以去看看 1972 年 [Go 的第一次提交？！](https://github.com/golang/go/commit/7d7c6a97f815e9279d08cfaea7d5efb5e90695a8)
*   Mozilla 的开发者网络(MDN)得到了一次彻底的改革:自从 MDN 的最后一次重新设计已经过去了[五年，现在计时器可以重置了，因为该网站本周](https://hacks.mozilla.org/2017/07/the-mdn-redesign-behind-the-scenes/)[得到了另一次彻底的改革](https://hacks.mozilla.org/2022/03/a-new-year-a-new-mdn/)。从他们所说的专注于“社区和简单性的核心概念”的新主页到“为改进导航而重新设计的文章页面”，Mozilla 表示，新的 MDN“雄心勃勃地计划利用我们的新工具来探索改进的导航，生成标准化和支持摘要，并将 MDN 文档嵌入到开发人员最需要的地方:他们的 IDE、浏览器工具等。”除了已经完成的工作，Mozilla 还表示，“MDN Plus”即将推出，它将“根据我们从希望定制 MDN 体验的 web 开发人员那里收到的反馈，提供一项高级订阅服务”，具有通知、文章收藏和 MDN 离线体验等功能。
*   水疗的错误？最后，我们把你引向一篇博文，这篇博文认为[的单页应用(SPAs)是一个错误](https://gomakethings.com/spas-were-a-mistake/)，这使得它成为本周黑客新闻的[高层。在博客文章中，JavaScript 开发者 Chris Ferdinandi 认为，虽然“有几个例子表明 spa 是有意义的，是正确的选择”，但总的来说，“spa 作为一种行业趋势或‘最佳实践’是错误的。”费迪南德第二天又发了一篇帖子，这次详细介绍了如何制作和温泉一样快的移动终端。关于这个话题的更多信息，你也可以看看我们最近关于 htmx 的报道以及关于 spa 和 MPAs 的争论。](https://news.ycombinator.com/item?id=30528473)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>