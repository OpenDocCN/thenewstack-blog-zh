# 谷歌为 Android Developer Studio 增加了 Kotlin 支持

> 原文：<https://thenewstack.io/google-adds-kotlin-support-android-developer-studio/>

当谷歌 I/O 上挤满了这家搜索引擎公司的新工具、产品和服务时，最令人惊讶的消息之一来自一个不是由谷歌开发的软件。上午的主题演讲结束后不久，[谷歌](https://www.google.com)透露，它将为其移动设备的安卓操作系统增加对[科特林](https://kotlinlang.org/)编程语言的支持。

Kotlin 最初是由 JetBrains 公司创建的，谷歌已经利用这家 IDE 公司创建了 Android 开发者工作室。事实上，Kotlin 支持声明伴随着 Android Developer Studio 3.0 Canary 的预览版发布。

许多 Android 开发人员喜欢上了 Kotlin，这是一种 Java 虚拟机(JVM)语言，因为它比 Scala 编译得更快，同时也比 Java 更容易使用。它还通过对 Lambda 表达式的支持为函数式编程打开了大门，这一特性在基于 Java 6 的 Android 代码库中仍然不可用(Oracle 在 Java 8 中引入了 Lambda 支持)。

“Kotlin 也非常适合现有的 Android 生态系统。它与 Java 编程语言 100%兼容。你可以在你现有的代码库中添加或多或少的 Kotlin，并在同一个项目中自由地混合这两种语言，”谷歌 Android 平台总监迈克·克莱伦在一篇博客文章中写道。

“从 Java 编程语言编写的代码中调用 Kotlin 代码是可行的。走另一个方向通常不需要任何开发人员的努力，通过一些自动应用的转换约定(例如，像属性 getters 和 setters 这样的东西是为您创建的)。在一些 Kotlin 注释的帮助下，你还可以定制翻译的方式，”Cleron 写道。

[https://www.youtube.com/embed/viiDaLpPfN4?feature=oembed](https://www.youtube.com/embed/viiDaLpPfN4?feature=oembed)

视频

Android 中 Kotlin 支持的引入伴随着对该语言在[Android Developer Studio 3.0](https://docs.google.com/document/d/1sMm5VIZUdLU5L3uwrpuMPyF2UtrOX9pwZVG091sWgk8/edit?usp=sharing)中的支持。Cleron 写道，该语言于 2012 年正式开源，编译速度和语言能力已经吸引了 Android 开发者。

总的来说，Android Studio 3.0 的第一个金丝雀版本有 20 多个新功能，[Android 产品经理贾马尔·伊森](https://www.linkedin.com/in/jamaleason/)，[在博客文章](https://docs.google.com/document/d/1sMm5VIZUdLU5L3uwrpuMPyF2UtrOX9pwZVG091sWgk8/edit?usp=sharing)中提到。除了对 Kotlin 的支持，该版本还附带了一套新的应用性能分析工具，用于快速诊断性能问题，并为针对大型应用优化的 Gradle 构建系统提高构建速度。

## Firebase 更新

[Firebase](https://firebase.google.com/) 也针对 Google I/O 进行了更新。[Google 产品经理 Francis Ma](https://www.linkedin.com/in/francisma/)[在一篇博客文章](https://docs.google.com/document/d/1H80OHXFbGROQSI7E2KC85ZR6JcwTluc7Ls4vCZKUb4g/edit?usp=sharing)中写道，Firebase 的分析现在也将能够支持自定义事件。“你们中的许多人还要求对定制事件和参数进行深入分析。从今天开始，您可以注册多达 50 个自定义事件参数，并在您的分析报告中查看它们的详细信息，”马写道。

然而，Google I/O 并不是今天早上关于这个平台的唯一新闻。在网上的其他地方，一家家庭自动化初创公司[发布了一篇博客文章](https://medium.com/@contact_16315/firebase-costs-increased-by-7-000-81dc0a27271d)声称，当谷歌对系统进行了一个小的计费更改后，他们的 Firebase 账单在一个月内从 25 美元涨到了 2000 多美元[。这一改变是对用于 SSL 和失败的 SSL 请求的处理器时间收费。](https://www.reddit.com/r/programming/comments/6bnhzy/due_to_a_change_in_how_they_report_data_usage_our/)

网络上的用户开始讨论涨价的可能性，Firebase management 最终联系到了最终用户，帮助他们弄清楚为什么他们的账单上涨如此之快。最终结果是，Firebase RESTful API 的使用导致了带宽费用的急剧增加。

在这场争论中，对 Firebase 的一个抱怨是，Firebase 不提供深入的带宽分析，而是给用户一个几乎没有背后的线图。今天围绕分析平台所做的一个改变是在 Google Analytics 的旗帜下重新命名这些分析功能。

谷歌 I/O 将持续到周五，请回来查看后续报道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>