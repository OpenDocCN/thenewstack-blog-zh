# 本周编程:GitHub 进入命令行

> 原文：<https://thenewstack.io/this-week-in-programming-github-goes-to-the-command-line/>

你们准备好像 1999 年那样狂欢了吗？如果是这样，请做好准备，因为 GitHub 已经为您准备了一个全新的命令行界面(CLI ),如果您幸运的话，您还可以使用一些 ANSI 颜色来设计它。所以准备好你的机械键盘，因为我们去的地方不需要鼠标！

除了 Snark 之外，人们本周对 GitHub CLI 1.0 的可用性感到兴奋，这是继今年早些时候的[测试版](https://github.blog/2020-02-12-supercharge-your-command-line-experience-github-cli-is-now-in-beta/)之后的又一个版本，部分原因是现在你不需要离开终端，部分原因是它实现了自动化。GitHub CLI 可用于 [Windows、macOS 和 Linux](https://cli.github.com/) ，并允许您直接从终端运行整个 GitHub 工作流程，从发布到发布，而且[对新 CLI 的一个常见批评](https://news.ycombinator.com/item?id=24509345)是它可能会进一步混淆年轻、敏感的编码人员对 git 和 GitHub 之间的区别。

当然，GitHub CLI 超越了基本的 git 功能，还允许用户调用 GitHub API，允许他们编写“几乎任何动作”的脚本。自测试版以来发布的一些新功能包括[创建和查看存储库](https://github.blog/changelog/2020-03-06-github-cli-now-supports-working-with-repositories-locally/)，[配置 GitHub CLI 以使用 SSH 和您的首选编辑器](https://github.blog/changelog/2020-04-23-github-cli-now-supports-autofilling-pull-requests-and-custom-configuration/)，[关闭、重新打开和添加标签、受托人和更多问题和拉请求](https://github.blog/changelog/2020-05-11-github-cli-allows-you-to-close-reopen-and-add-metadata-to-issues-and-pull-requests/)，以及[查看差异、审查和合并拉请求](https://github.blog/changelog/2020-05-26-mark-pull-requests-as-ready-for-review-review-and-merge-from-github-cli/)。

现在，许多人想知道“那么[中心](https://hub.github.com/)呢？”幸运的是，[有一篇简短的文章](https://github.com/cli/cli/blob/trunk/docs/gh-vs-hub.md)介绍了两者之间的区别以及创建全新 CLI 的原因。简而言之，GitHub 团队不希望被十年前的架构决策所束缚，并且“希望更加坚持己见并专注于 GitHub 工作流，而使用 Hub 这样做有疏远许多喜欢现有工具并希望它以他们习惯的方式工作的 Hub 用户的风险。”Hub 仍将是一个独立的项目，不由 GitHub 自己直接管理，“只要它得到维护并不断收到贡献，它就会继续存在。”

所以，如果这种把所有东西都放在浏览器中的做法让你感到恶心，那你很幸运。GitHub CLI 将帮助您保持终端状态，就像 1999 年一样。

说到 1999 年(尽管这个更像是 1989 年)，如果你想知道一个开发者是如何考虑打破马里奥 3 的速度记录的，看看这个:

[https://www.youtube.com/embed/WWbZFj-cLvk?feature=oembed](https://www.youtube.com/embed/WWbZFj-cLvk?feature=oembed)

视频

## 本周的节目中

*   **VS Code C++扩展升级到 1.0:** 虽然 Visual Studio C++扩展并不是全新的，但微软已经宣布[已经升级到 1.0 版本](https://devblogs.microsoft.com/cppblog/c-in-visual-studio-code-reaches-version-1-0/)。1.0 带来了一些新功能，如支持 ARM 和 ARM64 上的 Linux，以及更简单的智能感知配置、可定制的代码格式和一个 [C++扩展包](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools-extension-pack)，其中包括远程开发、GitHub 集成和一流的 CMake 等内容。在配置方面，团队已经创建了一个[视频教程](https://aka.ms/cpp-intelliSense)来帮助你，代码格式化现在已经内置了对新设置的 [EditorConfig](https://docs.microsoft.com/en-us/visualstudio/ide/cpp-editorconfig-properties?view=vs-2019) 支持。除了新功能，他们还说他们已经解决了九个[与性能相关的 GitHub 问题](https://github.com/microsoft/vscode-cpptools/issues?q=is%3Aissue+is%3Aclosed+label%3Aperformance+label%3A%22fixed+%28release+pending%29%22+sort%3Aupdated-desc)，所以去获得你的新 C++扩展吧。
*   **Kotlin 1.4 发布上线:**JetBrains 的团队表示，他们将在 10 月 12 日至 15 日举办一场 [Kotlin 1.4 在线活动](https://blog.jetbrains.com/kotlin/2020/09/kotlin-1-4-online-event/)，其中将包括你的标准问答环节、小组讨论、聊天，甚至还有一个虚拟 Kotlin 展台和一个参加抽奖的测验。完整的[日程和发言人名单](https://kotlinlang.org/lp/event-14/)已经公布，你可以在那里注册免费活动，即使你错过了，活动结束后所有的视频都可以在 YouTube 上看到。当然，对于那些虚拟出席的人来说，你可以走参与式路线，通过使用标签 [#kotlin14ask](https://twitter.com/search?q=%23kotlin14ask) ，将他们输入到[表格](https://surveys.jetbrains.com/s3/Q-A-Your-question-for-the-Kotlin-team)，或者使用实时聊天，向演讲者提问。至于虚拟展台，你可以在那里[注册一个时间](https://kotlinlang.org/lp/event-14/#registration)直接与 Kotlin 团队聊天。

*   **Java 15 带来了微调:**Java 的最新版本已经到来，Application Developer Times 为我们带来了 Java 15 即将正式上市的故事，它写道“最新的 Java 开发工具包(JDK)提供了新的功能，预览功能现已完成，预览功能正在酝酿中，现有代码继续现代化，以及大量的错误修复和过时功能的废弃。”更具体地说，Oracle 的一篇博客文章说，Java 15 带来了“[14 个主要增强/变化](https://openjdk.java.net/projects/jdk/15/)，包括一个孵化器模块、三个预览功能、两个不推荐使用的功能和两个删除功能。”该版本遵循 2018 年从 Java 10 开始的六个月发布节奏。ADT 援引一位人士的话说，“JDK 15 中的大部分内容要么是对早期版本中引入的功能(即所谓的预览功能)的微调，要么是已被否决或删除的功能。
*   **然后是 Java 应用程序的开源 ML 库:**随着 Java 15 的发布，Oracle 也在上周开源了一个 Java 应用程序的 ML 库。 [Tribuo](https://tribuo.org/) 已经在 Apache 2.0 许可下在 [Github](https://github.com/oracle/tribuo) 上发布，它解决了 Oracle 认为的“企业系统的期望和大多数 ML 库提供的功能之间的关键差距”，这与用于训练模型的数据以及 ML 库和企业系统本身之间经常发现的语言差异有关。换句话说，当你的系统使用静态类型的语言如 Java 时，你不再需要协调你的 ML 使用动态类型的语言如 Python 或 R。有趣的是，对于熟悉 Oracle 的人来说，这可能是一顶旧帽子，如果您想为这个特定的开源项目做出贡献，您需要签署[Oracle contributor agreement](https://www.oracle.com/technical-resources/oracle-contributor-agreement.html)——他们说的签署是指实际打印出来并签名，因为不接受电子签名。

*   **OneFuzz 瞄准大规模 bug:**发布开源项目的大公司的更多新闻，[微软开源了项目 OneFuzz framework](https://www.microsoft.com/security/blog/2020/09/15/microsoft-onefuzz-framework-open-source-developer-tool-fix-bugs/) ，这是一个可扩展的 Azure fuzz 测试框架，可作为开源工具在 [GitHub](https://github.com/microsoft/onefuzz) 上获得。微软已经开始在 Windows CI/CD 管道中使用该工具，并表示“在微软的 Visual Studio 中，对这些特性的实验性支持正在[增长。”该项目在麻省理工学院的许可下是开源的。](https://devblogs.microsoft.com/cppblog/asan-for-windows-x64-and-debug-build-support/)
*   **Shopify 着眼于解构一个整体:**上周，由超过 280 万行 Ruby 代码和 500，000 次提交组成的核心整体 Shopify 在本周写了一篇博文，关注其整体的状态，并研究如何使其整体更加模块化。如果这听起来很熟悉，这本书可能值得一读。该公司在这方面已经努力了两年半，他们有一些经验想要分享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>