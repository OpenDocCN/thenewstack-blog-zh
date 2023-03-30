# 可观察性应该为你的组织做什么

> 原文：<https://thenewstack.io/what-observability-should-do-for-your-organization/>

关于什么是可观测性，更具体地说，它应该为开发人员提供什么，尤其是那些经常负责检测那些降低系统性能的“未知的未知”的操作人员，业界仍在继续争论。在本期 [The New Stack Makers](/podcasts/makers) 播客中，我们将讨论 observability 应该如何更易于使用，以及它如何更具成本效益。

我们的嘉宾是 [Bartek Plotka](https://uk.linkedin.com/in/bwplotka) ，[红帽](https://www.openshift.com/try?utm_content=inline-mention)的首席工程师，以及[灭霸项目](https://thanos.io/)的 SIG 可观测性技术负责人和[普罗米修斯](https://prometheus.io/)维护者；还有 [Richard Hartmann](https://www.linkedin.com/in/%F0%9F%93%88-richard-hartmann-b71800107/?originalSubdomain=de) ，Grafana 的社区主管，普罗米修斯的维护者， [OpenMetrics](https://openmetrics.io/) 的创始人和[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)的 SIG observability 主席成员。

《新书库》的创始人兼发行人亚历克斯·威廉姆斯主持了这一集。

在 DevOps 环境中定义可观测性以及它提供了什么仍然很困难，因为这个主题太广泛了。哈特曼说，在许多方面，可观察性已经成为一个时髦词，这意味着“它的一些意义消失了”。然而，在当今高度分布式的环境中，它仍然非常有用。

[https://www.youtube.com/embed/fC6OyZrkvFU?feature=oembed](https://www.youtube.com/embed/fC6OyZrkvFU?feature=oembed)

视频

历史上，第一个定义来自控制理论，定义为“能够对内部状态进行推断，或者仅通过查看输入和输出来推断系统的完整内部状态，”哈特曼说。

哈特曼说，可观测性的重点更多的是“让人类理解或使人类能够理解实际发生的事情，什么可能被破坏，什么运行良好，并实际处理数据，从数据中提取关于系统的新知识”。

哈特曼说:“随着它的成熟，我认为人们越来越了解它实际上是什么:让人类了解正在发生的事情，而不是只有一个图表，一些阈值，仅此而已的旧式监测系统。”。“但你也有大量的机器接口……因此，你也可以让机器理解这些数据，还有其他流行词……但关键是要把系统状态和对系统状态的了解视为新信息来源的一个小管道。”

[可观察性应该为你的组织做些什么](https://thenewstack.simplecast.com/episodes/what-observability-should-do-for-your-organization)

对于普洛特卡，可观测性有更直接的定义。可观察性是“更实际的东西:当你真的不知道发生了什么，为什么它停止了，为什么它这么慢，为什么它没有处理你期望它处理的请求量时，当你的应用程序着火时，从本质上调试你的应用程序的能力。”

根据组织的 IT 基础设施，需要做什么可观察性也会改变。哈特曼解释说，拥有以微服务为中心的基础设施的组织通常比拥有传统系统的组织需要更多的跟踪功能。大多数组织还依赖日志和度量来满足他们的可观察性需求，而大型基础设施通常需要更多的度量数据。

哈特曼说，考虑到许多组织要管理的数据量很大，“拥有所有细节”变得非常困难。哈特曼说:“所以，要么你采样，然后丢弃数据，要么你只是引入计数器和其他数字数据，这可以让你对正在发生的事情有一个简单的了解。”。“这一点的美妙之处在于，你已经可以进行大量优化，以利于人类的理解。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>