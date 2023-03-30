# 本周编程:加密矿工在 Docker Hub 的自动建筑中泛滥

> 原文：<https://thenewstack.io/this-week-in-programming-crypto-miners-overrun-docker-hubs-autobuild/>

本周，Docker 宣布了对 Docker Hub Autobuilds 的一些[更改——最令人感兴趣的是 Autobuilds 将不再对免费用户开放——互联网上的许多人发出了“这就是为什么我们不能拥有美好事物”的集体抱怨](https://www.docker.com/blog/changes-to-docker-hub-autobuilds/)

因此，如果你碰巧正在寻找另一个理由，立即畏缩并抛弃任何向你吹嘘加密货币好处的人，Docker 摆脱其在 Docker Hub 上的自动构建功能可以添加到你的军火库中。

“正如你们许多人所知，对于提供免费云计算的公司来说，这是一个困难时期，”[的 Docker 首席产品经理 Shaun Mulligan](https://www.linkedin.com/in/shaun-mulligan-1739a067/) 在该公司的[博客文章](https://www.docker.com/blog/changes-to-docker-hub-autobuilds/)中写道，引用了一篇探索[密码挖掘团伙如何在免费云计算平台](https://therecord.media/crypto-mining-gangs-are-running-amok-on-free-cloud-computing-platforms/)上胡作非为的文章。Mulligan 继续解释道，Docker“看到了坏演员数量的大幅增长”，指出这不仅让他们花钱，还降低了他们付费客户的表现。

因此，在免费使用他们的 autobuild 功能七年后，即使你们所有的非付费 Docker 用户都可以免费为你们的容器化项目建立持续集成，末日即将来临。就像，真的，真的很近，就像下周——6 月 18 日。

虽然 Docker 表示，他们已经试图通过删除约 10，000 个帐户来纠正这个问题，但他们表示，矿工们在第二周又成群结队地回来了，所以他们“做出了艰难的选择，删除了 Autobuilds。”

肯定有一些用户认为这将成为一种模式的一部分，跟随[该公司去年对 Docker Hub 的限速](https://thenewstack.io/docker-hub-limits-what-they-are-and-how-to-route-around-them/)，还有其他人，如以太坊分散平台的团队领导，他们[称之为犯规](https://twitter.com/peter_szilagyi/status/1402252539773521927)，尽管这可能是那些 crypto 说服者所期望的。

就其本身而言，Docker 试图再次避开批评，向用户提供订阅折扣，并向其开源项目的成员提供继续免费使用 autobuilds 的能力，尽管我怀疑批评仍然与 Docker Hub 的限速相同:开源维护者已经有足够多的事情要做，更不用说维护和证明他们的资格以获得另一个成员资格了。

与此同时，对于那些向 Docker 付费的人来说——上次我们被提醒说，他们的订阅起价仅为每月 5 美元——该公司表示，它将把 Pro 的并行构建数量增加到 5 个，团队订阅者增加到 15 个，同时增加构建实例类型，并使用 BuildKit 来提供“更强大”的机器和更好的性能。

## 本周的节目中

*   **“Docker 扫描”登陆 Linux:** 当我们谈到 Docker 的话题时，该公司本周也宣布，在去年年底推出漏洞扫描功能后，它将[把“Docker 扫描”带到 Linux](https://www.docker.com/blog/bringing-docker-scan-to-linux/) 。该功能以前在 Docker Hub 以及 Mac 和 Windows 的 Docker 桌面上可用，现在它正在转移到 Linux 上的 Docker CLI。Docker 在其博客文章中写道:“在 Linux 上扫描的体验与我们已经推出的桌面 CLI 相同，”并指出它将使用所有相同的标志，但有一个主要区别。你不需要升级你的 Docker 桌面，你需要安装或升级你的 Docker 引擎，你可以在 Docker 文档的[安装 Docker 引擎](https://docs.docker.com/engine/install/)部分阅读所有相关内容。

*   **VS 代码获得对远程存储库的支持:**微软[发布了](https://code.visualstudio.com/blogs/2021/06/10/remote-repositories)一个新的[远程存储库](https://marketplace.visualstudio.com/items?itemName=github.remotehub)Visual Studio 代码的扩展，它与 GitHub 一起构建，支持与远程存储库一起工作。“开发人员每天所做的很大一部分工作都涉及阅读他人的代码:审查拉式请求、浏览开源存储库、试验新技术或项目、检查上游依赖性以调试应用程序等，”他们写道。虽然通常您需要克隆存储库来用 VS 代码做到这一点，但是现在您几乎可以瞬间做到。该扩展目前支持 GitHub repos，并将很快添加对 Azure repos 的支持，这意味着你可以“在你喜欢的任何 Repos 上工作，而不必在你的机器上保存任何源代码。”当然，您可以做的事情有一些限制:您不能使用终端，一些功能如 IntelliSense 和 Go to Definitions 可能无法正常工作，搜索可能受到远程存储库主机的限制，并且不是所有的扩展都支持在这种虚拟工作区中运行。如需快速介绍，请观看下面的视频:

[https://www.youtube.com/embed/wHsmaXoGIXI?feature=oembed](https://www.youtube.com/embed/wHsmaXoGIXI?feature=oembed)

视频

*   **GitLab 在 14.0 中默认为“主”分支:** GitLab 已经[转移到 14.0](https://about.gitlab.com/blog/2021/06/04/gitlab-moving-to-14-breaking-changes/) ，它的年度主要版本，它说这个版本包括一些突破性的变化，以[计划弃用](https://about.gitlab.com/releases/2021/05/22/gitlab-13-12-released/#release-deprecations)的形式出现。迁移将通过[日常部署](https://about.gitlab.com/handbook/engineering/infrastructure/library/scheduled-daily-deployments/)进行，直到 6 月 22 日，届时 GitLab.com 和自主管理的 GitLab 都将完全迁移到 14.0。除了反对之外，GitLab 正式开始使用“main”作为默认分支，而不是“master”——这一变化已经进行了一段时间，最近在 Git 本身中于今年早些时候做出。要了解 GitLab 14.0 中的所有新功能，请前往他们冗长的[博客帖子](https://about.gitlab.com/blog/2021/06/04/gitlab-moving-to-14-breaking-changes/)详细介绍所有的变化，或者查看[视频摘要](https://www.youtube.com/embed/Z1FqGH0pNvo)。
*   **网飞为 eBPF 指明了道路:**对于那些经常阅读我们页面的人来说，你知道我们[把 eBPF 视为值得关注的东西](https://thenewstack.io/linux-technology-for-the-new-year-ebpf/)。如果你不熟悉的话，扩展的 Berkeley 数据包过滤器(eBPF)为 Linux ( [和现在的 Windows](https://thenewstack.io/this-week-in-programming-ebpf-coming-to-a-windows-near-you/) )用户提供了一种在内核空间运行沙盒程序的方式，而无需更改内核源代码或加载模块，本周，网飞提供了一些关于它如何[大规模使用 eBPF 流量日志进行网络洞察](https://netflixtechblog.com/how-netflix-uses-ebpf-flow-logs-at-scale-for-network-insight-e3ea997dca96)的见解。他们通过使用一个称为流导出器的网络可观察性 sidecar 来做到这一点，该 sidecar 使用 eBPF 跟踪点来近乎实时地捕获 TCP 流。当然，有趣的是，这种情况正在网飞发生，他们“每小时接收和丰富数十亿条 eBPF 流日志”，这一切都是通过“利用高性能 eBPF 和精心选择的传输协议，在我们车队的任何实例上消耗不到 1%的 CPU 和内存实现的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>