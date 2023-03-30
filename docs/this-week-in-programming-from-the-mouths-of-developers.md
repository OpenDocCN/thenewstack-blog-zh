# 本周编程:来自开发人员的口中

> 原文：<https://thenewstack.io/this-week-in-programming-from-the-mouths-of-developers/>

本周早些时候，我参加了一个当地开发者团体的“Docker 和 Kubernetes 之夜”，该团体偶尔举办黑客马拉松，并主办一个相当活跃的 Slack 频道。令活动组织者惊讶的是，他们预订的房间几乎满座，尽管有几个发言者未能到场，但活动充满了演讲和热烈的讨论。

作为一个从事写作而不是使用 it 行业的人，听一屋子活跃的现场开发人员谈论他们使用容器的经历是很有趣的。在某些方面，听到来自该领域开发人员的故事、问题和解决方案是令人大开眼界的，而不是福音传道者和营销副总裁以及其他公关类型的天上掉馅饼的故事，他们可能会用朗朗上口的流行语填充电子邮件，而不是描述现实。

例如，当晚的第一位发言人在政府部门工作，在开始工作后，他发现他必须继续使用旧的代码库，使用不太新的语言，并且需要亲自前往 40 多个地点推广产品，每个地点都需要一周的时间。没错，一次部署就需要将近一年的旅行和时间。他很快开始将产品容器化，并让本地团队使用 Docker Compose 进行开发，并使用 OpenShift 进行部署。

现在，在开发过程中，他的团队可以简单地保存代码并刷新浏览器来测试更改，推出将不再需要以前所需的冗长过程，从而缩短部署时间，他说，“使用这种方法可以缩短 99.17%。”演讲充满了技术细节——具体的 docker 命令和 YAML 代码——来支持这样一个事实，即开发者确实在使用容器来实现更高的效率并节省大量不必要的工作。

与此同时，当晚的第二位发言人更进一步，用 Kubernetes 和 Helm 来支持他的申请，并指出托管自己的 Kubernetes 是浪费时间。打算走库伯内特的路？他说，然后一个由 GKE、EKS、AKS 或数字海洋托管、管理的 Kubernetes 取决于你的版本、定价和 GPU 需求——是唯一的出路。他说话时的恼怒足以让我信服。

最后，当晚的最后一位演讲者站起来提供了一个完全不同的观点——不要介意 Kubernetes 不必要的复杂性，如果可能的话，使用无服务器从头开始开发。在他的演讲中，他将 Kubernetes 称为“出血边缘”，他后来为我更好地定义了这一点:

“在我的职业生涯中，我不时听到有人用这个术语来形容那些正在使用但非常不成熟的技术。我认为 Kubernetes 很感兴趣，人们也在这方面做了很多工作，但我个人非常担心，如果它不能简化他们的堆栈管理，人们会对它失望(就像我一样)。”

我问，Istio 能对此有所帮助吗？“我不这么认为，”他回答道。“我认为这些旨在帮助简化跨多家供应商的部署的解决方案是问题的真实症状。真正的问题是，人们把 Kubernetes 当作一个东西，而实际上它是来自每个提供商的不同功能的集合。”

虽然他全心全意地推动无服务器，但他承认 Kubernetes 有自己的位置，他说“新的开发应该从无服务器开始，因为总拥有成本将大大降低”，但“我认为，如果你正在从事一个已经存在一段时间的项目，并且是在多层架构或容器架构上，那么转移到 Kubernetes 相对简单，并将提供许多好处。只是没有无服务器的好处。但最大的区别在于运营成本，这通常不能很好地归因于开发实践。”

现在你知道了——一些关于容器、Kubernetes 和无服务器的优点和缺点的观点，不是来自福音传道者、倡导者、Twitter 名人，甚至是寻找页面浏览量的开发人员博客，而是来自该领域的一些开发人员，他们试图让事情尽最大努力工作。你尽管拿去吧，但我觉得它相当有价值。现在，我们来看看本周的编程新闻。

https://www.youtube.com/watch?amp=&v=xE7sW6BX3eU

## 本周的节目中

