# 问与答:CNCF 应用交付 SIG 主席谈开发者体验和 Kubernetes

> 原文：<https://thenewstack.io/qa-cncf-app-delivery-sig-chairs-talk-developer-experience-and-kubernetes/>

这篇文章是为期三个月的系列文章的第二篇，探讨了 2020 年 Kubernetes 面临的挑战。一月份，我们将研究 Kubernetes 开发人员的体验。

我们已经确定,[Kubernetes](https://thenewstack.io/reality-check-a-peek-at-the-developer-experience-with-kubernetes/)的开发者体验并没有想象中的那么顺畅。这是一个阻碍 Kubernetes 采用的问题——但对于许多提供托管 Kubernetes 服务和专有发行版的公司来说，这也是一个机会。那么怎样做才能让开发者在生产中更容易地使用 Kubernetes 呢？

关于 Kubernetes 和开发者体验的第二篇文章，我们采访了[云计算原生计算基金会](https://www.cncf.io/)的[应用交付特别兴趣小组](https://github.com/cncf/sig-app-delivery)(SIG)[阿洛伊斯·雷特鲍尔](https://github.com/AloisReitbauer)、Dynatrace 首席技术策略师[、阿里巴巴员工工程师](https://github.com/resouer)张磊[和 VMware 高级员工工程师](https://github.com/bryanl)布莱恩·利莱斯[。我们讨论了利害关系，CNCF 和社区中的其他人正在做什么来改善开发人员的体验，以及还有什么其他项目正在酝酿中。这是我们谈话的摘要。](https://github.com/bryanl)

**为什么我们要关心 Kubernetes 的开发者体验？**

**Reitbauer** :公司正在大举投资迁移到云原生架构。我们希望他们成功，而不是因为他们没有意识到事情有多复杂而导致项目失败。这意味着我们需要迎合拥有各种技能的广大开发人员，包括习惯于开发传统企业应用程序的人。

> "对写软件的人来说，给事物命名实际上是一个难题."VMware 的 Bryan Liles

**Liles:** 在过去的六年里，Kubernetes 变得更容易使用了。起初，建立一个集群很困难。现在，您可以使用集群 API 并将对象放入您的集群来创建一个全新的集群。我们从只有 pod 发展到现在有了部署和副本集。但是开发人员没有在那个层面上考虑，我们需要到达我们考虑应用程序和配置的点——对开发人员来说很重要的东西。

**CNCF 正在做些什么来改善 Kubernetes 的开发者体验？**

**Liles:** 在应用交付 SIG 中，我们一直致力于一套指南，解释应用的不同部分，并为每个应用部分命名。对写软件的人来说，给事物命名实际上是一个难题。

Reitbauer :我们正在定义一种联合语言，并在概念上达成一致。我最喜欢的一个例子是，云原生空间中的每个人都喜欢谈论蓝/绿部署和渐进式交付。但是如果你问三个人关于这实际上意味着什么的细节，他们实际上将如何实现蓝/绿交付，你会得到三个不同的答案。

应用交付的部分作用是说，如果这是一个标准概念，它实际上意味着什么？它是如何工作的？

> “使用 Kubernetes 应该更像是开车，而不是造车。”–阿里张磊

**张:**SIG 正在积极思考 Kubernetes 社区缺少什么。我们知道所有的开发者都在抱怨 Kubernetes 的复杂性，但我们实际上认为 Kubernetes 本身应该是复杂的。这是一个管理基础设施层系统的平台。但这并不意味着每个开发者或运营商都应该直接与 Kubernetes 互动。因此，在 SIG 中，我们正在考虑什么是正确的抽象级别。

我们肯定地认为仍然有许多缺失的部分会让开发者更容易地使用 Kubernetes，而不必理解所有的底层技术。当你开车时，你只需要知道如何使用方向盘和刹车，而不是如何制造发动机或变速器。使用 Kubernetes 应该更像是开车而不是造车。

**在更大的社区中，你见过哪些培养体验计划？**

**Liles:** 首先，最新版本的 OpenShift 中的接口改进是一件大事——它专注于工作负载和管道，而不仅仅是 Kubernetes 中的对象。我还在做一个名为 [Octant](https://github.com/vmware-tanzu/octant) 的项目，目标是为 Kubernetes 创建一个更加以开发者为中心的 UI。您有一个工作负载，而不是关注副本集和 pod。Kubernetes 中的所有信息对新手来说都是隐藏的。我们需要更多的人从事这样的项目，重新思考这些界面应该如何工作。

您希望在未来更多地看到什么？

**Liles:**CNCF 会举办这些网络研讨会，通常都是以项目为中心的。例如，如何通过 Argo 进行持续集成。我希望看到 CNCF 在这些网络研讨会上后退一步，更多地谈论为什么。你希望通过持续集成实现什么？为什么持续集成很重要？

具体就 Kubernetes 而言，人们确实应该更容易知道下一步是什么。CI 和持续交付(CD)应该很容易。我们正在取得进展，但需要比现在更容易让人们使用 Kubernetes 来提高工作效率。

**Reitbauer:** 我认为固执己见的方法既有帮助又有点危险，因为你必须平衡标准化的想法，标准化有助于更容易提高生产力，同时需要避免偏袒一个项目。延伸汽车的比喻，我们都同意汽车应该有方向盘和转向灯，但我们可以选择我们最喜欢的汽车品牌。Kubernetes 也应该如此。目前，Kubernetes 中唯一达成一致的是基本构建模块级别。

**张:**是标准的最好归宿，并不一定意味着偏爱某一个项目。“标准”可以仅仅意味着标准化的词汇，正如 Bryan 之前提到的。比如什么是应用？它是一个容器还是一个 pod 还是一个部署？因此，这肯定是 CNCF 应该带头建立的。

> “我们需要迎合拥有不同技能的广大开发人员，包括习惯于开发传统企业应用程序的人。”Dynatrace 的 Alois Reitbauer

Kubernetes 社区中人们感到困惑的原因之一是，Kubernetes 是从堆栈的底部到顶部构建的，侧重于基础设施层。基础设施概念和开发人员/应用层概念之间有巨大的差距。我认为现在是我们将一些重点转移到应用层的时候了。

三位 SIG 主席一致认为，改善开发人员体验不仅是社区关注的问题，而且可能是未来一两年的主要关注点。作为一个可能的例子，Liles 提到了 Kubeflow，它极大地简化了数据科学家使用 Kubernetes 进行机器学习项目的体验。“我们需要将从这些项目中学到的经验应用到编写 web 服务的人身上，”他说。

*为清晰起见，我们对答案进行了编辑和压缩。*

云计算原生计算基金会、Dynatrace 和 VMware 是新体系的赞助商。

来自 Pixabay 的诺埃尔·包萨特写。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>