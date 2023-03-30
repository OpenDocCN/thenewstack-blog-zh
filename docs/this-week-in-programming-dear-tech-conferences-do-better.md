# 本周编程:亲爱的技术会议，做得更好

> 原文：<https://thenewstack.io/this-week-in-programming-dear-tech-conferences-do-better/>

上周，我们简要地写了 Linux 基金会如何决定[禁止某人](https://thenewstack.io/this-week-in-programming-buy-the-ticket-take-the-ride/)参加即将到来的 Kubecon+CloudNativeCon 2019。可以说，这是一个科技会议做正确事情的独特例子:制定一个[行为准则](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/attend/code-of-conduct/)，旨在为“所有参与者提供一个没有骚扰的体验”，在一个“鼓励思想和表达的开放交流，并要求一个承认每个人和团体固有价值的环境”的活动中，并执行这一准则。正如你所料，Twitter 的某个子部分因为诸如滑坡和他们的“言论自由”不知何故被侵犯的想法等逻辑谬误而失去了他们的集体大便(如果你们对导致上周事件的完整故事感兴趣，请花时间去阅读[切尔·斯卡利特的](https://cher.dev/)复述和分析，题为[“宣传和我们说的其他谎言】](https://medium.com/@cherp/propaganda-other-lies-we-tell-4325240379f7))。

让我再次思考技术会议以及他们需要做得更好的事情是 AWS“Container Czarina”[Abby Fuller](https://www.linkedin.com/in/abigailfuller/)本周的一条推文，指出 [DevOps Pro 2019 大会](https://devopspro.lt/)的 48 名发言者是……100%的男性。

会议组织者没有立即回复我们的电子邮件请求置评。但富勒的担忧在社交媒体上引发了大量讨论。对富勒的推文的大多数回应是其他人厌恶地摇头，并提供他们讽刺的理由，说明为什么可能找不到“DevOps pro”女性在这样的会议上发言。

但是，当然，还有不可避免的[“热拿”](https://en.wikipedia.org/wiki/Hot_take)(或三个)随之而来说，嗯，显然你们都错了，没有以逻辑、统计、基于理由(咳咳，“男子汉”)的方式来看待这个问题。

我们都知道这些争论即将到来，不是吗？他们总是这样做，他们总是有。所以，下次你遇到这种情况时，这里有两个有用的对策。首先，一篇文章问[从统计上来说，一个全是男性的演讲者名单有多大可能？并提供了数学家对这个问题的看法。剧透一下，从统计数据来看，可能性非常，非常小。但如果这还不足以满足你，你还可以继续使用](https://www.laurenbacon.com/how-likely-is-an-all-male-speakers-list-statistically/)[会议多样性分布计算器](http://aanandprasad.com/diversity-calculator/?groupName=women&numSpeakers=60&populationPercentage=2)，它“模拟了假设随机选择的男性/女性发言人平衡的概率分布”，通常会发现“无偏见选择过程产生一个完全没有女性的阵容的可能性远远低于直觉，而且——取决于你输入的数字——通常会远远低于他们过度代表的可能性。”

## 本周的节目中

*   **开发人员也需要拼写和语法:**本月早些时候， [JetBrains](https://www.jetbrains.com/) ， [IntelliJ 创意背后的公司](https://www.jetbrains.com/idea/)，[发布了一款面向开发人员的拼写、语法和风格检查器](https://sdtimes.com/softwaredev/jetbrains-releases-a-spelling-grammar-and-style-checker-for-developers/)，根据 SDTimes 上的一篇文章。根据 JetBrains 的一篇博客文章[所述，该检查器名为](https://blog.jetbrains.com/idea/2019/11/meet-grazie-the-ultimate-spelling-grammar-and-style-checker-for-intellij-idea/) [Grazie](https://plugins.jetbrains.com/plugin/12175-grazie/) ，它查看代码中的文本“是给人看的，不是给编译器看的:字符串、注释、Javadocs、提交消息”以及所有其他“至少需要一些英语或其他自然语言知识”的内容。默认情况下，Grazie 提供英语支持，但它可以添加 15 种其他语言。JetBrains 还解释说，Grazie 非常适合那些可能正在编写供使用另一种语言的人使用的代码的开发人员:“例如，如果你是俄罗斯人，而你的英语不是很理想，Grazie 有一些规则来强调俄罗斯人在英语文本中犯的常见错误。”
*   Golang 达到两位数:没错，谷歌支持的 Go 编程语言自从在[首次发布](https://opensource.googleblog.com/2009/11/hey-ho-lets-go.html)以来，已经在[待了十年](http://opensource.googleblog.com/2019/11/hey-ho-ten-years-of-go.html)，现在已经有大量的博客文章来庆祝这一事实。为了让你回到 2009 年，他们指出“Go 的最初目标是联网系统基础设施，预测我们现在所说的云”——没错，2009 年基本上是前云时代，以我们今天所知的形式——他们评论说 Go 已经成为许多开源云背后的语言，包括 Containerd、CoreDNS、Docker、Envoy、Etcd、Istio、Kubernetes、Prometheus、Terraform 和 Vitess。现在，十年后，全球有超过一百万的 Go 开发者，另一篇博客文章也庆祝了其在企业中的扩张性增长。11 月 10 日是 Go 的十周年纪念日——这是一个里程碑，我们有幸与我们的全球开发者社区一起庆祝。

https://twitter.com/flukejones/status/1194537682057039872

*   **对围棋有疑问？** Go.dev:除了该语言对两位数的庆祝之外，Go 团队还通过 [Go.dev](https://go.dev/) 为 Go 开发者揭开了[一个新的中心，它将为访问者提供学习资源、用例以及目前使用 Go 的公司的案例研究。当然，它也会在](https://blog.golang.org/go.dev) [pkg.go.dev](https://pkg.go.dev/) 中提供关于 Go 包和模块的文档和信息。根据宣布新网站的博客帖子，该发布是“最小可行产品[……]所以我们可以分享我们已经建立的东西来帮助社区并获得反馈。”因此，请访问它，并点击“共享反馈”按钮。
*   **OpenJDK 向 GitHub 出招？**最近 Java 世界发生了一些变化——随着控制权从 Oracle 转移到 Eclipse Foundation，Java EE 变成了 Jakarta 但是尽管有其他承诺，OpenJDK 仍然没有达到应有的开放程度。根据 InfoWorld 上的一篇文章，将 [OpenJDK repo 迁移到 GitHub](https://www.infoworld.com/article/3453397/openjdk-repo-migration-to-github-gains-steam.html) 的努力最近愈演愈烈。正如他们所写的，“移植计划已经考虑了一段时间，Git 工具的激增和版本控制元数据大小的减少被认为是原因”，但进展甚微。然而，一项新的提议“正式细化流程，明确将 GitHub 命名为迁移目标”，因此迁移到 GitHub 可能很快就会进行。

[https://www.youtube.com/embed/941Mn9m-kCE?feature=oembed](https://www.youtube.com/embed/941Mn9m-kCE?feature=oembed)

视频

*   **GitLab 获得“代码导航”:** GitLab 已经表示，随着 Sourcegraph 的集成，[本地代码智能正在](https://about.gitlab.com/blog/2019/11/12/sourcegraph-code-intelligence-integration-for-gitlab/)进入网站，提供诸如“转到定义”和“查找引用”等功能。该集成还将使开发人员能够通过悬停工具提示来探索函数实现，该工具提示将显示函数的定义、对该函数的引用以及导航到该函数的能力。本质上，GitLab 与 Sourcegraph 的集成将“通过收集更多关于他们正在阅读的代码的信息”给开发人员提供更丰富的 UX，并将在 11 月 22 日的 GitLab [12.5 版本](https://about.gitlab.com/upcoming-releases/)中提供，消除了对当前浏览器扩展的需求。
*   **Bytecode Alliance 想要一个浏览器之外的 WebAssembly 的坚实基础:** Mozilla 已经[推出了 Bytecode Alliance](https://hacks.mozilla.org/2019/11/announcing-the-bytecode-alliance/) ，这是一个涉及 Mozilla、Fastly、Intel 和 Red Hat 的“行业合作伙伴关系”，设想“一个默认安全的 WebAssembly 生态系统”基本上，今天的软件是使用大量外部源代码构建的，他们说——超过 80% —“坏人正在以惊人的速度利用这一点”因此，字节码联盟正致力于通过构建一个“通用的、可重用的基础集，可以独立使用或嵌入到其他库和应用程序中”，来提供“坚实、安全的基础，使使用不受信任的代码变得安全”目前，这套工具包括运行时、运行时组件和语言工具，所有这些都可以在[相当长的帖子](https://hacks.mozilla.org/2019/11/announcing-the-bytecode-alliance/)中读到——或者你可以通过前往[常见问题](https://bytecodealliance.org/#faq)获得要点。
*   **GitHub Universe:** 最后但同样重要的是，GitHub Universe 2019 有太多的[新闻，但时间有限，无法涵盖所有内容，因此我们为您呈现 GitHub 的 TLDR。请继续阅读，了解关于 GitHub 新的](https://github.blog/2019-11-13-universe-day-one/)[安全实验室](https://github.blog/2019-11-14-announcing-github-security-lab/)、 [GitHub for mobile](https://github.blog/2019-11-13-universe-day-one/#mobile) 、[GitHub Enterprise Server 2.19](https://github.blog/2019-11-13-universe-day-one/#server)、 [GitHub Actions](https://github.blog/2019-11-13-universe-day-one/#github-actions) 的所有信息，以及更多信息。

KubeCon + CloudNativeCon 和 Linux 基金会是新堆栈的赞助商。

特征图片: [DevOps Pros](https://www.facebook.com/pg/DevOpsProEurope/photos/?tab=album&album_id=839870516369846&__tn__=-UC-R) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>