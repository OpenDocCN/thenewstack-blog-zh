# MayaData Kubera 使用 Kubernetes 来管理数据层

> 原文：<https://thenewstack.io/mayadata-kubera-uses-kubernetes-to-manage-the-data-layer/>

MayaData 是开发 [OpenEBS](https://openebs.io/) 容器附加存储(CAS)软件的公司，该公司推出了 Kubera，这是一款 SaaS 或内部部署软件，增加了许多操作功能，进一步帮助 Kubernetes 和 OpenEBS 管理您的数据层。

“Kubera 专注于 Kubernetes 的运营，将其作为你的数据层，”[Maya data](http://mayadata.io/)CEO[Evan Powell](https://www.linkedin.com/in/epowell/)在一次采访中说道。“但这意味着什么呢？对我们来说，这意味着诸如集群外日志记录、备份、灾难恢复、迁移等。”

借助 CAS，存储软件完全由 Kubernetes 进行容器化和编排，这意味着每个开发人员或 DevOps 团队都可以针对其应用和工作负载拥有自己的专用存储控制器。这与更传统的整体存储架构不同，它能够为每个开发人员或团队提供不同的规则和数据格式，而不是试图让每个人都遵循相同的规则。

“现在你们作为一个团队，作为一个工作量，是松散耦合的。这是一个很大的突破。他们不必担心某种共享的依赖性。你有自己的小储物系统。开始吧，”鲍威尔解释道。“这种分散的数据，松散耦合的数据层，很适合。这就是为什么人们要搬到 Kubernetes 和 DevOps。它使这些小团队能够自治。如果你没有一个数据层来实现这一点，你就打破了这种模式。”

Powell 在一篇关于 CAS 的[博客文章中进一步解释了这一点，他写道:“如果他们只使用共享存储，他们的工作负载必须与使用共享存储的所有其他工作负载竞争，并且必须通过所谓的‘I/O blender’，而通过添加 OpenEBS，他们可以拥有自己的块大小、复制模式、备份策略等- >，并且他们不必请求中央存储机构的许可。”](https://www.cncf.io/blog/2018/04/19/container-attached-storage-a-primer/)

通过扩展 CAS 模型，并以 OpenEBS 为核心，Kubera 提供了 Powell 所说的用户要求的所有操作工具，如集群外日志记录、警报、可视化、报告、备份、维护、合规性检查、故障排除和生命周期自动化。Powell 强调脱离集群的日志记录是使用 Kubernetes 作为数据层的一个突出特性，因为即使是集群也可能失败或被重新调度，并带走日志记录数据。

“我们总是试图提到 Kubera 拥有伐木业。伐木，谁在乎呢，对吧？不，不是集群日志，”鲍威尔说。“这真的很重要，因为当您的集群崩溃时，有时您需要查看日志。显然，如果您将日志保存在集群上，当 Kubernetes 重新安排您的集群或您拥有日志的节点时，您就有丢失日志的风险。”

除了集群外日志记录，Kubera 还支持简化工作负载的配置、管理和监控，包括 Kafka、PostgreSQL 和 Cassandra、有状态工作负载的备份、带有快照和数据克隆控制的可视化，以及合规性检查和警报。鲍威尔解释说，没有 Kubera，用户只能安装和集成各种不同的工具来提供日志和修改等功能。

“他们花时间运行本应帮助他们运行的东西。他们什么时候才能真正管理自己的东西，对吗？因此，我们试图做的是通过 Kubera 为他们减轻这些操作工具的一些操作负担。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>