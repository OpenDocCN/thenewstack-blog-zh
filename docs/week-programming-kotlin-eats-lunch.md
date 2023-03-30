# 本周节目:科特林吃掉你的午餐

> 原文：<https://thenewstack.io/week-programming-kotlin-eats-lunch/>

召开会议是主导新闻周期的一种方式，本周轮到科特林了。当然，它有助于在您的用户中受欢迎，而 [Kotlin](https://kotlinlang.org/) ，一种静态类型的 JVM 语言，可以编译成 JavaScript，就是这样。被称为“[与 Android devs](https://adtmag.com/articles/2017/11/03/kotlin-update.aspx) 的碰撞，”应用开发趋势写道，Kotlin 已经迅速成为“移动操作系统的新宠儿编程语言”，甚至被谷歌的核心 Android 开发者用于他们自己的编程见鬼，几周前一个大胆的预测甚至敢断言 Kotlin 将在明年超越 Android 上的 Java。

作为这类会议的标准，上周 [KotlinConf](http://kotlinconf.com) 发布了许多公告(在其博客上[简要概括了这些公告)，这就是我们本周的开始。](https://blog.jetbrains.com/kotlin/2017/11/kotlinconf-keynote-recap/)

此外，我们有一个新的 TensorFlow 版本公告要谈论，一个新的 GitHub 功能，对 Visual Studio 下一版本的一瞥，一些区块链花絮，来自世界各地大学的 600 多门免费在线课程的列表，以及我们通常的零星想法和杂集。

## 本周在科特林的快速上升中

*   根据谷歌的更新，Kotlin 的明星地位正在迅速上升，因为“Android Studio 3.0 中超过 17%的项目现在都在使用 Kotlin。”就在六个月前，这种语言在谷歌 I/O 上被授予 Android 开发的一流地位(与 Java 和 C++并列)，上周，在谷歌的“旗舰”ide 中获得了全面支持。当然，Google 不会把 Java 和 C++抛在后面，它评论说“虽然 Kotlin 的采用增长惊人，但我们对 Java 和 C++编程语言的承诺保持不变。”
*   KotlinConf 发布的重大消息当然是 [Kotlin 1.2 Beta2 发布](https://blog.jetbrains.com/kotlin/2017/10/kotlin-1-2-beta2-is-out/)。[据 SD Times](https://sdtimes.com/kotlinconf-kicks-off-kotlin-1-2-rc/) 报道，新的候选版本“将包括对多平台项目的实验性支持、语言改进、对注释中数组文字的支持以及编译器增强。”
*   对于任何熟悉尝试在本地运行基于 Java 的应用程序的人来说，您知道该例程——您首先需要安装 Java 运行时环境。对于普通用户来说，这可能令人望而生畏，如果不是一个交易破坏者的话。虽然这对于像 Android 这样的操作系统来说不是问题，但这是 Windows/OSX/etc 用户一次又一次遇到的情况，在这方面，本周的赢家是 iOS。Kotlin [宣布](https://blog.jetbrains.com/kotlin/2017/11/kotlinconf-keynote-recap/)“用 Kotlin/Native 支持 iOS 开发。”Kotlin/Native”将 Kotlin 直接编译成机器码，并生成无需虚拟机即可运行的可执行文件。
*   除了 iOS 支持，Kotlin 还宣布了[kot Lin/原生 ide 支持](https://blog.jetbrains.com/kotlin/2017/11/kotlinnative-ide-support-preview/)在 [CLion 2017.3](https://www.jetbrains.com/clion/nextversion/) 上的预览版。新的 IDE 支持提供了示例代码和项目、代码调试、代码洞察以及使用 [kotlin.test](http://kotlinlang.org/api/latest/kotlin.test/index.html) 框架编写的测试。
*   最后，有些 Kotlin 的新闻不是直接来自大会，kot Lin/Java web framework Java Lin[在首次发布仅六个月后就宣布了 1.0 版本](http://javalin.io/news/javalin-1.0.0-stable.html)。根据公告，它“实际上更多的是库而不是框架”,并且提供了 Java 和 Kotlin 之间的互操作性，因此当你将一个项目从 Java 移植到 Kotlin 时“你不需要学习一种新的做事方式”。谈到 Kotlin 框架，Javalin 并不是唯一的游戏，Infoworld [提供了 JVM 开发工具的及时调查](https://www.infoworld.com/article/3236419/development-tools/kotlin-frameworks-a-survey-of-jvm-development-tools.html)，包括 Eclipse Foundation 的 Vert.x JVM 框架、Pivotal 的 Spring 框架和由 Kotlin 创建者 JetBrains 开发的 Ktor。

## 本周的非科特林节目新闻

*   “最受欢迎的开源机器学习项目之一的最新更新拥有巨大的变化、新功能，甚至还有几个漏洞修复，”[jax enter](https://jaxenter.com/whats-new-tensorflow-1-4-138769.html)在谷歌新发布的 [TensorFlow r1.4](http://developers.googleblog.com/2017/11/announcing-tensorflow-r14.html) 中写道。该版本的一个重大变化是 [Keras](https://keras.io/) 从贡献包升级到核心包，谷歌称之为“一个非常受欢迎的机器学习框架，由高级 API 组成，以最大限度地缩短你的想法和工作实现之间的时间。”
*   GitHub 现在提供了使用诸如“license:mit”这样的查询通过许可证搜索库的能力，以“帮助你找到你想要贡献的项目，以及符合你的许可要求的有用项目。”
*   Infoworld 让我们先睹为快，看看 Visual Studio 代码编辑器的下一步，包括“更好的性能，更低的内存消耗，以及对 JavaScript 和 TypeScript 的更多支持。”查看完整列表的帖子。
*   令人惊讶的是，Veracode 的一项基于“对数千个应用程序和数十亿行代码的扫描”的研究发现 [Java 开发者没有应用安全补丁](https://adtmag.com/articles/2017/11/08/java-patch-study.aspx)。根据[报告](https://www.veracode.com/state-of-software-security-report)，“四分之三的应用程序在初始扫描时至少有一个漏洞，12%的应用程序在初始扫描时有高或非常高严重性的漏洞。”
*   在 remoteStorage.js Git 库 7 岁生日的时候宣布， [remoteStorage.js 1.0.0 已经发布](https://community.remotestorage.io/t/remotestorage-js-1-0-0-released/414)。 [remoteStorage](https://remotestorage.io/) 是一种针对网络上每用户存储的开放式协议，有助于提供对数据的离线访问，防止数据锁定，并跨设备同步数据。新版本改进了布局，支持 Dropbox 和 Google Drive 等。

https://twitter.com/jessfraz/status/928428438477856769

*   最近，网络上有很多关于构建自己的区块链的教程和指南，像 Reddit、Hacker News 和 Lobsters 这样的网站也有一些例子。第一，[单纯](https://blockstream.com/simplicity.pdf)(。pdf warning)是区块链的一种新语言——更确切地说，是一种“类型化的、基于组合子的、没有循环和递归的函数式语言，设计用于加密货币和区块链应用。”在[/r/比特币](https://www.reddit.com/r/Bitcoin/comments/79ohjw/bitcoindev_simplicity_an_alternative_to_script/)和[黑客新闻](https://news.ycombinator.com/item?id=15588380)上，有趣的分析和对话比比皆是。
*   也是一个讨论的话题，一篇由加州大学伯克利分校的研究人员撰写的关于如何用 Python 构建自己的区块链的博客文章，附带 Github 的 Jupyter/iPython 笔记本。
*   最后，另一个系列的第三部分是关于如何构建你自己的区块链和附带的 GitHub 库。

## 本周在进一步思考中

*   首先，Oracle 软件开发副总裁 Chad Arimura 探讨了函数和容器的区别(这不是我想问的问题)。他指出“包括 [Fn](http://fnproject.io/) (我们的项目)在内的新一代框架是‘容器原生的’，这意味着 Docker 容器是一等公民，任何图像都可以用作函数本身。”他说，这是“混淆的关键——如果函数是容器，容器是函数，它们实际上是不同的吗？”

*   Eric Raymond 是一名拥有 35 年 C 语言编写经验的程序员，在获得“惊人的认识”之后，他写了一篇“[向 C 语言告别”](http://www.topix.com/tech/programming-languages/2017/11/the-long-goodbye-to-c?fromrss=1)”——尽管他每周都用 C 语言编写代码，但他已经不记得上次用 C 语言开始一个新项目是什么时候了。他写道，尽管在其他编程领域有所进展， “直到现在，第一批直接挑战 C 的传统地盘的语言才看起来可行”，而且“现在有可能看到所有代码都用特定的 C 替代品编写的未来”，如 Go、Rust 或 Cx。
*   还记得几周前，我们发现通过 WiFi 连接到互联网的每一台设备都突然受到威胁吗？它被称为 [Krack 攻击](https://www.krackattacks.com/)，作者[发布了](https://github.com/vanhoefm/krackattacks-scripts)“测试客户端或接入点(AP)是否受到针对 WPA2 的 Krack 攻击的影响的脚本。”
*   最后但同样重要的是，Quartz 公布的 [600 门免费在线课程](https://qz.com/1120344/200-universities-just-launched-600-free-online-courses-heres-the-full-list/)列表，包括计算机科学、数学、编程等众多课程。

通过像素的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>