# 本周编程:少于随机

> 原文：<https://thenewstack.io/this-week-in-programming-less-than-random/>

本周，一篇关于 I-Programmer 的文章告诉我们, [Mersenne Twister 被认为是有害的](https://www.i-programmer.info/news/112-theory/13172-mersenne-twister-considered-harmful.html),引用了由 [Sebastiano Vigna](http://vigna.di.unimi.it/) 发表的关于这个主题的学术论文。

这里是这种情况的要点:本质上，[梅森图](https://en.wikipedia.org/wiki/Mersenne_Twister)是一个非常普遍的伪随机数生成器(PRNG)，是“C 编译器、Python 语言、Maple 数学计算系统和许多其他环境中的默认生成器”，Vigna 认为(甚至在论文的标题中)，“[是我们放弃梅森图](https://arxiv.org/pdf/1910.06437.pdf)的时候了。”

这并不是 Mersenne Twister 第一次受到攻击(它在 PHP 中的实现实际上有几年的错别字)，但 Vigna 写道，“过去 20 年积累的知识表明，Mersenne Twister 实际上有严重的缺陷，永远不应该被用作通用的伪随机数发生器。这些结果中有许多是民间传说或者分散在非常专业的文献中。本文为非专业人士调查了这些结果，提供了新的、简单的、可理解的示例，旨在为最终用户或语言实现者提供指导，以便他们能够做出是否使用 Mersenne Twister 的明智决定。

那么，如果 PRNG 也存在这样的问题，为什么我们还在使用它呢？Vigna 提出“Mersenne Twister 的问题在日常应用中不会立即被发现，大多数真正对 PRNG 质量感兴趣的用户将做出明智的选择，而不是依赖于他们正在使用的任何编程环境的股票 PRNG。”

Mersenne Twister 是一种特殊类型的 PRNG，称为 F2 线性生成器，I-Programmer 写道，它的缺陷很容易避免，“如果您将生成的位均匀分布在 0 到 1 的区间中，然后对不同的分布应用非线性变换，缺陷就会消失”，因此仍然很受欢迎并在使用中。

类似地，Vigna 得出结论，“特别是，线性发生器永远不应该用作通用发生器，除非它们的输出通过与其他非线性发生器组合或通过应用非线性映射进行适当加扰。目前，梅森龙卷风作为基本 PRNG 在许多环境中无处不在，这是一个历史文物，我们作为一个社区，应该照顾好它。”

## 本周的节目中

*   再见，Perl 6，你好，樱庭落！没错，漫长的战斗终于结束了，随着 [Perl 的创造者拉里·沃尔](https://en.wikipedia.org/wiki/Larry_Wall)最终同意[批准将 Perl 6 重命名为 raku](http://blogs.perl.org/users/ovid/2019/10/larry-has-approved-renaming-perl-6-to-raku.html) ，正式将该语言从其前身中分离出来，并有望让两者在和平与和谐中前进。[时间](/this-week-in-programming-privacy-issues-around-googles-golang-proxy-calls/)和[再次](/week-programming-renaming-perl-save-terminal-unpopularity/)，这些年来，我们一直在关注关于 Perl 5 和 Perl 6 的争论以及这两种语言之间存在的巨大鸿沟——许多人认为它们毫无关联——最后我们可以继续前进了。在评论中，沃尔说他“赞成这一改变，因为它反映了一种古老的智慧。”引用《圣经》中的一段话,这段话本质上可以归结为是时候重新开始并继续前进了，于是决定将 Perl 6 重命名为樱庭落，Perl 博客作者 Ovid 写道,“这将有望平息 Perl 社区中人们在重命名问题上的许多深刻分歧。”。尽管对更名的支持势不可挡，但仍有少数人大声反对。但经历了这一切，有一点是清楚的:每个人都是好意。”

*   **在 Go 1.13 中陷入错误:**如果 [Go 1.13](https://blog.golang.org/go1.13) 中引入的[错误包装功能](https://golang.org/doc/go1.13#error_wrapping)让你感到困惑，Go 团队已经写了一篇博文，详细介绍了[在 Go 1.13](https://blog.golang.org/go1.13-errors) 中处理错误的所有细节。基本上，他们写道，“一个错误包含另一个错误的模式在 Go 代码中非常普遍，在[广泛讨论](https://golang.org/issue/29934)之后，Go 1.13 以“错误包中的三个新函数和 fmt.Errorf 的一个新格式化动词”的形式添加了对它的明确支持。”
*   **Python 转向 3 . 8 . 0:**Python 社区称 [Python 3.8.0 现已推出](https://pythoninsider.blogspot.com/2019/10/python-380-is-now-available.html)，这是最新的特性版本，“包含许多新特性和优化”要获得完整的信息，请务必查看展示了[Python 3.8](https://docs.python.org/3.8/whatsnew/3.8.html)新特性的完整文章，但这里有一些花絮。note 的主要特性似乎是“walrus 操作符”或“:=”，它将值作为更大表达式的一部分分配给变量，并节省了一些代码空间。一位 Reddit 用户[写道](https://www.reddit.com/r/programming/comments/dhwtvt/python_38_released/f3ru90r/)“Python 社区的一个非常直言不讳的部分在赋值表达式上抛弃了 Guido 或者，这个 walrus 操作符。另一位[说](https://www.reddit.com/r/programming/comments/dhwtvt/python_38_released/f3tcb0g/)他们最多期望海象操作员“偶尔有用”。除此之外，Python 3.8 还有其他几个特性，Packt 在检查特性和反应方面做得非常出色。

*   **Inside Rust&Rust up 1.2:**Rust 团队[在几周前推出了](https://blog.rust-lang.org/inside-rust/2019/09/25/Welcome.html)Inside Rust 博客，该博客以一系列团队会议和一些深入的博客文章开始，如[基础架构团队会议](https://blog.rust-lang.org/inside-rust/2019/10/15/infra-team-meeting.html)、[编译器团队分类会议](https://blog.rust-lang.org/inside-rust/2019/10/15/compiler-team-meeting.html)和 [Lang 团队分类会议](https://blog.rust-lang.org/inside-rust/2019/10/11/Lang-Team-Meeting.html)，以及一篇着眼于[改进 async-await 的“未来不发送”诊断的博客文章](https://blog.rust-lang.org/inside-rust/2019/10/11/AsyncAwait-Not-Send-Error-Improvements.html)。因此，如果你想真正深入 Rust 开发的内部，这看起来是一本好书。除了博客，Rustup 工作组一直很忙，本周[发布了 Rustup 1.20.0](https://blog.rust-lang.org/2019/10/15/Rustup-1.20.0.html) 。Rustup 是一个 [Rust](https://www.rust-lang.org/) 安装程序，它的最新版本支持概要文件，能够在每晚获得您需要的所有组件的最新版本，并对 rustup doc 命令进行了改进。基本上，概要文件支持将通过引入概要文件来加速安装，概要文件是组件的组合。目前，配置文件有最小、缺省和完整三种，大概就是您所期望的——最小配置文件包含您所需要的，缺省配置文件包含所有以前缺省安装的组件，完整配置文件包含 rustup 提供的所有组件，包括 miri 和 IDE 集成工具(rls 和 rust-analysis)。

*   **AWS 背锈在“推广积分”？**更多关于 Rust 的消息， [AWS 已经开始赞助 Rust 项目](https://aws.amazon.com/blogs/opensource/aws-sponsorship-of-the-rust-project/)。你可能会问，为什么？他们引用了 [Rust 的价值观](https://www.rust-lang.org/#language-values)，包括性能、可靠性和生产力。此外，所有其他酷孩子，如[谷歌](https://fuchsia.googlesource.com/fuchsia/)、[微软](https://msrc-blog.microsoft.com/2019/07/22/why-rust-for-safe-systems-programming/)和 [Mozilla](https://hacks.mozilla.org/2019/01/fearless-security-memory-safety/) 都在使用 Rust，Lambda、EC2 和 S3 都选择“在对性能敏感的组件中使用 Rust”别忘了，他们说，他们“甚至开源了[鞭炮微型视频](https://firecracker-microvm.github.io/)项目！”这种赞助意味着什么？在你过于兴奋之前，Register [写道](https://www.theregister.co.uk/2019/10/15/aws_sponsoring_rust_microsoft_azure/)它基本上提供“推广积分”作为亚马逊一般开源赞助计划的一部分。
*   微软为 WebDevs 发布新的调试工具:本周为 web 开发者发布了两个版本。首先， [Firefox 宣布了一个新的 WebSocket inspector](https://hacks.mozilla.org/2019/10/firefoxs-new-websocket-inspector/) ，它将在 Firefox 71 中发布。对于那些跃跃欲试的人来说，它也已经准备好在[火狐开发者版](https://www.mozilla.org/en-US/firefox/developer/)中使用了。该工具是谷歌代码之夏(GSoC)学生 Heng Yeow Tan(T7)的产品，它集成了一些库来帮助解决“连接故障、代理、认证和授权、可伸缩性等问题。”据说即将发布的版本承诺提供二进制有效载荷查看器，以及指示关闭的连接和导出 WebSocket 帧的能力。与此同时，微软也公布了从 Visual Studio 调试微软 Edge 中的 JavaScript 的能力[。他们注意到下一版本的 Microsoft Edge 将采用 Chromium 开源项目，并且从 Visual Studio 2019 版本 16.2 开始，他们将 Java 调试支持扩展到了 Microsoft Edge 的预览版。关于如何工作的完整冗长的细节，例如，点击进入](https://devblogs.microsoft.com/visualstudio/debug-javascript-in-microsoft-edge-from-visual-studio/)[文章](https://devblogs.microsoft.com/visualstudio/debug-javascript-in-microsoft-edge-from-visual-studio/)。

照片由来自 Pixabay 的 Gordon Johnson 拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>