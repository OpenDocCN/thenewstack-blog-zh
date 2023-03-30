# 受够了 Rust vs. Go 的零和游戏

> 原文：<https://thenewstack.io/enough-with-the-zero-sum-game-of-rust-vs-go/>

上周，在我们来自网络的编程相关新闻的每周综述中，我们简要地提到了亚马逊网络服务公司(AWS)发表的一篇文章，这篇文章,[吹捧 Rust 编程语言的可持续性。由 Rust 基金会主席谢恩·米勒](https://aws.amazon.com/blogs/opensource/sustainability-with-rust/)和 AWS 首席工程师兼异步 Rust 运行时 [Tokio](https://tokio.rs/) 的创造者[卡尔·勒什](https://www.linkedin.com/in/carllerche/)撰写的这篇文章认为，Rust 在效率方面击败了许多其他语言，AWS 称它“投资于 Rust 的可持续性，我们认为这种语言应该用于构建可持续和安全的解决方案。”

虽然这篇文章肯定不是第一篇提出 Rust 可以通过提供一种更有效的编程语言来帮助解决环境问题的文章，但它是对 Go 的引用，一种经常被认为是 Rust 的竞争对手的语言，这在本周引起了一点争议，形式是 Go 首席工程师 Russ Cox 的 Twitter 帖子。

在帖子中，Cox 认为文章的两个主要数据来源，几年前的一项研究和 2020 年初的一篇关于 Discord 决定从 go 转向 Rust 的博客文章，提供了关于 Rust 在性能和效率方面的优势的不准确观点。

考克斯写道，这项研究“有明显的问题”，因为它不仅是五年前的，而且是指在现在过时的硬件上运行的旧版本围棋。此外，考克斯指出，这项研究使用[计算机语言基准游戏](https://en.wikipedia.org/wiki/The_Computer_Language_Benchmarks_Game)作为“可比较程序的来源，如果你知道那个网站，这是完全不正确的。”

“所有这些都是为了说明‘真正有趣的研究’并不真正有趣。考克斯写道:“事实上，我们显然应该抱着适度的怀疑态度来看待这件事。

关于第二点，即 [Discord 博客文章](https://discord.com/blog/why-discord-is-switching-from-go-to-rust)，考克斯再次指出，所涉及的数据点指的是现在旧版本的围棋，这使得这一论点有所不同，以及他所谓的“令人难以置信的误导”的总结。虽然他说 Discord 博客帖子本身提供了“Go 服务器和 Rust 服务器的比较”，但他认为 AWS 的帖子是一种歪曲。

考克斯论点的真正关键在于他的最后两条推文，这两条推文有点呼吁和平。

“AWS 的帖子确实对 Rust 提出了一些诚实、公平的观点，这使得他们包括这些关于 Go 的误导性陈述更加令人遗憾。他们不需要那样做。考克斯写道:“铁锈足以独立存在。“就我个人而言，我不会去读那些假装围棋和 Rust 是某种零和游戏的博客文章，而是更愿意关注围棋和 Rust 相辅相成、可以很好地合作的方式。”

Cox 以一篇发表在 New Stack 上的文章的链接结束，这篇文章认为 [Rust 和 Go 在一起](https://thenewstack.io/rust-vs-go-why-theyre-better-together/)更好，而不是作为竞争对手。这篇由 Rust 和 Go 团队成员共同撰写的博客文章认为，“虽然其他人可能认为 [Rust](https://www.rust-lang.org/) 和 [Go](https://go.dev/) 是有竞争力的编程语言，但 Rust 和 Go 团队都不这么认为。恰恰相反，我们的团队非常尊重其他人正在做的事情，并将这些语言视为对整个行业软件开发现代化的共同愿景的补充。”

## 本周的节目中

*   **GitHub 开放漏洞咨询数据库:**虽然近年来开源安全的理念变得越来越流行，但贡献个人知识来解决漏洞的能力仍然有限。然而，GitHub 现在[向社区贡献开放了它的咨询数据库](https://github.blog/2022-02-22-github-advisory-database-now-open-to-community-contributions/)。咨询数据库，一个由 CVEs 和 GitHub 发起的影响开源软件的安全咨询数据库，已经发布到[的一个新的公共存储库](https://github.com/github/advisory-database)，旁边还有一个用户界面供用户投稿。该数据库是在知识共享许可下授权的，由“全职策展人的专门团队”维护，他们将审查对现有 CVE 的改进建议。GitHub 正在使用[开源漏洞(OSV)](https://ossf.github.io/osv-schema/) 格式的数据库，“本着进一步提高互操作性的精神”，该数据库将作为 npm、NuGet 和 GitHub 自己的 Dependabot 警报中的漏洞的基础。为了做出贡献，用户可以[导航到他们想要添加信息的建议](https://github.com/advisories)，并遵循“针对此漏洞的改进建议”工作流，或者直接提交拉请求。
*   **针对大型回购的预建代码空间进入测试版:**对于拥有大型存储库的组织来说，启动 GitHub 的代码空间可能是一项耗时的活动。作为回应，该公司一直在运行预构建这些代码空间的能力的私人预览。虽然他们说反馈在很大程度上是积极的，但他们也收到了“大量关于预构建的配置和管理的有价值的反馈”本周，该公司[将私人预览版扩展为公开测试版](https://github.blog/2022-02-23-codespaces-largest-repositories-faster/)，同时根据反馈做出了一些改变。预构建代码空间加快了大型复杂存储库的启动时间，为公司提供了“现成的”模板，其中已经下载、安装和应用了您的源代码、编辑器扩展、项目依赖项、命令和配置，因此您不必在每次创建新的代码空间时都等待这些任务完成。”除了进入公开测试版，GitHub 还增加了几项更新，如支持将由 Codespaces 服务管理的 GitHub Actions 工作流，以及基于 GitHub Actions 虚拟机构建的预构建配置。预构建适用于所有拥有 GitHub 企业云和团队计划的组织，并且[预构建文档](https://aka.ms/ghcs-prebuild)将帮助您开始。

*   **将 Linux eBPF 移植到 Windows？**自从微软说[将 eBPF 带到 Windows](https://thenewstack.io/this-week-in-programming-ebpf-coming-to-a-windows-near-you/) 已经过去将近一年了。最近，他们提供了一个关于他们进展的[更新](https://cloudblogs.microsoft.com/opensource/2021/11/29/progress-on-making-ebpf-work-on-windows/)，现在他们说他们想“在他们所在的地方会见开发者”，所以他们提供了一个指南[让基于 Linux 的 eBPF 程序与用于 Windows 的 eBPF 一起运行](https://cloudblogs.microsoft.com/opensource/2022/02/22/getting-linux-based-ebpf-programs-to-run-with-ebpf-for-windows/)。由于我们已经密切关注 eBPF 有一段时间了，我们认为这是值得指出的。在帖子中，微软提供了他们“使用一个基本上为 Linux 编写的应用程序进行的学习和观察”——[Cilium 第 4 层负载平衡器](https://cilium.io/blog/2021/05/20/cilium-110#standalonelb)——作为“非常相关的真实世界用例。”除此之外，他们还对 Windows 上的 [eBPF 的下一步提供了一些见解，写道他们“将继续以应用程序为中心，重点关注钩子和助手”，并且“最大化 eBPF 源代码兼容性将继续是一个重要的目标”，主题是如何接受当前正在积极讨论的签名 eBPF 程序。](https://github.com/microsoft/ebpf-for-windows)
*   **Rust 公开了编译器的雄心，Rust-Analyzer 的增加:**Rust 编译器团队有一些关于 2022 年的[雄心，他们已经决定与整个社区分享，包括今年的](https://blog.rust-lang.org/inside-rust/2022/02/22/compiler-team-ambitions-2022.html)[总体主题](https://blog.rust-lang.org/inside-rust/2022/02/22/compiler-team-ambitions-2022.html#overall-themes)，他们有资源推动的[具体计划](https://blog.rust-lang.org/inside-rust/2022/02/22/compiler-team-ambitions-2022.html#concrete-initiatives)，以及如果他们有更多的帮助，他们将解决的更大的[雄心](https://blog.rust-lang.org/inside-rust/2022/02/22/compiler-team-ambitions-2022.html#aspirations)(提示提示)。所以，对于你们这些乡下人来说，读一读这篇博文，看看是否有你能帮忙的地方。正如他们指出的那样，“ [Rust 不是一家公司](https://blog.m-ou.se/rust-is-not-a-company/)”“我们为项目设定的目标必须与我们当前和未来贡献者的目标保持一致；否则，他们就无法完成任务。”除此之外，rust 团队还宣布 [rust-analyzer 已经加入 Rust 组织](https://blog.rust-lang.org/2022/02/21/rust-analyzer-joins-rust-org.html)。rust-analyzer 项目是 rust 语言服务器协议(LSP)的一个新实现，其加入 Rust 组织“解除了技术工作的障碍，使 rust-analyzer 在不久的将来成为 Rust 官方推荐的语言服务器。”Rust-analyzer 目前可用于 [VS 代码](https://marketplace.visualstudio.com/items?itemName=matklad.rust-analyzer)、 [NeoVim](https://sharksforarms.dev/posts/neovim-rust/) 、 [Vim](https://github.com/fannheyward/coc-rust-analyzer) 、 [Emacs](https://robert.kra.hn/posts/2021-02-07_rust-with-emacs/) 和 [more](https://rust-analyzer.github.io/manual.html) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>