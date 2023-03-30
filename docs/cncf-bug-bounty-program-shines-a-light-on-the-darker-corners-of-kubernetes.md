# CNCF 虫赏金计划照亮了库伯内特的黑暗角落

> 原文：<https://thenewstack.io/cncf-bug-bounty-program-shines-a-light-on-the-darker-corners-of-kubernetes/>

在与选定的安全研究人员进行了几个月的测试后，Kubernetes bug bounty 计划于周二启动。它是由[云本地计算基金会](https://www.cncf.io/)(CNCF)[谷歌](https://www.google.com/)、 [HackerOne](https://www.hackerone.com/) 和 [Kubernetes 产品安全委员会](https://github.com/kubernetes/security)共同努力的结果。谷歌首次提出该计划，并在 2018 年初定义了[初步提案](https://docs.google.com/document/d/1dvlQsOGODhY3blKpjTg6UXzRdPzv5y8V55RD_Pbo7ag/edit#heading=h.7t1efwpev42p)，HackerOne 赢得了社区主导的提案请求(RFP)，CNCF 提供了资金。奖金将根据严重性从 100 美元到 10，000 美元不等，HackerOne 将处理新提交的 bug 的初步分类和评估。

在其发布的博客帖子中，安全委员会指出，开源基础设施工具的漏洞赏金非常罕见，并指出大多数此类程序都是针对“跨环境一致部署的组件”和基于网络的应用程序的。Kubernetes 提供了一个非常不同的挑战，bounty 计划的范围包括 GitHub 上主要 Kubernetes 组织的代码，以及持续集成、发布和文档工件——“基本上，你认为是‘核心’Kubernetes 的大多数内容，”他们写道。

在接受新堆栈采访时，谷歌产品经理 Maya Kaczorowski 描述了 Kubernetes 与其他工具的不同之处:

这个 bug bounty 不同于其他的 bug bounty，因为没有单一的真实环境供研究人员测试，这在 bug bounty 项目中很常见。由于 Kubernetes 可以以如此多的不同方式配置，我们正在寻找可能影响任何这些环境的错误。这使得验证漏洞变得更加困难，因为它们必须在环境对环境的基础上进行测试，以复制安全研究人员所使用的方法。Kubernetes 有超过 100 个认证发行版，任何程序的这个 bug 都必须适用于所有发行版。这给了我们很大的空间。

虽然邮件列表和 Slack channel 等社区工具不在范围内，但该委员会表示，它“对集群攻击以及信息泄露、意外的特权变化和 Kubernetes 供应链特别感兴趣”。这就是 Kubernetes 产品安全委员会成员 Tim Allclair 说他在几个月的测试中看到了一些意想不到的成功。虽然 Allclair 表示，委员会学习 HackerOne 工具和测试分流流程很有帮助，但更重要的是，他看到该计划将照亮 Kubernetes 中一些审查较少的领域。

“我们确实在供应链中发现了一些问题，这是我非常高兴看到这个项目成功的领域之一，”Allclair 说。“我们过去提交的许多报告主要集中在作为 Kubernetes 的一部分运行的代码上。我很高兴看到支持 Kubernetes 的所有基础设施得到了更多的关注。”

### 基础科技的 Bug 奖励

bug bounty 是 CNCF 为其项目之一设立的第一个项目，CNCF 首席运营官[克里斯·阿尼斯奇克](https://www.linkedin.com/in/caniszczyk)表示，对于 CNCF 的其他项目，他们将不得不逐案处理。

“并不是所有的项目都像 Kubernetes 那样需要一个 bug 奖励计划。Aniszczyk 告诉新的 Stack:“运行这些东西对基金会来说是一项成本，所以我们可能会更喜欢我们的毕业项目，而不是生态系统中其他较小的项目。“当我们开始为 CNCF 推出安全审计时，我们对其进行了测试，并在几个项目中进行了试点。我们很可能会为臭虫奖励计划做同样的事情。”

为了防止你认为这个项目只针对安全研究人员，Allclair 明确表示它对所有感兴趣的人开放。

“我们经常谈论安全研究人员，我们在博客文章中也使用这个术语，但是我们过去的许多安全问题都是由开发人员报告的，他们正在 Kubernetes 中构建一个功能，并注意到一些看起来不太正确的事情。他们通过我们之前的电子邮件披露流程向我们报告。那些开发者也欢迎加入这个项目，并提交他们的 bug 以获得奖金。你不需要成为一名现有的、公认的安全研究人员，就可以为你发现的漏洞申请奖金，”他说。

然而，Allclair 也肯定地指出，安全委员会对那些不想注册 HackerOne bug bounty 计划的人开放了电子邮件披露流程。

云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>