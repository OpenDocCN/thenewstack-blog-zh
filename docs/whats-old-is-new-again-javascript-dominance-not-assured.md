# 旧事重提:JavaScript 的统治地位没有得到保证

> 原文：<https://thenewstack.io/whats-old-is-new-again-javascript-dominance-not-assured/>

就像一只停了的手表一天会对两次一样，在科技世界里，如果你呆的时间足够长，你很久以前就知道的方法会再次成为做事的方式。本周， [GitHub 的 ReadME 项目](https://github.com/readme)的 [Klint Finley](https://klintfinley.com/) 写了一篇文章，讲述了一个旧事重提的故事，探索了所有正在走向前端的[后端语言](https://github.com/readme/featured/server-side-languages-for-front-end)。

芬利写道，自网络计算的早期以来，技术一直在服务器端和客户端处理之间来回摆动，过去十年由客户端 JavaScript 主导。“但是一种新的工具[正在把钟摆摆向服务器，”他写道。](https://github.com/dbohdan/liveviews)

现在，对于那些还记得用那些旧的后端语言(早期的 PHP 论坛)创建网页的人，有人记得吗？)，你可能会认为再次回到他们身边的想法是异端邪说。在这一点上，芬利肯定站在你这边，正如他所说的那样，他详述了“(不那么)美好的旧日网络开发”。这并不是要回到后端语言每次更新都需要重新创建完整网页的方法上，就像过去的 PHP 应用程序那样。相反，这种新的作物包括像 [Phoenix](https://www.phoenixframework.org/) 这样的工具，一个编程语言 Elixir 的框架，以及一个名为 [LiveView](https://github.com/dbohdan/liveviews) 的功能，该功能在将 UI 元素发送到浏览器之前在后端呈现它们。芬利还指出了采取类似方法的其他工具，如 [Laravel Livewire](https://laravel-livewire.com/) 和 [StimulusReflex](https://docs.stimulusreflex.com/) 。

虽然这篇文章的标题可能暗示 JavaScript 应该被淘汰，但芬利以更平衡的方式结束，写道“也许我们看到的与其说是钟摆摆动，不如说是一种平衡状态，在这种状态下，根据用户的需求，计算在客户端和服务器上以同等的速度进行。”

这一点是我们最近在前端(或者后端作为前端)开发领域越来越多地看到的。例如，当我们[最近将 htmx](https://thenewstack.io/htmx-html-approach-to-interactivity-in-a-javascript-world/) 视为 JavaScript 单页应用程序(SPAs)的替代方案时，htmx 创建者 Carson Gross 和 Svelte framework 创建者 Rich Harris 都以类似的方式结束了“过渡应用程序”的想法，其中没有一种方法可以完全依赖。

这篇文章的大部分讨论并不一定与提出的主张不一致，而是与没有提到的内容不一致，这篇文章在[登上了黑客新闻](https://news.ycombinator.com/item?id=30269161)的顶端。

WebAssembly 和 htmx 都是被认为从前景中消失的前两种方法，这两种方法似乎都提供了 JavaScript 及其无处不在的前端框架的替代品。但是当我们把这两个作为主要的争论列出来的时候，关于黑客新闻的评论是一个不同语言和方法的洗衣清单，可能就足够了。无论如何， [JavaScript 潜在的世界统治地位](https://thenewstack.io/will-2022-be-a-golden-age-for-full-stack-javascript/)是不确定的。

## 本周的节目中

*   **用 IBM 的开发沙箱测试驱动技术:** IBM 已经[预览了一个开发人员技术沙箱](https://developer.ibm.com/blogs/ibm-previews-developer-technology-sandbox-to-help-developers-explore-new-technologies/)，以帮助开发人员探索新技术，该公司将这一过程描述为通常“有点像在试驾前要求组装一辆汽车。”相比之下，使用 IBM 开发人员技术沙箱[，开发人员可以获得“一个交钥匙解决方案”，即“基于浏览器的无代码/低代码沙箱”，目前提供九种不同的技术，如使用 Watson 的视频洞察或 IBM Research 的异常检测。您不仅可以试用预构建的应用程序，还可以编辑它们并将代码直接导出到您自己的 GitHub 存储库中。](http://developer.ibm.com/sandbox)
*   **Flutter 获得稳定的 Windows 支持:**当 [Flutter 2 去年推出](https://developers.googleblog.com/2021/03/announcing-flutter-2.html)时，这是它可以用来瞄准的平台的重大扩展。当时，谷歌写道，它将允许开发者“使用相同的代码库向五种操作系统运送原生应用:iOS、Android、Windows、macOS 和 Linux 以及针对 Chrome、Firefox、Safari 或 Edge 等浏览器的网络体验。”然而，这个声明有点令人激动，因为对桌面的全面生产支持还没有发布。在 Windows 的情况下，这不再是情况，因为谷歌已经[宣布为 Windows](http://developers.googleblog.com/2022/02/announcing-flutter-for-windows.html) 颤振。他们写道:“今天标志着这一愿景的重大扩展，首次发布了支持 Windows 作为应用目标的产品，使 Windows 开发者能够受益于移动开发者一直享受的相同的生产力和能力。”在这个版本中，Flutter 应用程序将能够“使用 Flutter 框架的每个部分，在 Windows 上，它也可以直接通过 Dart 的 C 互操作层或使用用 C++编写的平台插件与 Win32、COM 和 Windows 运行时 API 对话。”所有这些都落在了 Flutter 2.10 中，还有各种其他功能、性能改进和错误修复，他们说对 macOS 和 Linux 的稳定支持正在进行中。

[https://www.youtube.com/embed/Ppx-QMtpV-g?feature=oembed](https://www.youtube.com/embed/Ppx-QMtpV-g?feature=oembed)

视频

*   **谷歌代码之夏向组织开放:**今年的[谷歌代码之夏](https://g.co/gsoc) (GSoC)正在向前推进，现在[向导师组织申请开放](http://opensource.googleblog.com/2022/02/Google%20Summer%20of%20Code%202022%20is%20open%20for%20mentor%20organization%20applications.html)，这意味着开源项目和组织现在可以申请参加，直到太平洋时间 2 月 21 日上午 10 点。该计划将新的开源贡献者与开源项目配对，实际上去年通过取消参与者必须是学生的要求[扩展了其资格](https://opensource.googleblog.com/2021/11/expanding-google-summer-of-code-in-2022.html)，取而代之的是，它不对所有 18 岁以上的新开源贡献者开放。今年的计划将是第 18 届，项目时间从 175 到 350 小时，为期 12 到 22 周。如果你是一个开源项目的一部分，想要帮助一些新的开发者进入开源领域，GSoC 无疑是一种方法，现在是申请的时候了。对于希望参与其中的开发人员来说，申请期即将开始。查看所有截止日期的[详细时间表](https://developers.google.com/open-source/gsoc/timeline)。

[https://www.youtube.com/embed/L4JNz6zWzLs?feature=oembed](https://www.youtube.com/embed/L4JNz6zWzLs?feature=oembed)

视频

*   **现在是停止使用旧版本 Visual Studio 的时候了:**对于那些仍在使用旧版本 Visual Studio 的人来说，升级的时间很快就要到了，[的一篇博客文章详细介绍了对各种版本支持的结束](https://devblogs.microsoft.com/visualstudio/support-ends-for-older-versions-of-visual-studio-feb2022/)。这一切都是推动停止支持旧软件的一部分，但也是推动开发人员使用微软最新的 IDE， [Visual Studio 2022](https://thenewstack.io/visual-studio-2022-and-net-6-finally-arrive/) ，它于去年年底上市。请务必查看所有日期的帖子，但要知道这些更新不仅适用于旧得多的版本，如 Visual Studio 2012 和 Visual Studio 2017，甚至还适用于更新的版本，如 Visual Studio 2019 版本 16.7。微软提供了这样一个简短的总结:“是时候完成从 Visual Studio 2012 到更高支持版本的迁移了。是时候从 Visual Studio 2019 的预览频道转移到 Visual Studio 2022 预览版了。是时候从 Visual Studio 2019 版本 16.7 迁移到 Visual Studio 2019 版本 16.11 或 Visual Studio 2022 了。”
*   关于 Rust 未来的更多想法:上周，Rust core 开发者 [Niko Matsakis](https://twitter.com/nikomatsakis) 提出了他的[想法](https://smallcultfollowing.com/babysteps//blog/2022/02/09/dare-to-ask-for-more-rust2024/#dare-to-ask-for-more-rust2024)，他希望看到这种语言下一步走向何方。“对我来说，不断浮现在脑海中的主题是敢于要求更多。在过去的几年里，Rust 已经变得更好用了，但是我并不满意。我相信 Rust 有比现在多 22 倍的生产力和易用性的空间，我认为我们可以做到这一点，而不会有意义地牺牲[可靠性](https://rustacean-principles.netlify.app/how_rust_empowers/reliable.html)、[性能](https://rustacean-principles.netlify.app/how_rust_empowers/performant.html)或[多功能性](https://rustacean-principles.netlify.app/how_rust_empowers/versatile.html)，”Matsakis 写道。在博文中，他解释了他希望看到更多关于让 Rust 更容易学习的内容，更多关于让 Rust 异步的内容(Matsakis 是异步工作组的一部分)，以及更多关于 Rust 工具的内容。总的主题是，如果你不明白，他希望 Rust 更多。他写道，“有时候，人们很容易说，Rust 已经足够好了，你不需要一种语言来处理所有的事情’，然后就此打住。”。“对于 Rust 2024，我不希望我们这样做。我觉得 Rust 很牛逼。但我认为铁锈可能更可怕。”请继续阅读他关于铁锈有多可怕的观点。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>