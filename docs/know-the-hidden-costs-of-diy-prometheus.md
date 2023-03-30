# 了解 DIY 普罗米修斯的隐性成本

> 原文：<https://thenewstack.io/know-the-hidden-costs-of-diy-prometheus/>

当普罗米修斯开源系统监控工具包[出现的时候，它给了超负荷工作的可观察性团队在当今的商业世界中取得成功的方法。这是一个基于指标的可观察性系统，可以确保他们的环境按照需要运行。](https://chronosphere.io/learn/inside-prometheus-documentary/)

然而，构建自己的 Prometheus 实例通常只能做到这一步，企业发现在内部运行 Prometheus 既不可扩展也不可靠，不足以应对快速增长的云原生环境。

## 为什么要从基于度量的可观察性的普罗米修斯开始？

DIY(自己动手)普罗米修斯是许多公司开始云原生之旅的自然起点。它是免费的；它是开源的；而且有很大的社区贡献和支持。

然而，随着他们的云原生环境增长，工程师需要更多数据来优化他们的应用程序和基础架构， [Prometheus](https://thenewstack.io/promcon-2022-why-prometheus-had-to-change/) 需要更复杂的架构和更多员工带宽来进行扩展。在某种程度上，几乎每个组织都有这样一种情况，即在内部管理一个复杂的 Prometheus 实现绝非易事。它比您的生产环境成本更高，消耗更多的工程资源。

## DIY 普罗米修斯的四大常见挑战是什么？

## 1.数据变得很难找到

当你听到工程师抱怨他们不能快速定位可观测性数据时，你知道你正在[撞上普罗米修斯](https://chronosphere.io/learn/four-signs-youre-outgrowing-prometheus/)的极限。要扩展 Prometheus，您需要启动单独的实例，并让每个实例存储和抓取来自特定服务的数据。这将在您的 Prometheus 实例之间手动分担负载，但这会在您扩展时导致问题。

### Prometheus 实例的仪表板和警报

从仪表板和警报的角度来看，您需要告诉每个仪表板或警报指向哪个节点/Prometheus 实例，以便[获取数据](https://thenewstack.io/query-optimization-in-the-prometheus-world/)。您还可能有一个需要来自多个 Prometheus 实例的数据的仪表板或警报，因此您联合实例并为原始实例创建一个数据子集。

底线是，扩展 Prometheus 会导致更多的联合节点，这导致您拥有一个更加复杂的 Prometheus 结构。在跨区域或地区执行此操作时，需要联合另一个 Prometheus 实例中的数据，并跨两个区域或地区进行组合。工程师需要记住哪个 Prometheus 实例包含他们正在寻找的数据。您可能会从工程师那里听说，查找数据、运行查询和修复问题的时间太长了。

## 2.可靠性差会导致数据丢失

开箱即用，Prometheus 有一个重要的故障点，因此如果它宕机，您[将丢失活动数据](https://thenewstack.io/how-to-permanently-lose-cloud-data-instantly/)和对历史数据的访问。因此，总是建议运行多个实例，它们都收集相同的端点。这样，如果有一个出了问题，您仍然有一份度量标准的副本。

### 依靠仪表板

另一个最佳实践是运行负载平衡器，并将您的仪表板实例指向负载平衡器。从你得到数据的一个拷贝的意义上来说，这通常是可靠的。问题是，如果您对 Prometheus 实例进行滚动重启，那么当 Prometheus 实例停机并重启时，您的数据中会出现一个间隙。同样，底线是您可能需要长期存储解决方案或远程存储解决方案，或者您可能需要跨多个云区域和云提供商分布以实现容错。这再次增加了工程团队的复杂性和运营负担。

## 3.数据保留时间越长，成本就越高

团队通常会要求将更多数据保留更长时间，以便更有效地进行故障排除。然而，对于长期数据，Prometheus 并不真正高效。没有内置的缩减采样功能。

### 数据保留多长时间会变得昂贵

例如，如果以 30 秒的擦除间隔存储六个月的数据，最终大约是 8k kbps。但是，如果您能够连续六个月向下采样到一小时的分辨率，则大约需要 68 kbps。因此，随着您存储越来越多的长期数据，下采样对于效率变得非常有价值。有一些解决方法，但是它增加了管理的复杂性和工程师时间。

## 4.数据增长迫使艰难的取舍

你正在[撞上 DIY 普罗米修斯](https://chronosphere.io/learn/abnormal-security-chooses-chronosphere/)的极限的一个明显迹象是，你正被迫做出艰难的数据收集与成本权衡。在一个完美的世界里，我们捕捉一切，所以我们总是有我们需要的数据。但实际上，当您从云过渡到原生云时，可观测性数据的绝对数量的增长速度比您的生产环境要快。

如果您以前在虚拟机上运行，现在在容器上运行，那么您的基础架构和云账单基本相同，集群大小也相同。但是，您现在运行的不是数十个虚拟机，而是数百或数千个容器，每个容器生成的遥测数据量与虚拟机相同。你的观察成本高于支持你的应用的基础设施。如果您在迁移到容器化应用程序的过程中减少了监控，那么可能是时候采用更具可伸缩性的解决方案了。

那么如果普罗米修斯跟不上，该怎么办呢？当你已经从你的 [DIY 普罗米修斯实现](https://chronosphere.io/learn/prometheus-native-monitoring-availability-and-reliability/)中获得尽可能多的东西时，是时候[考虑普罗米修斯替代方案](https://go.chronosphere.io/prometheus-native-monitoring-saas-solutions-buyers-guide.html)了。评估解决方案时，一个重要的考虑因素是该解决方案如何利用您在现有 Prometheus 环境中的投资，具体来说:

*   使用仪器
*   数据收集
*   数据呈现(仪表板和警报)

托管解决方案应该利用您的仪器和数据表示，但要减轻内部管理可观测性平台的不断增加的成本和操作负担。

## 超时空球如何帮助

Chronosphere 是为云的原生规模、复杂性和可靠性而从头开始构建的。Chronosphere 通过向工程师提供更快、更可行的警报来帮助他们快速进行分类，从而提高他们的工作效率。此外，这还能让他们花更少的时间监控仪器，将更多的时间投入到创新中，从而推动业务发展。

## 数据

根据 Forrester Research 的研究，一个典型的 [Chronosphere 客户在三年内可以看到 165%的投资回报和 775 万美元的收益](https://chronosphere.io/learn/independent-analyst-study-shows-chronosphere-delivers-165-roi/)。普通客户在转型后将可观察性数据量减少了 48%,同时提高了可观察性指标。

要了解更多信息，请阅读弗雷斯特总体经济影响研究。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>