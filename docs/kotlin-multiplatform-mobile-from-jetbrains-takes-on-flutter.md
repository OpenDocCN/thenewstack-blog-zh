# 来自 JetBrains 的 Kotlin 多平台移动设备掀起一阵热潮

> 原文：<https://thenewstack.io/kotlin-multiplatform-mobile-from-jetbrains-takes-on-flutter/>

一个新的 beta mobile SDK 将允许 Kotlin 开发人员从一个代码库向 iOS 和 Android 部署具有原生用户界面的移动应用程序。

JetBrains 周一发布了测试版的 Kotlin 多平台手机。产品营销经理[叶卡捷琳娜·佩特洛娃](https://github.com/KaterinaPetrova)说，测试版意味着 JetBrains 已经稳定了功能，可以用于生产。

像[网飞](https://thenewstack.io/how-culture-impacts-technology-choice-a-review-of-netflixs-use-of-microservices/)、 [VMware](https://thenewstack.io/vmware-targets-the-platform-engineer/) 和 Cash App 这样的公司已经测试了 alpha。网飞用这个工具创建了 Prodicle ，这是一款用于电视节目和电影制作的移动应用。

“对快速产品交付的需求促使我们尝试多平台架构。网飞软件工程师 [David Henry](https://www.linkedin.com/in/davidmatthewhenry/) (现在在 Meta)和 [Hemel Yahya](https://www.linkedin.com/in/hemel-yahya-b193681b/) 在 2020 年 10 月分享道:“现在我们更进一步，在 Kotlin 中使用 Kotlin 多平台编写平台无关的业务逻辑，并通过 Kotlin/Native 编译成用于 Android 的 Kotlin 库和用于 iOS 的原生通用框架。

## 应用程序逻辑的单一代码库

编写一次业务逻辑是 Kotlin Mobile Multiplatform 的一个关键优势，它为应用程序逻辑提供了一个单一的代码库，允许开发人员为他们的 [Android](https://thenewstack.io/this-week-in-programming-windows-opens-up-to-android-developers/) 和 [iOS](https://thenewstack.io/wwdc21-ios-platform-upgraded-but-what-about-the-web/) 应用程序的网络、数据存储、分析和其他逻辑维护一个单一的代码库。

Henry 和 Yahya 说:“Kotlin Multiplatform 采用了不同于该领域一些知名技术的跨平台移动开发方法。“当其他技术抽离或完全取代特定平台的应用开发时，Kotlin 多平台是现有特定平台技术的补充，旨在取代与平台无关的业务逻辑。”

JetBrains 的开发者倡导者 Pamela Hill 说:“共享业务逻辑和使用业务逻辑的公共代码意味着用户可以在本地开发他们的界面。”。

“Kotlin Multiplatform for Mobile 带来的是，它必须在平台之间共享公共代码，然后在本地完成其余的工作，而不是像其他多平台技术一样，用特定的框架用特定的语言做所有的事情，”Hill 说。“我们的客户真正喜欢的是拥有通用的代码业务逻辑，然后原生地开发他们的用户界面，这样就有了他们漂亮的 iOS、Android、Android、原生外观的用户界面。”

该平台支持原生和跨平台开发优势，因此开发人员可以“共享经常不同步的逻辑元素的代码，同时保留原生编程的优势，包括出色的应用性能和对 Android 和 iOS SDKs 的完全访问，”该公司在发布会上指出。

[Kotlin](https://thenewstack.io/this-week-in-programming-all-aboard-the-kotlin-train/) 可用于跨平台和原生应用，因此开发者不必为移动应用编写其他语言。该公司表示，它还使用 Kotlin 的工具和生态系统，并为 Android Studio 中的跨平台移动开发提供工具。希尔说，它可以用来将已经为 Android 或 iOS 编写的现有应用程序移植到竞争对手的移动平台上。

JetBrains 表示，移动图书馆如 Ktor、SQLDelight、Apollo 和 Koin 已经采用了 Kotlin 多平台。测试版还更新了内存管理方法，以在 Android 和 iOS 目标之间提供一致的体验。根据 JetBrains 的说法，Kotlin 语法遵循用于 iOS 开发的相同概念，对于 iOS 开发人员来说很容易学习，JetBrains 还指出，超过 60%的 Android 开发人员已经使用开源的静态类型编程语言。

## 科特林对颤振

Kotlin 多平台手机与谷歌的 [Flutter](https://thenewstack.io/12-ways-flutter-streamlines-app-development/) 竞争，后者也支持多平台部署。Hill 说，区别在于 Flutter 用于开发整个应用程序，而 Kotlin 可以逐步采用。她说，另一个不同之处是，至少根据希尔的说法，Flutter 的用户界面材料设计“永远不会看起来完全自然，尤其是在 iOS 上”。

“而在多平台手机上，你可以在 iOS 上使用你的 [Swift UI](https://thenewstack.io/apple-highlights-swift-enhancements-at-wwdc22/) ，你可以在 Android 上使用你自己的 Jetpack Compose 或你的 [Vue](https://thenewstack.io/vue-js-big-china/) 系统，并拥有完美的本地外观用户界面，”她说。“采用真的是渐进的，由您选择，而不是被迫采取全有或全无的方法。”

然而，Kotlin Multiplatform 可能会有一场说服开发者的艰苦战斗:根据 [Statistica 的最新数据](https://www.statista.com/statistics/869224/worldwide-software-developer-working-hours/)，截至 2021 年，Kotlin Multiplatform 拥有跨平台移动市场的 2%，相比之下，Flutter 拥有 42%。Flutter 也有很大的优势，因为新的堆栈已经列举了。eSparkBiz Technologies 的创始人兼首席执行官 Harikrishna Kundariya 对 Flutter 的能力提出了更积极的看法。

“由于依赖于 Dart 编程语言，Flutter 可以快速执行代码，”Kundariva 写道。“通过使它看起来、工作起来和感觉起来都像一个精确的本机应用程序，它大大有助于提高整体性能。”

昆达里亚还指出，UI/UX 为开发者提供了清晰的视觉和丰富的体验，并补充说，Flutter 的架构“确保以快速的方式将编程应用定制到各自的操作系统中。”

尽管如此， [Kotlin 和 Java 仍然是用来部署 Android 应用程序的主要语言](https://www.geeksforgeeks.org/top-programming-languages-for-android-app-development/#:~:text=1.,most%20supported%20language%20by%20Google.)——甚至创造了 Flutter 的[谷歌也使用 Kotlin](https://developer.android.com/kotlin/first) ，报告称其超过 70 个应用程序，包括地图、游戏、驾驶和信息，都是使用这种编程语言构建的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>