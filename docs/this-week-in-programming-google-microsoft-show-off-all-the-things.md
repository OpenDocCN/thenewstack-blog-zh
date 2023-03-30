# 本周编程:谷歌，微软炫耀所有的东西

> 原文：<https://thenewstack.io/this-week-in-programming-google-microsoft-show-off-all-the-things/>

本周，我们看到 IT 界的两大巨头 [Google I/O](https://events.google.com/io/) 和[微软 Build](https://www.microsoft.com/en-us/build) 召开了各自的开发者大会。在这两家公司之间，有…好吧，让我们只说许多公告。见鬼，根据谷歌的一篇博客文章，这个搜索巨头展示了[至少 100 个新东西](https://www.blog.google/technology/developers/100-things-we-announced-io-19/)。如果你真的想获得完整的体验，谷歌目前有 175 个视频来自 I/O，而微软有 356 个视频来自 Build。

当然，没有人有时间做这个，如果你看一下谷歌公告的列表，只有 14 个正好属于“开发者”新闻部分。因此，我们不会花一周的时间来观看每一个公司的每一段录音，我们会为您做一些新闻报道，看看这两家公司本周为您的开发人员准备了什么。现在，买家请注意，我们当然不能声称详尽无遗，但这里有一些过去一周的顶级语言和环境相关的新闻。首先，谷歌。

## 谷歌输入/输出开发者新闻

*   **Kotlin 现在是 Android 开发的“首选”:**我们已经关注 [Kotlin](https://kotlinlang.org/) 几年了[到现在](https://thenewstack.io/week-programming-kotlin-eats-lunch/)，谷歌本周告诉我们它正在全力以赴开发这种语言，宣布它是 Android 应用开发的首选语言。在一篇博客文章中，谷歌指出，自从该公司在 2017 年首次宣布官方支持该语言以来，开发者对 Kotlin 的使用已经增长到 50%以上。现在，在可以编译成 JavaScript 的静态类型 JVM 语言的“另一大步”中，谷歌宣布它不仅受支持，而且是首选，Kotlin-first 提供了“许多新的 Jetpack APIs 和功能”。“如果你开始一个新项目，你应该用科特林语写，”谷歌敦促道。用 Kotlin 编写代码通常意味着更少的代码——需要键入、测试和维护的代码更少。TechCrunch 援引 Android 倡导者切特·哈斯(Chet Haase)的话说:“我们知道现在不是每个人都在 Kotlin 上，但我们相信你应该去那里，”哈斯说。可能有充分的理由让你继续使用 C++和 Java 编程语言，这完全没问题。这些不会消失。"

[https://www.youtube.com/embed/roSp-SsBPp4?feature=oembed](https://www.youtube.com/embed/roSp-SsBPp4?feature=oembed)

视频

*   **Android Studio 测试版升级:**在自己版本的[“错误修复和性能改进”中，](https://thenewstack.io/this-week-in-programming-practicing-good-developer-self-care/) Android Studio 3.5 测试版[本周上架](https://android-developers.googleblog.com/2019/05/android-studio-35-beta.html)，承诺“更加关注质量和稳定性，而不是功能”这一最新版本是谷歌在一月份首次推出的项目 Marble 的产品，在被更多琐碎的功能所困扰之前，该项目致力于基础工作。因此，一些新的“功能”是对诸如“33 个有影响的内存泄漏”等问题的错误修复，这些问题使 IDE 变慢，还有“功能抛光”，如 C++项目支持 [Chrome OS 支持](https://developer.android.com/studio/install#chrome-os)。总的来说，谷歌表示，Android Studio 3.5 在系统健康和功能完善这两个基本类别中有“数百个漏洞修复和显著变化”要报告。为了获得更好的总结，请务必阅读[博客文章](https://android-developers.googleblog.com/2019/05/android-studio-35-beta.html)或深入阅读[发行说明](https://developer.android.com/studio/preview/features)。或者更好的是，[下载](https://d.android.com/studio/preview)带走。

[https://www.youtube.com/embed/8rfvfojtRss?feature=oembed](https://www.youtube.com/embed/8rfvfojtRss?feature=oembed)

视频

*   **JetPack 增加了汽车和相机库&更多:**谷歌一年前才推出 JetPack，但已经表示,“旨在加速 Android 开发的软件组件集合”正在 Play store 前 1000 款应用中的 80%中使用。本周，[公司透露了](https://android-developers.googleblog.com/2019/05/whats-new-with-android-jetpack.html)增加了近十几个新的 JetPack 库，包括 [CameraX](https://d.android.com/camerax) ，这是一个旨在提供“跨设备一致的相机体验，因此你不再需要维护设备特定的配置”的库，以及 [Android for Cars](https://d.android.com/cars) 库的测试版，它使你的应用程序更容易与 Android Auto 应用程序和 Android Automotive OS 集成。当然，那些只是引人注目的、有趣的标题特征。新的 JetPack 还包括一个测试版的 [Jetpack Enterprise library](https://developer.android.com/jetpack/androidx/releases/enterprise) ，一些架构组件更新，如“支持常见一次性异步操作的 LiveData 和 Lifecycles w/ coroutines”，以及 JetPack Compose 的早期预览，“一个新的非捆绑工具包，旨在通过将反应式编程模型与 Kotlin 的简洁性和易用性相结合来简化 UI 开发。”

[https://www.youtube.com/embed/QYkTXJ2TuiA?feature=oembed](https://www.youtube.com/embed/QYkTXJ2TuiA?feature=oembed)

视频

## Microsoft Build 开发者新闻

*   **Windows 现在做什么？Linux？**仅仅是因为 Windows 曾经由[领导，他称 Linux](https://www.theregister.co.uk/2001/06/02/ballmer_linux_is_a_cancer/) 为“一种癌症，从知识产权的角度来说，它附着在它所触及的一切事物上”，我们必须包括这一点——微软已经透露[一个合法的 Linux 内核](/windows-subsystem-for-linux-brings-the-full-4-19-kernel-to-windows/)将从今年夏天开始与 Windows 一起发布。Mary Branscombe 为新的堆栈写道，这对开发者来说无疑是一个进步。“WSL 2 承诺对文件 IO 性能进行急需的改进，以及对 Docker 的本机支持，从而简化 Linux 容器的使用，”Branscombe 写道。“但它也使 Linux 在 Windows 上完全兼容，这是 Windows 所能提供的一个重大转变。”[Windows Linux 子系统(WSL)](https://devblogs.microsoft.com/commandline/shipping-a-linux-kernel-with-windows/) 将是 Linux 内核第一次与近 24 年的操作系统一起发布——相比之下，Linux 将于今年 9 月满 18 岁——随着这些天来在微软变得越来越常见，内核将完全开源。

*   **Visual Studio 即将上线:**微软提供了三个新功能的[私人预览](https://devblogs.microsoft.com/visualstudio/intelligent-productivity-and-collaboration-from-anywhere/)，这将使开发人员能够“在任何地方、任何设备上工作，同时几乎消除了开始高效编码所需的设置量。”听起来不错！首先，从 C#和 C++开始，Visual Studio 远程开发将允许用户将他们的“本地工具连接到 WSL、Docker 容器或 SSH 环境，同时保留 Visual Studio 代码中的全保真编辑体验”。接下来，云托管的开发人员环境将让开发人员快速在云中构建开发人员环境(因此得名)，而不是花费所有时间担心依赖性。最后，微软更新了 Visual Studio Online，“一个新的基于网络的配套编辑器，补充了 Visual Studio 家族，并确保您可以从任何设备有效地工作”，并且“将支持 IntelliCode 和即时共享”(另一个相关的消息是，IDE 上线已经成为一个确定的趋势，因为 Red Hat 也在本周的会议上让[关注其基于 Web 的 CodeReady work spaces IDE](https://thenewstack.io/red-hats-openshift-4-adds-knative-key-coreos-features/)。)有兴趣的，现在就可以[报名私人预览](https://aka.ms/vsfutures-signup)。

*   **。微软本周宣布“继[之后的下一个版本。网芯 3.0](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-5/) 会。NET 5，“用”就一个。这将让你“瞄准 Windows、Linux、macOS、iOS、Android、tvOS、watchOS 和 WebAssembly 等等。”对于那些一直在跟踪的人，你可能会喊“但是 4 在 3 之后，而不是 5！”但是微软解释说，它“跳过第 4 版，因为它会使熟悉。NET Framework，已经用了 4.x 系列很久了。”撇开命名不谈，将于 2020 年某个时候上市的新版本将致力于提供“单一的”。NET 运行时和框架，可以在任何地方使用，具有统一的运行时行为和开发人员体验。NET Framework、Xamarin 和 Mono，并在“一个开发人员(微软和社区)可以一起工作和扩展的单一代码库”中完成这一切当然，所有这些只是冰山一角，所以如果你感兴趣，一定要看看微软[关于主题](https://devblogs.microsoft.com/dotnet/introducing-net-5/)的冗长帖子的其余部分。**

由 [Belinda Fewings](https://unsplash.com/photos/_uuDLuOdTh0?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/search/photos/everything?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>