# SRE vs Devops vs 平台工程|新堆栈

> 原文：<https://thenewstack.io/platform-engineering/sre-vs-devops-vs-platform-engineering/>

在过去几年中，许多技术公司一直致力于一套通用的最佳实践，即通过在平台上创建和部署应用程序来利用云技术。这些最佳实践可分为三个部分，如分隔或集装箱化、一致和连续的交付，以及开发可观察的系统。

云原生的组织已经发生了巨大的变化，从大型部门变成了核开发团队。两个新功能为这些开发提供了支持:

1.  现场可靠性工程
2.  平台工程

可以说，SRE 和[平台工程](https://thenewstack.io/platform-engineering-what-is-it-and-who-does-it/)团队是典型和传统运营团队的继承者。可以说 SRE 给软件工程领域带来了更多的学科。

## 什么是现场可靠性工程(SRE)？

[站点可靠性工程](https://thenewstack.io/site-reliability-engineering-kind-magic/)是工程师创建能够以可靠方式运行应用程序的系统。SRE 概念的发起始于谷歌，这在[谷歌 SRE 的书](https://sre.google/sre-book/introduction)中有非常清晰的记录。

在 SRE 的帮助下，工程师可以在服务级别定义目标。一旦确定了目标，就要开发系统来实现这些目标。最后，这些系统进一步扩展到平台，这些平台解决了事件管理、故障缓解甚至消除单点故障等领域的问题。

SRE 方法的一个非常重要的方面是，每一次失败都被视为一次失败，并进行详细的根本原因分析，以找到失败的原因。此外，为了在可靠性方面不断进步，在系统级引入了纠正措施。

## 什么是平台工程？

[https://www.youtube.com/embed/WCyiUWIB1wU](https://www.youtube.com/embed/WCyiUWIB1wU)

视频

在这里，平台工程师监控软件开发过程的整个生命周期，从源代码到产品。作为这一过程的一部分，平台工程师开发工作流，帮助软件开发人员快速编码和部署软件。如果我们看一个基本级别的工作流系统，它包括一个源系统，它进一步连接到一个集成系统。

由于应用程序开发人员数量的增加，我们可以预计平台工程师会相应地发展。平台工程师确实花了很多时间指导应用程序开发人员各种最佳实践，以及他们如何利用平台的力量。

## DevOps 是什么？

在过去的十年里， [DevOps](https://thenewstack.io/category/devops/) 获得了巨大的人气。最近兴起的另一个术语是 GitOps。从技术上讲，DevOps 和 GitOps 都是一套松散编纂的原则。这些原则用于监控和管理基础设施的不同元素。

DevOps 从一个更广泛的议程开始，以消除运营团队和开发团队之间存在的传统孤岛。因此，基础设施自动化和工程应用等策略已被广泛接受。

## SRE 对德沃普斯

虽然 DevOps 的重点主要是自动化的什么方面，但 SRE 更关注如何实现。这里有三个不同之处，可以帮助你更好地了解这两者:

1.  新功能:DevOps 负责创建新功能，而 SRE 必须确保不会因为这些新功能而出现进一步的故障。
2.  过程流:DevOps 团队的观点是将应用程序从开发阶段带到生产阶段，因此他们知道所涉及的过程。而 SRE 团队只从生产的角度来看。
3.  重点领域:DevOps 团队主要关注产品开发的速度和连续性。然而，SRE 团队专注于可靠性、可伸缩性和可用性。

## SRE 和平台化工程差异

在 SRE 角色中，最常用的工具[普罗米修斯](https://thenewstack.io/prometheus-at-10-whats-been-its-impact-on-observability/)和 Grafana 主要用于收集不同的指标，如内存消耗和处理器使用情况。然而，平台工程师使用 Crossplane 等工具来管理基础设施，Qovery 帮助他们预览生产环境，而 [GitLab CI](https://thenewstack.io/how-to-improve-your-kubernetes-ci-cd-pipelines-with-gitlab-and-open-source/) 则用于应用程序的持续开发。

为 SRE 和平台工程建立独立团队背后的一个关键因素是角色的差异。虽然 sre 和平台工程师除了编程知识之外，还需要很强的系统工程技能，但角色实际上是不同的。sre 更擅长危机管理，在排除故障时会肾上腺素激增。相反，平台工程师更多的是典型的软件工程师。他们喜欢处理大型复杂的问题，不喜欢被打断。

虽然听起来很相似，但 SRE 团队的目标是为极其可靠的应用程序提供基础设施。平台工程师的目标是创建和交付纯粹用于快速应用程序开发的基础设施。

## 开发运维团队和 SRE 团队的通用工具

如果说 SREs，其中最常用的工具就是普罗米修斯和格拉夫纳。这两个工具用于收集和可视化各种指标。这些指标包括 CPU 使用率、内存和磁盘空间。除此之外，sre 还使用 OP5、PagerDuty、xMatters 等事件报告工具。

然而，如果我们看一下 DevOps 工程师的角色，最广泛使用的工具包括集成开发环境、用于持续集成和开发的 Jenkins、用于变更管理的 JIRA、SVN 和 GitHub。

## 现场可靠性工程、开发运营计划和平台工程如何协同工作

如果我们仔细观察每个团队的工作，SRE 团队主要关注于构建能够可靠运行的应用程序。平台工程师确保这些应用运行的基础设施能够无缝运行。DevOps 是一套有助于加快上述两个过程的过程。因此，这三者必须共同发挥作用，通过它们可以交付可靠的软件应用程序。

## 平台工程与开发运维

虽然有人说 DevOps 只是平台工程的另一个别出心裁的名字，但很少有区分两者的领域。正如我们所知，DevOps 完全是利用工具来简化部署流程，并通过自动化和可视化来进一步管理和监控应用程序。

平台工程使用这些工具、最佳实践和流程来创建可重用的服务和工具，供组织中的不同团队使用。

虽然这三种技术方法有其独立的功能，组织可以选择其中的一种；然而，在理想的情况下，在经历了一系列的过程和最佳实践之后，最好同时拥有这三者，以确保您的技术驱动的自动化项目能够快速、可靠地交付。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>