# 本周编程:。NET 6 预览版在疫情推迟后加快统一进程

> 原文：<https://thenewstack.io/this-week-in-programming-net-6-preview-picks-up-unification-efforts-after-pandemic-delays/>

对你们中的一些人来说。NET 开发人员，他们还没有特别关注，您可能会对本周的新闻感到有点头晕。不过，没有必要重复，因为这都是真的——微软已经发布了。NET 6 ，就在[上映四个月后。NET 5](https://devblogs.microsoft.com/dotnet/announcing-net-5-0/) ，该公司免费、跨平台、开源开发者平台的当前生产阅读版本。

其实这并不令人惊讶。NET 6 一直计划在 2021 年发布，预览版已经在预计的 2021 年 11 月发布之前[可供下载](https://dotnet.microsoft.com/download/dotnet/6.0)。事实上，微软已经创建了一个面向公众的路线图。NET 显示了不同的主题，清楚地表明。NET 6 在这里是为了学习和运行中引入的许多主题。净 5。与。在经历了一点与大流行相关的口吃之后，微软正在收拾残局，当时该公司未能兑现其在年的一些统一承诺。净 5。

[统一](https://devblogs.microsoft.com/dotnet/introducing-net-5/)始于。NET 5 在 2019 年，试图使它将有“只有一个。forward”面向各种平台，包括 Windows、Linux、macOS、iOS、Android、tvOS、watchOS 和 WebAssembly 等等。该团队表示，在这个版本中，他们正在将属于 Xamarin 的 Android、iOS 和 macOS 功能集成到中。NET 6，并扩展了 Blazor web 框架来创建“一种新的混合客户端应用——将 web 和本地 UI 结合在一起”微软描述了这种“统一”努力的可能性:

我们的统一努力为所有人提供了一些东西。NET 开发人员。如果你是一名桌面应用开发者，你将有机会接触到新用户。如果你是一个移动应用开发者，你将从使用主线中受益。NET 工具和 API，同时瞄准 iOS 和 Android 平台。如果您是 web 或云开发人员，那么向其公开服务会更容易。NET 移动应用程序，并与它们共享代码。”

的另一个亮点。NET 6 是对[的长期支持](https://github.com/dotnet/core/blob/master/release-policies.md)，使这个版本成为用于生产的版本之一，并且增加了“显著扩展的”操作系统支持，为 x64 和苹果硅“M1”增加了 Android、iOS、Mac 和 Mac Catalyst，以及 Windows Arm64。

当然是存在。NET，新功能的列表是广泛的，并且在[的一篇冗长的博客文章](https://devblogs.microsoft.com/dotnet/announcing-net-6-preview-1/)中有充分的细节，但是如果你想要比我们在这里提供的多一点，而是一个仍然简洁的摘要，你可能会前往 [Neowin](https://www.neowin.net/news/the-first-preview-of-net-6-is-now-live-heres-what-you-need-to-know) 进行简单的概述，或者前往 [The Register](https://www.theregister.com/2021/02/18/microsoft_previews_net_6_native/) ，它称预览“仍然一团糟”——正如最初的预览所预期的那样。

## 本周的节目中

*   **VSCode 有助于发现“坏”扩展:**关于微软相关的新闻，流行的 Visual Studio 代码编辑器背后的团队本周发布了一篇博客文章，详细介绍了其最近发布的 [Visual Studio 代码扩展等分实用程序](https://code.visualstudio.com/blogs/2021/02/16/extension-bisect)，它有助于找出可能会妨碍您体验的“坏”扩展。注意到“Visual Studio 代码的真正力量是它的扩展”，并且“用户安装 50 个或更多扩展并不罕见”，该团队说他们希望使故障排除更容易，这就是扩展平分实用程序的目的。最初受[git sector](https://git-scm.com/docs/git-bisect)命令的启发，该命令有助于找出存储库中的哪个提交引入了问题，该实用程序基本上遵循一种排序方法，其中它将扩展分成两半并禁用它们，然后询问用户问题是否已被修复。通过这样做，它可以更快地隔离问题背后的扩展，而不是要求您逐个检查每个扩展。

*   **GitHub Enterprise Server 3.0 带来了“有史以来最大的变化”:**今年早些时候， [GitHub Enterprise Server 3.0 现已全面上市](https://github.blog/2021-02-16-github-enterprise-server-3-0-is-now-generally-available/)，该公司称之为“有史以来最大的变化”，增加了 GitHub 操作、GitHub 包和秘密扫描工具。这一版本将上个月[候选版本](https://github.blog/2021-01-15-github-enterprise-server-3-0-is-here/)中的功能推向了全面可用，也是 GitHub 新[候选版本计划](https://github.blog/2020-12-03-improving-the-ghes-release-process-release-candidates/)的首次完成，该公司去年年底讨论了该计划。随着 GitHub Enterprise Server 3.0 的发布，也有一些更新的[文档](https://docs.github.com/en/enterprise-server@3.0)可用，所有新功能都在[发行说明](https://docs.github.com/en/enterprise-server@3.0/admin/release-notes#3.0.0)中有详细说明。
*   **Go 1.16 使模块默认:**最新版本的 Go 编程语言 Go 1.16 已经在[发布](https://blog.golang.org/go1.16)，带来了许多新特性。首先，根据 2020 年 Go 开发者调查[，Go 1.16](https://blog.golang.org/survey2020) [默认要求使用 Go 模块](https://golang.org/doc/go1.16#modules)，该团队表示这是有意义的，因为 96%的 Go 开发者已经打开了它们。围绕 Go 模块的讨论[已经有一段时间了，第一次](https://blog.golang.org/modules2019)[初步讨论](https://golang.org/doc/go1.11#modules)发生在 2018 年，Go 1.1 发布了，现在，两年后，对功能的[“创新方法”已经默认开启。这个最新版本还引入了一个新的](https://thenewstack.io/whats-coming-to-golang-in-2019-modules-generics-better-error-handling/)[嵌入包](https://golang.org/doc/go1.16#library-embed)，它提供了对编译时嵌入的文件的访问，并使其更容易将支持数据文件捆绑到您的 Go 程序中，以及对 macOS ARM64 支持(又名 Apple silicon)的[支持。最后，除了其他的改进和错误修复之外，该语言还宣称“构建速度提高了 25%，内存使用量减少了 15%”。](https://golang.org/doc/go1.16#darwin)

*   **Docker 桌面 M1 预览版增加 Kubernetes:** 苹果 M1 最新的 [Docker 桌面预览版已经发布](https://www.docker.com/blog/new-docker-desktop-preview-for-apple-m1-released/)，并提供[下载](https://docs.docker.com/docker-for-mac/apple-m1/)，其中“最令人兴奋的变化”就是增加了 Kubernetes。以前，预览版是“在私有分支的开发人员的笔记本电脑上构建的”，但现在 Docker 对预览版拥有更大的所有权，代码完全集成到其主要开发分支中。该公司表示，它还更新了 CI 代码，并将“能够更经常地发布新的预览，并对我们的变化没有破坏任何东西更有信心。”至于 Kubernetes，嗯，它现在工作了，这是一个巨大的进步。Docker 表示，它还使`host.docker.internal`和`vm.docker.internal` DNS 条目现在可以解析，删除了硬编码的 IP 地址，修复了 osxfs 文件共享，进行了配置更改以提高磁盘性能，并修复了 Docker 菜单中的重启选项。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>