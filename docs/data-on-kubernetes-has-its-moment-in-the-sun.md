# Kubernetes 上的数据在阳光下有它的时刻

> 原文：<https://thenewstack.io/data-on-kubernetes-has-its-moment-in-the-sun/>

[MayaData](https://mayadata.io/) 赞助本帖。

 [埃文·鲍威尔

埃文·鲍威尔是 MayaData 的首席执行官。](https://www.linkedin.com/in/epowell/) 

应用需要数据。Kubernetes 上的应用也不例外，这就是为什么我们 MayaData 和 [OpenEBS](https://openebs.io/) 社区多年来一直致力于成为在 Kubernetes 上运行数据的最受欢迎的解决方案(根据去年来自云本地计算基金会的[调查)。在 Kubernetes 上有什么要说的秘密？集装箱附加存储。](https://www.cncf.io/wp-content/uploads/2020/03/CNCF_Survey_Report.pdf)

在本文中，我想解释在 OpenEBS 所体现的[容器附加存储](https://www.cncf.io/blog/2018/04/19/container-attached-storage-a-primer/) (CAS)模式的帮助下，使用 Kubernetes 作为数据层的可能性。

## 不要打破你的 DevOps。小团队统治！

DevOps 和向微服务的转移的一个中心租户是，小团队应该能够选择他们需要的工具，并且应该是自治的和负责任的。共享存储或使用集中的“数据库来管理它们”打破了这种模式。OpenEBS 的容器附加存储让这些小团队重新掌控局面。他们可以选择是否需要一个数据引擎来复制他们的数据库或其他工作负载，或者他们是否信任他们的 Kafka 或 Cassandra 或其他工作负载能够自行处理恢复能力。或者，如果他们有 NVMe 系统，他们可以——第一次——在 MayaData 的 [MayaStor](https://mayadata.io/product) (刚刚达到测试版)的帮助下部署极高性能的 PVC。

## 你的错误或运营债务不会成为黑客新闻的趋势

在过去的几周里，Garmin 和 Red Hat (via Quay.io)已经成为新闻。Garmin 的数据被扣为人质，Quay 的 MySQL 和其他数据管理似乎出现了多次连锁故障，这在其[根本原因分析博客](https://www.openshift.com/blog/about-the-quay.io-outage-post-mortem)中有所解释。

使用像 OpenEBS 这样的 CAS 解决方案可以最小化你的爆炸半径。是的，您可以并且通常会在 core IT 的旧共享存储系统之上运行它，甚至是您最喜欢的大云中的存储服务。然而，a)你不需要，b)无论你做什么，你的爆炸半径将不可避免地小得多。

嘿，这种“松散耦合”的东西(在 CNCF 关于云原生的定义[这里](https://github.com/cncf/toc/blob/master/DEFINITION.md))有很多好处！避免[分布式整体模式](https://thenewstack.io/this-week-in-programming-forget-microservices-monoliths-are-the-way-forward/)的危险，这种模式依赖于云 A 或共享存储 B 微妙地引入到您的环境中。

## 锁定:不要争论，结束它

在[最近的一篇文章](https://thenewstack.io/should-you-really-be-so-worried-about-cloud-lock-in/)中，新的堆栈询问云锁定是否如此重要。他们的结论是，事实并非如此，因为云提供商不会大幅提高价格。

事情是这样的:IT 成本的基线是由戈登·摩尔在 55 年前预测的。因此，当云没有降低价格时，它们正在提高价格。如果你的竞争对手能够在 IT 的成本效益方面获得更多指数级的提升——可能是因为他们没有被锁定，并且能够在 [MayaData 的 Kubera](https://mayadata.io/product) 和 OpenEBS 的帮助下更好地与他们的底层云进行协商——那么他们将能够更好地编写和操作软件，因此他们将在创新和竞争方面超过你。

更重要的是，锁定是传统存储公司商业模式的基本组成部分。他们鼓励你利用他们的特殊能力，一旦你这样做了，他们就利用他们的优势来削弱你的谈判能力。它们也使得在不同供应商的系统之间转移数据变得困难。

通过在 Kubernetes 上运行您的数据，同时扩展 Kubernetes 的功能，您拥有了一个像 Kubernetes 一样可移动的数据平面。如果这些对 Kubernetes 的扩展，比如 OpenEBS，是开源的，那么你就一步到位地减少了对云的锁定，也减少了对旧存储公司的锁定。结果是，您的团队可以自由地做出更明智的决策，并摆脱锁定风险，此外，您还可以节省资金。

## 你并不孤单

保留小团队自主权、减少爆炸半径、防止云和供应商锁定是长久以来的梦想。对于 OpenEBS 的几十个公共参考用户——从彭博到 Arista，从 Orange 到 Comcast 等等——这个梦想正在实现。

因此，请前往 [OpenEBS.io](https://openebs.io/) 进行尝试，或者获取我们名为 [Kubera](https://mayadata.io/product) 的免费个人使用 SaaS 解决方案，将 OpenEBS 作为您的数据层进行部署和管理。

如果您和 Kubernetes 社区中的许多人一样，那么在 Kubernetes 上运行数据是您最关心的事情。如果你想和其他从业者交换意见，我们强烈推荐一个独立的供应商和项目中立的社区，也许并不奇怪，叫做 Kubernetes 社区上的数据。前往 Kubernetes 论坛上的[数据，在那里你可以找到即将到来的会谈的坐标、他们的 Slack 频道、保存在 YouTube 上的过去的讨论等等。](https://dok.community/,)

云计算原生计算基金会和 Red Hat 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

*目前，新堆栈不允许在该网站上直接发表评论。我们邀请所有希望讨论某个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>