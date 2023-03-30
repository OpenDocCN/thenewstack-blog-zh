# 关注可持续发展:云效率，而非碳排放

> 原文：<https://thenewstack.io/sustainability-focus-cloud-efficiency-not-carbon-emissions/>

[](https://www.linkedin.com/in/jan-st%C3%BCcke/)

[Jan STücke](https://www.linkedin.com/in/jan-st%C3%BCcke/)

[Jan 是一名专注于产品的营销人员，在软件行业有十年的经验。他在科隆技术大学学习信息经济学，并运用这一知识来确定哪些信息对谁、何时以及为什么重要。](https://www.linkedin.com/in/jan-st%C3%BCcke/)

[](https://www.linkedin.com/in/jan-st%C3%BCcke/)[](https://www.linkedin.com/in/jan-st%C3%BCcke/)

今天有许多全球普及的应用程序——网飞、Zoom 和抖音，例如——使用大量的计算能力。此外，许多创新和重要技术的碳足迹也很大，如[物联网](https://arxiv.org/abs/2105.02082)。所以，是的，数据中心的碳排放和不断增长的互联网流量当然是一个问题。

然而，这不是开发人员或技术社区的其他人可以直接影响的。集体“我们”应该关注的是减少我们现在和未来编码的基于云的数字产品的资源需求。

本文将探讨隐藏的碳成本、与数据中心能耗上升相关的风险、主要云提供商已经在做的事情以及如何实现云中的资源效率。

## **碳是问题所在吗？**

相互矛盾的研究混淆了碳排放和数据中心的问题。一项研究发现，美国数据中心的温室气体排放(GHG)仅占[3150 万吨或 GHG 总排放量的 0.5%](https://iopscience.iop.org/article/10.1088/1748-9326/abfba1#erlabfba1s3)。

然而，耶鲁大学的另一项研究发现，全球数据中心的 GHG 排放量相当于人类影响的碳排放量的 2%以上，[相当于全球航空业的排放量](https://www.atag.org/facts-figures.html)，超过全球电力生产的 2%。

第三项研究指出，与之前引用的报告一样，估算的排放量[并不准确](https://energyinnovation.org/2020/03/17/how-much-energy-do-data-centers-really-use/)，并指出缺乏自下而上的研究，因此无法对全球数据中心使用的能源和这种能源的碳排放进行精确比对。总的来说，结果是不确定的。

幸运的是，无论数据可能告诉我们什么，也可能不告诉我们什么，所有主要的云提供商都承诺使用可再生能源，并且[大量投资于更高效的超大规模数据中心](https://www.datacenterknowledge.com/cloud/synergy-says-number-hyperscale-data-centers-doubled-2015)。他们展示了在计算设施的设计、管理和供电方式中优先考虑基础设施优化和规模。

在 [AWS](https://sustainability.aboutamazon.com/environment/the-cloud?energyType=true) 、[谷歌](https://cloud.google.com/blog/topics/sustainability/google-achieves-four-consecutive-years-of-100-percent-renewable-energy)和[微软](https://blogs.microsoft.com/on-the-issues/2020/07/21/carbon-negative-transform-to-net-zero/)的倡议都有很好的记录。虽然他们为清洁云技术所做的努力值得称赞，但仍然存在一个问题:数据中心必须为他们的电厂保留[柴油驱动的备用发电机](https://www.computerweekly.com/blog/Ahead-in-the-Clouds/Hydrogen-vs-diesel-The-great-datacentre-backup-power-debate)，并且[柴油在最好的条件下只有 6 到 12 个月的保质期](https://www.wpowerproducts.com/news/how-long-can-you-store-diesel/)。像微软这样的大公司正试图找到更好的解决方案来应对这种碳密集型备份技术。天然气和氢燃料电池是更清洁途径的候选，但这些方法仍处于试验阶段。

## **缺乏可再生能源储存技术**

尽管云技术存在许多与碳相关的问题，但令人担忧的不是碳排放，而是运行基于云的应用程序所需的能源需求的快速增长。随着越来越多的任务被数字化，越来越多的计算密集型应用成为主流，[摩尔定律的效率增益可能会超过市场需求](https://www.sciencedirect.com/science/article/pii/S0306261921003019#!)，从而也超过可再生能源生产。芯片和电路设计可以通过提高效率来帮助“平坦化曲线”，但很快就会遇到物理的限制。未来数据中心的能源需求将如何随着其使用的增加而发展，并因当今没有足够大规模的存储技术来存储可再生能源发电而加剧？

更复杂的是，数字领域并不是孤立存在的。其他能源密集型用例，如电动汽车，在能源需求方面与软件竞争，并且[已经达到今天电网的极限](https://www.telegraph.co.uk/news/2021/07/28/blackout-warning-drivers-must-charge-electric-cars-off-peak/)。

## **未来取决于云中的资源效率**

每个人都想为应对气候变化做出贡献，让人类更容易拥有一个可持续的未来。技术社区如何尽自己的一份力量？亚马逊首席可持续发展架构师阿德里安·科克罗夫特对当今不可忽视的云进行了重要观察。也就是说，既然我们已经成功地将云用于数字化转型，为什么不也将其用于[可持续转型](https://www.aboutamazon.com/news/sustainability/cloud-computing-pioneers-new-focus-is-on-sustainability-transformation)？

为了实现这一点，重点需要放在[云效率](https://www.stormforge.io/cloud-efficiency/)上。如今，运行应用程序所需的云资源丰富且易于调配，因此很容易被浪费。在云中过度配置计算资源并不是一个新现象。 [FinOps 生命周期](https://www.finops.org/framework/phases/)为追求云效率提供了一个成熟的框架。

*   第一步:告知。首先，了解您的当前状态以确定提高效率的最佳机会非常重要。这需要深入了解计算堆栈所有级别的资源分配和实际利用率。
*   第二步:优化。通知阶段向您展示资源效率低下的程度，而优化阶段则告诉您如何应对。鉴于当今数字生态系统的复杂性，这并不总是容易的。好消息是，现在可以使用基于[机器学习的优化](https://www.stormforge.io/application-optimization/)来识别和补救云浪费，它可以解释您系统的信号，并建议围绕成本和性能进行峰值优化的更改。
*   第三步:操作。优化不是一次性的活动。鉴于当今云原生应用的动态特性，需要时刻保持警惕以确保最高效率。真正的转变需要在构建和操作您的应用程序的整个团队中灌输可持续性能和效率的文化。

作为技术社区的成员，我们有责任确保应用程序尽可能高效地运行，以便我们有尽可能多的时间来创建可持续的数字化未来所需的能源生态系统。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>