# 混乱工程在混乱采购之前从 Harness 的 CI/CD 中消失

> 原文：<https://thenewstack.io/chaos-engineering-was-missing-from-harness-ci-cd-before-chaosnative-purchase/>

Harness 对 ChaosNative 的收购不仅显示了其 CI/CD 平台是如何缺少 chaos 工程集成的，还反映了 Harness 确信 CD/CD 平台普遍缺乏这种能力。

在近期内，Harness 将把混沌石蕊企业的名字改为 Harness 混沌工程，它将作为一个独立的模块提供。Harness 将把 ChaosNative Litmus Enterprise 与 Harness CI/CD 平台“非常紧密地”集成在一起，它将在其他 CI/CD“功能标志”工具中可用，[Harish Dodd ala](https://www.linkedin.com/in/harishdh)Harness 产品管理高级总监告诉新的 Stack Harness 试图将 ChaosNative Litmus Enterprise 与其平台集成在一起，就像它试图通过将它在 2020 年购买的无人机转变为 [Harness CI 社区版](https://harness.io/platform/continuous-integration/)开源项目来简化其 CI 产品一样。

然而，这并不意味着 DevOps 团队不会使用 Harness 混沌工程模块，如果他们不采用 Harness 的平台的话。“这不是‘要么接受，要么放弃’，也不是‘要么使用我们的平台，要么什么都不用’”，哈斯霖 CMO [Scott Sanchez](https://www.linkedin.com/in/scottcsanchez) 告诉新堆栈如果你有一个不同的 CI 或 CD 平台，你想把这个或另一个线束模块，它肯定会工作。

## 继续扩张

Harness 将继续扩展 ChaosNative 的能力，包括其在开源软件 LitmusChaos 的开源开发中发挥主导作用的计划(Harness 以前并不是该项目的主要贡献者)。

换句话说，Harness 对采用 LitmusChaos 的独立企业版寄予厚望，无论它是与 Harness '还是另一个 CI/CD 平台一起使用。多达拉说，这是因为在今天的 CI/CD 世界中，混沌工程严重缺乏，特别是对于高度复杂和分布式的微服务和 Kubernetes 环境。

“LitmusChaos 的创造者们早就注意到有多少企业需要通过混沌工程做很多定制实验，”Doddala 说。

## 混沌工程的出现

[混沌工程](https://thenewstack.io/chaos-engineering-for-cloud-native/)已经成为维护云原生环境中应用程序可靠性的一个日益重要的过程。与生产前测试不同，混沌工程通过在非生产场景中测试来确定软件何时以及如何在生产中崩溃。

可以将混沌工程视为可靠性测试与通过[持续集成/持续交付(CI/CD)管道](https://thenewstack.io/category/ci-cd/)对代码和应用程序进行实验之间的重叠，通过获取关于当某些错误被引发时应用程序可能如何失败的指标和数据。

具体到 Harness 购买的 ChaosNative 的产品，ChaosNative Litmus Enterprise 已经帮助 [DevOps](https://thenewstack.io/category/devops/) 和站点可靠性工程师(SREs)采用自我管理的 chaos 工程工具，而云服务 ChaosNative Litmus Cloud 提供托管 LitmusChaos 控制平面。

## 流行替代品

事实上，混沌工程对于 DevOps 团队已经变得越来越重要，特别是那些寻求通过能够将混沌工程应用到生产周期的最开始来增加敏捷性的团队。它还被视为一种方法，通过允许所有团队参与混沌工程而不减慢生产周期，来帮助消除开发人员、安全和运营 DevOps 团队成员之间经常谈论的孤岛。

[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk/) 告诉 New Stack，混沌石蕊企业和混沌石蕊云是两种受欢迎的选择。“将 left chaos 作为 CI/CD 管道的一个组成部分，对于成功的数字化转型至关重要，因为它向产品团队灌输了一种负责任和可靠的文化，”Volk 说。“这降低了利用现有微服务创建创新业务解决方案的门槛，从而从现有代码中获取更多价值。因此，混沌工程和 [CI/CD 流水线自动化](https://thenewstack.io/3-ways-to-use-automation-in-ci-cd-pipelines/)之间的集成对于企业客户来说非常有趣。”

LitmusChaos 的诞生是出于提高弹性和“在生产中建立对云原生服务的信心”的需要，[chaos native 的首席执行官和 LitmusChaos 的维护者 Uma Mukkara 在](https://twitter.com/Uma_Mukkara)[博客文章](https://harness.io/blog/news/chaosnative-is-joining-harness/)中写道。Mukkara 写道:“最初是为了给基于 Kubernetes 的微服务提供开箱即用的混沌实验，最终发展成为一个端到端的框架，在各种应用和基础设施目标上进行混沌工程，支持多租户、SLO 验证和自定义工作流等功能。”

LitmusChaos 创建于 2017 年，并于 1 月从 CNCF 沙盒级被批准成为[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)孵化项目。

Mukkara 今年早些时候在[说，这个开源平台支持 50 多个混沌实验，“覆盖了整个 Kubernetes 资源范围”。其中包括主要的云平台，如那些](https://thenewstack.io/chaosnative-litmus-enterprise-supports-more-experiments/)[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)，谷歌云平台和 Azure offer，以及 Cassandra 和 Kafka 等应用程序。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>