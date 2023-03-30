# 本周编程:GitLab 从主/从术语转移开去

> 原文：<https://thenewstack.io/this-week-in-programming-gitlab-moves-on-from-master-slave-terminology/>

如果说去年在网上花了太多时间还没有教会我什么的话，我已经明白了花时间阅读匿名网络陌生人的评论是最大的时间浪费，而这个特别的话题就是一个突出的例子。如果你今天过得很好，想毁了它，就直接去 [GitLab 的 tweet](https://twitter.com/gitlab/status/1369777337252904960) 宣布它将把默认的分支术语从“主”改为“主”,然后点击所有的回复。

我的朋友们，对使用“主人/奴隶”二分法的愤慨和坚持是真实的。

随着 Atlassian 的 BitBucket [在去年 6 月采取行动](https://bitbucket.org/blog/moving-away-from-master-as-the-default-name-for-branches-in-git)，GitHub [在几个月后跟进](https://github.blog/changelog/2020-10-01-the-default-branch-for-newly-created-repositories-is-now-main/)，GitLab 只是[加入正在进行的摆脱这些旧术语趋势的最新](https://about.gitlab.com/blog/2021/03/10/new-git-default-branch-name/)。与此同时，git 项目也在努力做同样的事情。正如 GitLab 在关于这一变化的博客文章中所描述的那样，这个术语直接来自 Bitkeeper，一个比 git 早五年的分布式源代码管理系统，尽管它也遵循了更早的命名传统，从硬盘驱动器到数据库再到汽车制动系统。背离这一传统的趋势一直在持续，不仅在源代码控制系统中，在其他技术解决方案中也是如此，例如 [Python 编程语言](https://bugs.python.org/issue34605)。

在计算机术语中，“主/从”代表两个实体，其中一个“从”从另一个实体“主”那里接受所有命令。像许多计算机术语一样，这些术语可能是随意选择的，因为它们是隐喻性的描述。但是他们想起了令人憎恶的奴隶制，一个人可以“拥有”另一个人。

在互联网工程任务组的一份讨论文件中，Niels ten Oever 和 MalloryKnodel [说得好](https://tools.ietf.org/html/draft-knodel-terminology-02)他们断言“主从是一个令人不快的隐喻，将永远也不应该完全脱离历史。”

如果你想多读一点关于这个话题的文章，那就看看我们去年的网页吧，当时[詹妮弗·李金斯](https://thenewstack.io/author/jennifer-riggins/)认为[的话事实上很重要](https://thenewstack.io/words-matter-finally-tech-looks-at-removing-exclusionary-language/)。简短摘录:

*“当[想要有所作为](https://thenewstack.io/black-lives-matter-how-the-tech-community-can-provide-support/)时，言语会留下影响。因为语言很重要。整个社交媒体诞生于对语义的痴迷。语言是我们作为人类的定义。*

因此，当一种语言出现变化时，它标志着更多的东西。因为，不管是书还是代码，文字都会留下遗产。网上的词汇选择类似于现场的雕像——它们通常只被少数人选择，如果不定期重新考虑，就会变得过时和生锈。”

正如 Riggins 在她的文章中指出的，技术有一点多样性的问题，当看前面提到的 Twitter 评论线程时，这个问题就更加明显了。

至于 GitLab 脱离所讨论术语的细节，从 2021 年 4 月 22 日到来的 GitLab 13.11 开始，默认的分支名称变化将出现在 GitLab.com 和自管理实例中。起初，变更将在一个特性标志下发布，尽管一个月后这个标志将被删除，新项目将使用默认的名称“main”。GitLab 项目本身也将在此时更改它自己的存储库分支名称。

## 本周的节目中

*   2020 年 Go 开发者调查的[结果出来了，令人惊讶的是，绝大多数受访者——9648 个回复中的 92%——表示他们对语言的](https://blog.golang.org/survey2020-results)[总体满意度](https://blog.golang.org/survey2020-results#TOC_6.)很高。同样，81%的人说他们在不到三个月的时间里觉得围棋很有效率，几乎同样多的人(76%)说他们在工作中使用这门语言。至于用例，调查发现 Go 继续大量用于[API、CLIs、web、DevOps 和数据处理](https://blog.golang.org/survey2020-results#TOC_7.)。如果你想知道哪里缺少 Go，似乎在社区层面上，[代表性不足的群体](https://blog.golang.org/survey2020-results#TOC_12.1)在社区中更不受欢迎。在技术层面上，只有 26%的人说他们觉得 Go 缺乏他们需要的语言功能，88%的受访者认为，你猜对了，即将添加的[泛型](https://thenewstack.io/this-week-in-programming-go-approves-generics-long-at-last/)是关键的缺失部分。
*   **GitHub 讨论转为私有:** [GitHub 讨论](https://docs.github.com/en/discussions)，GitHub 库和社区的协作交流论坛[现在对私有库](https://github.blog/2021-03-09-github-discussions-now-available-for-private-repositories/)开放。该功能于 2020 年 12 月宣布，最初是在公共测试版中为公共存储库提供的，在该公司表示“随着数万个开源社区和讨论的创建”快速增长后，该功能现在将面向私有存储库进行公共测试。GitHub 表示，这项功能已经被用于新兵训练营和教室，并在 Stripe 建立了一个开发者网络。开始使用该特性就像在存储库设置中的“特性”下启用讨论一样简单。

*   **GitHub Actions 获得 Visual Studio 改造:继去年 9 月在 Visual Studio 中添加[动作以及随后的反馈之后，Visual Studio](https://devblogs.microsoft.com/visualstudio/using-github-actions-in-visual-studio-is-as-easy-as-right-click-and-publish/) 中有**一些[新的 GitHub Actions 工具可以试用。在最初发布后，Visual Studio 团队与社区合作，发现有一些令人困惑的 UI 和不充分的摘要页面，并表示“因此，我们对体验进行了一些更改，以使其更符合这一反馈以及我们对未来更多潜在集成的愿景。”在这个最新的更新中，您可以期待一个重新设计的摘要页面，一个新的状态部分，它明确了可能的后续步骤，并且只需单击一下就可以提交和推送工作流。在最后一点上，单击将在本地提交工作流文件，将工作流推送到远程，创建工作流成功执行所需的必要 GitHub 机密，并最终在 GitHub repo 和用于部署的 Azure 实例之间建立链接。如果你有其他你认为需要解决的更新，团队会通过](https://devblogs.microsoft.com/visualstudio/whats-new-with-github-actions-tooling-in-visual-studio/)[开发者社区](https://developercommunity.visualstudio.com/spaces/8/index.html)请求反馈。
*   **用 Azure 可信启动根除 rootkit:**微软[宣布了一个针对虚拟机](https://azure.microsoft.com/blog/announcing-preview-of-azure-trusted-launch-for-virtual-machines/)的 Azure 可信启动的预览版，该功能据说可以帮助 Azure 客户防止 bootkit 和 rootkit 感染，这是一种以内核模式权限运行的恶意软件类型，可能“极难检测，几乎不可能删除。”借助用于虚拟机的 [Azure 可信启动](https://aka.ms/trustedlaunch)，管理员可以“部署虚拟机，这些虚拟机具有经过验证和签名的引导加载程序、操作系统内核和引导策略，该策略利用可信启动虚拟可信平台模块(vTPM)来测量和证明引导是否被破坏”，并且可以在 Azure Security Center 中看到和启用一切。目前，Trusted Launch 正在最常用的操作系统映像上的选定 Azure 区域中进行预览，更多将很快推出。有关更多信息，请查看[文档](https://aka.ms/trustedlaunch)。

*   **谷歌代码之夏开启，有 200 多个导师组织:**随着春天即将来临(至少在谷歌称之为家的半球)，谷歌代码之夏即将来临，学生申请将于 3 月 29 日开放，[宣布了 2021 个导师组织](https://opensource.googleblog.com/2021/03/google-summer-of-code-2021-mentoring-orgs-announced.html)，其中 31 个是今年新成立的。在 200 多个组织中有一些著名的云原生项目，包括云原生计算基金会、持续交付基金会和 Ceph，以及许多其他项目，如 Ruby、Git、ReactOS、GitLab、Linux 基金会、Python 软件基金会等等。如果你没有听说过谷歌的代码之夏，看看 [FAQ](https://developers.google.com/open-source/gsoc/faq) 或者他们准确描述[什么是 GSoC](https://www.youtube.com/watch?v=S6IP_6HG2QE&feature=emb_title) 的视频。对于你生活中年轻的有抱负的程序员来说，这可能是完美的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>