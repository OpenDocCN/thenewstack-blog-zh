# 本周编程:eBPF 来到你身边的窗口

> 原文：<https://thenewstack.io/this-week-in-programming-ebpf-coming-to-a-windows-near-you/>

几年来，新的团队一直在密切关注 eBPF ，称这项技术[是 2020 年](https://thenewstack.io/the-new-stack-top-cloud-native-technology-trends-from-2020/)的顶级趋势之一。如果你以前没有听说过 [eBPF](https://ebpf.io/what-is-ebpf) ，你很可能会听到更多关于它的消息，因为微软本周表示是[将它引入 Windows](https://cloudblogs.microsoft.com/opensource/2021/05/10/making-ebpf-work-on-windows/) 。

扩展的 Berkeley 数据包过滤器(eBPF) [最初用作 Berkeley 软件分发版(BSD)的](http://www.tcpdump.org/papers/bpf-usenix93.pdf) HTTP 数据包过滤器，后来被扩展用于软件定义的网络，为 Linux 内核提供了一种代表用户执行定制操作的方式。虽然 eBPF 最初以提供内核监控而闻名，但它为 Linux 用户提供了一种在内核空间中运行沙盒程序的方式，而无需更改内核源代码或加载模块。

“尽管对 eBPF 的支持最初是在 Linux 内核中实现的，但越来越多的人希望允许 eBPF 用于其他操作系统，并扩展内核之外的用户模式服务和守护程序，”微软在其声明中指出。

这一扩展将从一个新的开源项目[开始，该项目旨在将 eBPF 引入 Windows 10 和 Windows Server 2016。随后，该扩展将把几个现有的开源 eBPF 项目粘在一起，如](https://github.com/Microsoft/ebpf-for-windows) [IOVisor uBPF 项目](https://github.com/iovisor/ubpf)和[previous verifier](https://github.com/vbpf/ebpf-verifier)，使它们能够在 Windows 上工作。使用 [ebpf-for-windows](https://github.com/microsoft/ebpf-for-windows) ，开发人员可以使用现有的 ebpf 工具链从各种语言的源代码中生成 eBPF 字节码，这些字节码“然后可以由任何应用程序使用，或者通过 Windows `netsh`命令行工具手动使用，这两者都使用一个公开了[Libbpf API](https://github.com/libbpf/libbpf)的共享库，尽管这项工作仍在进行中。”

至于新闻是如何被接受的，“普遍乐观”在这种情况下可能不是一个过于宽泛的短语。整个 Twitter 的开发者都为这个声明欢呼，[称之为](https://twitter.com/abnerg/status/1391835860358754305)一个“公平竞争的举动”当 Windows 开发者欢欣鼓舞的时候，[专家、作家、eBPF 话题的共同发言人布兰登·格雷戈](http://www.brendangregg.com/)说，这一举措不仅仅让 Windows 开发者自己受益。

正如 Gregg 所指出的，从这里开始，任何人都不知道 eBPF 下一步会走向何方，但是很有可能在不久的将来你会听到更多关于它的消息。

## 本周的节目中

*   Rust 发布其 2021 版计划:最近没有一周没有一系列与 Rust 相关的新闻，本周也不例外。这一次，我们从 Rust 2021 版的计划开始。Rust 的“版本”是一种添加不向后兼容特性的方式。例如，`async`关键字是在 2018 年之后添加的，即使你将 Rust 更新到更新的版本，它也不会被识别为关键字，除非你也更新到 2018 年或更高版本。至于 Rust 2021 版本会有什么变化，这篇博客文章列出了其中的一些变化:prelude 的增加，默认的 Cargo 功能解析器，数组的 intolerator，闭包中的分离捕获，恐慌宏一致性，保留语法，以及对硬错误的两个特定警告的升级。目前，Rust 2021 版计划在 9 月份推出 Rust 1.56.0，测试版将持续到 10 月 21 日。然而，这篇博文指出，“Rust 是一个由志愿者运营的项目”，人们比功能发布更优先，这意味着一切都是试探性的。进一步的细节将在 7 月份发布，在不久的将来，关于流程和被拒绝的提案的更多细节也将发布在 [Inside Rust](https://blog.rust-lang.org/inside-rust/) 博客上。

*   **AWS 推出新的 Rust SDK:** 接下来在 Rust 领域，[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)向 alpha [发布了新的 Rust AWS SDK](https://aws.amazon.com/blogs/developer/a-new-aws-sdk-for-rust-alpha-launch/)，该公司表示，这将为熟悉 Rust 的开发人员提供他们习惯的语言结构，同时还提供一个与其他语言的其他 AWS SDK 行为类似的 SDK。新的 Rust AWS SDK 目前将与七个 AWS 服务合作，更多服务正在开发中:亚马逊 DynamoDB、亚马逊 API Gateway、亚马逊 Kinesis、AWS 密钥管理服务、亚马逊 Polly、AWS Secrets Manager 和亚马逊 Quantum Ledger 数据库。如果你想知道 SDK 将何去何从，请前往[路线图](https://github.com/awslabs/aws-sdk-rust/projects/1)，它概述了预期的新特性，例如 AWS 服务的新功能和对额外凭证提供者的支持，并查看[入门指南](https://github.com/awslabs/aws-sdk-rust)。
*   **Rust for Windows v0.9 发布:**本周，微软[发布了 Rust for Windows v0.9](https://blogs.windows.com/windowsdeveloper/2021/05/06/announcing-rust-for-windows-v0-9/) ，其中包括完全消费支持，这意味着现在你可以使用 Rust 语言投影调用任何 Windows APIs(过去、现在和未来)。上个月，我们看到[微软如何对](https://thenewstack.io/this-week-in-programming-microsoft-gets-rusty/) [Rust for Windows](https://docs.microsoft.com/en-us/windows/dev-environment/rust/rust-for-windows) 变得越来越生疏，现在该公司表示，自去年 [Rust/WinRT 公开预览公告](https://blogs.windows.com/windowsdeveloper/2020/04/30/rust-winrt-public-preview/)以来，它已经“取得了巨大的进步”。最新版本增加了对 Win32 和 COM APIs 的支持，统一了可通过 windows crate 使用的 Windows APIs，同时为 Rust for Windows repo 添加了几个示例。crates.io 上的 windows crate 的发布，现在在 MIT 或 Apache 下获得了双重许可，它使用生成的绑定而不是内部手写的绑定，并建立在 Linux 上。关于更新的完整列表，一如既往，请查看变更日志，并前往[最新文档](https://docs.microsoft.com/windows/dev-environment/rust/)开始。

*   **GitHub 为 SSH Git 操作启用安全密钥:**安全密钥——被认为是 21 世纪的“加密狗”—[现在支持 GitHub 上的 SSH Git 操作](https://github.blog/2021-05-10-security-keys-supported-ssh-git-operations/),这为用户提供了一种方便的方式来执行双因素身份验证，而不需要智能手机。安全钥匙通过 USB、NFC 或蓝牙连接，比智能手机短信更安全，因为钥匙上的数据受到保护，不会被外部访问和修改，也没有办法像短信那样重定向[。GitHub 解释说:“只要你保留对安全密钥的访问权，你就可以确信它不会被其他任何人用于任何其他目的。”有了这个新功能，你可以生成一个 SSH 密钥，然后](https://www.vice.com/en/article/y3g8wb/hacker-got-my-texts-16-dollars-sakari-netnumber)[将密钥添加到你的账户](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)，就像任何其他 SSH 密钥一样，即使你机器上的私有密钥文件被盗，如果没有物理安全密钥，它[也是无用的。“如果你是唯一能接触到你的安全钥匙的人，那么让它一直插着电源是安全的，”他们进一步解释道。关于这将如何具体影响您的工作流程的更多细节，请阅读博客帖子，但要知道这是一个更大的计划的一部分，GitHub 表示在不久的将来 Git 操作](https://cvsweb.openbsd.org/src/usr.bin/ssh/PROTOCOL.u2f?rev=HEAD)将不再支持[密码，这是它已经为其 API](https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/) 所做的事情。

*   **视频在 GitHub 上直播:**GitHub 领域的另一个趣闻是，该网站已经在 GitHub 上提供了[视频上传](https://github.blog/2021-05-13-video-uploads-available-github/)。该功能是去年在 beta 版中推出的，现在已经普遍可用，允许用户上传. mp4 和。问题、请求、讨论等中的 mov 文件。他们可以展示 bug，提供拉请求的上下文，讨论一个特性是如何形成的，或者做任何在视频中比书面形式更容易做的事情。除了可以在所有 GitHub 上使用，这些功能也可以在 Android 和 iOS GitHub 应用程序上使用，所以开始录制吧。
*   **VS Code Python 增加了 Pylance，调试自动重载:**最后，本月的 [Python 在 Visual Studio 中的代码发布](https://devblogs.microsoft.com/python/python-in-visual-studio-code-may-2021-release/)出来了，它有几个大的新特性。首先， [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance) 现在是默认的语言服务器，并且从这个版本开始作为可选的扩展与核心 Python 扩展捆绑在一起，不过如果你愿意，你可以选择退出。他们写道，Pylance“为 Visual Studio 代码提供了我们认为最具性能和用户友好的 Python 编辑体验。”但是如果您不同意，您可以卸载 Pylance 扩展并使用您选择的语言服务器。除了 Pylance 之外，Python 扩展现在还具有 Python 脚本的实时重新加载功能，这意味着“您的更改将在调试器已经开始执行并遇到断点之后应用，而无需重启调试器。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>