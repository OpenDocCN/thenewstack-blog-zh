# 本周编程:Linux 内核管理员考虑对 Rust 的树内支持

> 原文：<https://thenewstack.io/this-week-in-programming-linux-kernel-keepers-mull-in-tree-support-for-rust/>

虽然这不是第一次出现 Linux 内核生锈的话题，但本周互联网上充斥着推特和 T2 的传言，说这一时刻终于到来了。这一切都是从[Linux 内核邮件列表](https://lore.kernel.org/lkml/CAKwvOdmuYc8rW_H4aQG4DsJzho=F+djd68fp7mzmBp3-wY--Uw@mail.gmail.com/T/#u)上的一个帖子开始的，软件开发人员 [Nick Desaulniers](http://nickdesaulniers.github.io/about/) ，他致力于用 [Clang](https://clang.llvm.org/) (和 [LLVM](https://llvm.org/) )编译 [Linux 内核](https://www.kernel.org/)，提出了在即将到来的 [Linux 管道工会议](https://www.linuxplumbersconf.org/event/7/page/47-attend)上举办一场关于支持 Rust“in tree”的会议的想法。虽然这个想法以前已经提出过，但是根据 [Hackaday](https://hackaday.com/2020/07/15/will-2020-be-the-year-of-rust-in-the-linux-kernel/) 上的一篇文章，每个人都在问[2020 年是否会是 Linux 内核生锈的一年](https://hackaday.com/2020/07/15/will-2020-be-the-year-of-rust-in-the-linux-kernel/)，事实是 Linux 的创造者 Linus Torvalds 似乎对这个想法表示支持。

“有趣的部分是[莱纳斯·托沃兹]对在 LKML 线程上的 T20 回应，这让每个人都希望得到一个类似于 T22 他的 c++ one 失望的衷心签名铁锈咆哮，”他们写道相反，他主要担心的是，在构建系统中引入这种支持会隐藏可能的错误，因此如果 Rust 编译器存在，应该自动启用这种支持——本质上意味着他似乎另有打算。"

在 [The Register](https://www.theregister.com/2020/07/13/rust_code_in_linux_kernel/) 上的一篇文章更深入地探讨了这个话题，指出微软最近[引用](https://msrc-blog.microsoft.com/2019/07/22/why-rust-for-safe-systems-programming/) Rust 作为“目前可用的 C 和 C++的最佳替代品”——这个话题[我们在](/microsoft-rust-is-the-industrys-best-chance-at-safe-systems-programming/)之前肯定已经谈到过——内存安全是 Rust 相对于其他的主要好处。

为了进一步支持这个话题，本周又有一篇博客文章越过了 feeds，这篇文章惊呼 Rust 作为一种服务器语言好得惊人。虽然它并没有以任何方式直接涉及 Rust 和 Linux 的主题，但作者的结论对 Rust 作为一种系统语言的整体思想进行了一些思考:

我会推荐某人用 Rust 编写他们的下一个服务器吗？不，生态系统还没有完全形成，大多数服务器仍然会受到 I/O 的限制，所以速度的提高可能不会有太大影响。但是，一旦生态系统成熟，老实说，我认为 Rust 是编写服务器的好语言。你得到了速度和安全，老实说，你付出的代价与你通常对抗(或至少想到)借贷方的代价不同。

## 本周的节目中

*   **如果帮助设计 Rust 的想法吸引了你…** 那么你可能想在本周再次前往 Rust 博客，阅读关于该语言的 [lang 团队](https://www.rust-lang.org/governance/teams/lang)的[成员资格](https://blog.rust-lang.org/inside-rust/2020/07/09/lang-team-path-to-membership.html)的所有信息，该团队负责设计和实现新的语言功能。这篇文章列出了对潜在团队成员的期望——例如领导项目组或参与 RFC 讨论——并强调了“成员之路”,包括参与单个项目组和“以富有成效的方式”解决技术纠纷等步骤虽然这是这篇博文的一个焦点，但 Rust 团队写道，这一切都是为了解决一个不同的问题。他们写道:“简而言之，我们的想法是通过引入一个名为重大变更提案(MCP)的“预先步骤”，试图更早地‘拦截’RFC 流程。”“我们的想法是，如果你有一个想要追求的想法，你可以提出一个 MCP 问题，并描述高层次的细节。如果这个想法引起了团队中某个人的注意，我们将创建一个项目小组来实现这个想法，该成员将担任 lang 团队的联络员，而您(或其他人)将担任小组组长。”本质上，这里的努力是招募更多的人来参与这个过程，使语言开发更加顺利——他们需要你的帮助。
*   **Android&kot Lin for the Noobs:**kot Lin 摆脱其弱势地位并成为 Android 开发的官方支持语言已经有一段时间了，现在 Google 已经为没有编程经验的潜在开发者推出了一些课程[来学习 Android 和 kot Lin](https://feedproxy.google.com/~r/blogspot/hsDu/~3/pFFLyW6Oz5c/learn-android-and-kotlin-with-no-experience.html)。继 2016 年发布 [Android 基础课程](https://android-developers.googleblog.com/2016/06/introducing-android-basics-nanodegree.html)之后，谷歌现在在 Kotlin 中推出 [Android 基础课程，“一门新的在线课程，供没有编程经验的人学习如何构建 Android 应用。”该课程提供了如何使用 Android Studio 构建应用程序的分步说明，以及如何在 Android 设备(或虚拟设备)上运行应用程序，并通过实践来学习基础知识。该课程完全免费，第一单元立即可用，随后还会有更多单元。](https://g.co/android/basics)

[https://www.youtube.com/embed/oSim9fBFy-E?feature=oembed](https://www.youtube.com/embed/oSim9fBFy-E?feature=oembed)

视频

*   **Visual Studio Code 的新 JavaScript 调试器:** ADTMag 已经[注意到](https://adtmag.com/articles/2020/07/15/vs-code-javascript-debugger.aspx)VS Code 正在获得[一个新的 JavaScript 调试器](https://github.com/microsoft/vscode-js-debug#whats-new)，根据项目描述，它“调试 Node.js 和 web 应用程序(在 Edge 和 Chrome 中)，最终将成为 VS 代码的内置调试器”。微软[上个月宣布了](https://code.visualstudio.com/updates/v1_47)新的调试器，它允许用户在终端中调试 Node.js 进程，调试 npm 脚本，允许插入断点和顶级 await，并将包括对微软 Edge 和 WEbView2 的支持，以及一大堆其他功能，包括可访问性改进、Windows ARM 构建等等。
*   **PHP 在 Windows 上的支持正式结束:** InfoWorld 给我们带来了[PHP 在 Windows 上的终结的故事](https://www.infoworld.com/article/3566379/the-end-of-the-line-for-php-on-windows.html#tk.rss_applicationdevelopment)，引用了一条消息说[微软将不会为 Windows](https://externals.io/message/110907) 生产 PHP 8 的官方版本。据报道，微软已经在 windows.php.net 为 IIS 和其他 Windows 网络服务器提供了 Windows 版本的二进制文件和源代码，但这种情况即将结束。尽管如此，他们写道，“PHP for Windows 不会消失。很明显，对于继续构建和发布 PHP 7 以外的 Windows 版本的 PHP 来说，已经有了足够的需求。”相反，只是“[微软不会直接为构建贡献资源和服务器](https://www.reddit.com/r/PHP/comments/ho9dgq/microsoft_not_going_to_officially_support_php_8/fxgk1sc/?utm_source=share&utm_medium=web2x)，但更有可能的是，它会向 PHP 项目捐赠许可证和服务器。”

特征图片由[文斯·维拉斯](https://unsplash.com/@vinceveras?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/s/photos/tree-rust?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特(Twitter)或脸书(T2)与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[反馈@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>