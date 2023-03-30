# LitmusChaos 将混沌工程引入 CNCF 沙盒

> 原文：<https://thenewstack.io/litmuschaos-brings-chaos-engineering-to-cncf-sandbox/>

Kubernetes 的云原生混沌工程框架 LitmusChaos 在沙盒级别加入了[云原生计算基金会](https://www.cncf.io/) (CNCF)，成为第一个加入 CNCF 的混沌工程项目。这也是继去年捐赠 [OpenEBS](https://openebs.io/) 之后 [MayaData](https://mayadata.io/) 加入该基金会的第二个项目。

由网飞首创的混沌工程是一种通过故意造成生产环境崩溃来测试系统对网络、应用和基础设施故障的恢复能力的方法。MayaData 首席执行官 Evan Powell 解释说，除了确保弹性，LitmusChaos 这样的工具还有助于确保应用系统以促进弹性的松耦合方式构建。

“在某种程度上，我看到混沌工程被用来保持开发者的诚实。鲍威尔说:“你告诉你的开发人员以一种松散耦合的方式进行构建，这样你就可以在任何失败中幸存下来，他们都会说，‘是的，这当然是我们正在做的事情，但是现在，我只需要将它推向生产’。“嗯，混沌工程所做的就是破坏部分基础设施或环境，或那些依赖关系。你说过它是松散耦合的。事实上，您的系统宕机是因为您认为这个特定的 DNS 服务器无论如何都会正常运行，这是您的责任。”

LitmusChaos 通过 Kubernetes 自定义资源定义(CRD)的方式通过自定义 API 提供这种服务。该工具是可扩展的，允许与其他工具集成，并允许创建自定义实验，然后可以在 [ChaosHub](https://hub.litmuschaos.io) 上共享，这是开发人员和 Kubernetes 网站可靠性工程师(SREs)共享混沌实验的集中位置。

MayaData 联合创始人 [Uma Mukkara](https://in.linkedin.com/in/uma-mukkara) 解释说 LitmusChaos 的实验是“非常非常精细的”，这允许用户将它们分组到更复杂的实验和工作流程中。

“这完全是陈述性的。Kubernetes 开发人员和 sre 希望能够控制他们对 Kubernetes 资源的使用。我们试图将混沌本身定义为 Kubernetes 中的自定义资源。Mukkara 说:“开发者和 sre 可以声明性地定义在哪里使用 chaos。“您可以在基础设施级别、Kubernetes 节点和节点内的其他资源(如内存、CPU、磁盘)上进行，也可以在应用程序级别进行。这是完全可定制的。”

他解释说，通过在 ChaosHub 中共享预定义的实验，用户不需要专业知识，甚至不需要知道细节，而是将随机的混沌引入系统。该中心已与 LitmusChaos 一起捐赠给 CNCF，Mukkara 表示，他们希望加入 CNCF 将吸引生态系统中的更多合作伙伴来进行实验，并与更广泛的社区共享。

流行的图表已经包括杀死豆荚和容器、猪 CPU 使用率和模拟满磁盘的实验，正如 Mukkara 提到的，通过与 [Argo](https://argoproj.github.io/) 的集成，实验可以串在一起，[今年早些时候加入了 CNCF](https://thenewstack.io/argo-the-kubernetes-native-workflow-engine-joins-the-cncf/) 。此外，已经有针对 OpenEBS、Cassandra、Kafka 和 CoreDNS 等项目的混沌图集合。展望未来，Mukkara 说，增加这些收藏是当务之急。

“我们的下一步是真正与其他社区和 Kubernetes 社区本身合作，编写更多的混沌实验和工作流，”Mukkara 说。“产品路线图还将包括 Litmus 的可见性和流程编排门户。监控是混沌工程中非常重要的一部分，因此我们正在通过社区推动的讨论来公开构建这个门户。”

云计算原生计算基金会是新堆栈的赞助商。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过[推特](https://twitter.com/thenewstack)或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>