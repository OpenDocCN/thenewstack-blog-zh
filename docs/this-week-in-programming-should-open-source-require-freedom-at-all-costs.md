# 本周编程:开源应该要求“不惜一切代价的自由”吗？

> 原文：<https://thenewstack.io/this-week-in-programming-should-open-source-require-freedom-at-all-costs/>

对于开源软件世界的直接行动来说，这是辉煌的一周，至少对于一个坚定的开发者来说是如此。前厨师，现任谷歌云工程师 [Seth Vargo](https://twitter.com/sethvargo) ，在注意到他的图书馆被厨师使用后，通过合同，联邦政府移民和海关执法局(ICE)部门，从 GitHub 上撤下该软件以示抗议，并使 ground Chef 的整个运营停止。起初，在[发布更新](https://blog.chef.io/an-important-update-from-chef/)之前，Chef 坚持自己的立场，称“经过 Chef 内部的深刻反省和对话，我们将不会与 ICE 和 CBP 续签明年到期的合同。”

https://twitter.com/smrt_fasizmu/status/1174736586870685696

与此同时，“代码女巫”Coraline Ada Ehmke 从这个场景中获得灵感，并决定发布她所谓的[希波克拉底许可证](https://github.com/ContributorCovenant/hippocratic-license)，这立即得到了大量的回应——有支持的，也有强烈反对的。

最初的许可证使用了有问题的和法律上模糊的术语，如“弱势群体”,在接下来的几天里，Ehmke 对许多批评做出了回应，迅速改变了许可证的语言，删除了一些有问题的部分，并试图更好地定义谁将不能使用许可证——所有这些对她的批评者来说都没有成功。虽然 Ehmke 试图通过使用联合国世界人权宣言作为比较标准来更好地定义许可证，但许多人仍然不满意。

许多人很快指出，该许可证只是一长串类似的许可证中的一个，这些许可证试图监管开放源代码的使用(从而使其不开放)，这些许可证已经失败或仅仅存在而没有明显的效果。例如, [JSON 许可证](https://wiki.debian.org/qa.debian.org/jsonevil)上写着“软件应该被用来做好事，而不是坏事”,据我们所知，这一条款对软件的使用没有任何影响。

Matt Asay [指出了这种授权尝试中道德模糊的问题，他写道什么被视为正确或错误是“一个主观问题”对于 Asay 来说，这个问题也归结为开放性，将限制开源比作限制言论自由，写道“……为什么这些许可证几乎事实上是坏的，不管意图多么好，因为它们使开源变得不那么开放。随着每一个这样的许可，开源变得越来越少。如果不限制开源软件可以做的所有事情，很难甚至不可能规定开源软件不能做什么。”](https://www.infoworld.com/article/3440557/should-open-source-licenses-fight-evil.html)

同样，开源运动的创始人之一 Bruce Perens 写道[“希波克拉底许可证”不能工作](https://perens.com/2019/09/23/sorry-ms-ehmke-the-hippocratic-license-cant-work/)，再次挑剔许可证的语言，说它不符合[对开源的定义](https://opensource.com/resources/what-open-source)，并说 Ehmke 应该以其他方式为纠正世界的错误而斗争。

要是世界上的好心人也有律师来写这些东西就好了，嗯？

这一切都引出了我心中的一个观点，另一条推文对此做了最好的说明:

事实上，虽然这可能是一个困难和不完美的尝试，但我们都应该如此努力地关闭它，而不是纠正和建设它吗？我猜想，对许多人来说，答案仍然是肯定的，因为这把利刃既有利也有弊，但就像其他法律一样，条款能说得足够具体吗？

不管怎样，Ehmke 现在写道，在所有这些讨论中，至少有一个主要目标已经实现。

Ehmke 进一步阐述了她的目标是看到开源定义的第五和第六条被修改:

*“…鉴于政府及其合作者滥用权力、侵犯公民权利和人权，我的目标是引发关于“不惜一切代价自由”要求对官方批准的开源软件的影响的讨论。开发人员不希望他们的劳动被用来造成伤害，开源软件的当前结构剥夺了创作者防止这种情况发生的任何权力。我们被剥削了。人类的自由正在被用来换取所谓的‘软件自由’。”*

## 本周的节目中

*   **。NET Core 3.0 带来了 F# 3.7 和 C# 8:** 的[版本。NET Core 3.0](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/) 包含了很多东西，比如增加了 Windows 窗体和 WPF，新的 JSON APIs，对 ARM64 的支持，当然还有性能的提升。除此之外。NET Core 3.0 包括 C# 8，其中包括可空、异步流和更多模式，以及 [F# 4.7](https://devblogs.microsoft.com/dotnet/announcing-f-4-7/) ，微软称其“专注于放松语法和目标”。网标 2.0。”[。NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0) 可供 Windows、macOS 和 Linux 下载，并且已经“针对 Docker 进行了加固以启用”。NET 应用程序在容器中可预测地、高效地工作”，这一点你们中的一些新栈读者可能会喜欢。微软也呼吁。NET Core 3.0 是“一个重要的新版本”，指出“大量的改进[……]如 SDK 大小的大规模缩减，以及对容器和 Windows 桌面应用程序等关键场景的支持的极大改进。”

*   **关于 F# 4.7 的更多信息:**关于新[首次亮相的 F# 4.7](https://devblogs.microsoft.com/dotnet/announcing-f-4-7/) 的更多细节——最新版本不再支持。NET Standard 1.6，并引入了用编译器调整有效语言版本的能力，允许团队为任何给定的编译器版本提供预览功能以及已发布的功能。对于使用预览版的用户。NET Core 和/或 Visual Studio，语言版本将默认设置为预览。F#团队在发布会的最后谈到了。NET 的“巨大转变”。NET 5”并指出 F#也将效仿:“它还具有用于‘分析性’工作负载的强大传统:处理数据、做数值工作、数据科学和机器学习等。我们认为 F#非常适合继续这条道路，我们打算强调能够更好地适应这些工作负载的功能。”同样值得注意的是，他们提到他们打算通过。NET 内核。
*   **学习 C#。NET 免费:**如果你对这个领域有什么倾向， [Scott Hanselman](https://www.hanselman.com/) 也公布了一些[的免费 C#。NET 和 ASP.NET 视频课程和教程](https://www.hanselman.com/blog/AnnouncingFreeCNETAndASPNETForBeginnersVideoCoursesAndTutorials.aspx)，他说他已经为此工作了几个月。[课程](http://feeds.hanselman.com/~/t/0/0/scotthanselman/~dot.net/videos)包括“近百个短视频(还会有更多！)会教你 C# 101、。NET，制作桌面应用，制作 ASP.NET web 应用，学习容器和 Docker，甚至从机器学习开始。”

*   **Rust 1.38.0 带来流水线编译:**Rust 团队已经[宣布了 Rust 1.38.0](https://blog.rust-lang.org/2019/09/26/Rust-1.38.0.html) ，写道该版本的亮点是[流水线编译](https://blog.rust-lang.org/2019/09/26/Rust-1.38.0.html#pipelined-compilation)，它说这将提高编译速度高达 10-20%，尽管[一些人报告](https://twitter.com/nnethercote/status/1177114232178954241)比这更好。该版本还引入了 [#【已弃用】宏](https://blog.rust-lang.org/2019/09/26/Rust-1.38.0.html#%5Bdeprecated%5D-macros)，部分[库更改](https://blog.rust-lang.org/2019/09/26/Rust-1.38.0.html#library-changes)，并针对 mem 的一些不正确用法增加了[林挺::{未初始化，归零}](https://blog.rust-lang.org/2019/09/26/Rust-1.38.0.html#linting-some-incorrect-uses-of-mem:%7Buninitialized,-zeroed%7D) 。
*   自从 Google 宣布 Kotlin 是 Android 开发的官方首选语言已经有一段时间了，所以如果你还没有开始学习 Kotlin，现在是时候了。谷歌已经推出了一些 [Android Kotlin codelab 课程](http://android-developers.googleblog.com/2019/09/new-android-kotlin-codelab-courses-are.html)，这些课程是基于教程的，而不仅仅是视频，并且在 Kotlin 课程中包括[面向程序员的 kot Lin boot camp](https://codelabs.developers.google.com/kotlin-bootcamp/)和[开发 Android 应用。例如，通过 bootcamp 课程，您将从构建一个交互式界面到与其他服务连接，并在此过程中了解许多其他功能。总的来说，他们写道，“你将创建并使用 10 个以上的应用程序，因此，在本课程结束时，你将拥有一个示例代码组合，可以用来实现你自己的惊人的应用程序想法！”](https://codelabs.developers.google.com/android-kotlin-fundamentals/)

由 [Pratik Gupta](https://unsplash.com/@graylab?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>