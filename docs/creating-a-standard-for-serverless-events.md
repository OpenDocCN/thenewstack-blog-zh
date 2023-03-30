# 为无服务器事件创建标准

> 原文：<https://thenewstack.io/creating-a-standard-for-serverless-events/>

[为无服务器事件创建标准](https://thenewstack.simplecast.com/episodes/creating-a-standard-for-serverless-events)

云本地计算基金会(CNCF)去年成立了一个无服务器工作组，以帮助定义无服务器技术以及它们如何适应云本地架构。该小组首先解决的也是最常见的问题之一是缺乏事件和相关元数据的全行业定义。

万事达卡数字架构副总裁、CNCF 无服务器工作组成员肯·欧文斯说:“每个人对事件的定义都有所不同，他们并没有真正考虑事件的背景。”。“我们曾经有过一种常见的模式，那就是能够启动一件事，然后忘掉它，希望它能起作用。我们现在有了更多围绕这些事件所需的业务逻辑，以便更好地了解这些事件的背景和成败。”

缺乏事件的标准使得在生产中很难解决性能问题或找到区分业务的模式。它还阻碍了需要快速、轻松地从其他服务接收事件，以及跨环境交付事件数据和集成服务的开发人员。

CNCF 无服务器工作组的 CloudEvents 规范定义了一个标准的事件格式，其中包括元数据、一些扩展数据和实际的事件有效负载本身。

甲骨文公司无服务器副总裁、CNCF 无服务器工作组成员查德·阿里穆拉说:“我们的目标是在事件系统之间找到一些互操作性，这样你就可以建立相互独立的消费者和生产者，但他们可以说一种共同的语言。

最终，无服务器工作组的目标是帮助确定无服务器功能和应用程序可以且应该如何在云原生环境中运行，以便在最终用户、供应商和云提供商之间建立一致性，并促进互操作性和可移植性。

Arimura 说:“业界正在研究如何将所有这些部分结合在一起，以便社区能够部署基于 Kubernetes 的[无服务器]应用程序。”。"这些进入 Kubernetes 的接口将会是 Knative、Fn Project 和 OpenWhisk 之类的东西."

在本播客中，了解更多关于 CloudEvents 规范、事件驱动架构的特征以及在基于 Kubernetes 的云原生基础设施上部署无服务器应用的一些注意事项。

### 在这个版本中:

[2:44:](https://thenewstack.simplecast.com/episodes/creating-a-standard-for-serverless-events?t=2:44) 为什么我们需要一个围绕无服务器主题的工作组？
[6:47:](https://thenewstack.simplecast.com/episodes/creating-a-standard-for-serverless-events?t=6:47) 在今天的语境下你是如何定义事件驱动架构的
[13:05:](https://thenewstack.simplecast.com/episodes/creating-a-standard-for-serverless-events?t=13:05) 从历史的语境和角度来看有什么比较？
[19:04:](https://thenewstack.simplecast.com/episodes/creating-a-standard-for-serverless-events?t=19:04) 在 Kubernetes
[23:51:](https://thenewstack.simplecast.com/episodes/creating-a-standard-for-serverless-events?t=23:51) 为什么元数据变得如此重要
[28:13:](https://thenewstack.simplecast.com/episodes/creating-a-standard-for-serverless-events?t=28:13) 在整个市场中，新出现的复杂性是什么？

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>