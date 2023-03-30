# 本周编程:无服务器向何处去？

> 原文：<https://thenewstack.io/this-week-in-programming-whither-serverless/>

去年，无服务器风靡一时。但是现在呢？也许是这样？也许不是？

无论如何，这个话题似乎是本周人们的心头之患，因为它以无数种方式穿过了我的各种订阅源，首先是 Doug Davis 给云计算原生计算基金会(CNCF)技术监督委员会(TOC) listserv 的一封电子邮件。在这封电子邮件中，无服务器工作组(WG)的联合主席 Davis 总结了最近围绕是否将 AppDelivery 特别兴趣组(SIG)纳入其权限的讨论，最终决定，虽然有一些重叠，但单独的“app platform”SIG 可能更合适。让我觉得有趣的是其中的推理，关于界限模糊的话题。

“创建无服务器 SIG 的范围可能太有限。我们注意到的一件事是，CaaS、PaaS、FaaS 和无服务器之间的界限越来越模糊，”Davis 写道。“这意味着各种平台或每种基础技术之间的区别变得越来越不明显。相反，差异越来越类似于配置设置，而不是完全不同的平台考虑因素。”

与此同时，ZDNet 上的一篇文章询问[容器炒作是否跳过了鲨鱼](https://www.zdnet.com/article/has-container-hype-jumped-the-shark/)，因为它看到了来自[的一些数字，一份由 Cloud Foundry](https://www.cloudfoundry.org/developer-abstraction-trends-report-2019/) 最近的报告，简而言之，发现开发者喜欢生产力，欣赏可用的抽象，但最重视稳定性。然而，这里再次引起注意的是这种重叠的想法——尽管容器和无服务器的增长都有所放缓，但采用率仍在上升，用户经常选择两者，而不是非此即彼。如果你对邮件中的首字母缩写感到困惑，要点是容器、平台、功能(都是“作为服务”)和无服务器之间的界限变得模糊了。

与此同时，云和 Kubernetes 的专家 Kelsey Hightower 本周在 Twitter 上询问现实世界中是否有任何非常具体的公司已经 100%转向无服务器。

虽然有些人提出他们确实满足了海托华非常具体的条件，但大多数受访者倾向于回答“谁做任何事情都是 100%？”

所以，关于无服务器最近去了哪里的问题，我不会特别冒险去任何地方，但也许会去抛物线的另一边，这是一个炒作周期。尽管它的支持者可能宣称“无服务器”工具适用于所有用例，但更有可能的结果是它成为更大堆栈的一部分，与所有其他“即服务”工具并列。至少，这是本周所有事情都指向的。

## 本周的节目中

*   **生物信息学，数据处理&用 Go 进行机器学习:**虽然 Go 可能不是第一次提到这些领域时想到的第一种语言，但是利用数据早期检测癌症的公司 [GRAIL](https://grail.com/) ，[说](https://medium.com/grail-eng/bigslice-a-cluster-computing-system-for-go-7e03acd2419b)它选择这种语言有几个原因:“Go 的简单性使新手容易学习；其透明的运行时语义使得对性能进行推理变得容易，其控制数据布局和分配的能力使得编写高性能的数据处理代码成为可能。”除此之外，GRAIL 表示，这种语言缺少一种用于大规模数据处理的工具，因此它发布了 [Bigslice](https://bigslice.io/) ，这是一个用于数据处理的 Go 库，它“提供了一组连贯的运算符，帮助用户使用普通的 Go 代码高效地计算大型数据集。”Bigslice 允许您在并行执行的同时编写顺序代码，创建它所谓的“Go 集群计算系统”该库在 Apache 2.0 许可下作为[开源](https://github.com/grailbio/bigslice)提供。

*   **网飞开放其多语言笔记本:**网飞本周写了一篇博文，宣布将[开源其 IDE 启发的多语言笔记本](https://medium.com/netflix-techblog/open-sourcing-polynote-an-ide-inspired-polyglot-notebook-7f929d3f447?source=rss----2615bd06b42e---4)，名为 [Polynote](http://www.polynote.org/) 。该笔记本是“一个新的多语言笔记本，具有一流的 Scala 支持、 [Apache Spark](https://spark.apache.org/) 集成、多语言互操作性，包括 Scala、Python 和 SQL、随输入自动完成等功能。”如果你发现自己在问“为什么是 Scala？”这是因为网飞也有一个[基于 JVM 的 ML 平台](https://www.slideshare.net/FaisalZakariaSiddiqi/ml-infra-for-netflix-recommendations-ai-nextcon-talk)，恰好“大量使用”Scala，并且这与 Scala 紧密集成。至于具体的功能，网飞说，Polynote 旨在通过设计提供可再现性，类似 ide 的功能，如自动完成和内嵌错误突出显示，对内核和任务状态的可见性，依赖性和配置管理，数据可视化，当然，还有多语言能力，每个单元格都可以用不同的语言编写，尽管也可以共享变量。目前，Polynote 支持 Scala、Python 和 SQL。

*   **谷歌推出安卓游戏:** ProgrammableWeb 以“三套核心工具:Jetpack Compose 的开发者预览版；Android Jetpack 的扩展 APIs 和金丝雀的 Android Studio 4”，该公司称其灵感来自开发者的反馈。Jetpack Compose 作为开发者预览版推出，改进了 API 以构建原生 Android 应用程序，而 Android Studio 4 的 canary 版本包括 Java“去糖”和运动编辑器。ProgrammableWeb 还指出，谷歌通过新的投资增加了对 Kotlin、Java 和 C++的承诺，现在通过 APK 共享使测试应用程序变得更加容易。[阅读](https://www.programmableweb.com/news/google-makes-progress-modernizing-android-development/2019/10/23)了解所有细节。哦，当我们谈论科特林的时候，不要忘记[科特林 Conf 2019](https://blog.jetbrains.com/kotlin/2019/10/kotlinconf-2019-global-join-in/) 即将到来！
*   **微软添加免费 Azure 认知服务:**没错，Azure 免费账户持有者现在可以[开始免费构建 Azure 认知服务](https://azure.microsoft.com/blog/start-building-with-azure-cognitive-services-for-free/)，通过 API 调用将 AI 添加到他们的应用中。你能用 Azure 认知服务做什么？例子包括面部检测、文本提取和语言检测、个性化、计算机视觉建模以及自动构建“对话体验”即机器人的能力。

*   **亚马逊与 JCP 交恶:**上周，我们看到 AWS 支持 Rust，本周其[亚马逊加入 Java 社区进程(JCP)](https://aws.amazon.com/blogs/opensource/amazon-joins-the-java-community-process-jcp/) 。该公司表示，它“运行着数以千计的 Java 生产服务”，并严重依赖于 Java 开发工具包(JDK)，包括[亚马逊 Corretto](https://aws.amazon.com/corretto/) ，它自己的 OpenJDK 二进制发行版用于运行 AWS 和其他亚马逊服务，后来它开源了这些服务。亚马逊还表示，它贡献了补丁，并帮助维护 OpenJDK 8 和 11 更新项目。也就是说，该公司想让你知道它打倒了 Java，现在它已经加入了 Java 平台标准组织 [Java 社区进程](https://jcp.org/en/home/index)。
*   **先是樱庭落，现在是 JS？上周，所有人的目光都转向了这个建议，或者更确切地说，是这个问题，关于我们是否应该重新命名 JavaScript——因为非技术观察者一直混淆了 Java 和 JavaScript，以及它们之间的完全不相关。最常见的膝跳反应是快速大笑和惊呼“不！”而其他人则认为 JS 的简单缩写就足够了，既保持了文件扩展名的原样，又注意到简洁性通常会导致它的使用。如果 Perl 6 能成为樱庭落，我会说为什么不把 JavaScript 变成 JS 呢——你呢？**

Cloud Foundry 和 CNCF 是新堆栈的赞助商。

由 Pixabay 的 3D 动画制作公司制作的专题图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>