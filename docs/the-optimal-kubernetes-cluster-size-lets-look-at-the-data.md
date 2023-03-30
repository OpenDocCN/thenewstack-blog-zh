# 最佳 Kubernetes 集群大小？让我们看看数据

> 原文：<https://thenewstack.io/the-optimal-kubernetes-cluster-size-lets-look-at-the-data/>

[](http://robhirschfeld.com/digital-rebar/)

 [罗布·希施菲尔德

罗布·希施菲尔德是 RackN 的首席执行官兼联合创始人，该公司为以容器为中心的数据中心提供编排软件。他已经在云计算和基础设施领域工作了近 15 年，从早期的 ESX 测试版开始工作，到在 OpenStack Foundation 董事会任职四届。](http://robhirschfeld.com/digital-rebar/) [](http://robhirschfeld.com/digital-rebar/)

TL；DR:较小的集群显然会赢，但原因很重要。

随着 Kubernetes 成为事实上的管理平台，我们仍在思考这意味着什么。挑战在于它存在于专用应用平台和通用基础设施抽象之间的灰色地带。我想了解一组用例是否更常见。

几个月前，我在 Twitter 上自由调查了 Kubernetes 集群。我想知道 Kubernetes 是作为虚拟化平台的大规模替代品出现，还是仅仅作为一个应用程序框架发展。如果是前者，我希望运营商将该平台用作大规模多租户系统，为 Google Borg、VMware vCenter、OpenStack 或 Mesosphere 等“数据中心操作系统”提供通用的运营基准。如果是后者，我希望看到开发人员将该平台作为一个单一的应用程序、生命周期管理系统，为管理持续部署提供改进的自动化。显然，两者都在发生，但其中一个占主导地位，为什么？

在近 30 份回复中，超过一半的人认为较小的特定应用集群是正确的选择。总的来说，回答反映了对小型集群提供的分离、隔离和控制的渴望。我还预计小型集群更有可能利用基于底层虚拟机的 IaaS。这与我的现场轶事相吻合，用户在获得运营经验的同时在现有 IaaS 上利用 k8。

那么，小集群更好吗？对于大多数用例来说，是的。他们将问题的“爆炸半径”最小化，并隔离 Kubernetes 版本和升级问题。Kubernetes 的管理开销很低，所以目前蔓延是可以容忍的。此外，即使缺少多集群治理，云提供商也几乎消除了创建新集群的管理成本。随着多租户运营模式的出现以及运营团队提出治理需求，预计这种趋势将会改变。

我个人对这次调查的问题是预测裸机 Kubernetes 的趋势线。由于裸机服务器更大，我们更有可能看到它用于更大的多租户集群，以便用户可以像虚拟机云一样共享资源。这种使用案例虽然不太常见，但在调查中明显出现，并表明裸机集群需要更多时间。

还值得注意的是 OpenStack 社区使用 Kubernetes 作为底层的临时方法。由于 strategy 是将单个功能集群作为安装程序来构建，所以这实际上是一种小集群方法，对提高 Kubernetes 的更广泛可用性没有任何帮助。我观察到其他独立软件供应商(ISV)也在尝试类似的策略，采用单一应用程序 Kubernetes 作为安装程序；然而，这种方法带来了新的挑战，因为供应商还没有准备好解决必要的 Kubernetes 发行版或安装问题。

我的观点是，小型集群总是会在投票中胜出，因为它们的设置和操作更简单。这意味着小客户是 Kubernetes 的门户；然而，我不认为这说明了全部情况。在大型共享集群方面有足够的动力来预测 Kubernetes 将成长为一个更常见的基础设施底层。今天，名称空间的采用可能有限，但是池表明它们变得越来越普遍。名称空间[允许集群中的多个用户限制他们在集群中的范围和可见性](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/)。它[不是一个完整的多租户功能](https://blog.jessfraz.com/post/hard-multi-tenancy-in-kubernetes/)，但目前提供了一些相同的好处。

## 原始资料

*公众意见(以其原始形式)与 Twitter 属性一起提交以供参考:*

### 小型集群的注释

### 支持大集群规模的意见

### 基于名称空间的集群的注释

### 混合规模集群的注释

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>