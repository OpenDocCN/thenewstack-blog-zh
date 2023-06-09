# 云效率的三条腿:成本、性能和速度

> 原文：<https://thenewstack.io/3-legs-of-cloud-efficiency-cost-performance-and-velocity/>

[](https://www.linkedin.com/in/bradascar/)

[Brad Ascar](https://www.linkedin.com/in/bradascar/)

[Brad 是一名资深的云实践者，拥有超过 30 年的行业经验，在 Red Hat、AutoTrader.com 和惠普等公司担任认证的 Kubernetes 管理员和产品经理。](https://www.linkedin.com/in/bradascar/)

[](https://www.linkedin.com/in/bradascar/)[](https://www.linkedin.com/in/bradascar/)

当考虑实现云效率时，它通常与围绕成本的讨论有关。然而，成本只是三脚凳中的一条腿。本文将更好地定义云效率及其三个组成部分—成本、性能和速度—并提供在各个方面实现云效率的建议。此外，我将讨论被称为 Kubernetes 的“房间里的大象”,以及如何克服其固有的复杂性。首先:需要历史和背景来理解云中低效的一些根源。

在云出现之前的“旧时代”,本地数据中心的预算和采购需要购买硬件和软件许可证等物品。，然后进行安装，这需要很长的准备时间，通常需要三个月或更长时间。中央财政控制了这种方式。有了云，这种模式发生了巨大的变化。首先，它是按需提供的，所以你只需在使用时付费。它也更有活力，因为你可以随意开关东西。第二，打破了中央财政采购模式。云允许个人开发者在财务部门不知情的情况下增加或关闭东西。它的动态环境对组织来说是一个巨大的文化转变。这也增加了复杂性。例如，您不仅要在四种不同的节点类型和四种不同的节点大小之间进行选择，还要准确地选择每个节点中用于 CPU 的部分和用于内存的部分。您在不同的节点之间共享所有的资源，这使得一个困难的问题变得更加困难。

系统的动态本质使这一切变得如此复杂。如果你看看云提供商，他们的计费流程非常复杂。您想要什么类型的节点？您想要即时实例、按需实例、保留实例吗？你预付多少钱？您是如何混合保留实例和按需实例的？扩展是需要考虑的一个重要方面，因为您可以通过在需要资源之前添加资源来提升性能，从而避免延迟高峰。但是，如果您为了性能而纵向扩展，那么永远不要关闭它，您只是在为大云做准备，这与您应该做的事情背道而驰。

由于云的复杂性，人们通常会默认过度调配云资源或通过反复试验进行手动调整。这里有一个陷阱:必须在成本效率和损害客户绩效之间做出选择。这个陷阱的一个重要原因是缺乏可见性。除了成本和性能的权衡，还有速度。您可能能够实现性能和成本效率，但这将需要大量艰苦的手动工作。这就是你没有在发布功能上投入的努力。

## **尽管复杂，但实现云成本效益**

实现云效率的第一步是理解问题。了解你把钱花在了哪里，并决定它是否提供了期望的投资回报(ROI)。这种理解超越了只看花费的美元；在某些情况下，降低成本并不是首要任务。仅仅因为一个工程团队比另一个团队多花费 10 倍，这真的是一个问题吗？或者这是合理的吗？他们支持更多的流量吗？他们是否故意过度配置，以便团队可以更快地行动，将新产品推向市场？了解你的花费并确保你获得投资回报可能需要巨大的努力，但这绝对是你的第一步，甚至在优化之前。例如，一个团队可能决定最初为了稳定性而过度配置，虽然这很昂贵，但是没有太多的生产负载，并且优先考虑的是将产品推向市场。后来，一旦产品进入市场，负载增加，成本激增，投入工程时间来降低成本，同时不牺牲性能。

第二，明确取胜的地方。例如，找到孤立的实例——有人启动了它，忘记了它，离开了公司，现在它无限期地运行。这是一个令人惊讶的普遍问题，也可能是削减成本最简单的方法之一。如果削减成本是目的，你有两个基本选择:要么使用更少的资源，要么使用相同的资源，但支付更少的费用，如 AWS 储蓄计划。最终，您必须开始适当调整工作负载，这需要可见性。有成本管理供应商可以识别您的云支出，并允许您关闭任何闲置资源。

关于可见性，云成本失控的部分原因是因为没有人注意到。这并不意味着工程师不关心，他们只是不知道。大多数工程师，如果显示，实际上会尝试自己修复它。这被称为[普锐斯效应](https://powerhousedynamics.com/resources/white-papers/prius-effect1/)。一项研究显示，据观察和记录，大量普锐斯驾驶员会以降低油耗的方式驾驶，从而对有关车辆电池电量的数据可见性做出反应。如果开发者意识到他们的云使用和花费，他们会努力改进。

一句话:云效率超越成本。云效率应该定义为尽最大能力使用您请求的资源。它将性能和成本考虑在内。它考虑了开发人员进行管理云资源所需的手动维护所需的时间。真正的云效率是指在正确的时间拥有正确的资源。

随着云在企业中的快速采用，云效率的考虑是至关重要的，并且需要超越基本的成本分析。如果组织希望充分利用其云基础架构，他们必须考虑云效率凳子的另外两条腿，即性能和速度。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>