*   **TypeScript 3.4 候选版本:**微软本周宣布了 [TypeScript 3.4 RC](https://devblogs.microsoft.com/typescript/announcing-typescript-3-4-rc/) ，其中最值得注意的功能可能是增量编译，“它告诉 TypeScript 保存有关上次编译的项目图的信息，”这样，“下次使用—incremental 调用 TypeScript 时，它将使用该信息来检测类型检查的最低成本方式，并向您的项目发出更改。”根据[在 SDTimes](https://sdtimes.com/msft/typescript-3-4-rc-now-available-with-incremental-compilation/) 上的一篇文章，TypeScript 3.4 是“第一个拥有概述发布计划的迭代计划的版本”，它“旨在与其语言的[六个月路线图](https://sdtimes.com/msft/microsoft-reveals-plans-to-improve-typescript-in-2019/)保持一致”当然，这些只是新版本的一瞥，新版本还包括类似只读数组的类型、对只读元组的支持以及一个新的文字值构造。一如既往，查看[公告](https://devblogs.microsoft.com/typescript/announcing-typescript-3-4-rc/)了解全部细节。
*   **Java 12 来了:**当我们谈论新的语言版本时，SDTimes 也有另一个关于 Java 12 的很好的[摘要，根据甲骨文的新发布时间表，这是今年两个主要版本的第一个，在 Java 13 于 2019 年 9 月到来之前还会有两个更新。根据这篇文章，“Java 12 中的新特性包括新的低暂停时间垃圾收集器、微基准测试套件、开关表达式、JVM 约束 API、单个 AArch64 端口、默认 CDS 归档、可接受的 G1 混合收集，以及从 G1 返回未使用的提交内存的能力。”甲骨文表示，Java 12 修复了 1919 个 JIRA 问题，“其中 1433 个由甲骨文员工完成，486 个由个人开发人员完成。”与此同时，JAXEnter 采访了 Oracle Java 产品管理高级主管 Donald Smith，他们谈论了“最新版本、新版本节奏如何影响 Java 团队的工作流程、他最感兴趣的新特性等等。](https://sdtimes.com/java/java-12-is-now-available/)

*   **iOS 应用商店提交要求注意:**苹果公司就一些[即将到来的应用商店提交要求](https://developer.apple.com/news/?id=03202019a)向 iOS 开发者发出通知，指出“从 2019 年 3 月 27 日开始，iPhone 或 iPad 的所有新应用和应用更新，包括通用应用，必须使用 iOS 12.1 SDK 或更高版本构建，并支持 iPhone XS Max 或 12.9 英寸 iPad Pro(第三代)，”并要求截图。苹果电视和苹果手表也有新的要求，所以如果那是你的领域，一定要去[看看细节](https://developer.apple.com/ios/submit/)。
*   **red monk 排名是这样说的:**没错，“第一季度双年度” [RedMonk 编程语言排名](https://redmonk.com/sogrady/2019/03/20/language-rankings-1-19/?utm_source=rss&utm_medium=rss&utm_campaign=language-rankings-1-19)已经出炉，其中分析公司从 GitHub 和 Stack Overflow 两方面进行排名，以实现“试图反映代码(GitHub)和讨论(Stack Overflow)牵引力的排名。”这一次，他们注意到，“我们的第一级语言没有什么变化”，但这通常是常态。然而，更值得注意的是 TypeScript、Kotlin 和 Julia 的一些变化。TypeScript 的受欢迎程度持续飙升，已经升至第 12 位，RedMonk 表示，TypeScript 肯定不仅仅来自于功能，而是被“越来越多的项目广泛使用”至于 Kotlin，它的增长“仅次于 Swift”，这是值得注意的，因为 Swift 是“这些排名历史上增长最快的语言。”他们指出，与此同时，Kotlin“大幅增长，而其他三家基于 JVM 的同行却在下滑。”最后， [JAXEnter 注意到](https://jaxenter.com/redmonk-rankings-for-q1-2019-typescript-157131.html)“另一个值得一提的要点是，尽管没有出现在前 20 名的名单中，但朱莉娅的成长并没有突飞猛进；然而，它确实表现出了一些缓慢的、递增的上升，跃升了两位，排在第 34 位，”RedMonk 将其与 TypeScript 过去的类似举动进行了比较。“当然，这并不是说 Julia 注定要步 TypeScript 的后尘，”Redmonk 写道，“而是提醒我们，虽然语言并不常见，但它可以从缓慢、几乎无法衡量的增长时期快速过渡到一个又一个季度的持续高速增长。”

*   **Twitter 费率限制其 API:**Twitter 的 API 困境已经持续了很长时间，本周，ProgrammableWeb 为我们带来了 [Twitter 实施更新费率限制以清除 API 滥用](https://www.programmableweb.com/news/twitter-imposes-updated-rate-limits-to-flush-out-api-abuse/2019/03/20)的故事，这是其试图“[通过对希望获得平台访问权的新开发者施加额外限制来保护他们的平台免受垃圾邮件和滥用](https://www.programmableweb.com/news/twitter-unveils-new-developer-requirements/2018/07/24)的一部分简而言之，Twitter 宣布将从 2019 年 6 月 19 日开始，默认情况下将/status/mentions _ timeline 和/status/user _ timeline 端点限制为每天 100，000 个请求，并且“需要访问超过此速率限制的应用程序将被要求请求豁免，以便 Twitter 分析用例。”与此同时，Techcrunch [提供了一点历史背景](https://techcrunch.com/2019/03/19/twitter-developer-review/)，写道“过去，Twitter 通过突然改变其 API 政策，用鞭子痛打了开发者。这导致应用程序崩溃，企业倒闭，人们认为 Twitter 对开发者来说是一个不可靠甚至充满敌意的地方。这一次，Twitter 给了开发者三个月的时间，以尽量减少意外和问题。”干得好，推特。才过了十年。
*   **波音 737Max 的软件故事:**现在，我对开发大型商用客机的软件一无所知，但这位作者在他关于[737 max 以及为什么软件工程师可能想要关注](https://medium.com/@jpaulreed/the-737max-and-why-software-engineers-should-pay-attention-a041290994bd)的文章中似乎知道。"那么，作为软件专业人员，我们为什么要关心这种特殊的调查和补救是如何展开的呢？"他问道。“如果你退后一步，用‘系统’代替‘737’，用‘操作工程师’代替‘飞行员’，737Max 的情况就是一个新的、市场驱动的业务需求的例子，促使人们对广泛认为稳定可靠的生产系统进行重新设计。”

专题图片:《Fortran，最伟大的编程语言》， [The Simpsons](http://www.simpsonsworld.com/) ，截图(第 26 季第 10 集)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>