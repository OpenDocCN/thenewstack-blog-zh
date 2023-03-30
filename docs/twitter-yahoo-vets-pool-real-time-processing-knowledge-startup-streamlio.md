# Twitter、Yahoo Vets 在初创企业 Streamlio 中汇集实时处理知识

> 原文：<https://thenewstack.io/twitter-yahoo-vets-pool-real-time-processing-knowledge-startup-streamlio/>

由 Twitter 和雅虎资深人士创办的初创公司 Streamlio 已经秘密推出了一个提供企业级实时数据处理的平台。

该公司的名字来自“流”处理，“ML”代表机器学习，“IO”代表消息传递和存储，并整合了开源项目 [Apache Pulsar](https://github.com/apache/incubator-pulsar) (孵化)、Heron 和 [Apache BookKeeper](http://bookkeeper.apache.org/) 。

这家总部位于加州帕洛阿尔托的公司现在只有 14 名工程师，计划利用由 Lightspeed Venture Partners 牵头的 750 万美元的超额认购 A 轮融资来扩大业务。

他们的愿景的一个关键方面是在没有人工干预的情况下，在企业范围内根据实时数据采取行动的技术。

“世界正在向实时转变，应用程序需要变得由事件驱动，这是一种无人参与的理念。联合创始人兼首席执行官 [Lewis Kaneshiro](https://twitter.com/lewiskaneshiro?lang=en) 表示:“数据在不断地流动，应用程序需要持续可用并与环境相关。

其他联合创始人包括 Heron 的联合创始人 [Karthik Ramasamy](https://www.linkedin.com/in/kramasamy/) 和[Sanjeev Kulkarniare](https://twitter.com/sanjeevrk?lang=en)；[Twitter 的 Apache DistributedLog 技术负责人、Apache 簿记员主席郭思杰](https://github.com/sijie)；以及雅虎 Apache Pulsar 的技术负责人、Apache BookKeeper 的 PMC 成员 Matteo Merli。

## 事件驱动架构

去年 7 月，Gartner 表示[事件驱动架构](http://www.gartner.com/newsroom/id/3758164)，一种软件组件在收到一个或多个事件通知后采取行动的设计，是实现数字化转型目标的关键技术方法。

“组织必须能够响应并利用‘商业时刻’(一个短暂的机会)，这些实时需求正在推动首席信息官们使他们的应用软件更加事件驱动，”Gartner 的 [Anne Thomas](https://www.gartner.com/analyst/37083/Anne-Thomas) [当时](http://www.gartner.com/smarterwithgartner/the-rise-of-the-business-moment/)说。

它将事件驱动架构描述为基础，强调它必须支持连续可用性、大规模可伸缩性、自动恢复和动态可扩展性。

Streamlio 团队着手解决企业在应用程序方面面临的问题，如数据丢失、复杂性、地理复制和无法扩展。

“到目前为止，你可以看到数据驱动的策略推动着可视化甚至报告的发展。人类会对此进行评估，然后做出决定。我们实际上相信，我们正在进入一个令人兴奋的实时行动时代，在这个时代，不仅数据被处理，而且必须有一个潜在的行动与之发生，”Kaneshiro 说。

金融服务中的一个例子是实时提取、转换和加载(ETL)流程，该流程为算法交易提供内部数据湖，或者将 ETL 数据传播到实时系统中。

在智慧城市场景中，基础设施的实时压力数据(如桥梁上的传感器)和天气数据可用于优化交通模式或自动化应急响应服务。

## 企业级

Streamlio 使用 Heron 作为其计算引擎。Twitter 建立了 Heron 作为 Storm 的[替代品，以提高实时流处理的速度和规模。同时，它将 Heron 设计为向后兼容 Storm。在](http://www.infoworld.com/article/3078134/analytics/had-it-with-apache-storm-heron-swoops-to-the-rescue.html)[一篇概述这一转变的论文](https://blog.acolyer.org/2015/06/15/twitter-heron-stream-processing-at-scale/)中，Twitter 报告称，与 Storm 相比，Heron 使用了更少的 CPU 资源，提高了吞吐量，减少了延迟。Twitter 去年开源了这项技术。三年多来，Twitter 一直将 Heron 用于所有实时计算。

据 Heron 团队的工程经理、现任 Streamlio 首席技术官的 Ramasamy 说，Twitter 使用 Heron 的方式包括实时 ETL 和实时商业智能，例如使用位置和主题等因素来确定趋势。

[机器学习](/category/machine-learning/)可以让你持续模拟用户行为的变化，例如，Twitter 将它用于许多用途，如提出建议和实时操作，分析来自 100 多万个来源点的数据，他说。

[https://www.youtube.com/embed/pUaFOuGgmco?feature=oembed](https://www.youtube.com/embed/pUaFOuGgmco?feature=oembed)

视频

消息系统 Apache Pulsar 是雅虎设计和制造的，用于处理数据丢失等问题。雅虎已经使用它三年多了，因为它具有强大的耐用性保证、高吞吐量、低延迟和多数据中心地理复制。Pulsar 于 2016 年末开源。

Apache BookKeeper 的贡献与 Twitter 的分布式日志合并，提供流存储。Twitter 和雅虎已经使用了四年多。它旨在支持企业发布/订阅，提供高性能持久性保证，并且可针对超过一年的存储进行配置。

Streamlio 运行在容器化技术上，使用 Kubernetes 编排。然而，据 Kaneshiro 说，它不仅仅是这三种开源技术的管理版本。

他说:“我们提供的是机器学习模块，这些模块提供了在 Streamlio 平台上运行的端到端企业解决方案。”它在内部、云中、混合中和边缘交付。

作为预览，您可以在笔记本电脑上本地试用 Streamlio Sandbox。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>