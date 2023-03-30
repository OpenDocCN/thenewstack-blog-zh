# 随着 Elastic 的 Prelert 收购，Elasticsearch 将很快获得机器学习

> 原文：<https://thenewstack.io/elasticsearch-will-get-machine-learning-elastics-prelert-acquisition/>

搜索和分析引擎 Elasticsearch 背后的公司 Elastic 喜欢今年 2 月在 [Elastic{con}](https://www.elastic.co/elasticon) 上 [Prelert](http://info.prelert.com/products/behavioral-analytics-for-the-elastic-stack) 推出的行为分析整合，它已经[收购了](https://www.elastic.co/blog/welcome-prelert-to-the-elastic-team)该公司。

此举将推动 Elastic 进军机器学习，这对大数据和基础设施监控供应商来说正日益成为一项业务要务。

Elastic 产品副总裁 Gaurav Gupta 说:“他们只是将如此多的功能从盒子中拿出来放在堆栈中。

“我们有客户要求这样做，这真的很难制造。…许多系统会产生误报，或者在许多数据集上运行不佳。我们认为 Prelert 的技术非常普通，但同时从与客户的交谈来看非常准确。他们七年的工作成果不是我们能拿出来的，所以雇佣他们是非常有意义的。”

据 Elastic 的全球营销主管 Jeff yoshi mura[称，这项新技术将允许用户查看 IT 基础设施内的异常情况、安全交易数据内的异常情况或检测欺诈行为。](https://www.linkedin.com/in/jeff-yoshimura-4055)

“这项技术让我们能够为用户提供更复杂的功能，不仅仅是搜索——让数据变得可消费，并对其采取行动，”他说。

它还应该能够在别人已经领先的地方建立自己的 It 监控能力。Datadog 去年进行了自己的[收购](https://thenewstack.io/datadog-adds-big-data-analytics-mortar-data-buyout/)，最近发布了一个应用性能监控(APM)扩展，其中包括基于机器学习的异常检测。新的 APM 供应商 [Instana](https://www.instana.com/blog/monitoring-microservice-applications-introducing-dynamic-graph/) 使用一个 Elasticsearch 集群来解释它的动态图如何深入问题。

Prelert 集成涵盖了 Elasticsearch 和可视化工具 [Kibana](https://www.elastic.co/products/kibana) 。从短期来看，其 API 引擎和对 Elastic Stack 的集成将被标记为 beta，而 Elastic 更正式地将机器学习集成到其 X-Pack 商业产品线中，其中包括 3 月份宣布的 [Graph](https://thenewstack.io/elasticsearch-expands-relationship-modeling-new-graph-plug/) 插件。

## **需要一些指导**

【Prelert 使用的无监督机器学习，在学习过程中没有“老师”指导或纠正它。算法自行发现并呈现数据中有趣的结构。

然而，这并不意味着你可以按下一个神奇的按钮——瞧！—它吐出了令人信服的见解。“它不会取代人类的接触，”Prelert 产品负责人[迈克·帕盖特](https://www.linkedin.com/in/mikepaquette1)说。他将其描述为拥有一个算法助手。

“务实的现实是，需要你自己人的主题专业知识来指导机器学习。他们需要说，‘有这类数据，我认为其中可能有一些有趣的东西。“去模拟这类数据，告诉我是否有什么异常，”

“你可以有没有数据科学学位的人，但他们确实知道数据如何影响他们的业务，所以这种专业知识水平是真正能让这项技术发挥作用的，”他说。

他描述了之前的两个预发布用例:

*   在一家大型在线零售商的后端系统 21 天未能为其最大的客户生成带时间戳的发票后，该公司被召回。没有人注意到这一点，但问题非常严重，影响了公司的年度收益。通过使用机器学习，Prelert 为客户的数千名客户中的每一位建立了随时间推移的正常行为模型，并发现了异常情况——以及客户不知道的其他两种中断。
*   一家全球电信公司在面向客户的在线和商店应用程序方面遇到了问题。在完成销售计划和设备的流程后，用户会发现实际提交订单的按钮不见了。这个问题也影响了客户的底线。使用针对这个仍然存在的问题的概念验证，查看支持该应用程序的所有系统—数据库服务器、网络连接、中间件服务器、应用服务器—以帮助找到并修复这个 bug。

## **业务需求**

人工智能(机器学习只是其中的一个方面)正日益成为商业技术和 IT 工具的“秘方”。想想看，就在这个月:

*   Salesforce 推出了 [Einstein](https://www.salesforce.com/blog/2016/09/introducing-salesforce-einstein.html) ，将机器学习、自然语言处理和预测分析的平台置于其 CRM 产品的背景中。
*   在旧金山的 OpenWorld 大会上，拉里·埃里森概述了一项“自适应智能应用”战略，该战略结合了第三方数据、企业数据和行为分析。
*   IBM 推出了其 OpenPOWER 服务器,旨在提高人工智能工作负载的能力。
*   安全厂商 [Webroot](https://www.webroot.com) 收购了 CyberFlow Analytics，该公司应用机器学习来自动检测网络安全威胁。

古普塔指出，人工智能这些年来被证明相当令人失望，他补充说，他认为现在是时候看到真正的好处了，包括投资回报。

斯坦福大学(Stanford University)一份关于人工智能的新报告指出了目前对该技术兴趣增加背后的各种因素，包括机器学习的成熟，这是由计算能力和基于网络的数据收集的提高推动的；信息处理算法性能的飞跃；数据驱动产品的新平台和市场，以及寻找这些产品和市场的经济激励。

它说，现在最大的挑战是扩展现有算法，以处理极大的数据集——弹性公司的客户拥有的那种数据集。

人工智能或认知计算提供了三个主要的好处， [Manoj Saxena](https://twitter.com/manojsaxena) ，企业家基金的创始普通合伙人和 IBM Watson 的前总经理，在[高盛报告](http://live-cognitive-scale.pantheonsite.io/wp-content/uploads/2015/03/FT-Artificial-Intelligence.pdf)中说。它们增强了向客户提供高度个性化的见解和体验的能力；更好和更及时的决策；并与客户和供应商建立更有利可图的关系。

他说，缓慢采用 it 的公司将失去竞争优势，被更灵活的竞争对手取代。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>