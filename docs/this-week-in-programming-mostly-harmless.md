# 本周编程:基本无害

> 原文：<https://thenewstack.io/this-week-in-programming-mostly-harmless/>

纵观计算机科学的历史，看“[被认为有害的](https://en.wikipedia.org/wiki/Considered_harmful)”文章的趋势，最有趣的部分可能是他们陷入了[认为“被认为有害的”文章有害的](https://meyerweb.com/eric/comment/chech.html)的元循环的趋势。正如杰夫·阿特伍德(Jeff Atwood)很久以前在他题为“[我也会认为那是有害的](https://blog.codinghorror.com/id-consider-that-harmful-too/)”的博客文章中所指出的，第一篇具有里程碑意义的“被认为是有害的”文章出现在[艾德格斯格·迪克斯特拉(Edsger Dijkstra)1968 年的](https://en.wikipedia.org/wiki/Edsger_Dijkstra)论文“[后藤被认为是有害的](http://www.u.arizona.edu/~rubinson/copyright_violations/Go_To_Considered_Harmful.html)”中，几十年后，这篇文章遭遇了“‘后藤被认为是有害的’被认为是有害的”以及更深入的兔子洞，“‘后藤被认为是有害的’被认为是有害的？”

只有程序员(或者可能是哲学家)能够达到这种嵌套层次而不爆头。对于大多数编辑来说，甚至写下最后一句话(我认为我正确地关闭了所有的引号)都是困难的。

正如开发者 Tim Oxley 在一篇博客文章(四年前撰写)中所言，如果那些迷失在“被认为有害的”论点的嵌套循环中的人能够[避开 else 并尽早返回](http://blog.timoxley.com/post/47041269194/avoid-else-return-early)该多好。奥克斯利的帖子仅仅是另一篇“被认为有害”的文章吗？这是坏脾气和哀怨的程序员的悠久传统吗？我们是否抛弃了仅仅基于这样一种想法的任何论点，即它们反对教条主义的实践，而这些实践本身又导致了不同种类的教条主义的实践？

在我看来，这个论点的核心是围绕它的[论点](https://www.reddit.com/r/programming/comments/878zi2/avoid_else_return_early/) [。虽然有很多受过大学教育的传统程序员，但这里也有很多自学成才的类型，我发现，至少这些互联网讨论是我学到最多的地方。](https://news.ycombinator.com/item?id=16678209)

回到正题，在文章中奥克斯利提出了四点 TL/dr；–

*   一旦您知道您的方法不能做任何更有意义的工作，就立即返回
*   通过使用 if/return 而不是顶级 if/else 来减少缩进
*   试着将你的方法的“实质”保持在最低的缩进层次。
*   错误处理是噪音。

有这么简单吗？你应该抛弃传统的 if-then-else 语句方法吗？这仅仅是[其他被认为有害的](https://www.youtube.com/watch?v=XDqZemwVXUk)吗？你应该搬到[快速](https://en.wikipedia.org/wiki/Fail-fast)并且早点回来吗？你多年来的“如果，那么，否则”的退出方式有没有把你引入歧途？

正如一位 Reddit 评论者[指出的](https://www.reddit.com/r/programming/comments/878zi2/avoid_else_return_early/dwb96ak/)，“如果你正在使用一种需要在返回之前清理东西的语言，提前返回是一件坏事”，指出需要“释放内存、套接字、文件句柄和其他资源”另一个[回复](https://www.reddit.com/r/programming/comments/878zi2/avoid_else_return_early/dwbuypz/)认为这在 C++中是必要的，而在作者使用的 Javascript 中是不需要的。在[的另一个讨论](https://news.ycombinator.com/item?id=16678209)中，一位评论者[提出](https://news.ycombinator.com/item?id=16678284)这可能只是[“保护条款”](https://refactoring.com/catalog/replaceNestedConditionalWithGuardClauses.html)的一种情况，这已经在 Swift 中[形式化了。](https://thatthinginswift.com/guard-statement-swift/)

无论是哪种情况，也许回到冗长的、学术性的反驳和“被认为有害的”循环的永恒嵌套循环的时代，我们都可以抛弃这个论点作为另一个例子，但正是在这里，我觉得我学到了最多。见鬼，如果没有它，我可能会一直不知道这种奇妙的“有害”现象。

总之，再次感谢匿名的网络评论者和潜在的不知道“被认为有害”的作者教会了我关于这个世界的新东西。这是我这周学到的关于编程世界的一些新东西。

## 本周的节目中

*   **TypeScript 2.8 带来了条件类型:**微软[宣布了 TypeScript 2.8](https://blogs.msdn.microsoft.com/typescript/2018/03/27/announcing-typescript-2-8/) ，它说“带来了一些我们认为你会无条件地爱上*的功能*！”斜体强调的是，作为此次声明的重要部分之一，包含了[条件类型](https://blogs.msdn.microsoft.com/typescript/2018/03/27/announcing-typescript-2-8/#conditional-types)，这是 TypeScript 中的一个新构造，允许您基于其他类型选择类型。当然，TypeScript 的一个定义特性是它向 JavaScript 添加了可选的静态类型，这“有助于保证您的代码避免输入错误和其他愚蠢的错误。”ITWorld 将这一新特性总结为“在运行时帮助基于类型的简单选择建模，同时允许更具表达性的设计时构造”。该结构采用以下形式:A 扩展了 B？C : D。应该理解为“如果类型 A 可赋给 B，则该类型归结为 C，否则就变成 D”。条件类型还提供了一种新的方法来根据新的 infer 关键字从类型中推断新的类型，该关键字引入了一个新的类型变量。"
*   **谷歌基于云的文本到语音转换:**谷歌[引入了云文本到语音转换](http://cloudplatform.googleblog.com/2018/03/introducing-Cloud-Text-to-Speech-powered-by-Deepmind-WaveNet-technology.html)作为其[谷歌云平台](https://cloud.google.com/)的一部分，它可以让你从 12 种语言和变体的 32 种不同声音中进行选择。该公司声称，“云文本到语音转换可以正确地读出复杂的文本，如姓名、日期、时间和地址，以便在一开始就发出听起来真实的语音，”尽管如果这与谷歌地图试图读出街道名称等类似内容有所不同，那么……云文本到语音转换功能由 WaveNet 提供支持，允许您定制音高、语速和音量增益，并支持各种音频格式，包括 MP3 和 WAV。[云文本到语音转换](https://cloud.google.com/text-to-speech/)现已推出公测版
*   **Rust 1.25 的一堆东西:**当我们向 [Rust 的“新时代版本”](https://thenewstack.io/week-programming-rusts-roadmap-epoch-release/)前进的时候，我们又得到了 [Rust 1.25 的另一个增量版本](https://blog.rust-lang.org/2018/03/29/Rust-1.25.html)，博客帖子说“包含了一堆东西！”Rust 1.25 已经从 LLVM 4 的[升级到 LLVM 6 的](https://github.com/rust-lang/rust/pull/47828)，并且现在允许[嵌套的导入组](https://github.com/rust-lang/rust/pull/47948)，这允许在一行中导入(或者其他)，这取决于你的偏好。此外，在该语言不断努力使学习 Rust 更容易的过程中， [Rust By Example 现在包含在 doc.rust-lang.org](https://doc.rust-lang.org/rust-by-example/)中。这只是其中的几个亮点，但请务必查看[发行说明](https://github.com/rust-lang/rust/blob/master/RELEASES.md#version-1250-2018-03-29)和[博客文章](https://blog.rust-lang.org/2018/03/29/Rust-1.25.html)以了解全部细节。
*   **Wear OS 开发者预览:**谷歌更名后的 Wear OS(之前的 Android Wear)在本周的开发者预览中[发布，为可穿戴设备带来了 Android P。预览版包括官方 Android 仿真器上的更新系统映像，以及华为 Watch 2 蓝牙或华为 Watch 2 Classic 蓝牙的可下载系统映像。正如谷歌对 Android 应用程序所做的一般，它在这个版本的 Wear OS 中实施了与非 SDK 方法和字段](http://android-developers.googleblog.com/2018/03/wear-os-by-google-developer-preview.html)相关的[限制。此外，预览版提供了一个黑暗的 UI 系统主题，并通过限制后台活动，关闭身体时关闭无线电，以及在蓝牙断开时关闭 WiFi 来改善电源使用。](https://g.co/dev/appcompat)
*   **tensor flow YouTube 官方频道:**谷歌还宣布了[tensor flow YouTube 频道](https://www.youtube.com/watch?v=BXgBOwDYsNg)，用于直播 3 月 30 日正在直播的 TensorFlow Dev 峰会。显示包括[编码张量流](https://goo.gl/XZTYsT)、[张量流满足](https://goo.gl/G9Y46n)、 [#AskTensorFlow](https://www.youtube.com/results?search_query=%23AskTensorFlow) 。
*   **Android Studio 3.1:** 本周加入 dot 发布的长长列表的是 [Android Studio 3.1](https://android-developers.googleblog.com/2018/03/android-studio-3-1.html) ， [SDTimes](https://sdtimes.com/android/sd-times-news-digest-android-studio-3-1-microsoft-open-sources-wsl-sample-valohais-machine-learning-funding/) 将其总结为包括“C++性能分析器、Kotlin 链接检查、数据库代码编辑、IntelliJ 平台更新、新构建输出窗口、快速启动和 C++ CPU 分析”Android Studio 3.1 现已于今日[下载](https://developer.android.com/studio/index.html)。

*   没有复杂性的兼容性: JAXEnter 介绍了最近提出的 [Go 包版本提案](https://jaxenter.com/go-package-versioning-proposal-142768.html)，它说该提案提供了没有复杂性的兼容性。根据这篇文章，Go 一直在处理版本信息方面有困难，但是一个新的提议超越了特设工具，以“在不增加复杂性的情况下提供向后的能力。”文章解释说“Go 1 的主要特点实际上并不是任何类型的语言变化或特殊功能”，而是“一个简单的承诺:Go 对向后兼容性的坚持”，强调了这种生产使用的可靠性如何推动 Go 的发展。不幸的是，如果有任何渐进的代码修复或部分代码升级，这会导致问题。“解决办法？[Russ Cox 提出了一个名为 vgo](https://github.com/golang/go/issues/24301) 的新提议，该提议“表明导入兼容性和语义版本化共同需要[语义导入版本化](https://research.swtch.com/vgo-import)。"
*   **集装箱？改为无服务器怎么样？**最后，本周，Matt Asay 在 Infoworld 上提出了一个论点，建议开发人员继续前进，[跳过容器，转而进行无服务器计算](https://www.infoworld.com/article/3265457/containers/why-serverless-is-the-better-option-than-containers.html)。虽然我们谈到了[拥抱其他人都在谈论的与容器相关的](https://thenewstack.io/week-programming-embracing-thing-everyone-else-talking/)，但 Assay 认为“尽管它们很棒，但容器有一个内在的缺陷:它们还不够简单。”Assay 将无服务器描述为向开发人员提供了一种专注于编写应用程序逻辑而不是服务器基础设施的方式，它还标志着开发人员需要“相信 AWS、微软或谷歌会得到正确的基础设施，但拥抱这些云后端的好处是巨大的。”你怎么看——集装箱还是无服务器，FTW？

谷歌和微软[是新堆栈的赞助商。](https://azure.microsoft.com/en-us/?v=17.14)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>