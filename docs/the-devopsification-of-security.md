# 安全的非人格化

> 原文：<https://thenewstack.io/the-devopsification-of-security/>

[](https://twitter.com/lennypruss)

[Lenny Pruss](https://twitter.com/lennypruss)

[Lenny Pruss 是 Redpoint Ventures 的负责人，他主要从事云基础设施、开发工具和安全方面的投资。他在 Memory Leak 上写了关于开发人员业务的文章。](https://twitter.com/lennypruss)

[](https://twitter.com/lennypruss)[](https://twitter.com/lennypruss)

2009 年 12 月，谷歌成为一系列高度协调、复杂的高级持续威胁(APT)攻击的目标，来自中国的政府支持的黑客窃取知识产权，试图访问并可能修改谷歌源代码——该公司皇冠上的宝石。这场被称为[极光行动](https://www.wired.com/2010/01/operation-aurora/)的攻击被证明是对谷歌基于边界的分层安全模式的公投。

五年后，在 2014 年，谷歌发表了一篇名为“ [BeyondCorp:企业安全新方法](https://research.google.com/pubs/pub43231.html)”的论文，详细描述了该公司彻底的安全改革，过渡到一种无信任模式，所有应用程序都生活在公共互联网上。谷歌写道:

*“如今，几乎每个公司都使用防火墙来加强外围安全。然而，这种安全模型是有问题的，因为当边界被突破时，攻击者可以相对容易地访问公司的特权内部网。随着公司采用移动和云技术，边界变得越来越难以实施。谷歌正在采取不同的方法……我们正在取消对特权内部网的要求，并将我们的企业应用程序转移到互联网上。”*

然而，尽管世界上大部分地区都在努力采用开放、按需的 IT 范式，这种范式的特点是敏捷性和弹性[谷歌帮助定义了](https://medium.com/memory-leak/the-googlization-of-it-three-google-papers-transforming-enterprise-infrastructure-69ad975352e8#.ns4efv57i)，但安全性尚未在云和 [DevOps](/category/devops/) 的形象中重新想象，更不用说谷歌了。

云架构和 [DevOps 原则](/category/devops/)需要轻量级、松耦合和可扩展的系统，但是安全性仍然是孤立的，在开发生命周期之外实现，并且通常通过专有的“黑盒”产品交付。

这就是说，安全性仍然停留在企业 IT 的黑暗时代。打个比方，安全部门把它当成了一座中世纪的城堡:一座有着厚厚城墙的堡垒，被护城河环绕，只有一个戒备森严的出入口。位于墙外的任何东西都被认为是危险的，而位于墙内的任何东西都是可信的。

在单服务器、单一应用程序和定义良好的公司局域网时代，这种模式工作得很好；在主机上安装杀毒软件，在网络周围设置防火墙，你就安全了！但是在云、开发运维及移动世界中，应用程序是分散的，部署是即时完成的，企业边界已被破坏，这些传统方法往好里说是无效的，往坏里说会导致安全运营完全崩溃。

现实情况是，安全性就像 DevOps 一样，不能是你简单购买的东西，它必须是你做的事情，包含原则、实践和产品的集合。

因此，它认为今天的安全范例必须是以应用为中心的、由开发者驱动的、由内而外构建的。

**以应用为中心:**应用现在是企业的命脉，但应用安全传统上是通过代码分析在生产前实施的，然后在生产中被视为端点和/或基于网络的方法的延伸。逻辑是这样的:如果我保护了主机，那么应用程序就是安全的。但是在一个分布式应用的世界里，这些应用是在短暂的计算构建块上动态调度的，你可能甚至不知道你的应用在哪里运行，那么你如何保护它呢？安全性和策略必须融入到应用程序中。保护网络和终端已经不够了，必须保护的是工作负载本身。

**开发人员驱动:**如果安全性是以应用为中心的，它必须 1)集成到应用的生命周期中，2)像可编程基础设施一样实施和管理，这意味着安全性必须随您的应用和云而扩展，并且是开放和可扩展的。像 Hashicorp 的保险库这样的工具提供了对未来的一瞥。

**由内向外构建，而不是由外向内构建:**企业安全被描述为具有坚硬、易碎的外壳，内部黏糊糊的，这意味着一旦边界被突破，攻击者就可以自由支配。构建由内而外的安全性需要优先考虑新的运营工具链，以实现持续监控和测试、策略驱动的控制以及细粒度的授权和访问管理。最重要的是，这需要从预防到控制和应对的认知转变。

相应地，基于这些设计和实施原则，我们看到了新一代产品和公司的出现，这些产品和公司为安全运营提供了类似 DevOps 的功能—可见性、自动化和协作。

> 现实情况是，安全性就像 DevOps 一样，不能是你简单购买的东西，它必须是你做的事情，包含原则、实践和产品的集合。

### 能见度

对于安全分析师来说，“你无法保护你看不到的东西”，因此可见性工具除了提供所有进程间通信的逻辑视图之外，还提供了组织的资产、用户和它们之间的数据流的视图。通过对整个系统的威胁进行可视化和情境化，目标是以更高的保真度检测和阻止异常行为。像 [Illumio](http://www.illumio.com) 、 [Guardicore](http://www.guardicore.com) 、 [CloudPassage](http://www.cloudpassage.com) 、 [vArmour](http://www.varmour.com) 和 [ThreatStack](http://www.threatstack.com) 这样的公司为您的数据中心和/或云做这些事情。 [ProtectWise](http://www.protectwise.com) 、 [DarkTrace](http://www.darktrace.com) 和 Niara 采取以网络为中心的方式，而 [Prevoty](http://www.prevoty.com) 、[对比安全](http://www.contrastsecurity.com)、 [tCell](http://www.tcell.io) 和 [Stackrox](http://www.stackrox.com) 则是以 app 为中心。最终，所有人都在竞争成为网络世界的[数据狗](http://www.datadog.com)或[新遗迹](http://www.newrelic.com)。

### 自动化

与任何一位 CISO 交谈，他们都会告诉你，雇佣和留住合格的安保人员是他们最大的挑战。此外，一般大型企业都部署了 50 到 70 种不同的安全产品。结果是人手不足的团队根本无法跟上当今高速、快速发展的威胁形势。唯一的解决方案是用机器代替人，让系统自动理解并响应警报。像 [Phantom](http://www.phantom.us) 、Evident.io、[除雾](http://www.demisto.com)和 [Hexadite](http://www.hexadite.com) 这样的平台有助于这一点。此外，以高度自动化的方式测试生产环境弱点的新类别正在出现，像 [SafeBreach](http://www.safebreach.com) 、 [Verodin](http://www.verodin.com) 和 [AttackIQ](http://www.attackiq.com) 这样的公司走在了前面。

### 合作

组织逐渐意识到，安全不能再孤立运行了。为了有效阻止或至少减轻复杂的攻击，安全分析师、开发人员和运营人员必须通力合作，并获得统一的数据平台来帮助确定警报的优先级并进行调查，主动寻找新的威胁，并提供分析、审计和报告功能。像 [JASK](https://www.sumologic.com/) 、 [Siemplify](http://www.siemplify.co) 、 [Skybox](https://www.skyboxsecurity.com/) 和隐形 [Awake Networks](http://www.awakenetworks.com) 这样的公司正在帮助定义这个被 Gartner 称为 [SOAR](https://www.gartner.com/doc/3166239/innovation-tech-insight-security-operations) (安全运营、分析和报告)的新类别。

DevOps 最终帮助将工程与运营结合起来，使各种规模的组织能够开发更好的软件，从而更快地将创新推向市场。现在，我们看到类似的做法和工具侵入网络安全，希望减少数量，或至少最小化破坏的爆炸半径。这一切意味着我们正处于一个新的安全时代的开端，在这个时代中，获胜的公司和产品将由开放性、灵活性、UX 及其工作流的能力来定义，而不仅仅是检测算法。

DataDog 和 New Relic 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>