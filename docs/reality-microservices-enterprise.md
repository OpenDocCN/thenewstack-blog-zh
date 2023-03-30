# 企业中微服务的现实

> 原文：<https://thenewstack.io/reality-microservices-enterprise/>

[](https://blog.appdynamics.com/author/jkowall/)

 [乔纳·科瓦尔

乔纳·科瓦尔接受过计算机科学培训，并在 20 世纪 90 年代末与人合作创建了首批内容过滤公司之一。乔纳成为了一名安全专家，负责编写 FreeBSD 项目的代码，并帮助构建了第一个无线破解算法。Jonah 获得了 CISSP 奖和 CISA 奖，以及多项与基础设施相关的认证和奖项。15 年来，我在初创企业和大型企业中担任从业者和管理者，专注于基础设施和运营、安全和性能工程。引领战术和战略运营计划，深入监控和调整基础设施和应用。](https://blog.appdynamics.com/author/jkowall/) [](https://blog.appdynamics.com/author/jkowall/)

据 Gartner 称，微服务正接近膨胀预期的峰值。每个组织的词汇表中都有这个词，但是很少有人理解它的含义。这种趋势比我在过去十年中见过的任何其他应用程序范式都要显著得多。这种最新时尚最令人担忧的部分是缺乏对利用这种新设计模式如何影响您的文化、人员、组织和过程的理解。

大多数组织一直在尝试并向在整个生命周期中拥有特定服务的开发运维团队转移。这些新计划侧重于新产品，这些新产品更加环保，可以用现代 DevOps 思维来设计、构建和运行。最大的挑战是拥有合适的人员和技能，并以文化作为结束。这意味着分担责任，每个人都随叫随到，分享产品的所有权和自豪感。

> 对于不准备重组数据环境来构建解耦微服务的企业来说，微服务垫脚石更有意义。

即使这些趋势变得普遍，大多数企业仍然远离重新设计他们的数据平台。微服务要求数据与服务相结合，而不是在一个大型的共享中央存储库中。如果您的服务依赖于记录系统(大型机、Oracle 数据库、SAP 系统等)，那么您的微服务不符合定义。

数据重构、可靠性以及必须与传统和现代系统兼容的挑战是大多数人面临的障碍。紧密耦合增加了风险，使得策略远非平稳或安全。很多时候，这是通过使用消息队列和大量移动部件来保持数据存储库同步实现的。

## 迷你服务

Gartner 在微服务炒作的兴起过程中已经看到了这一趋势，并创造和开始撰写关于微服务的文章。这些都是 SOA 做得对的。大多数最终会构建服务包装器，在较小的服务之上添加发现、治理和其他功能，而没有 SOA 框架的负担，从而提供两全其美的服务，而没有过去 SOA 项目带来的负担。

对于不准备重组数据环境来构建解耦微服务的企业来说，微服务垫脚石更有意义。尽管 Miniservices 用户不能获得解耦的所有好处，但在遗留系统上构建服务至少可以在一定程度上有所帮助。不利的一面是，复杂性将继续增加，这将增加成本和质量问题，因为这两条路径将继续分歧。最有可能的是，双模团队在应用程序和基础架构方面有不同的策略，这最终也导致了基础架构和云的双模方法。新的结果是缺乏清晰的 IT 战略和方向。

没有真正地分离服务对组织有影响。对于 Gartner 的双峰 IT 战略和研究，一直不乏批评性的讨论。双峰模式的目标不是永远以这种模式运行，而是在坚实的基础上前进的一步。分阶段方法有利于微服务和开发运维的发展。虽然转移到纯敏捷和 DevOps 组织的概念在理论上听起来很棒，但大多数组织无法做到这一点；他们缺乏人才、资金或需求来改变当前日常业务运行的许多遗留系统。

这些策略的结果是技术上和组织内部的复杂性。沟通、标准和文化都会受到影响。拥有对现代和遗留系统的正确可见性至关重要。尽管双峰使得这些团队看起来是独立的，但是它们相互之间极其依赖。双月运营的企业需要正确的数据来快速识别和隔离问题。拥有新老兼容的灵活监控技术至关重要。

监控系统还必须支持应用程序和基础架构的两个方面。它们必须是开放的和可扩展的，同时提供对传统打包应用程序的支持。团队必须一致地共享和交流，当他们使用不同的技术来监控和提供可见性时，这几乎是不可能的。共享当前的服务级别和架构是运营敏捷业务时实现必要的治理所必需的。

由[卡伦·艾姆斯利](https://unsplash.com/@kalenemsley)通过 [Unsplash](https://unsplash.com/?photo=HpiYsNBORAw) 拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>