# 本周编程:Kubernetes 从第一天开始？

> 原文：<https://thenewstack.io/this-week-in-programming-kubernetes-from-day-one/>

当你听到“Kubernetes”这个词时，你的第一反应是什么？

如果你对围绕我们最喜欢的云原生容器编排系统的一般对话有所了解，那么“复杂性”这个词很可能是首先想到的词之一。因此，当你构建一个新的应用程序时，你的第一直觉可能不包括为 Kubernetes 构建的想法——只是保持简单，并基于客户的需求构建一个 MVP，对吗？——但是 StackOverflow 公司的人本周发表了一篇博客文章，为[辩护为什么你应该从第一天开始就建立 Kubernetes。](https://stackoverflow.blog/2021/07/21/why-you-should-build-on-kubernetes-from-day-one/)

“如果你是一家企业的开发人员，你会希望确保满足企业的期望和需求。他们写道:“规模化经营充其量只是明天的问题。“如果你现在正在开发一个新的应用程序，也许值得仔细研究一下如何让它成为云原生的，并从一开始就使用 Kubernetes。建立 Kubernetes 的努力比你想象的要少。当然，这比以后为了支持容器化而重构你的应用要少得多。”

现在，如果你曾经尝试过自己建立和运行 Kubernetes，并直接进入陡峭的学习曲线，你现在可能会想到“不”。当然，他们的解决方案很简单——只需使用他们的托管 Kubernetes 服务，将这部分内容交给您最喜欢的大型云提供商，瞧！在那里，StackOverflow 的人们只是看到了面向未来的好处，成为“(某种程度上)云不可知的”能力，以及使用 Kubernetes 快速启动新环境的能力，从而实现 GitOps 类型的工作流。

对于持怀疑态度的人来说，最近几周的另外两篇博文也浮现在脑海中。首先，[巧妙地](https://ably.com/)写道“[不，我们不使用 Kubernetes](https://ably.com/blog/no-we-dont-use-kubernetes) ，而是主张结合 AWS 服务来处理所有的扩展和复杂性。

“要迁移到 Kubernetes，一个组织需要一个完整的工程团队来保持 Kubernetes 集群的运行，这是假设一个托管的 Kubernetes 服务，并且他们可以依靠额外的基础设施工程师来维护组织实际产品或服务之上的其他支持服务，”他们写道。

虽然这是 StackOverflow 推理的一部分——“建立 Kubernetes 的努力比你想象的要少。当然，这比以后为了支持容器化而重构你的应用要少得多。”——Ably 认为，“似乎引入如此昂贵的组件只会转移我们的一些问题，而不是真正解决它们。”

与此同时，本周的另一篇博客文章认为, [Kubernetes 是我们这一代的 Multics](http://www.oilshell.org/blog/2021/07/blog-backlog-2.html#kubernetes-is-our-generations-multics) ,再次以这种复杂性的想法为中心。本质上，这里的论点是 Kubernetes 是“一个严肃的、值得尊敬的、但过于复杂的系统，最终将被更简单的系统所取代:分布式操作系统的 Unix。”那么，回到 Unix 吧！

当然，这里提出的任何论点都不会成为你围绕 Kubernetes 做出决定的成败因素，但是你怎么想呢？你会从头开始为 Kubernetes 构建下一个应用程序吗？或者，你认为果汁不值得如此复杂的压榨吗？

## 本周的节目中

*   **CI/CD 滥用仍在继续:**本周，Atlassian 的 Bitbucket 表示，由于加密采矿滥用，它需要对 Bitbucket 管道进行一些[更改。这种趋势似乎没有留下任何蛛丝马迹，因为我们已经写了关于](https://bitbucket.org/blog/changes-to-bitbucket-pipelines-due-to-crypto-mining-abuse) [Docker 关闭对 Docker Hub Autobuilds](https://thenewstack.io/this-week-in-programming-crypto-miners-overrun-docker-hubs-autobuild/) 的免费访问，以及 [TravisCI 出于同样的原因限制对 builds](https://thenewstack.io/this-week-in-programming-travis-ci-hopes-to-clear-up-confusion-again/) 的访问。现在，轮到 Bitbucket 指责最近“不良行为者利用免费时间挖掘加密货币的滥用行为大幅增加”。然而，在 Bitbucket 的情况下，这些变化并不意味着访问的结束，而是要求新的 Bitbucket 云用户使用[两步验证](https://support.atlassian.com/bitbucket-cloud/docs/enable-two-step-verification/)。现有的付费团队将被豁免，可以继续像以前一样。该公司表示，它已经开始实施配额制，并“减少自由层用户的现有宽限期”，以及自动检测和终止滥用账户及其管道。
*   Rust 2021 进入公开测试:对于那些想站在 Rust 前沿的人来说，现在是时候了，因为语言团队已经宣布 [Rust 2021 公开测试期](https://blog.rust-lang.org/2021/07/21/Rust-2021-public-testing.html)开始了。Rust 团队表示，他们正在“鼓励冒险的用户测试将他们的板条箱迁移到 Rust 2021”，并为那些希望迁移到公认不稳定版本的 Rust 的人提供了一套简短的说明(或根据需要提供[更详细的说明](https://doc.rust-lang.org/nightly/edition-guide/editions/transitioning-an-existing-project-to-a-new-edition.html))。他们写道:“该版本的所有计划功能现在都可以在夜间版本中使用，以及将您的代码从 Rust 2018 迁移到 Rust 2021 的迁移，”他们将潜在测试人员引向版本指南的[夜间版本，了解 Rust 2021 中的所有新功能。如果您决定进行这一跨越，他们还建议您将您的箱子迁移到代码的临时副本中，而不是您的主分支中，以防万一。](https://doc.rust-lang.org/nightly/edition-guide/rust-2021/index.html)

*   **Go 谈到 GitHub 的供应链安全:** GitHub 在 2019 年向供应链安全迈出了第一大步，当时[收购了语义代码分析引擎 Semmle](https://github.blog/2019-09-18-github-welcomes-semmle/) 。从那以后，该公司[增加了各种代码扫描工具](https://github.blog/2020-10-07-announcing-third-party-code-scanning-tools-infrastructure-as-code-and-container-scanning/)，现在它说它是[将其供应链安全功能带到 Go 社区](https://github.blog/2021-07-22-github-supply-chain-security-features-go-community/)。例如，Go 模块维护者现在可以使用安全咨询来协调漏洞的披露，这意味着他们可以更容易地与研究人员合作，在公开宣布漏洞之前私下讨论并修复漏洞，也可以更容易地为他们的咨询申请[常见漏洞和暴露](https://cve.mitre.org/) (CVE)标识号，并将其发布到[国家漏洞数据库](https://nvd.nist.gov/) (NVD)。Go 开发者还将获得依赖图，以帮助发现供应链中的漏洞，以及 Dependabot 警报，当在您已经使用的 Go 模块中发现新的漏洞时，它会通知您。关于如何开始的全部细节，请阅读[博客文章](https://github.blog/2021-07-22-github-supply-chain-security-features-go-community/)。哦，当我们在这里的时候， [/r/dataisbeautiful](https://www.reddit.com/r/dataisbeautiful/) 的人制作了[一个视频，展示了随着时间的推移 GitHub 上最流行的语言](https://www.reddit.com/r/dataisbeautiful/comments/om66b5/oc_most_popular_programming_languages_according/)，它现在已经排名第四，仅次于 JavaScript、Python 和 Java。
*   **Visual Studio 2022 for Mac:**Visual Studio for Mac 的[私人预览版](https://devblogs.microsoft.com/visualstudio/join-the-visual-studio-2022-for-mac-private-preview/)已经开放，带来了的第一个版本。NET IDE 具有“刷新的、完全本机的 macOS 用户界面”如果你犹豫要不要提交，要知道它可以和早期版本同时安装，所以现在[可以随意注册](https://aka.ms/vs/mac/2022-signup)。Visual Studio 团队写道，他们的“Visual Studio 2022 for Mac 的目标是打造一个现代的。NET IDE tailored for the Mac ”,因此侧重于提高 IDE 性能和减少崩溃，利用 macOS 的更多内置辅助功能，并更新体验，以在 Mac 和 Windows 之间感觉更熟悉。听起来，最大的变化来自新的原生 MacOS 用户界面，他们说这“影响了 Mac 版 Visual Studio 的每个部分”。此举将修复 100 多个与性能、可靠性和产品质量相关的问题，并改善 IDE 与 macOS 内置辅助技术的配合。视觉上的变化包括页脚状态栏，文档/工具窗口的新标签模型，以及刷新的浅色和深色主题。然而，变化并不仅限于外观，用户可以期待看到菜单和术语的一些变化，以使从 Windows 过来的用户更容易使用。最后，最近添加到 Visual Studio 中的新 Git 体验也将加入 Mac 版本，从 Git 更改工具窗口开始。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>