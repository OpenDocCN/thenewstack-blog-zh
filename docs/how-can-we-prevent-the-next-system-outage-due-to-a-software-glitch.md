# 我们如何防止由于软件故障导致的下一次系统中断？

> 原文：<https://thenewstack.io/how-can-we-prevent-the-next-system-outage-due-to-a-software-glitch/>

[](https://www.broadcom.com/info/aiops/docker-monitoring)

 [斯科特·王绍博，CA Automation 产品营销总监

斯科特·王绍博是 CA Automation 产品营销总监——发布自动化。Scott 拥有 20 多年的企业技术经验，在加入 CA 之前，他曾在 Compuware 和 BMC Software 等领先品牌担任领导职务。](https://www.broadcom.com/info/aiops/docker-monitoring) [](https://www.broadcom.com/info/aiops/docker-monitoring)

上个月初，4 月 3 日，欧洲大约一半的航班被延误或取消——影响了大约 50 万旅客。原因？[一个软件故障导致了欧控的增强型战术流量管理系统](https://www.independent.co.uk/travel/news-and-advice/eurocontrol-air-traffic-systems-failure-flights-cancelled-delays-a8286651.html)的重大故障，该系统[协调并安全地最大化所有穿越欧洲领空的航班](https://www.continuitycentral.com/index.php/news/business-continuity-news/2821-lessons-from-the-eurocontrol-it-failure)。在描述这一事件时，Eurocontrol [发推文](https://twitter.com/eurocontrol/status/981143526103805953):

“增强型战术流量管理系统出现了故障。应急程序正在实施中，这将使欧洲网络的容量减少约 10%。将尽快提供进一步的信息。”

后来，欧控对故障做出了如下解释:

“断电的触发事件已经确定，措施已经到位，以确保不会再次发生。触发事件是新软件版本的测试和实际操作系统之间的错误链接；这导致实时系统上所有当前飞行计划被删除。我们相信没有外来干涉。”

欧控事件是最近又一个软件故障导致重大中断、损失和不便的例子。

## 复杂系统面临的挑战

事实上，复杂系统带来了许多挑战和风险。Eurocontrol 的中断与 2012 年骑士资本(Knight Capital)导致的华尔街交易崩溃没有什么不同。在那种情况下，不完整的升级导致旧代码在华尔街引发了一波又一波的买卖订单。影响？骑士资本那天损失了 4.4 亿美元。

风险在于多个系统之间有太多的相互联系和松散的集成。对于大型系统来说，这种相互依赖的网络需要超出人类所能理解的细节和因果关系。需要这些知识来可预测地、重复地将变更安全地部署到这些系统中。

为了更好地了解 IT 专业人员在部署复杂系统时所面临的挑战，我们可以参考一篇名为[复杂系统如何失败](http://web.mit.edu/2.75/resources/random/How%20Complex%20Systems%20Fail.pdf)的论文，该论文由麻省理工学院出版，作者为 Richard I . Cook MD。Cook 博士列举和阐述的 18 个要点对于 DevOps 从业者来说应该很熟悉。

## 失败的根本原因？

关于 Eurocontrol 中断以及本可以采取的预防措施，可以说的很多。尽管 Eurocontrol 做出了声明，但许多细节仍然缺失，因此很难提供具有任何准确度的明确处方。

事实上，库克论文的第七点指出“事故后将事故归因于‘根本原因’是根本错误的。”这是因为复杂系统的故障有多种成因。结果，多个更小的故障可能共同产生一个故障。由于软件在不断更新，任何从根本原因吸取的经验教训实际上可能都不适用于下一次停机，因为复杂的系统会随着每个版本而变化。

最好培养一种安全文化，并有一个可靠的故障计划，甚至像欧控那样手动制定，而不是试图找出谁该负责，这样你就可以解雇他们。具有讽刺意味的是，当失败真的发生时，解雇“负有责任的人”就没什么意义了。这是因为减少失败的最佳预防处方是失败本身的经验。尤其是当我们谈论复杂系统的时候。

## 连续交付自动化的案例

同样，关于这次停机，可以说和推测很多事情。然而，值得考虑的是连续交付自动化如何帮助最大限度地降低风险和部署成本，为部署提供可预测性和可审核性，并潜在地减少对任何停机的响应。

在他们的书《持续交付》中，作者 David Farley 和 Jez Humble 假设用于部署的自动化机制需要对每个环境都相同，而不仅仅是生产前(prod)。这个最佳实践允许自动化机制在整个发布过程中被审查和测试。这意味着，当变更准备好被部署到生产中时，您完全有信心生产部署将像以前被证明和演示过的那样工作。

自动化确保了超出人类能力的精确度和可预测性，尤其是针对复杂系统。自动化提供了巨大的价值，可以确保“测试一个新的软件版本和实时操作系统”是相同的。这是因为在非生产和生产环境中使用了相同的自动化机制。

持续交付自动化工具，比如发布自动化解决方案，提供了超越部署本身的自动化层。功能包括获取所有正确版本的工件、直接集成到 CI 工具和输出、环境数据集建模、依赖关系映射、管道反馈循环等等。这样的解决方案能够帮助协调和响应复杂系统中许多相关组件的测试自动化。结果呢？帮助确保下一个软件故障不会发生

[CA Technologies](https://www.broadcom.com/info/aiops/docker-monitoring) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>