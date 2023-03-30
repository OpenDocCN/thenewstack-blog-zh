# 云原生社区需要谈论测试

> 原文：<https://thenewstack.io/the-cloud-native-community-needs-to-talk-about-testing/>

KubeCon + CloudNativeCon 欧洲快到了，最近发布的时间表让我们议论纷纷。

 [布鲁诺·洛佩斯

Bruno 是一名产品经理，他一直从事云生态系统方面的工作，是一名授权研究员、全栈开发人员，在过去几年中，他还担任 Kubernetes 为 Mercedes-Benz 开发专有解决方案的项目经理。最近，布鲁诺渴望为开源世界做出更多贡献，并加入了 Kubeshop。](https://pt.linkedin.com/in/bruno-lopes-a73b48103) 

我们期待着大量精彩的演示，但令我们震惊的是，在 100 多个演示中，只有一个是关于测试的。这是整个云原生生态系统中规模最大的以工程师为中心的活动之一！

我决定做一些研究，看看这是否是一个异常现象，以及测试，集成测试，自动化测试，连续测试，单元测试，甚至手动测试，是否在以前的活动中被更广泛地覆盖。

但这似乎是整个行业的趋势。这个[搞什么鬼难道是云族的人？](https://www.cloud-native-conf.wtf/)去年的虚拟会议没有关于测试的讨论。除了一个关于大众汽车如何使用虚拟测试汽车零部件的精彩演讲之外，[红帽的 2021 年峰会没有包括这个内容。三场会谈涵盖了去年在洛杉矶的 KubeCon 的测试，在 2021 年的虚拟欧洲活动中，出现了一个测试主题。](https://developers.redhat.com/summit/2021#assembly-field-sections-64401)

## 在云环境中进行测试

事实上，当我们仔细观察[云的原生环境](https://landscape.cncf.io/?category=continuous-integration-delivery&grouping=category)时，我们会发现没有测试本身的类别。有可能看到一些测试工具的地方是在持续集成和交付类别中，尽管并不是所有的工具都是 Kubernetes 本地的。

仔细观察，我们可以看到这个类别被描述为“使用嵌入式质量保证实现快速有效的开发”的工具的位置，因此它可以放在测试工具类别中，但是也许它可以有助于质量保证/测试有一个自己的类别。

## 我们需要谈谈…

那么，作为在全球软件开发团队工作的云原生工程师，我们为什么不更多地谈论测试呢？为什么我们不像在安全或流程编排方面那样，与社区分享我们的成功、失败和黑客呢？

我们是否停留在考虑像 Kubernetes 这样的平台和测试这样的过程的思维定势中，而忘记了专业测试自动化工具和 QA 工程师可以对过程产生影响？

是因为测试不像我们在瀑布开发周期中工作时那么重要了吗？如果第一次遗漏了什么，现在很容易发布快速的错误修复。

或者仅仅是在 DevOps/site 可靠性工程有经验的人不专注于测试？

我与许多使用云原生工具的工程师交谈，询问他们如何管理他们的测试管道，并提出了这样一个问题:

### 为什么觉得测试在云原生社区不是一个很突出的话题？

以下是他们不得不说的话:

Mario-Leander Reimer，首席软件架构师@ QAware GmbH:

“测试从来都不是一个突出的话题，无论我们是否与云原生社区交流。当短的期限和预算或者对特性的高需求打击团队时，质量保证总是达不到要求。首先牺牲的是 QA 活动。除此之外，如果技术栈和设置变得太复杂，就越难写出好的和大量的测试。这些都是根本原因。”

我还在 [r/kubernetes](https://www.reddit.com/r/kubernetes) 上[提出了问题](https://www.reddit.com/r/kubernetes/comments/tkc6ye/why_do_you_guys_think_testing_is_not_a_very/)，以了解社区的想法。

一位 redditor 说:

u/foottuns:
“我和 openshift 合作；当我们构建或测试一个框架时，我们使用 BDD、Golang 和 godog。自从我在开发运维及基础设施领域开始职业生涯以来，大多数工程师都倾向于放弃这个主题。很多人不喜欢或者太懒。但是，也缺乏工具和文档，这使得人们这样做。”

一些评论者认为测试与 CI/CD 紧密相关，例如:

u/clustersam:
“如今测试是自动化的一个功能。如果你构建了某个东西，你编写了属于管道的测试。如果您发现 QoS 问题，您可以在管道中添加自动测试。如果它是一个需要综合测试的浏览器应用程序，你可以使用 Selenium，在你用手工的方式解决了它之后，把它也扔进管道。

您稍后观察结果，修复问题，管道完成它的工作。

这再加上对生产周期的良好促进，包括人们使用较低的 env，可能就是“这种方式”"

更幽默(或愤世嫉俗)的一面是:

u/fearphage:
“首先想到的是懒惰和冷漠。”

## 我的假设

从社区(包括 DevOps 和 QA 工程师)获得反馈后，我得到的普遍共识是，很容易看出云原生是一个仍在建立其最佳实践的发展中领域。我们可以看看仍在成熟的领域的不同例子。不久前，我们开始听说 DevOps，它带来了更短、更高效的发布周期的概念，这在今天感觉像是一个正常的标准。

最近，我们看到 GitOps 也在遵循同样的路线，我们看到更多的团队正在使用 Git 来管理他们的基础设施。我相信云原生测试将很快跟进，团队不会将测试视为负担或额外的工作，只是“很高兴拥有”，而是过程的一部分，将节省他们大量的开发时间。

## 所以，让我们改变云原生测试

我相信所有阅读这篇文章的人都是像我一样的技术爱好者，可能已经构建和发布产品有一段时间了，我也相信你们中的许多人已经注意到在 Kubernetes 上进行集成测试存在着[重大挑战](https://thenewstack.io/top-5-challenges-in-modern-kubernetes-testing/)，特别是当涉及到在你们的[持续集成/持续交付(CI/CD)管道](https://thenewstack.io/3-ways-to-use-automation-in-ci-cd-pipelines/)中配置测试以遵循 GitOps 方法的时候。这就是为什么我认为像 [Testkube](https://testkube.kubeshop.io/) 这样的项目能够改变游戏规则，让测试在 Kubernetes 中变得更容易。

Testkube 的目标是使测试管道不那么复杂，这样我们的 DevOps 人员的生活变得更容易，并为测试人员提供更多的能力，以更一致和集中的方式管理测试。

似乎很多人都有同样的挫败感。在两个月多一点的时间里，我们的“[云原生测试简介](https://www.youtube.com/watch?v=GVvgLuxdrXE)”视频的浏览量已经超过了 12 万次，对于一个刚刚开始这项计划的小型初创公司来说，这是相当令人印象深刻的。

如果你在 Kubernetes 中运行应用程序，并想改善测试它们的方式，你可能想尝试一下 Testkube。查看我们的[安装文档](https://kubeshop.github.io/testkube/installing/)并检查它是否有助于解决 Kubernetes 上集成测试的挑战。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>