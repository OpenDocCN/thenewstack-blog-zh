# 本周节目:R 因为新冠肺炎而越来越受欢迎吗？

> 原文：<https://thenewstack.io/this-week-in-programming-is-r-gaining-popularity-because-of-covid-19/>

每个月， [TIOBE 指数](https://www.tiobe.com/tiobe-index/)根据使用流行搜索引擎发现的“全球熟练工程师、课程和第三方供应商的数量”来探索编程语言的受欢迎程度。自从世纪之交以来，他们已经做了这项工作，他们有一些一致的数据来探索语言受欢迎程度如何随着时间的推移而变化，至少根据他们的标准，这个月他们说 R 编程语言已经跃升到第八位的“历史高点”。关于历史背景，我们在大约两年前写了 R ' s spot in TIOBE，它刚刚从第 50 名跃升至第 39 名。

那么，为什么现在是“历史新高”呢？很明显，这种语言一段时间以来一直呈上升趋势，但是是什么最终把它推到了前十名的位置并达到了现在的顶峰呢？

TIOBE 首席执行官 Paul Jansen 推测，有两种趋势可能会促进 R 语言的发展。其一是“SAS、Stata、SPSS 等商业统计语言和软件包的时代已经结束。大学和研究机构将 Python 和 R 用于统计分析，”他写道。其次，“需要做大量的统计和数据挖掘来找到新冠肺炎病毒的疫苗。"

我猜我们今年看到的[新冠肺炎黑客马拉松](https://thenewstack.io/this-week-in-programming-how-devs-can-help-beat-the-covid-19-pandemic/)的数量肯定支持了这样一个观点，即有很多开发者在从事数据工作，尤其是在大学方面。如果我们去看一下根据谷歌搜索教程对语言进行排名的 [PYPL 流行指数](http://pypl.github.io/PYPL.html)，看起来 R 的排名相当稳定。与此同时，ZDNet 写道[关于 R 的上升](https://www.zdnet.com/article/programming-language-rankings-r-makes-a-comeback-but-theres-debate-about-its-rise/)有一些争论，引用 R 倡导者和数据科学家 [Hadley Wickham](http://hadley.nz/) 作为 TIOBE 最新 R 排名的[嫌疑人。](https://twitter.com/hadleywickham/status/1279405379449913344)

当然，当我们在图表上向上移动时，Python 仍然舒适地坐在第三位，仅次于 C 和 Java，是处理数据的明显选择。Jansen 注意到“在 Python 的推动下，R 的受欢迎程度仍在增加”，“易于学习和使用的统计编程语言现在越来越受欢迎。”

## 本周的节目中

*   **孤立开源:**本周首先， [Jack Wallen](https://thenewstack.io/author/jack-wallen/) 在 New Stack 看一看[当开发者离开他们的开源项目](https://thenewstack.io/what-happens-when-developers-leave-their-open-source-projects/)时会发生什么，注意到这个问题是一个广泛传播的问题，专有软件经常使用这样的项目，使他们自己在没有更新或补丁的情况下很容易被安全利用。虽然有些人可能认为显而易见的解决方案是从存储库中自动剔除废弃的项目，但 Wallen 认为这可能是一个可行的选择，但需要考虑更多的因素，并且“在一些废弃的项目中可以挖掘出隐喻意义上的黄金”[继续阅读](https://thenewstack.io/what-happens-when-developers-leave-their-open-source-projects/),了解一个如此富有成效的项目的故事，以及 Wallen 关于虚拟开源孤儿院的想法，在那里，有希望的废弃开源项目可以留给那些有兴趣的开发者，他们可能会采用这些项目。
*   **脸书让 Haskell 重构变得简单:**脸书已经[决定开源 Haskell 的代码重构工具](https://engineering.fb.com/open-source/retrie/)，据说它“让代码重构更快、更容易、更安全”现在，[retrieve](https://github.com/facebookincubator/retrie/)不是针对小型项目，而是针对高效地重写大型代码库，比如那些超过一百万行的代码，并使用 Haskell 语法中的等式而不是正则表达式来这样做，从而避免大量代码修改错误。该工具可以重写表达式、类型和模式，尊重和维护局部范围，保留空白，并且不重写代码注释。在现有的重构工具中，脸书说 Retrie 在其方法中“占据了一个舒适的中间地带”，提供了一个比字符串替换更强大的方法，也是一个比定义复杂的正则表达式或 AST 遍历更简单的方法。

*   **获得 Rust Lang 团队的内部消息:**该团队继续专注于 Rust 发展的方式和原因，本周写了一篇博客文章，提供了关于 [Rust Lang 团队设计会议](https://blog.rust-lang.org/inside-rust/2020/07/08/lang-team-design-meeting-update.html)的更新，据说该会议定期召开，你可以在他们的 YouTube 上找到，会议记录发布在 lang-team 知识库中。如果你有兴趣更深入一点，“你可以看看标有会议提议标签的[未决问题，以了解正在考虑的会议，”他们写道，“如果会议已经安排，它也会标有](https://github.com/rust-lang/lang-team/issues?q=label%3Ameeting-proposal)[会议安排](https://github.com/rust-lang/lang-team/issues?q=label%3Ameeting-scheduled)，并有一些关于当前日期的评论。”一些即将召开的会议包括[讨论 lang-team 成员资格的提案](https://github.com/rust-lang/lang-team/issues/32)和[讨论强制类型别名界限的提案](https://github.com/rust-lang/lang-team/issues/25)。
*   **Docker 与 AWS 挂钩:**对于那些将 Docker 用于容器、将 AWS 用于计算的开发人员来说，你们感兴趣的是什么(你们只有几个人，对吗？)这两家公司今天[宣布了](https://www.docker.com/blog/from-docker-straight-to-aws/)一项合作，他们说这将使从 Docker 直接部署到 ECS 变得更加容易。本质上，这里的想法是保留在 Docker Compose 和 Docker Desktop 中使用 Docker CLI 所提供的简单性。关于新闻的更多信息，你也可以查看我们的帖子或观看解说视频。

[https://www.youtube.com/embed/UE162PzO2s0?feature=oembed](https://www.youtube.com/embed/UE162PzO2s0?feature=oembed)

视频

*   **GitHub 更好地整理了它的停机借口:** GitHub，这个你花了太多时间，只是偶尔希望停机的网站，这样你就有借口不工作了，[推出了 GitHub 可用性报告](https://github.blog/2020-07-08-introducing-the-github-availability-report/)，在这里它将每月解释它的可用性缺点。到目前为止，该公司已经发布了重大事件的事后审查，但现在他们承诺在每个月的第一个周三发布这种信息，提供“任何可能已经发生的事件的描述，并向您更新我们如何发展我们的工程系统和实践作为回应。”他们写道，“当事情没有按计划进行时，我们不想等待分享关于特别有趣的事件的信息，而是想描述所有可能影响你的事件。”
*   **Git 想通用认证你:**现在不用担心，一点都不会痛。GitHub 写道，随着新的证书管理器的发布，它正在[构建通用的认证体验](https://github.blog/2020-07-02-git-credential-manager-core-building-a-universal-authentication-experience/)，可用于 Windows 和 macOS: [Git 证书管理器(GCM)核心](https://github.com/microsoft/Git-Credential-Manager-Core)。GCM 是一个免费的、开源的、跨平台的 Git 凭证管理器，目前支持对 GitHub、Bitbucket 和 Azure Repos 的认证。虽然 GCM 目前处于测试阶段，但该团队已经计划[在 Linux](https://github.com/microsoft/Git-Credential-Manager-Core/issues/135) 上提供 GCM 核心，一旦完成，经过一段时间的使用，他们预计 GCM 将取代 GCM for Windows 和 GCM for Mac & Linux。

亚马逊网络服务是新堆栈的赞助商。

由 Pixabay 的 chiplanay 提供的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>