# JASK 采用人工智能实现更智能的安全自动化

> 原文：<https://thenewstack.io/jask-employs-artificial-intelligence-automate-smarter-security/>

将 JASK 加入到寻求通过使用人工智能来减轻不堪重负的安全团队负担的创业公司名单中。这家总部位于旧金山的公司在最近的黑帽会议上发布了 JASK 三叉戟平台。

[JASK](https://www.sumologic.com/) 提供端到端的网络视图，提供“智能警报”，帮助安全专家对问题进行分类，更有效地利用时间。联合创始人[达米安·米勒](https://www.linkedin.com/in/jasklabs/)称之为“安全团队的力量倍增器 10”，指的是许多组织面临的安全人员配备困难。

米勒说，公司是在挫折中诞生的，他讲述了他和联合创始人格雷格·马丁与大型企业客户合作的故事，包括联邦政府机构，他们的技术跟不上快速变化的威胁。

“我们关注的是那些因过时技术导致警报数据或信号数据完全过载而受害最深的企业。…对于传统技术，当您向其中添加网络级数据时，它往往会成为成本驱动因素。当您使用过时的技术时，每天索引这些卷的成本比有效地使用元数据并将其上传到云要高得多，”Miller 说。

该公司的软件即服务平台主要侧重于发现和调查。该公司希望稍后提供响应和自动响应行动的建议。

## 网络可见性

它托管在亚马逊网络服务上，采用了源自谷歌的开源 TensorFlow 机器学习技术。它还使用部署在 Hadoop 版本上的 Apache Spark 内存计算框架，该版本由 Cloudera 策划，名为 [Cloudera CDH](https://www.cloudera.com/products/open-source/apache-hadoop/key-cdh-components.html) 。

它在混合云或内部环境中进行监控，并与现有的安全工具相集成。

在客户的环境中部署了一个轻量级包，它与网络中的数据流相连接。通过与 Gigamon 的合作，它的触角可以延伸到新的 SSL 解密类设备。如果客户愿意，它还可以处理日志数据。

所有这些都安全地传输到云，平台通过机器学习处理数据，并为近即时搜索和探索做好准备。

他解释说，分析师不必查看 10，000 个独特的信号，而是可能会收到三个智能警报，时间线为“这些是围绕这些资产发展的信号，表明这种类型的攻击发生的可能性很高”。

分析师还可以与 UI 进行交互，比如说，如果漏洞评估扫描器总是在周一生成 5000 个新信号。它可以提醒系统这种常规行为，并设置它来观察该行为的任何变化。

它通过“笔记本”提供数据探索和可视化功能，安全分析师可以添加外部和内部环境，以缩短洞察时间。

JASK 允许每一个客户保持单一租赁，同时不断受益于客户之间的学习。每个 JASK 用户都为特定威胁的知识库做出了贡献，新客户可以立即利用人工智能模型之前的所有训练。

“老派的方法是不断添加设备来增加计算能力——添加机箱来增加更多内存、更多存储、更多计算。云更加灵活和动态。它使我们能够为客户提供对数据本身的访问，而不是将其锁定在专有数据库中，”米勒说。

他们现在可以通过 REST APIs 做到这一点。然而，在未来，它正在考虑通过亚马逊 S3 以及公共云对象存储来实现这一点。

## **安全利基**

米勒和马丁于 2016 年 1 月创立了这家公司。他们曾在安全软件供应商 [ArcSight](https://en.wikipedia.org/wiki/ArcSight) 共事，该公司于 2010 年被 HPE 收购。马丁还创立了 ThreatStream，去年变成了[Anomali](http://www.eweek.com/servers/threatstream-renames-and-refocuses-itself-as-anomali)。

该公司最近获得了由戴尔技术资本(Dell Technologies Capital)牵头的 1200 万美元的首轮融资，使其总融资额达到 1450 万美元。

它是 Gartner 称之为 [SOAR](https://www.gartner.com/doc/reprints?id=1-34U4IPG&ct=160502&st=sb) (安全运营、分析和报告)的细分市场的最新参与者，其中包括包括 [DFLabs](https://thenewstack.io/playbooks-machine-learning-key-dflabs-incident-response-technology/) 、[hex idate](https://thenewstack.io/hexadite-uses-ai-automate-routine-security-incident-response/)和 [Swimlane](https://swimlane.com/) 在内的参与者。

“事件响应技术(如 SIEMs)在显示当前安全事件方面功能强大，但过于战术化，无法提供理解当前安全状态的战略价值所需的所有数据。这使得安全团队不得不手动从各种来源收集数据，以获得与其安全状态相关的全局信息，”Gartner 在一份关于该细分市场的报告中指出。

“随着组织越来越多地集中其安全运营并在企业内提供安全服务，为实施安全数据以及协调和整合安全管理流程的技术开辟了一个新的领域。”

一份新的 [McAfee 报告](https://www.mcafee.com/us/solutions/lp/evolution-soc.html)表明自动化正在安全实践中起飞。从 700 多名安全专业人士的反馈中，它发现:

*   71%的高级安全运营中心采用人机结合的方式，在一周或更短时间内完成网络安全调查。
*   在最先进的组织中，37%的组织在不到 24 小时内结束了威胁调查。
*   68%的人表示，需要更好的自动化和威胁搜寻程序来实现领先能力。
*   成功的网络安全团队实现威胁调查自动化的可能性是其他团队的三倍，并在实际威胁搜索方面投入了 50%以上的时间。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>