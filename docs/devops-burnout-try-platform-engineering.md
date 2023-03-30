# DevOps 倦怠？尝试平台工程

> 原文：<https://thenewstack.io/devops-burnout-try-platform-engineering/>

我们是不是正处于大开发的倦怠期？

[这份来自草堆的报告](https://haystack-books.s3.amazonaws.com/Study+to+understand+the+impact+of+COVID-19+on+Software+Engineers+-+Full+Report.pdf)说是的。在接受调查的 258 名软件工程师中，83%的人报告说，高工作量、低效的流程以及不明确的目标和指标让他们感到精疲力竭。只有 26%的参与者报告说他们只从事产品开发，而 74%的参与者报告说他们以某种身份从事运营工作。

虽然最初研究的样本量很小，但结果似乎是可信的。在 DevOps 社区中，关于开发人员是否能够或者想要承担运营任务的讨论越来越多。InfoWorld 的 Scott Carey 大胆宣称“[开发者不想做 Ops](https://www.infoworld.com/article/3669477/devs-don-t-want-to-do-ops.html) ”这个 Reddit 帖子是对 Carey 的文章的回应，进一步说明了开发者在这个问题上的两极分化。

这种分歧是 DevOps 的一个主要问题。正如 Aeris Stewart 在之前的一篇文章[中所写的，“当团队中的开发人员不能就他们应该或者能够在多大程度上完成运营任务达成一致时，强迫每个人都以一种通用的方式来完成开发任务会带来灾难性的后果。”不幸的是，这是许多组织在接受这种文化转变时采取的方法。而在这种背景下，主要的后果是显而易见的:DevOps 倦怠。](https://thenewstack.io/devops-is-dead-embrace-platform-engineering/)

那么我们是怎么到这里的呢？

在 2006 年之前，大多数组织遵循一种软件交付的“把它扔过墙去操作”模型。当亚马逊首席技术官沃纳·威格尔宣布该公司已经实施了“你建立它，你运行它”的方法时，他改变了一切。然后，开发人员负责端到端地部署和运行他们的应用程序和服务。这很快成为大多数工程组织努力实现的标准。

一些组织能够很好地驾驭这种文化转变。其他人就没这么幸运了。Kubernetes、GitOps 和 Infrastructure as Code (IaC)等更复杂的微服务架构和技术成为了行业标准。与此同时，开发人员开始对他们的应用程序的生命周期和交付工作流负责。即使是简单的任务也需要对日益复杂的工具链有端到端的理解。

技术和架构日益增长的复杂性，以及对开发人员负责的期望，对许多组织来说都是一个严重的组合。

在这样的设置中，开发人员的认知负荷是压倒性的，并且造成了各种各样的组织效率低下。一个例子是 Humanitec 的 [2021 DevOps 设置:基准测试报告](https://humanitec.com/whitepapers/2021-devops-setups-benchmarking-report#whitepaper)称之为“影子操作”。在这里，经验丰富的后端工程师承担基础设施任务，并帮助团队中经验较少的开发人员完成 DevOps 工作。

这种额外的责任使他们无法专注于开发功能和为公司提供最大价值。该组织的效率因此受到影响。

如果认知负荷是问题的根源，那么解决的办法是什么？对于许多组织来说，关键是[平台工程](https://platformengineering.org/blog/what-is-platform-engineering)，设计和构建工具链和工作流，以便在云原生时代为软件工程组织提供自助服务能力。

[https://www.youtube.com/embed/WCyiUWIB1wU](https://www.youtube.com/embed/WCyiUWIB1wU)

视频

平台工程师构建通常被称为内部开发人员平台的东西，它涵盖了应用程序整个生命周期的操作需求。

平台工程试图通过遵循[平台即产品](https://thenewstack.io/platform-as-a-product-true-devops/)方法来实现真正的开发运维，从而在维护开发人员自由和找到正确的抽象级别之间取得恰当的平衡。

平台团队为使用平台的开发人员铺设阻力最小的路径，称为黄金路径，通过设计推动标准化，并将工具链的各个部分连接在一起，以构建连贯和改进的开发人员体验。这为组织提供了自助服务功能，同时抽象出了增加认知负荷的不必要的复杂性。

成功的平台减少了重复性和人工工作。它们使开发人员无需深入学习所有技术就能完成他们的工作。这给了开发人员独立部署代码的信心，而不用担心会把一切搞砸。

内部开发人员平台也与更低的变更失败率相关，这意味着待命工程师更少的夜班或周末工作。显而易见，所有这些好处都有助于最小化开发人员精疲力竭的风险。

但是搭建平台并不能让认知负荷完全消失。Syntasso 的首席运营官 [Paula Kennedy 正确地问](https://platformengineering.org/blog/cognitive-load)，“除了开发者体验，我们不应该也考虑平台工程师体验吗？”

Kennedy 解释说，认知负荷经常从开发人员转移到平台团队，他们必须想办法将工具的广阔前景整合到黄金路径中。

伟大的 DevOps 倦怠是真实的。平台工程可能是解决方案的一部分，但我们必须小心不要在这个过程中烧毁平台团队。这就是[平台工程社区](https://platformengineering.org/slack-rd)存在的原因:分享专家见解和最佳实践，以便组织能够最大限度地过渡到这一令人兴奋的新学科。

想要深入了解平台工程的方方面面吗？查看我们的[平台工程状态报告](https://humanitec.com/whitepapers/state-of-platform-engineering-report-volume-1)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>