# Nyansa:深入网络健康的分析

> 原文：<https://thenewstack.io/nyansa-analytics-for-diving-into-network-health/>

如此多的供应商抛出“分析”一词，这对网络管理意味着什么？

最近，在田纳西州纳什维尔举行的 [Voyers 会议](https://www.nyansa.com/voyers/)上，Nyansa 首席技术官 [Anand Srinivas](https://www.linkedin.com/in/anand-srinivas-5019a89/) 解决了这个问题，来自优步、Mulesoft、Mission Health、卫斯理大学和其他公司的客户讲述了他们使用其网络分析产品 Voyance 的体验。

“最终，分析会让您的工作流程变得更好。技术是存在的，但它应该隐藏起来，”他说，随后补充道，“收集数据不能是我们所做的一切的结束。”

他指出，网飞、谷歌和亚马逊等公司已经成功展示了 analytics 向客户提供有用信息、见解和建议的能力。

他指出，当你观察网络时，会发现网络中有大量数据——包数据、合成测试、来自无线局域网的数据、来自无线控制器的实时数据、系统日志数据、网络流数据、traceroute 等数据以及来自应用程序端的数据——问题是如何使用这些数据。

他说，提供综合测试、EMS/NMS、NetFlow 收集器或 DPI 引擎的产品以图形和图表的形式提供基本信息，并称之为分析。您可以设置阈值和警报，但是“很明显，基础级别的监控不是分析。它不是获取数据，并为你的工作注入价值、节省时间或洞察力，”他说。

更高级的产品，如 Airway、 [Prime](https://www.cisco.com/c/en/us/products/cloud-systems-management/prime-network/index.html) 和 [Splunk](https://www.splunk.com/) ，提供了热图或分类和搜索日志的功能，但仍无法与谷歌或网飞的推荐引擎提供的洞察力相比。

他提供了这个测试来评估声称提供分析的产品:

*   我有一个问题:X 大楼的 Skype for Business 用户体验是什么样的？分析平台应该能够获取必要的数据源，如 API 和 WAN 数据，并将其与答案关联起来。这可能是一个复杂的问题，如“我在 VLAN 10 上的 DNS 性能如何？”这需要的不仅仅是基本的原始数据。
*   在你没有问题的情况下，它的推荐引擎会告诉你从哪里开始以及如何积极主动。它应该为你提供最有趣和最可行的东西。“我们把它归类为‘采取这一行动对你的钱有什么好处，你应该在哪里采取这一行动’，”他说。
*   第三个方面是提供反馈的能力。例如，网飞有恒星系统。你应该能够告诉系统，它提供的信息是没有用的。Nyansa 提供了一个基线，您应该能够快速判断出更改是否产生了影响。

## “从学习中获得智慧”

首席执行官兼联合创始人 [Abe Ankumah](https://www.linkedin.com/in/abeankumah/) 于 2013 年与斯里尼瓦斯和[现任工程副总裁的丹尼尔坎](https://www.linkedin.com/in/daniel-kan-4502482/)一起创立了该公司。Nyansa(“膝安 sah”)是加纳人说的阿坎语中的一个词，意思是从学习中获得智慧。

Ankumah 说，当他为 [Aruba Networks](http://www.arubanetworks.com/) 和 [Meraki](https://meraki.cisco.com/) 工作时，公司从与客户的互动中成长起来。

Gartner 最近预测[网络性能监控和诊断](https://www.networkworld.com/article/3267851/network-monitoring/network-performance-monitoring-market-poised-for-explosive-growth.html) (NPMD)市场价值 21 亿美元，年复合增长率为 15.9%(CAGR)。然而，云工作负载、异构设备和物联网带来了特殊的挑战。

Nyansa 只专注于用户体验，尽管会议上出现了关于它是否会发展成为配置管理或 SecOps 团队也可以使用的工具的问题。Ankumah 说，客户需求将决定这些事情。

“你已经看到了设备端和应用端的创新，但中间连接它们的东西并不多，”Ankumah 在采访中说。

“用户体验不仅仅是连接到网络，而是‘我对应用程序的体验如何？’我们为 IT 运营部门提供工具，让他们成为网络中更有效的医生。"

该公司提供了一种所谓的“云源”方法，以帮助客户解决有线和无线网络、应用程序或客户端设备中的用户体验问题。

它使用网络上的爬虫或探测器，可以是虚拟机或 1RU 服务器。它从多个来源收集数据，并将低比特率元数据流发送到云后端。该公司花了一年半的时间来构建其推荐引擎，该引擎采用了监督机器学习，使用了 Cassandra、Apache Spark 和 Elasticsearch 等组件。

该系统建立了每台设备的基准性能(在[大学](https://www.nyansa.com/news/press-releases/nyansa-eight-universities-team-deliver-customized-user-performance-management-solutions-%E2%80%A8for-u-s-research-education-community/)中，可能有数千台学生和教职员工设备)以及整个环境的总体基准。用户可以查看特定时间段的性能，或者调用特定设备来解决特定用户的问题。在会议上，卫斯理大学副首席信息官[卡伦·沃伦](https://www.linkedin.com/in/karenvwarren/)谈到了 Nyansa 与 [ServiceNow](https://www.servicenow.com/) 的集成如何为帮助台提供了更多工具。

“云外包”使客户能够匿名地将其性能与运行类似网络基础设施的其他用户进行比较。

## 给行为定价

Ankumah 说，一个区别是该技术能够帮助 IT 部门确定某些行动的成本。

[ZK 研究公司的创始人兼首席分析师 Zeus Kerravala](https://www.linkedin.com/in/zkerravala/)[这样解释](http://zkresearch.com/blog/2017/02/startup-nyansa-helps-companies-quantify-the-impact-of-application-performance/):

例如，Voyance 可能测量出与某个应用程序相关联的 90%的客户端时间发生在单个 VLAN 或特定的 Wi-Fi 接入点上。如果有几个问题，客户机时间的分配为 IT 提供了一种了解如何确定与解决问题相关的资源的优先级的方法。此外，Voyance 为 IT 组织提供了一种为性能问题赋值的方法，并主动衡量变更和升级的投资回报。”

他说，Nyansa 的一大优势是能够对多供应商环境进行故障排除，并建议客户可以创建数字孪生环境，在其中他们可以探索假设情景。

Voyance 的早期用户 Creative Artists Agency 的 IT 总监安迪·加兰(Andy Garland)称之为了解 Wi-Fi 体验的伟大工具。他说，随着时间的推移，Nyansa 已经改善了推荐引擎的洞察力。

“它真的很擅长识别趋势。你可以看到随着时间的推移会发生什么。真的没有工具可以做这种长期趋势分析，”他说。

“我们对 Voyance 又爱又恨，因为它告诉我网络发生了什么，”他说。“我的网络工程师讨厌它，因为它告诉他网络发生了什么。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>