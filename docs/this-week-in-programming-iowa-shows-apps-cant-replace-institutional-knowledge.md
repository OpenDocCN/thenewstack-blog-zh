# 本周节目:爱荷华州显示应用程序不能取代机构知识

> 原文：<https://thenewstack.io/this-week-in-programming-iowa-shows-apps-cant-replace-institutional-knowledge/>

多年来，有报道称外国政府正在影响美国的选举，爱荷华州(和内华达州)除了雇佣一家名为“Shadow Inc .”的公司来开发一款智能手机应用程序，以帮助记录民主党初选中的选举结果外，还能做些什么呢？你可以编造这个故事，但是一个有眼光的编辑会告诉你这是 B 级电影的素材，也是汤姆·克兰西最糟糕的情节。

好吧，这个星期关于所有出错的事情的故事——还有很多——正在互联网上流传，在第一个简单的大纲之后，剧本并没有变得更好。我不禁想起了几年前的那个时候，当[的一次误击](/week-programming-oops-clicked-wrong-link-set-off-nuclear-scare/)发出核导弹袭击即将来临的警报后，夏威夷群岛的全体居民都认为他们只有几分钟可活了。

这一次，虽然没有人立即担心他们的生命和几英里内所有人的生命，但我们在一个漫长的选举季节的第一场比赛中被蒙上了怀疑的阴影，这一切都是一个灾难性的应用程序的错，即使它尝试也不会做得更糟。正如 [Axios](https://www.axios.com/iowa-caucus-2020-election-app-fiasco-739eeee7-c0e3-4615-ac09-cc7bd6265719.html) 对这场失败的描述，“这基本上是一个如何在选举中不使用技术的剧本。”

[Motherboard](https://www.vice.com/en_us/article/y3m33x/heres-the-shadow-inc-app-that-failed-in-iowa-last-night) 中的一个故事详细介绍了所有出错的地方，发现不仅在初级夜之前[很少甚至没有进行测试](https://www.nytimes.com/2020/02/03/us/politics/iowa-caucus-app.html?smid=nytcore-ios-share)，该应用程序实际上是通过安卓移动应用程序测试平台 [TestFairy](https://www.testfairy.com/) 和 iOS 移动应用程序测试平台 [TestFlight](https://testflight.apple.com/) 分发的，这两者都是为了规避应用程序商店的限制(包括安全要求)，并为开发者提供一种在 beta 测试期间分发的方法。然而，这仅仅是开始。与此同时，ProPublica 写道，“据总部位于马萨诸塞州的 Veracode 的官员称，IowaReporterApp 非常不安全，投票总数、密码和其他敏感信息可能会被拦截甚至更改。”

除此之外，Twitter 上有一条[帖子](https://twitter.com/jjoque/status/1224704596364464131)对整个事情提出了稍微不同的观点，不看应用程序分发、安全、测试或任何类似的东西，而是关注我们越来越依赖技术来取代机构知识的趋势。

本周流传的这篇简短帖子的作者贾斯汀·乔克(Justin Joque)进一步指出，“这是老板和工人之间更大冲突的一部分，老板们自欺欺人地认为，没有不断修理、修补和维护这些复杂系统的工人，他们也可以单干。”

虽然你可以去阅读大量的文章，在某种意义上，这些文章等同于我们忍不住盯着看的火车残骸，但这个帖子及其回应提供了对整个惨败的另一种观点:我们被告知“[有一个针对那个](https://www.wired.com/2010/10/app-for-that/)的应用程序”，我们用技术解决它的膝跳反应已经一次又一次地被证明是表面上的错误。

当然，可能有一种介于两者之间的观点认为，经过适当的时间、准备、测试、强化、分发等等，你仍然会有一个可以被黑客攻击的应用。我说过吗？你认为——这里有中间地带吗？我们可以用机构知识来扩充应用程序吗？我们能把同样的知识编码吗？或者，我们是否正在不断地将自己引向一条技术绝望的道路？

## 本周的节目中

*   **HackerRank 的 2020 年开发者技能报告:**又到了一年中各种“状态”地址和报告的时间，包括科技招聘平台 [HackerRank](https://www.hackerrank.com/) 的 [2020 年开发者技能报告](https://research.hackerrank.com/developer-skills/2020)，这份报告已经成为本周的头条新闻。仅浏览这些，我们可以了解到[大多数开发人员都知道 JavaScript，并且最想知道 Go](https://www.infoworld.com/article/3519613/more-developers-know-javascript-mostly-want-to-know-go.html) 根据 InfoWorld 的说法，[2020 年的开发人员通过非传统方法学习](https://jaxenter.com/coding-bootcamps-2020-167773.html)如 bootcamps 和 YouTube 编写 JAXEnter，根据 iProgrammer 的说法，显然存在[新的代沟](https://i-programmer.info/news/99-professional/13443-hackerrank.html)。最后一个标题对我来说特别值得注意，因为音乐和出生年份似乎不是我是否属于 GenX 或 Z 的真正辨别因素，而是我学会了主要用 BASIC 而不是 c 编写代码这一事实。
*   **Java，C & Python 高居榜首:**当我们在这里谈论投票和调查之类的事情时，最新的 TIOBE 指数出来了，DevClass 注意到 [Java，C 和 Python 并列编程语言前三名……再次](https://devclass.com/2020/02/06/java-c-and-python-tie-up-programming-language-top-3-again/)，注意到自从 TIOBE 在 1985 年开始记录以来，C 一直保持在顶级。根据 TIOBE 的说法，C 语言最近一直在上升，尽管 Java 仍然是第一名，Python 包揽了前三名。但你已经知道了，对吧？同样也是最后一点，关于排名和调查，StackOverflow 已经[开放了](https://stackoverflow.blog/2020/02/05/the-2020-developer-survey-is-now-open/)其 [2020 年开发者调查](https://stackoverflow.az1.qualtrics.com/jfe/form/SV_eL0mFVwuo7KWeXP?utm_source=so-owned&utm_medium=blog&utm_campaign=dev-survey-2020&site=stackoverflow.com)，它希望得到足够多的回应，以真正“代表每个编码的人”GitLab 也来凑热闹，它的 [2020 DevSecOps 调查](https://about.gitlab.com/2020-devsecops-survey/new/)将持续到本月底。

*   **一个从“走”到“生锈”的转变故事:**我们看这些数字，部分是因为我们想知道我们在职业生涯和语言选择上都走在正确的道路上，对吗？嗯，本周我们还发现了[为什么 Discord 正在从 Go 转向 Rust](https://blog.discordapp.com/why-discord-is-switching-from-go-to-rust-a190bbca2b1f) 的故事，该公司称“通过切换其实现，极大地提高了服务的性能。”由于专注于提高特定服务的性能，该公司发现 Go 的内存模型和垃圾收集器导致了较大的延迟峰值。然而，Rust 没有垃圾收集功能，所以选择了 switch。当然，没有一个是那么简单的，但是如果你对完整的细节感兴趣，博客文章提供了很多。一个关键要点是:“值得注意的是，在编写 Rust 版本时，我们只对优化进行了非常基本的思考。即使只有基本的优化，Rust 也能够超越超级手动调整的 Go 版本。这是一个巨大的证明，与我们不得不深入研究 Go 相比，用 Rust 编写高效的程序是多么容易。”

*   pkg.go.dev 的下一步是什么:pkg . go . dev 网站作为 go 软件包和模块的主要信息源，将在 2020 年进行一些更新，Go 团队在一篇博客文章中概述了 pkg.go.dev 的[下一步](https://blog.golang.org/pkg.go.dev-2020)。他们写道，即将添加的功能将“帮助我们的用户更好地理解他们的依赖性，并帮助他们就导入什么库做出更好的决定。”一些变化包括从 godoc.org 的重定向，以及引入对 pkg.go.dev 的 API 访问
*   **关于 GitHub Actions API 的更多细节:**我们在一两周前写过关于 GitHub Actions API 的介绍，但当时还没有多少细节。本周，GitHub 发布了一篇关于如何使用 GitHub Actions API 管理秘密和更多内容的博客文章，提供了一些具体的用例示例，说明如何使用 beta API。GitHub 写道，在审查了一些最初的反馈后，他们决定在第一次迭代中关注四个离散的主题:读取[工作流运行](https://developer.github.com/v3/actions/workflow_runs/)和[作业](https://developer.github.com/v3/actions/workflow_jobs/)数据，管理存储库[秘密](https://developer.github.com/v3/actions/secrets/)，下载[工件](https://developer.github.com/v3/actions/artifacts/)，以及注册[自托管运行者](https://developer.github.com/v3/actions/self_hosted_runners/)。详情请继续阅读。

来自 Pixabay 的 David Mark 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>