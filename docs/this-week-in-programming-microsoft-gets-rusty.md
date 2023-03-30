# 本周编程:微软变得生疏

> 原文：<https://thenewstack.io/this-week-in-programming-microsoft-gets-rusty/>

“微软的生锈已经开始了，”[在推特上写道](https://twitter.com/migueldeicaza/status/1383833546276573185)微软杰出的工程师[米盖尔·德·伊卡萨](https://github.com/migueldeicaza)。

德伊卡萨指的是微软新开设的关于[用 Rust 迈出第一步](https://docs.microsoft.com/en-us/learn/paths/rust-first-steps/)的课程，Rust 爱好者的许多推特成员认为这是一个信号，表明该公司正在进一步增加对他们选择的螃蟹主题语言的青睐。当然，这不是我们第一次听说微软希望 Rust 处理 70%的微软漏洞，据说这些漏洞来自于在其软件中使用内存不安全的 C++编程语言。几年前，微软启动了维罗纳项目(T8 Project Verona )( T9 ),这是一种研究型编程语言，它在 Rust 的所有权领域(T10 ownership )( T11)中占有一席之地，据说它的灵感来自 Rust(T13)以及其他领域。

然而，最近，微软[宣布了 Rust for Windows](https://docs.microsoft.com/en-us/windows/dev-environment/rust/rust-for-windows) 的预览版，它“让你可以通过 windows crate (crate 是 Rust 对二进制或库的术语，和/或构建到其中的源代码)直接无缝地使用任何 Windows API(过去、现在和未来)。”有了 Rust for Windows，开发者现在不仅可以在 Windows 上使用 Rust，还可以使用 Rust 为 Windows 编写应用。

Rust for Windows 是由微软 Windows 开发者平台团队的首席软件工程师[肯尼·克尔](https://github.com/kennykerr)牵头的项目，[于 2019 年 11 月开始努力将 Rust 引入 Windows](https://kennykerr.ca/2019/11/05/rust/) 。当时，创建了 [C++/WinRT 语言项目](https://github.com/microsoft/cppwinrt)的克尔写道，他对它的工作方式“很大程度上感到满意”，并且“Windows 运行时一直不仅仅是一种语言，我们已经开始着手[几个不同的项目](https://kennykerr.ca/2019/10/09/xlang-cppwinrt-repos/)来增加对各种语言的支持。然而，所有这些努力都无法让我远离 c++……直到 Rust 出现在我的雷达上。”

长话短说，Rust 被证明是“一种有趣的语言”,“在许多方面与 C++非常相似，在编译和运行时模型、类型系统和确定性终结方面都很好”,并且“有可能解决 C++与 WinRT 之间一些最棘手的问题。"

快进到今年 1 月，Kerr [说](https://kennykerr.ca/2021/01/21/rust-for-windows/)他“很兴奋终于可以谈论我们已经努力了一段时间的宏伟计划，即 Windows API 的统一。不再有 Win32 在这里，WinRT 在那里，COM 这个，UWP 那个。别说了。 [Rust for Windows](https://github.com/microsoft/windows-rs) 让您可以通过 Windows 机箱直接无缝地使用任何 Windows API。”

根据项目描述，Windows crate“允许您使用直接从描述 API 的元数据动态生成的代码调用任何 Windows API 的过去、现在和未来，并直接进入 Rust 包，在那里您可以调用它们，就好像它们只是另一个 Rust 模块一样”,这与 Rust 学习课程的引入一起，正是所有 Rust 爱好者如此兴奋的原因。

[https://www.youtube.com/embed/LajquCjHXK4?feature=oembed](https://www.youtube.com/embed/LajquCjHXK4?feature=oembed)

视频

## 本周的节目中

*   **Linux 图形用户界面来到 WSL:** 对于使用 Windows 的人们来说，这似乎是一个值得庆祝的一周，因为微软也发布了对 Linux(WSL)[Windows 子系统的 Linux 图形用户界面应用支持](https://docs.microsoft.com/en-us/windows/wsl/about)的[初始预览版。WSL 让 Windows 用户能够在启动到 Windows 时运行 Linux 环境，这意味着不需要双重启动，但直到现在它只提供命令行工具和应用程序。现在，这个](https://devblogs.microsoft.com/commandline/the-initial-preview-of-gui-app-support-is-now-available-for-the-windows-subsystem-for-linux-2/)[备受期待的](https://github.com/microsoft/WSL/issues/938)和[开源特性](https://github.com/microsoft/wslg)意味着 WSL 用户可以运行 GUI 应用程序，比如 [VS Code Remote](https://code.visualstudio.com/docs/remote/remote-overview) ，为他们提供“直接在 Windows 机器上的成熟 Linux IDE”，以及其他 IDE，比如 gedit、基于 JetBrains 的编辑器、gvim 等等。在 WSL 中运行 GUI Linux 应用程序的能力也意味着基于 Windows 的开发人员可以在 Linux 环境中测试应用程序，而无需更换机器、引导到 Linux 或运行虚拟机，微软指出还有一个额外的功能:您可以使用 WSL 的 GPU 访问来运行具有 3D 加速的 Linux 应用程序。关于这一切是如何工作的更多信息，请前往[博客](https://devblogs.microsoft.com/commandline/the-initial-preview-of-gui-app-support-is-now-available-for-the-windows-subsystem-for-linux-2/)阅读更多信息(包括漂亮的图表)或查看[自述文件以获得安装说明](https://github.com/microsoft/wslg)。此外，请查看下面的演示:

[https://www.youtube.com/embed/f8_nvJzuaSU?feature=oembed](https://www.youtube.com/embed/f8_nvJzuaSU?feature=oembed)

视频

*   **Visual Studio 2022 升级至 64 位，获得可访问性改造:**最后，微软的开发者们，[公司发布了 Visual Studio 2022](https://devblogs.microsoft.com/visualstudio/visual-studio-2022/) 的公开预览，据称将于今年晚些时候发布。他们写道，Visual Studio 2022 将“更快、更易接近、更轻量级”，增加了远程协作的功能，更重要的是，它将是一个 64 位应用程序，“不再局限于主 devenv.exe 进程中的 4gb 内存”虽然该公司指出，这并不意味着 Visual Studio“不会改变你构建的应用程序的类型或特点”， [Visual Studio 杂志报道](https://visualstudiomagazine.com/articles/2021/04/20/vs-2020-feedback.aspx)用户的反应是一个大杂烩，大多数评论“主要是'花了这么长时间'的性质”，而其他人则评论说需要更新 Visual Studio 扩展，担心扩展作者永远不会这样做。预览版宣布的其他功能将包括更新的图标和辅助功能，完全支持。NET 6 及其用于 web、客户端和移动应用程序的统一框架，通过新的生产力特性、C++20 工具和智能感知支持 C++工作负载，以及对 CMake、Linux 和 WSL 的支持。虽然有太多的其他功能可以在这里完全列出，但值得注意的是，Visual Studio 2022 将“包括对 Git 和 GitHub 的强大新支持”，以及更好地与 Azure 合作的功能。

*   谷歌文档季参与者中的 NumPy，Perl，Julia】现在是谷歌一年一度的[文档季](https://developers.google.com/season-of-docs)计划的时候了，该计划将开源组织与技术作家配对，以创建更好的文档(这是我们都可以支持的，对吧？)并且该项目已经[公布了 2021 年](https://opensource.googleblog.com/2021/04/season-of-docs-announces-participating-organizations-2021.html)的参与机构。[参与组织列表](https://developers.google.com/season-of-docs/docs/participants/)详细列出了今年参与的 30 个组织，其中包括一些我们的读者可能非常熟悉的项目，例如 LitmusChaos、NumPy、Perl、Julia 和 R 等等。该项目将持续到今年 11 月，鼓励感兴趣的技术作家尽快申请，因为组织必须在 5 月中旬之前雇佣作家。如需了解更多详情，请查看[技术作者付款流程指南](https://developers.google.com/season-of-docs/docs/tech-writer-payments)、[时间表](https://developers.google.com/season-of-docs/docs/timeline)，当然还有[常见问题解答](https://developers.google.com/season-of-docs/docs/faq)。
*   **Node.js 16 带来了苹果芯片支持:**node . js 的最新版本 [Node.js 16](https://nodejs.medium.com/node-js-16-available-now-7f5099a97e70?source=rss-96cd9a1fb56------2) 现已推出，并带来了额外的稳定 API，对 V8 JavaScript engine v9.0 的更新，以及对预构建苹果芯片二进制文件的 M1 芯片组的支持。Node.js 16 成为 Node.js 的“当前”版本，计划于今年 10 月进入长期支持(LTS)，Node.js 12 将在 LTS 保留到 2022 年 4 月，Node.js 14 直到 2023 年 4 月，Node.js 将于本月停止使用。Node.js 16 包括 Node.js 15 中引入的许多功能，如标准 [Web Crypto API](https://www.w3.org/TR/WebCryptoAPI/) 的实验性实现，但该版本的特别新之处是为 Apple Silicon 提供了预构建的二进制文件，为 Intel (darwin-x64)和 ARM (darwin-arm64)架构提供了单独的 tarballs。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>