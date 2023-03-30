# 本周编程:Windows 向 Android 开发者开放

> 原文：<https://thenewstack.io/this-week-in-programming-windows-opens-up-to-android-developers/>

就好像地狱一次又一次地结冰。如果几年前有人告诉你，Windows 不仅会开放运行 Linux，而且 T2 也会发布自己的 OpenJDK 开源版本，你会告诉他们他们疯了。但是，事实上，这两件事都已经有了结果，现在微软真的降低了地狱的温度，宣布[下一个版本的 Windows 将运行 Android 应用](https://blogs.windows.com/windowsexperience/2021/06/24/introducing-windows-11/)。

真的，微软 Windows 最近的故事是一个曾经垄断的实体[向其他技术](https://en.wikipedia.org/wiki/United_States_v._Microsoft_Corp.)敞开怀抱的故事(例如[将 Rust 纳入麾下](https://thenewstack.io/this-week-in-programming-microsoft-gets-rusty/))和传统的基于 Linux 的工具 [eBPF](https://thenewstack.io/this-week-in-programming-ebpf-coming-to-a-windows-near-you/) 和 [Envoy proxy](https://blog.envoyproxy.io/general-availability-of-envoy-on-windows-267e4544994a) ，有人知道吗？)，现在应用程序完全是为另一个操作系统开发的——又一次！当然，有些人对这一宣布并不感到惊讶，他们说这是继 Windows Subsystem for Linux 之后的下一步。

“我们也很高兴地宣布，我们将首次把 Android 应用程序引入 Windows，”微软在其介绍性博客帖子中写道。“从今年晚些时候开始，人们将能够在微软商店发现 Android 应用程序，并通过亚马逊应用商店下载它们。”

新的微软商店将 Android 应用程序添加到 Windows 中，该公司表示，它正试图进一步开放“为创作者和开发者释放更大的经济机会”现在，在我们走得太远之前，新商店是通过与亚马逊(不是谷歌)的合作，通过亚马逊的目录将 Android 应用程序带到 windows。

微软杰出的工程师米格尔·德·伊卡萨说，在开发者方面，没有太大的变化，他似乎总是在这类公告的内部轨道上。

德·伊卡萨[将 Android 应用程序添加到 Windows 中与苹果将 iOS 应用程序带到自己的桌面上进行比较，指出“就 IDE 而言，Windows 只是 Android 的另一个目标，它在虚拟机下运行。”](https://twitter.com/migueldeicaza/status/1408089914219143175)

## 本周的节目中

*   **GitLab 14 旨在秒杀“DIY devo PS”:**[git lab](https://about.gitlab.com/?utm_content=inline-mention)已经[推出了 GitLab 14.0](https://about.gitlab.com/releases/2021/06/22/gitlab-14-0-released/) ，称其为“过去一年的高潮”如果你读过关于最新版本的任何东西，你会看到该公司正在稳步地鼓吹他们如何试图[通过将所有这些都纳入他们的一个 DevOps 平台来消除“DIY DevOps 工具链”](https://about.gitlab.com/blog/2021/06/22/gitlab-14-modern-devops/)。“GitLab 14 是一个完整的 DevOps 平台，其 DNA 中嵌入了安全性，其单一数据存储实现了可见性和洞察力，以及无缝的体验和可扩展的系统，”该公司在其最新版本的介绍中写道。在这方面，它还增加了一些功能。一些亮点包括 Epic Boards，它允许用户在拖放界面而不是列表中使用 Epic，直接内置于 GitLab 的 Terraform 模块注册表，简化的顶部导航和重新设计的侧栏，以及在 Visual Studio 代码中执行合并请求审查的能力。还有一个新的 WYSIWYG Markdown 编辑器，所以你可以编辑你的维基和容器扫描，现在默认使用 [Trivy](https://www.aquasec.com/news/trivy-vulnerability-scanner-aqua-security-adopted-by-leading-cloud-native-platforms/) 引擎。
*   去年底，围绕 Docker Hub 引入费率限制引发了一场[的争论，许多公司争相提供自己的替代方案，](https://thenewstack.io/docker-hub-limits-what-they-are-and-how-to-route-around-them/)[也包括 GitHub](https://thenewstack.io/this-week-in-programming-github-steps-in-where-dockerhub-left-off/) 。本周，GitHub 已经表示 [GitHub Packages 容器注册表](https://github.com/features/packages)现已[普遍可用](https://github.blog/2021-06-21-github-packages-container-registry-generally-available/)，它现在引入了一些[附加功能](https://github.blog/changelog/label/containers/)，包括公共容器的匿名访问、组织级所有权、细粒度权限、容器特定的登录页面、不同的可见性设置等等。从测试版的迁移还可以看到 GitHub Docker 注册中心整合到容器注册中心，这意味着之前将 Docker 容器发布到 docker.pkg.github.com 的用户将在未来几周内看到他们的容器自动迁移到容器注册中心，尽管现有的链接将继续发挥作用。目前，这一切都将是免费的，但这将会改变“在未来几个月内，随着足够的通知，当这种变化将会发生。”

*   **AWS 引入 CloudFormation 公共注册表:**当我们谈到注册表的话题时， [Amazon Web Services](https://aws.amazon.com/?utm_content=inline-mention) 也在本周[为 AWS CloudFormation](https://aws.amazon.com/blogs/aws/introducing-a-public-registry-for-aws-cloudformation/) 引入了一个公共注册表，它表示将提供“一个由 AWS、APN 合作伙伴、第三方和开发人员社区发布的扩展(资源类型或模块)的可搜索集合。”CloudFormation 和[AWS Cloud Development Kit](https://aws.amazon.com/cdk/)(CDK)已经提供了 [AWS](https://aws.amazon.com/) 资源的可扩展和一致的供应，现在用户将拥有从 [AWS 合作伙伴网络(APN)](https://aws.amazon.com/partners/) 成员、第三方供应商和开源技术供应资源的相同一致性。公共注册中心(加入了 2019 年推出的私有注册中心功能)与十几个合作伙伴一起推出，如 MongoDB、Sysdig、Aqua Security 和 Snyk，以及超过 35 个扩展。
*   **Docker 预览开发环境:**在上个月的 DockerCon 上宣布，Docker 开发环境的[技术预览版现已作为](https://www.docker.com/blog/tech-preview-docker-dev-environments/) [Docker 桌面 3.5](https://www.docker.com/products/docker-desktop) 的一部分提供。有趣的是，在 Docker Dev Environments 中，Docker 仍然致力于解决同样的“它在我的机器上工作”的问题，但这一次是关于团队如何使用 Git 在项目上合作。开发环境允许开发人员创建“可重复和可再现的开发环境”，然后存储在他们选择的源代码管理工具中，允许他们“通过 Docker Hub 一键共享他们正在进行的工作代码和依赖关系。”从那里，开发人员可以从一个环境切换到另一个环境，将所有代码装入一个容器，该容器“隔离开发人员机器上的工具、文件和运行的服务，允许它们的多个版本并存。”
*   **GitHub Issues 获得新的测试版特性:**最后，本周，GitHub [推出了新的 GitHub Issues](https://github.blog/2021-06-23-introducing-new-github-issues/) ，它带来了一系列测试版的新特性。这些新功能包括“像电子表格一样构建的项目表、自定义字段、键盘驱动的命令面板、改进的任务列表和问题表单。”GitHub 说，要想看到这些新功能，你必须[加入测试版](https://github.com/features/issues#issues-cta)，个人和组织账户都可以使用。要了解更多信息，请查看 GitHub 问题页面或常见问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>