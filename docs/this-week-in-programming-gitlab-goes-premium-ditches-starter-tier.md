# 本周编程:GitLab 升级，放弃初级层

> 原文：<https://thenewstack.io/this-week-in-programming-gitlab-goes-premium-ditches-starter-tier/>

GitLab 一直坚持认为它不仅仅是一个源代码库和版本控制系统。相反，该公司已经取得了长足的进步，成为并被称为功能齐全的“DevOps 平台”，从源代码管理一直到软件生命周期，为用户提供持续集成和持续部署(CI/CD)等服务。本周，该公司通过[转向三层产品订阅模式](https://about.gitlab.com/blog/2021/01/26/new-gitlab-product-subscription-model/)并逐步淘汰其青铜/入门层，进一步巩固了这种认知和用例。

“在过去的几年里，GitLab 已经发展成为一个完整的 DevOps 平台。许多青铜/初学者客户只是为了源代码管理(SCM)或持续集成(CI)而采用 GitLab，但 GitLab 现在是一个强大的 DevOps 平台，可以取代整个工具链，”该公司解释说，并指出该层“没有达到[的最低回报率](https://www.investopedia.com/terms/h/hurdlerate.asp)，这是一种巧妙的方式，表明他们在这笔交易中没有赚到足够的钱。

对于他们来说， [GitLab](https://about.gitlab.com/?utm_content=inline-mention) 还指出，在过去的一年中，它已经为其免费服务增加了 450 多项功能，该公司不仅为当前的青铜级/初级用户提供一年的过渡期，还为那些立即升级到高级版的用户提供折扣。

随着价格的任何变化，有一部分用户对这种变化感到非常失望，他们谴责百分比的增加，并经常发誓要将他们的业务转移到另一个系统，或者各种 DevOps 工具的大杂烩。

HackerNews 上的[讨论传达了类似的苦恼，一位用户](https://news.ycombinator.com/item?id=25918717)[将](https://news.ycombinator.com/item?id=25925512)的帖子总结为“GitLab:你的产品很棒；你的定价太疯狂了。”另一位[指出](https://news.ycombinator.com/item?id=25920200)即使有折扣，GitLab 的服务最终还是“贵了整整一个数量级”，其锁定程度令人无法接受。

在一片喧嚣中，有一些用户看到了这一举动的原因。GitLab 论坛的一位用户[评论](https://forum.gitlab.com/t/new-gitlab-product-subscription-model/45923/27)说“新的层有一定的意义。之前，4 个€和 19 个€之间没有明显的区别——至少看起来是相当武断的 Twitter 上的另一名用户指出，部分问题可能在于他们没有“充分”使用这些服务，或许新价格只是反映了完全购买的团队的价值。

## 本周的节目中

*   **Red Hat 增加了 100 多个免费下载的数据集:**去年年底，Red Hat 和 IBM 推出了 [Red Hat Marketplace](https://marketplace.redhat.com/en-us) ，现在这些公司正在[提供 100 多个公共数据集](https://marketplace.redhat.com/en-us/blog/getting-started-with-datasets-on-red-hat-marketplace)，比如“与新冠肺炎、美国人口普查、就业数字、人口统计、天气、城市数据等相关的数据集”他们写道，他们的目标是“让你能够找到和使用原始数据，以及 Kubeflow 管道”，并为开发人员提供“一个单一的位置，他们可以访问企业应用程序和公共数据集来构建他们的应用程序。”当前的数据集只是一个开始，未来一年还会有更多的数据集，以及新的模型和 API。想了解博客文章以外的更多信息，请查看[文档](https://marketplace.redhat.com/en-us/documentation/datasets)。
*   **OpenSSF 提供更新:**[开源安全基金会(OpenSSF)](https://openssf.org/) ，由[于去年年底](https://thenewstack.io/the-open-source-security-foundation-looks-to-unite-and-conquer/)发起，旨在解决开源软件生态系统中的安全问题，已经提供了一个更新，包括[新的“技术愿景”，](https://openssf.org/blog/2021/01/28/jan_2021_announcement/)以及来自其一些独立工作组的一些特定更新。该组织表示，它设想了“一个开源生态系统的参与者使用和共享高质量软件的未来，在默认情况下，安全性得到主动处理，这是理所当然的。”为此，该小组进一步看到开发人员能够更容易地识别安全问题，学习安全开发实践，并通过他们的工具创建和分发安全策略。在各个工作组提供的具体更新中，有针对工具和数据集的 [CVE 基准](https://openssf.org/blog/2020/12/09/introducing-the-openssf-cve-benchmark/)、帮助理解哪些开源软件项目是最关键的[关键度分数](https://github.com/ossf/criticality_score)，以便安全工作可以相应地优先化、针对开源项目的[安全度量](https://github.com/ossf/Project-Security-Metrics)仪表板以及[安全记分卡](https://github.com/ossf/scorecard)，它通过对 OSS 项目的多次检查自动生成“安全分数”。对于感兴趣的人，该项目正在寻找其他人参与进来，并将于美国东部时间 2 月 22 日星期一下午 1-2 点举行市政厅会议。

*   **Docker 开源 Linux CLI 工具，与 JFrog 合作:** Docker 上个月在其 [All Hands](https://youtu.be/-A9jp-R_mBc?t=1820) 会议期间发布了其 Docker Hub 命令行界面(CLI)工具，现在该公司已经决定[开源](https://www.docker.com/blog/open-sourcing-the-docker-hub-cli-tool/)该工具的 Linux 版本。众所周知，hub-tool 在 Github 上可用，虽然仍处于试验阶段，但 v0.3.0 引入了一些新功能，例如检查组织状态的能力，或者如果图像是多拱图像，则检查特定平台。当我们在这里的时候，Docker 和 JFrog 也[宣布了本周的合作](https://jfrog.com/blog/jfrog-docker-partnership-for-dockerhub/)，这将免除 JFrog 用户对 Docker 最近实施的[Docker Hub 图像拉取](https://thenewstack.io/docker-hub-limits-what-they-are-and-how-to-route-around-them/)的速率限制。
*   **2020 年顶级开发者工具:**距离 2021 年的第一个月只剩下几天了，还有一点时间来回顾我们宁愿不记得的这一年，StackShare 已经通过其年度列表[100+顶级开发者工具](https://stackshare.io/posts/top-developer-tools-2020)做到了这一点。它通过分析“由您分享的超过 800 万个数据点 StackShare 社区”并将结果组织成众多类别，例如年度[新工具](https://stackshare.io/posts/top-developer-tools-2020#new)、[分析](https://stackshare.io/posts/top-developer-tools-2020#analytics)、[应用托管](https://stackshare.io/posts/top-developer-tools-2020#application-hosting)、 [web 服务器](https://stackshare.io/posts/top-developer-tools-2020#web-servers)、[应用实用程序](https://stackshare.io/posts/top-developer-tools-2020#application-utilities)等等。因为作为开发人员的一部分总是要跟上最新的，所以像这样的列表肯定是非常宝贵的，对于好奇的人来说，StackShare 提供了一些关于其[方法](https://stackshare.io/posts/top-developer-tools-2020#methodology)的注释，以供进一步回顾。

*   Linkerd 成立了一个指导委员会:上周，[浮力](https://buoyant.io/)，开源服务网 [Linkerd](https://linkerd.io/) 背后的主要公司[成立了 Linkerd 指导委员会](https://buoyant.io/newsroom/announcing-the-linkerd-steering-committee/)。该项目现在正在组建一个指导委员会，它说，因为它已经看到了快速的增长，并希望“拓宽最终用户参与项目的方式”——换句话说，不仅仅是通过代码贡献。然而，Linkerd 指导委员会与其他委员会的不同之处在于，“Linkerd 的指导委员会成员代表 Linkerd 用户，而不是代表供应商。”根据帖子，所有指导委员会成员目前必须运行“非平凡规模”的 Linkerd 生产部署，以确保“没有生产化就没有代表”。该委员会将于二月份成立，具体日期将在 cncf-linkerd-users 邮件列表中公布。要了解更深入的背景，请前往 SDxCentral，了解指导委员会的组建据说是如何收集烦恼的 Istio 用户的。

阿尔文·马赫穆多夫在 [Unsplash](https://unsplash.com/s/photos/freezing?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>