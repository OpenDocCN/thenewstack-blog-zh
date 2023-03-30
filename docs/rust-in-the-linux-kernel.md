# Linux 内核中的铁锈

> 原文：<https://thenewstack.io/rust-in-the-linux-kernel/>

不久以前，Linux 内核将支持另一种主要语言的想法是可笑的。Linux 是 C 的典型代表。当然，也有人努力将其他语言引入内核，特别是 C++。他们失败了。很糟糕。正如 Linux 的创造者 Linus Torvalds 曾经说过的，“C++是一种可怕的语言。“那么，为什么[托瓦尔兹现在欢迎铁锈进入内核](https://www.zdnet.com/article/linus-torvalds-rust-will-go-into-linux-6-1/)？听着，我的朋友，我会告诉你。

[Rust](https://www.rust-lang.org/) 始于 [Mozilla 基金会](https://foundation.mozilla.org/en/)项目。这种当时新的临时构建的语言的目的是将高级语言的表达语法和灵活性与低级语言的良好控制和性能结合起来。特别是，它旨在提高性能、并行性和内存安全性。

正是性能和内存安全的结合引起了 Linux 开发人员的注意。毫无疑问，C 能让程序员写出非常快的代码，但毫无疑问，C 也让他们很容易犯内存错误。

在 C 出现几十年后，C 程序的内存错误似乎是所有编码安全错误中最常见的。2019 年，微软承认，其 70%的常见漏洞和暴露(CVE)安全问题是由开发人员在其 C 和 C++代码中犯[内存损坏错误引起的。](https://msrc-blog.microsoft.com/2019/07/16/a-proactive-approach-to-more-secure-code/)

尽管我嘲笑微软的安全错误，但这不仅仅是该公司的问题。是所有使用 c 的人，正如 Alex Gaynor 和 Geoffrey Thomas 在 2019 Linux 安全峰会上所说，三分之二的 Linux 内核漏洞来自内存安全问题。哪里都差不多。无论哪里出现了内存问题，你都有可能找到 C 或 C++。

对于愿意超越 K&R C 的 Linux 内核开发人员来说，Rust 可能就是答案。的确，你可以尝试用 C 语言编写内存安全的程序，比如像 [SEI CERT C](https://wiki.sei.cmu.edu/confluence/display/c/SEI+CERT+C+Coding+Standard) 这样的语言变体，或者使用更安全的指南，比如 [C++核心指南](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)。但是，在一天结束时，在生产代码中仍然有大量的 C 内存错误。

将 Rust 和 Linux 结合在一起的第一步是 Taesoo Kim 的 2013 年 Linux 内核模块，可惜来得太早了。许多公司都在观察 Rust 的发展，并得出结论:它是系统编程的未来。

[亚马逊](https://aws.amazon.com/?utm_content=inline-mention)，谷歌，微软都在 21 世纪 10 年代末和 21 世纪 20 年代初得出了这个结论。到 2018 年，[亚马逊网络服务(AWS)已经将 Rust 用于鞭炮](https://aws.amazon.com/blogs/opensource/sustainability-with-rust/?tag=zd-buy-button-20&ascsubtag=1ddc6af3e945494ebd3b89e022b5e7ac%7Caccf3de4-4a83-4c81-8514-635e90015433%7Cdtp-oo)，这是 [AWS Lambda](https://aws.amazon.com/lambda/) 及其其他无服务器产品背后的开源虚拟化。到 2020 年， [AWS 推出了基于 Linux 的容器操作系统 Bottlerocket](https://www.zdnet.com/article/aws-introduces-bottlerocket-a-rust-language-oriented-linux-for-containers/) 。

与此同时，谷歌正致力于将 Rust 引入移动 Linux 发行版 Android。正如谷歌工程师在 2021 年所说，改进 Android 的代码“是每个 Android 版本的安全性、稳定性和质量的重中之重。”尽管如此，C 和 C++中的内存安全缺陷仍然是最难解决的。

尽管谷歌投入了“大量的精力和资源来检测、修复和缓解这类漏洞”，…内存安全漏洞仍然是稳定性问题的主要原因，并且始终占 Android 高严重性安全漏洞的大约 70%。:因此，由于“内存安全语言是防止内存错误的最具成本效益的方法”，我们很高兴地宣布，Android 开源项目(AOSP)现在支持 Rust 编程语言来开发操作系统本身。"

与此同时，通常是谷歌员工的 Linux 内核开发人员开始探索是否可以将 Rust 引入 Linux 本身。Linux 内核开发人员 Miguel Ojeda 领导了这些工作。他创建了 [Rust for Linux 项目](https://github.com/Rust-for-Linux)以便在 2019 年将树外 Rust 模块引入 Linux。

但真正开始是在 2020 年。

## Rust for Linux

首先，2021 年 4 月，Ojeda 在 [Linux 内核邮件列表(LKML)](https://lkml.org/) 上推出了关于将 Rust 带入 Linux 的[征求意见(RFC)。随后在 2020 年 7 月，谷歌软件工程师 Nick Desaulniers 在谷歌工作，致力于用 Clang 和 LLVM 编译 Linux 内核，建议为 2020 年 Linux 管道工会议(LPC)举办一场“树内生锈”会议。这导致了 2020 年 8 月的](https://lore.kernel.org/lkml/20210414184604.23473-1-ojeda@kernel.org/)[“树内锈病壁垒”](https://lpc.events/event/7/contributions/804/)会谈。这反过来又把 Linux 中的 Rust 的想法推到了前台。

Ojeda 从互联网安全研究小组(ISRG)和谷歌那里获得了资金支持，这也有所帮助。ISRG 在这方面投资是因为它的主要目标是为关键的互联网操作系统和程序(如 Linux、Apache 和 OpenSSL)促进内存安全编程。

然后，在 2021 年 9 月 20 日，Ojeda 提交了 Rust for Linux 项目的第一个 pull 请求。这增加了[初始 Rust 支持](https://github.com/Rust-for-Linux/linux/pull/4)，包括 Kbuild 集成、初始内置模块支持，以及 Alex Gaynor 和 Geoffrey Thomas 的[安全 Rust 抽象](https://www.youtube.com/watch?v=RyY01fRyGhM)的内核创建。

Sylvestre Ledru，Debian Linux 开发者，于 2021 年 9 月使用 LLVM 编译器基础设施和工具基础设施将 Rust 版本的 Coreutils 移植到 Linux 上。Coreutils 是 GNU shell 核心实用程序。有了这些，Ledru 启动了 Linux，并且能够运行最流行的 Debian 软件包。

到 2021 年 3 月，这个想法已经有了足够的动力，当我与托瓦尔兹和 Linux 稳定内核维护者格雷格·克罗亚-哈特曼谈论 Linux 中的 Rust 时，托瓦尔兹说，他“绝不”推动“Rust，[但]考虑到承诺的优势和避免一些安全隐患，我对此持开放态度，但我也知道有时承诺不会成功。

Kroah-Hartman 也持谨慎乐观的态度，“这将取决于内核结构和用 C 编写的生命周期规则之间的交互如何映射到 Rust 结构和生命周期规则，以便 Rust 中的驱动程序能够正确使用它们。想要把这一切连接起来的开发者需要做大量细致的工作，我祝他们好运。”

其他人则更加乐观。谷歌 Android 团队的 Wedson Almeida Filho 表示,“我们认为 [Rust 现在已经准备好加入 C 语言，作为实现内核](https://security.googleblog.com/2021/04/rust-in-linux-kernel.html)的实用语言。它可以帮助我们减少特权代码中潜在的错误和安全漏洞，同时很好地处理核心内核并保留其性能特征。”

Linux 中的 Rust 团队知道这将是一项繁重的工作。正如 Ojeda 在 2022 年 6 月所说，“内核是一个庞大的项目，有很多利益相关者。从一开始，很明显[向内核添加第二种‘主要’语言将会面临技术和管理两方面的挑战。](https://www.memorysafety.org/blog/memory-safety-in-linux-kernel/)

他们证明了自己能够应对挑战。2022 年 9 月，托沃兹告诉我，“除非发生什么奇怪的事情，否则它会变成 6.1。”Linux 内核 6.1，以及其中的 Rust，将会在 2023 年初出现，如果运气好的话，将会在 2022 年末出现。

托沃兹说，现在，Rust 将“只拥有核心基础设施(也就是说，还没有真正的用例)。”不过，不要搞错了。这是向前迈出的一大步。

Ojeda 说，你将在 Linux 下一代内核中看到的第一个 Rust 工作将是在 LKML 中“[Rust subsystem 和 write drivers 和其他模块的抽象](https://lkml.org/lkml/2022/9/27/672)”。

最终，Rust 将成为 Linux 内核中完全集成的第二语言。不要以为，这意味着所有 3000 多万行内核代码都将在 Rust 中重写。这在 2050 年不会发生。不过，之后就不要赌对了。Rust 使得任何用它编写的程序都比 C 语言的同类程序更安全。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>