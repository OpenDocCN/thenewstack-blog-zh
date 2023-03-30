# 混乱的石蕊企业支持更多的实验

> 原文：<https://thenewstack.io/chaosnative-litmus-enterprise-supports-more-experiments/>

[混沌工程](https://thenewstack.io/chaos-engineering-for-cloud-native/)已经成为维护云原生环境中应用程序可靠性的一个越来越重要的过程。与生产前测试不同，混沌工程通过在非生产场景中测试来确定软件何时以及如何在生产中崩溃。

将混沌工程视为可靠性测试与通过[持续集成/持续交付(CI/CD)管道](https://thenewstack.io/category/ci-cd/)对代码和应用程序进行实验之间的重叠，通过获取关于当某些错误被引发时应用程序可能如何失败的指标和数据。

[LitmusChaos](https://github.com/litmuschaos/litmus) 是混沌工程比较流行的开源替代品之一，有 2500 个 GitHub stars 和 400 个 fork。LitmusChaos 的创造者 ChaosNative 周五在其年度用户大会上宣布，该平台的两个企业版正式上市， [Chaos Carnival 2022](http://chaoscarnival.io) 。

ChaosNative Litmus Enterprise 面向寻找自我管理的内部混沌工程工具的开发人员和现场可靠性工程师，而云服务 ChaosNative Litmus Cloud 提供托管 LitmusChaos 控制平面。

在他的混沌嘉年华主题演讲中， [Uma Mukkara，](https://twitter.com/Uma_Mukkara) ChaosNative 的首席执行官和 LitmusChaos 的维护者，描述了他的公司的最新版本 Litmus，建立在开源 Litmus 之上，如何提供与 CI/CD 或 [observability](https://thenewstack.io/category/monitoring/) 平台集成的插件。

Mukkara 说，更重要的是，它还为非 Kubernetes 目标提供了许多高级实验，如 VMware 和其他云平台以及裸机。

## “混沌实验民主化”

Mukkara 说，LitmusChaos 将为不同的应用程序开发“更多的混沌实验:不仅是 Kubernetes，还有运行在云原生生态系统或其他系统上的应用程序，以及传统生态系统”。

“所以，换句话说，我们可以说我们正在使混沌实验民主化，”他补充道。“我们可以期待更多基于应用的实验”成为可能。

穆卡拉说，在 2022 年期间，“实验将成为一种商品”。“这意味着你不需要自己编写基本的混沌实验，因为它们将会提供给你。”

LitmusChaos 创建于 2017 年，并于 1 月从 CNCF 沙盒级被批准成为[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)孵化项目。

Mukkara 说，开源平台支持 50 多个混沌实验，“覆盖了 Kubernetes 的整个资源范围”。其中包括主要的云平台，如那些[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)，谷歌云平台和 Azure offer，以及 Cassandra 和 Kafka 等应用程序。

Mukkara 说:“灵活性是 Litmus 平台的一个非常显著的特点，在这个平台上，你可以进行高度可调的混沌实验，你可以使用这些混沌实验来建立可再次使用的混沌工作流。”“所以，你可以把石蕊实验想象成乐高积木，把混沌工作流想象成有特定用途的乐高玩具。”

对于企业版，寻求将自我管理的混沌工程集成到他们的工作流中的组织[可以下载 30 天的试用版](http://chaosnative.com/onprem)。DevOps 工程师、sre 和寻求混沌即服务的组织[可以免费注册](http://chaosnative.com/cloud)，即时访问他们自己的石蕊控制平面，并连接他们的混沌目标。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>