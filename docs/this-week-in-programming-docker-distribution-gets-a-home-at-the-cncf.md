# 本周节目:码头配送在 CNCF 安家

> 原文：<https://thenewstack.io/this-week-in-programming-docker-distribution-gets-a-home-at-the-cncf/>

[Docker Distribution](https://github.com/distribution/distribution) ，作为[Docker Hub](https://hub.docker.com/)container registry 和其他几个如 [Harbor](https://goharbor.io/) 的基础的开源项目，已经于本周[捐赠](https://www.docker.com/blog/donating-docker-distribution-to-the-cncf/)给[Cloud Native Computing Foundation](https://cncf.io/?utm_content=inline-mention)(CNCF)，似乎得到了整个社区的一致好评。

如果你一直在关注的话，最近几个月围绕 Docker Hub 有一点[要做的事情，当该公司表示将开始限速图像拉，导致许多公司推出自己的替代产品。虽然 Docker 没有直接提到这种情况，但它指出现在有“许多注册中心”基于 Docker 分发代码。他们写道，问题是“许多人有小的分叉和变化，他们没有为上游版本做出贡献，项目需要更广泛的维护者群体。”因此，他们决定将该项目转移到 CNCF，在那里，它现在将享受来自 Docker、GitHub、GitLab、Digital Ocean、Mirantis、开放集装箱倡议和 Harbor project 的维护者。](https://thenewstack.io/docker-hub-limits-what-they-are-and-how-to-route-around-them/)

当然，如果你去寻找它，你总能找到这样或那样的不同意见，黑客新闻上的一位评论者认为，他们担心这只是 Docker 的一个举动，以保护其“不断减少的现金”然而，Docker 首席技术官贾斯汀·科马克很快纠正了评论，指出了大量的维护者，写道“在 Docker GitHub 组织中将其作为一个项目而不是开放治理对于这么多用户来说没有意义。”谷歌的开发人员 Ahmet Alp Balkan 也在 Twitter 上支持这一举动，他写道，看到项目转移到 CNCF“让我个人感到高兴，因为我在回购中有相当多的承诺。”

目前，该项目将是一个 CNCF 沙盒项目，但 Docker 写道，“由于它是一个成熟的项目，我们将建议它很快进入孵化阶段。”

## 本周的节目中

*   **NPM 7 CLI 已经到来:**吹捧“对性能的重大影响”， [npm 7 现已正式发布](https://github.blog/2021-02-02-npm-7-is-now-generally-available/)，为 Javascript package manager 的最新版本带来了新功能和突破性变化。根据公告， [npm CLI 7](https://github.com/npm/cli) 自 8 月以来发布了 [45 个版本，减少了约 54%的依赖性，增加了约 17%的代码覆盖率，并显著提高了性能，如跨越众多](https://www.npmjs.com/package/npm?activeTab=versions#versions)[示例](https://github.com/npm/benchmarks#example-usage)的[各种基准](https://github.com/npm/benchmarks)所示。虽然 npm 7 最初是在 10 月发布的[，但它是选择加入的，现在已经被设为默认。正如第一次发布时提到的，npm 7 最大的特性之一是](https://github.blog/2020-10-13-presenting-v7-0-0-of-the-npm-cli/)[工作区](https://github.com/npm/rfcs/blob/latest/implemented/0026-workspaces.md)，它增加了对从单个顶级根包中管理多个包的支持。在这次最新发布中，突出强调了两个额外的变化。首先，有了一个[新的锁文件格式](https://blog.npmjs.org/post/621733939456933888/npm-v7-series-why-keep-package-lockjson.html)，它“释放了进行确定性的和可再现的构建来产生一个包树的能力。”其次，npm 7 现在将“如果存在无法自动解决的上游依赖关系冲突，将阻止安装”，使用户能够强制它绕过冲突或完全忽略对等依赖关系，而不是像 npm 版本 4-6 那样，默认情况下在没有警告的情况下继续安装。

*   **GitHub 降低市场费用，扩大视频评论支持:**本周最新的“GitHub 近况”是以[降低其市场中销售的应用程序的市场交易费用](https://github.blog/2021-02-04-github-reduces-marketplace-transaction-fees-revamps-technology-partner-program/)的形式出现的，应用程序所有者将其收取的费用从 75%增加到 95%，因为 GitHub 将其交易费用降低到仅 5%。与此同时，该公司表示将[简化其应用程序验证过程](https://docs.github.com/en/developers/github-marketplace/about-marketplace-badges)以纳入其市场。GitHub 现在将在包含应用程序之前验证“常识性的安全预防措施”，而不是“对应用程序安全性和功能的深度审查”。除了市场更新，GitHub 还表示正在扩展对视频上传的支持，这是该公司在 12 月份的公测版中增加的功能，当时它开始允许用户上传. mp4 和。问题、拉动请求和讨论注释的 mov 文件。现在，用户可以将视频上传到 gist 评论和团队帖子，大小限制为 100MB。
*   **微软提供量子计算公开预览:**什么，你办公室里没有量子计算机坐？现在你可以了，因为微软已经开始提供“世界上第一个用于量子解决方案的全栈公共云生态系统”，并发布了 Azure Quantum 的[公共预览版](https://cloudblogs.microsoft.com/quantum/2021/02/01/azure-quantum-preview/)。预览版不仅可以让你使用量子计算机，还可以使用一些工具，如开源的[量子开发工具包(QDK)](https://www.microsoft.com/en-us/quantum/development-kit) 、微软新的[量子中间表示(QIR)](https://devblogs.microsoft.com/qsharp/introducing-quantum-intermediate-representation-qir/) 、语言和目标量子计算平台之间的公共开源接口，以及充满 [Katas](https://github.com/Microsoft/QuantumKatas) 和[样本](https://aka.ms/AQ/Samples)的[资源库](https://aka.ms/AQ/Overview)。有关更多细节，微软还将在 2 月 2 日上午 8 点(太平洋标准时间)举办一场 Azure Quantum 开发者研讨会，其中将包括演示和研讨会结束时的现场问答。

*   **Red Hat 使用 CentOS 代码的“指南”:** [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 最近[宣布了一些围绕 CentOS 的变化](https://thenewstack.io/red-hat-deprecates-linux-centos-in-favor-of-a-streaming-edition/)，反对 CentOS 而支持其流媒体版本，现在该公司正在提供一个使用 CentOS 项目代码的[指南，以“该做和不该做”的列表的形式。该公司表示，“许多人向我们询问我们将如何发布 CentOS 源”，并且“简而言之，我们不会对这一过程进行任何更改。”现在，如果这对你来说还不够，请随意点击并阅读 Red Hat 的“指南”，它主要是建议你“遵循](https://developers.redhat.com/blog/2021/02/03/a-guide-for-using-centos-project-code/) [Red Hat 商标指南](https://www.redhat.com/en/about/trademark-guidelines-and-policies)”，遵守许可，甚至可能“突出包括”关于 Red Hat 商标所有权的免责声明。
*   **FOSDEM 重新定义:**众所周知，本周末是 [FOSDEM 21](https://fosdem.org/) ，这个( [now online](https://fosdem.org/2021/practical/online/) )会议主要讨论自由和开源软件，以及所有相关主题。至少有一个开发者不是大会的粉丝，他提供了一个替代的日程表，标题是“ [FOSDEM: more boring shit](http://n-gate.com/fosdem/2021/02/01/0/) ”，如果你想吃点零食的话，这很值得一读。至于他们是谁，嗯，我不完全确定，因为我没有挖得那么深，他们的“关于”页面也没有提供任何见解，但看看来源确实让他们对 FOSDEM 的看法更加清晰。他们写道:“自由和开源软件开发者欧洲会议(FOSDEM)是一个非商业的、志愿者组织的欧洲错误，其中心是自由和开源的注意力嫖娼。它的目标是 TEDx 的崇拜者和任何对自由和开源噪音运动感兴趣的人。它旨在使社交媒体参与专家能够会面，并促进他们自己的意识和使用。“好吧，那好吧。

云计算原生计算基金会和 Red Hat 是新堆栈的赞助商。

罗伯特·奥尔曼·德·皮沙贝的特写。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>