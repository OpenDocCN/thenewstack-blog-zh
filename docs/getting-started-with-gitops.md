# GitOps 入门

> 原文：<https://thenewstack.io/getting-started-with-gitops/>

[](https://uk.linkedin.com/in/jordimoncompanys)

 [乔迪·蒙公司

乔迪是 Weaveworks 的产品营销总监。他是一名开源产品专家、社区建设者和公共演说家。他是 OpenUK 和 PMM 联盟大使，常驻伦敦。](https://uk.linkedin.com/in/jordimoncompanys) [](https://uk.linkedin.com/in/jordimoncompanys)

软件开发。软件工程。不管你怎么称呼它，这个过程变得越来越复杂。它在计算解决问题方面也变得越来越好，但与此同时，构建弹性分布式系统的学习曲线变得越来越平坦。(是的，[平坦的学习曲线](https://en.wikipedia.org/wiki/Learning_curve)才是最难的，各位)。

虽然我认为这不会扼杀这个行业，但肯定会让人们更难成为软件工程师。当我为现代运营的艺术播客采访[泰勒·朱厄尔时，他解释说，虽然开发人员的数量仍在增长，但增长速度太慢了，以至于人数开始趋于稳定。](http://www.weave.works/blog/continous-delivery-gitops-experimentation)

与此同时，软件需求的增长正在加速。换句话说，对可靠软件的需求开始超过制作软件所需技能的供给。因此，成功的关键是让今天的开发人员尽可能地有能力和生产力。因此，GitOps 在云原生开发方面取得了成功。

## 软件很难，GitOps 和 Kubernetes 来帮忙了

让我们退后一步。是的，软件开发一直都很艰难。计算机不容易理解，技术也不总是适合简单的操作，尽管可以说，机器只能解析原语。

这不是计算技术独有的。我的母亲是一名地质学家，她过去常说，规划任何干预措施——无论是隧道、地下停车场还是仅仅是建筑物的地基——都意味着管理一系列几乎无法确定的变量。

这就是为什么复杂系统，无论是地壳还是计算机，都难以置信地难以掌握。正如艾米莉·弗里曼所言，这是一场管理不断增长的熵的游戏。

那么，云原生社区如何应对这种不断增长的熵和复杂性呢？作为一种拥抱协作、无可指责的改进和整体的、渐进的软件开发方法的文化，DevOps 将是最有可能成功解决这个问题的候选人。

然而，这个社区的一个子集——主要是那些大规模参与 CD 的人，尤其是 Kubernetes 逐渐找到了一个答案，我们现在称之为 GitOps。

在 Kubernetes 之前，出现了持续集成(CI)、配置管理/自动化和持续交付(CD)。然而，容器化应用程序部署的编排仍然相当复杂。它仍然涉及 CI 引擎、配置管理数据库(CMDB)服务器、包存储库的组合，当然还有大量的人工协调。

不管这些过程有多麻烦，结果是相当明显的:推出应用程序时出现的错误更少了。换句话说，价值更频繁地无缝交付给最终用户。这部分是由于 Kubernetes 的声明性质。

## 变化来了:操作化复杂性

类似的过程也发生在 Weaveworks。早在 2017 年原生构建产品云的时候，我们就像其他人一样，希望发布时问题尽可能少。因此，我们自动化了我们的构建、测试和发布流程。

尽管开始时并不明显，但有几项要求很快就显示出其重要性:

*   用声明的方式将系统存储在 git 中
*   在 git 中存储配置清单
*   让他们观察构建管道的工件更新
*   自动将任何更改部署到声明的系统

考虑到这一点——当时我们称之为“拉式请求操作”——Flux 诞生了。它实际上是作为一个监控图像工件库的守护程序而诞生的，寻找部署在 [Weave Cloud](https://www.weave.works/product/cloud/) 中的 Kubernetes 清单中引用的图像的新版本。

当我们当时使用的构建管道更新 Flux 守护进程正在监视的映像时，它会自动更新部署清单，以便部署最新的 semver 工件。

最终，它还会调用 kubectl 并部署该映像。实际上，我们是在连接一个自动化的 CI 管道和一个 CD 管道。

通过这种方式，特别是 Flux，以及一般的 GitOps，已经逐渐成为云原生开发的操作模型。Flux 现在是 CNCF 的一个[孵化项目，它包含了一个 GitOps 工具包——一个用于构建 Kubernetes 控制器的 SDK 以进一步扩展 GitOps 的覆盖范围。](https://fluxcd.io/blog/2021/03/flux-is-a-cncf-incubation-project/)

## 从有意义到富有成效

为云原生时代简化软件开发的过程才刚刚开始。像 Flux 和 Weave GitOps 这样的产品被站点可靠性工程师或 DevOps 工程师用来构建平台。

平台应该是开发环境，其中工具、工作流和策略提供给开发人员阅读。这个想法是让开发人员能够从 git 内部管理 Kubernetes。

这样，入门门槛相当低，因为几乎所有开发人员都对 git 最基本的命令感到满意([可以说](https://twitter.com/janakiramm/status/1455067698618982401?s=20) git init、git add、git commit、git status、git log 和 git revert 就足够了)。

变更变成了一个需要批准、审查或团队间可见性的门控流程。它也变得更便宜，因为 git 中的分支很便宜。

因此，最终，如果开发人员能够从 git 管理工作负载、配置和基础架构，并且启动集群只需[两个命令](https://www.weave.works/product/gitops-core/)，那么扩展任何环境都变得相当容易，跨环境提升工作负载更是如此！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>