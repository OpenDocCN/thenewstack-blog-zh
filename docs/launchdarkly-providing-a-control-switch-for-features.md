# 黑暗启动:为功能提供控制开关

> 原文：<https://thenewstack.io/launchdarkly-providing-a-control-switch-for-features/>

在持续集成和持续交付的时代，功能标志——使开发人员能够隐藏功能、向受限用户提供访问权限或执行终止开关——正在获得新的关注。

随着 CI/CD 管道变得越来越复杂，特性标志，也称为[特性切换](https://martinfowler.com/articles/feature-toggles.html)，为维护多个源代码分支提供了一个[选择](https://www.linkedin.com/pulse/feature-branching-flags-accelerated-product-justin-baker/)。与平台无关的 DevOps 监控工具 [Honeycomb.io](https://honeycomb.io/) 的联合创始人兼首席执行官 [Charity Majors](https://twitter.com/mipsytipsy) 最近指出，功能标志是用于管理生产中无服务器测试的五种新兴技术[之一](https://thenewstack.io/serverless-testing-in-production/)。她将其描述为一种方式来说，“‘在我同意之前，不要派任何人去写这段代码，”并对总部位于加州奥克兰的[launch crystally](https://launchdarkly.com/)大声疾呼。

据[launch blackly](https://launchdarkly.com/)的产品和营销副总裁[亚当·齐曼](https://www.linkedin.com/in/adamzimman/)说，这不是新技术。

它包括在代码中放置一个标记，表示“如果你满足这些标准，我将向你展示这个东西。如果你没有，我就没有，”他说。有些属性是必须满足的。每次在代码中遇到这种情况，它都会检查数据库中的值。如果符合标准，它就执行代码。对于 SaaS 应用程序，这种类型的查找已经变得非常标准。

它使客户能够锁定目标用户，进行受控部署和 A/B 测试，而无需重新部署应用程序。用户可以为不同的国家或客户群打开或关闭某些功能。齐曼说，如果某个功能真的很糟糕，它可以像按下电灯开关一样被轻易扼杀。

他说，公司传统上建立和维护系统来管理谁有权访问什么代码，但因为它们不是业务的核心，这些项目往往缺乏资源，得不到很好的维护。

联合创始人兼首席执行官 Edith Harbaugh 在 InfoQ [的一篇文章中指出](https://www.infoq.com/articles/feature-flags-gone-wrong)功能标志如果没有得到很好的维护，可能会出错。LaunchDarkly 的业务就是为客户应对这一挑战。齐曼说，它正在将这些控制扩展到业务方面，如营销方面。

“我们已经在生产中测试了互联网迷因，并使之成为最佳实践。因为特征标志具有隔离的概念，它可以控制谁可以看到那里有什么，我们有能力消除在生产环境中运行不完整代码的风险，”齐曼说。

[https://www.youtube.com/embed/pwA_Ehp2SMY?feature=oembed](https://www.youtube.com/embed/pwA_Ehp2SMY?feature=oembed)

视频

这个领域的其他公司包括像 [Optimizely](https://www.optimizely.com/) 这样的公司，他们已经开发了能够进行前端用户测试的工具， [Rollout.io](https://rollout.io/) 和 [Taplytics](https://taplytics.com/blog/feature-flags-use-cases-benefits/) 。

launch crystally 一直专注于开发人员的体验——使入职变得快速和简单——并且在应用程序中使用服务只需要最小的开销或不需要开销。

它的 SDK 在 GitHub 上有一系列的编程语言，包括 JavaScript、C#、Java、Go、TypeScript、PHP、Python、Swift、Objective C、Ruby、iOS、Android 和. NET。

“一旦[开发人员]对某个功能有了概念或者更新了某个功能，他们就可以创建一个功能标志，创建这个入口。把它放在 LaunchDarkly 里，每次遇到那个代码，它都会知道该怎么做，”他说。

当应用程序启动时，会与服务进行一次性通信，服务会将值加载到应用程序中以供使用。

如果开发人员在应用程序运行时更改了这些值，它将使用服务器发送事件(SSE )(一种用于单向实时消息传递的协议)向您的服务器发送消息，并将这些值下推到所有应用程序端点。他说，变化可以在 200 毫秒或更短的时间内完成。

它的 [webhooks API](https://docs.launchdarkly.com/docs/webhooks) 允许你构建自己的集成，订阅 LaunchDarkly 中的变化。

Zimman 说，launch crystally 在后端使用多个数据库，包括 MongoDB、Elastic、Postgres 和 Redis，使用适合存储值的数据库。该公司建立了自己的流媒体协议，并快速使用内容交付网络进行分发。

所有标志都存储在本地，因此即使 CDN 关闭，您的服务器也将继续使用最后一组功能标志规则运行。其企业用户可以创建自定义角色，类似于[【IAM】](https://aws.amazon.com/iam/)AWS 身份与访问管理(IAM)系统，以及自定义目标，如点击和页面查看目标。

Zimman 说，展望未来，该公司正在寻求为开发商、运营商和企业用户提供更多的控制点，并在工作流程中实现自动化，同时提供更好的反馈。

客户包括 GoPro 和 TrueCar。Atlassian 在去年秋天的用户大会上强调了 launch crystally，最近宣布与 launch crystally 和 Rollout 合作，将 [功能标记集成](https://www.atlassian.com/blog/jira-software/feature-flagging-integrations) 到吉拉软件中。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>