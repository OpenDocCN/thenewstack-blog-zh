# 本周编程:vgo 和“所有可能场景的技术解决方案”的责任

> 原文：<https://thenewstack.io/this-week-in-programming-vgo-and-the-onus-of-a-technical-solution-to-all-possible-scenarios/>

几个月前，[首次提出了用于 Go](https://blog.golang.org/versioning-proposal) 的 [vgo 包版本](https://github.com/golang/vgo)，本周，[接受了该提议](https://github.com/golang/go/issues/24301#issuecomment-390766926')——尽管在此过程中并非没有评论和争论。

在互联网上，很少有其他事情像围绕一种流行编程语言的变化而展开的辩论。找一大群人，他们的工作和总体趋势是寻找一些技术变化影响事物的无数方式，你的讨论可能会很快深入到各个方向。围绕 vgo 的争论也不例外。

当然，这场辩论也是围绕 Golang 等开源项目的社区与直接支持它的公司和团队之间斗争的一个例子。请阅读“ [Go:从 Godep 到 vgo，一段评论性的历史，](https://codeengineered.com/blog/2018/golang-godep-to-vgo/)”，其中提供了一个关于 Go 版本化之争的观点，然后在评论中详细阐述，Golang 团队成员 [Russ Cox 提供了他自己的事件版本](https://codeengineered.com/blog/2018/golang-godep-to-vgo/#comment-3912763285)。

即使在导致新版本化系统的事件的辩论和复述中，事件的版本就像[在不远的将来可能会或可能不会破坏您的代码的包的版本](https://codeengineered.com/blog/2018/golang-vgo-broken-dep-tree/)一样被辩论。

无论如何，vgo 接受通知中的语言相当有趣。社区对 vgo 的反对意见是“该提案将要求人们改变他们使用和发布库的一些做法”，以及“该提案未能为所有可能出现的涉及不兼容性的场景提供技术解决方案。”

正是这种为所有可能的场景提供技术解决方案的想法真正打动了我。作为程序员，我认为这是我们一直在寻找的东西，但我想知道这是否是我们总能找到的东西。从我这个局外人的角度来看，我觉得这很有趣，因为这听起来像是对提案不完美的一种让步，但却是一种更好的前进方式，有些问题需要在“伴随的实现而不是提案”中解决当然，很多人并不是这么看的。

“代码*的作者和用户*将不得不改变他们在使用和发布库方面的一些做法，”提案接受书中写道，“就像开发人员已经适应了 Go 的其他细节，比如运行 gofmt。改变最佳实践有时是正确的解决方案。”

在开源项目的历史和围绕它们的各种斗争中，我不禁想知道上次像这样的长时间辩论以一致结束是什么时候。有过吗？在与机构群体合作和最终结束争论并说“这是前进的方向”之间，需要划清什么样的界限

最后，各种反应不一而足，从“[这是令人惊讶的无痛](https://github.com/gohugoio/hugo/pull/4754)”到“这绝对会打破一切！”亲爱的 Golang 贡献者，你的立场是什么？Go 开发者？是否需要在提议的 vgo 版本控制的结构中或者在实现和使用它的人员中进一步发现灵活性？

至此，我们可以看看过去一周编程领域的一些新闻和想法，首先快速了解一下 GoLand IDE 中的 vgo 集成。

## 本周的节目中

*   **GoLand 支持 vgo:** 接受 vgo 版本系统的墨迹未干，但是 JetBrains 的 GoLand IDE 已经准备好支持它了[。“包管理长期以来一直是 Go 社区中许多人感兴趣的话题，”公告轻描淡写地说。“今天我们很高兴地宣布，这一集成的第一个版本作为 GoLand 2018.1.2+的插件提供。”](https://blog.jetbrains.com/go/2018/05/18/vgo-integration-support/)
*   **GitHub Desktop 1.2:**GitHub Desktop 的[最新 dot 版本现在可以“帮助你与同事的变化保持同步，并让你与你的团队保持同步。最新的功能包括比较分支和选择多个文件的能力，这意味着您可以“将您的分支与存储库中的任何其他分支进行比较，如您的主分支或基本分支，并将该工作合并到您的当前分支中”。“至于多个文件选择”，现在您可以通过按住 Shift 或 Command/Ctrl 并单击您想要选择的文件来选择多个文件以对其执行操作。"](https://blog.github.com/2018-05-22-github-desktop-1-2/)
*   **Slack 增加动作&其他开发工具:** Slack 上周举行了其 Spec 开发者大会，据 SD Times 报道，[为开发者提供了新的工作方式](https://sdtimes.com/softwaredev/slack-spec-gives-developers-new-ways-to-work/)“开发者可以添加到他们现有工作流程中的新工具”，包括动作，“一种提供与开发工具和 Slack 协作解决方案更深层次集成的新方式。”基本上，“通过操作，开发人员可以将消息转换为任务、评论或跟进，以及将消息附加到票证。”除了 Actions，Slack 还宣布了 Block Kit，这是一个面向开发者的新 UI 工具包，将“为日期选择器、任务对象、溢出菜单等提供标准设计，使应用程序更强大、更易于使用。”
*   **关于学习 Kotlin:** 对于那些正在学习或打算学习 Kotlin 的人来说，这是两个快速的花絮，Kotlin 是 Google 认可的用于开发 Android 应用程序的语言。首先，谷歌本周宣布了一项免费的自定进度的课程。该课程涵盖了基础知识，如编写 Kotlin 语句和表达式。它还涉及到函数和类的编写，并超越了基础知识，涉及到对、集合和常量等等。对于那些已经在编写 Kotlin 的人来说，你可以快速阅读一下 Karumi 博客上的[这篇关于 Kotlin 开发六个月后的经验教训的博文](http://blog.karumi.com/kotlin-android-development-6-months-into-it)，这篇博文提供了他们“对当前技术水平的看法”
*   **学习机器学习:**当我们谈论学习时，TechCrunch 上也有一篇关于[谷歌和 Coursera 推出新的机器学习专业](https://techcrunch.com/2018/05/23/google-and-coursera-launch-a-new-machine-learning-specialization/)的帖子。这不是两家公司的第一次，而是建立在以前的努力之上，包括[机器学习速成班](https://developers.google.com/machine-learning/crash-course/)，“为开发者提供机器学习的介绍。”这个[机器学习专业](https://www.coursera.org/specializations/machine-learning-tensorflow-gcp)名为“在谷歌云平台上使用 TensorFlow 进行机器学习”，由五门课程组成，让学生“从设置环境到学习如何创建和净化数据集，再到在 TensorFlow 中编写分布式模型，提高这些模型的准确性并调整它们以找到正确的参数。”

*   **专有应用中的开源:**在 Black Duck 的一项调查中，本周的一篇文章发现[专有应用中开源代码的比例正在上升](https://www.helpnetsecurity.com/2018/05/22/open-source-code-security-risk/),“96%的扫描应用包含开源组件，平均每个应用有 257 个组件。”根据这份报告，“在被扫描的应用程序的代码库中，开放源代码的平均比例从去年的 36%增长到 57%，这表明大量应用程序现在包含的开放源代码比专有代码多得多。”
*   **关于维护微软记事本:**微软最近宣布记事本现在支持 Linux 换行符，这让很多人感到惊讶。事实上，在另一篇关于过时的文本编辑器的博客文章中，微软本周写道[维护记事本不是一份全职工作，但也不是一份空泛的工作](https://blogs.msdn.microsoft.com/oldnewthing/20180521-00/?p=98795)，指出“记事本是一个普通的实验品。”值得一读。
*   **为 PHP 辩护:**这篇文章是写给那些喜欢抨击 PHP 的人的。在一篇名为“ [PHP 允许 X 的设计”](http://blog.krakjoe.ninja/2018/05/php-allows-for-design-of-x.html)的博客文章中，PHP 开发人员 Joe Watkins 引用了一句古老的格言和一些反对使用 PHP 的常见论点(例如“但是 PHP 是作为模板语言设计的”)。“几乎我写的每一个扩展都得到了同样的回应:‘仅仅因为你能，并不意味着你应该’。他们所传达的是‘你能不能没关系，你不应该’，这介于愚蠢和有害之间。如果可以的话，这真的很重要。”继续读下去，你会发现 PHP 并不像你所说的那样简单。
*   **离开服务:**最后，本周，我们将向您展示一个真正有用的服务。点击即可。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>