# 本周节目:Istio 重组指导委员会以避免单一供应商占多数

> 原文：<https://thenewstack.io/this-week-in-programming-istio-restructures-steering-committee-to-avoid-single-vendor-majority/>

虽然有些人可能永远无法接受这样一个事实，即最初由谷歌和 IBM 创建的 Istio 服务网不会[移交给](https://thenewstack.io/googles-management-of-the-istio-service-mesh-raises-questions-in-the-cloud-native-community/)[云本地计算基金会](https://www.cncf.io/) (CNCF)，但该项目在过去一周迈出了[一大步](https://istio.io/latest/blog/2020/steering-changes/)，以平息那些批评该项目受谷歌多数控制的人:Istio 已经[引入了一个新的 Istio 指导委员会](https://istio.io/latest/blog/2020/steering-changes/)。

根据这篇博文，新的指导委员会将由 13 个席位组成，其中四个是“选举产生的社区席位”，九个是“按比例分配的贡献席位”，他们说这一变化“巩固了我们对开放治理的承诺，确保项目周围的社区始终能够引导其方向，并且没有一家公司对项目拥有多数投票控制权。”这最后一点实际上是此次发布的关键，他们后来进一步更明确地澄清，“没有一个供应商，不管他们的贡献有多大，对 Istio 项目拥有多数投票控制权。”为此，他们写道，他们“对一家公司可以拥有的席位数量实施了限制，这样他们既不能一致赢得投票，也不能否决委员会其他成员的决定。”

至于这些席位如何分配，四个社区席位将由来自四个不同组织的四名代表组成，并将在年度选举中选出。九个贡献席位将被分配给至少三个不同的公司，“按照前 12 个月对 Istio 的贡献比例”，今年的指标[是合并的拉式请求。Istio 团队将其贡献席位的方法与 Kubernetes 的方法进行了比较，写道:“在 Kubernetes，口号是‘砍柴，挑水’，我们同样希望奖励那些通过贡献推动项目增长的公司。”](https://github.com/istio/community/blob/master/steering/CONTRIBUTION-FORMULA.md)

这里有一个关键词——“公司”——几个评论者都提到了这个词，包括 Kubernetes 的联合创始人乔·贝达(Joe Beda)在[云本地计算基金会](https://www.cncf.io/)技术监督委员会[关于这个话题的帖子](https://lists.cncf.io/g/cncf-toc/topic/76403099#5215)中的评论。Beda [写道](https://lists.cncf.io/g/cncf-toc/message/5217)“值得指出的一个重大区别是，Istio 模式似乎将所有贡献的功劳归于公司，而非个人。这意味着社区是由供应商定义的，而不是贡献者。”Beda 进一步假设，如果有人离开一份工作，因此离开一家公司，他们可能不得不放弃他们在指导委员会的职位，这与 Kubernetes 的“产品或公司的社区”价值观形成对比。

亚马逊网络服务 [Matthew Wilson](https://www.linkedin.com/in/matthewswilson/) 同样对这一措辞提出异议，[发推文](https://twitter.com/_msw_/status/1298001337414643713)表达了他对关注企业实体而非个人的不满，Knative 联合创始人 [Matt Moore](https://www.linkedin.com/in/mattmoor/) 似乎也表达了他的担忧。

Wilson [进一步指出](https://twitter.com/_msw_/status/1298083645194829825)最有意义的开源贡献通常是由“忠诚的个人”做出的，他认为开源项目不应该“仅仅因为支付账单就给予公司巨大的荣誉，这不是认知劳动。”这种关注的含义将是“公司将不太可能允许开发人员将工作时间花在处理治理问题上，”[New Stack 分析师](https://twitter.com/LawrenceHecht/status/1298253581133312007) [Lawrence Hecht](https://thenewstack.io/author/lawrence-hecht/) 在推特上写道。

尽管如此，Weaveworks 首席执行官 [Alexis Richardson](https://uk.linkedin.com/in/richardsonalexis) 在他给 CNCF 技术运营委员会的[消息中指出，Istio 的指导委员会实际上“强调了[指导委员会]模式的一些好处”，包括指导委员会在项目中的广泛应用，而不仅仅是回购，它鼓励非编码成员的多样性，以及它对“代表最终用户和社区的总体方向(避免我们在其他情况下看到的开放核心问题)”的关注](https://lists.cncf.io/g/cncf-toc/message/5215)

## 本周的节目中

*   **谷歌推出每月一次的开源聚会:**谷歌[宣布了谷歌开源直播](https://opensource.googleblog.com/2020/08/google-open-source-live-monthly.html)，这是一系列从 9 月 3 日开始的虚拟活动，活动的主题是“新开源:领导力、贡献和可持续性”这些活动将包括现场问答环节以及某种形式的“会后派对”。会议安排在下一个日历年，有[活动日](https://opensourcelive.withgoogle.com/events/knative)、[活动日](https://opensourcelive.withgoogle.com/events/go)，还有一天是为 Kubernetes 设定的，以此结束这一年。
*   **看看谷歌对围棋的使用:**对于那些对围棋感兴趣的人来说，该公司已经[发布了三个新的案例研究](https://opensource.googleblog.com/2020/08/new-case-studies-about-googles-use-of-go.html)，内容是关于谷歌自 2009 年开始开发的围棋语言的使用。这些研究着眼于谷歌的核心数据团队如何用基于 Go 的微服务系统取代单片 C++实现，谷歌如何构建 Chrome 优化指南服务器，以及如何将 Node.js 的 Firebase 后端迁移到 Go。除了新的案例研究，该公司还简要概述了该语言的其他用途，它说这是从 2011 年推出 [Go on App Engine](https://blog.golang.org/appengine) 开始的，也是从用 Vitess 为 YouTube 数据库流量提供服务的[开始的。](https://www.youtube.com/watch?v=midJ6b1LkA0)

*   **Go 1.15 回顾:**当我们在这里的时候，我们有一个倒数第二个与谷歌相关的片段，该公司提供了一个关于本月早些时候发布的 [Go 1.15](https://blog.golang.org/go1.15) 中主要改进的的[回顾。要点是 1.15 带来了“一系列的性能改进”和编译器的变化“减少了大约 5%的二进制文件大小，并提高了构建 Go 应用程序的速度约 20%，平均需要的内存减少了 30%。”](https://opensource.googleblog.com/2020/08/recapping-major-improvements-in-go-115.html)
*   **Jetpack Compose 首次亮相 Alpha:** 上一个与谷歌相关的花絮本周，该公司[发布了 Jetpack Compose Alpha](https://android-developers.googleblog.com/2020/08/announcing-jetpack-compose-alpha.html) ，这是一个用于构建 Android 应用程序的 UI 工具包。Jetpack compose 是一些你的 Android 开发者已经熟悉的东西的组合，例如 Android Jetpack，它提供了一套库，以及 [Kotlin](https://kotlinlang.org/) 编程语言，谷歌最近支持它，现在说“60%的 pro-Android 开发者”都在使用它。除此之外，Jetpack Compose 还添加了“用于构建 UI 的声明式 API 的简单性”，以及一组[规范示例应用](https://www.github.com/android/compose-samples)。如果你有兴趣尝试一下，有一个 [Compose 教程](https://developer.android.com/jetpack/compose/tutorial)或者一个 [setup](https://developer.android.com/jetpack/compose/setup#add-compose) 如果你准备好了，但是不要太努力——Compose 还不推荐完全生产使用，因为团队正在致力于 API 稳定性和完成性能优化。Compose 1.0 预计在 2021 年推出。

[https://www.youtube.com/embed/U5BwfqBpiWU?feature=oembed](https://www.youtube.com/embed/U5BwfqBpiWU?feature=oembed)

视频

*   **GitHub 升级到 Ruby 2.7:** GitHub 在 7 月份全面转向在生产中使用 Ruby 2.7，现在该公司已经写了一份关于该过程的[回顾](https://github.blog/2020-08-25-upgrading-github-to-ruby-2-7/)。根据这篇博客文章，为了运行一个“无弃用”的 Ruby 2.7，他们有超过 11，000 个警告需要修复，该团队提供了他们这样做的策略，其中一部分归结为将他们的 400，000 行代码应用程序设置为在 Ruby 2.6 和 2.7 中双可启动，这样他们就可以“进行向后兼容的更改，将这些更改合并到主分支，并避免为我们的升级维护一个长时间运行的分支。”GitHub 还设计了一个流程来降低部署期间的风险，该流程涉及双构建，基本上是一次做一点点，整个部署大约需要两个小时。“对于任何怀疑这种升级是否值得的公司来说，答案是:100%，”他们写道。“即使没有性能提升，落后于 Ruby 升级也会对代码库的稳定性产生严重的负面影响。”

亚马逊网络服务和云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>