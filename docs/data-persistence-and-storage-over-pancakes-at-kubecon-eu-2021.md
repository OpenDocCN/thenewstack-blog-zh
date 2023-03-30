# KubeCon EU 2021 上煎饼上的数据持久性和存储

> 原文：<https://thenewstack.io/data-persistence-and-storage-over-pancakes-at-kubecon-eu-2021/>

在今年的[kube con+CloudNativeCon EU 2021](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)上，有些事情是相同的——它仍然是虚拟的，这意味着它吸引了更广泛的国际观众的大量参与——有些事情是不同的——比如几乎每个人都购买了 Kubernetes 和云原生架构，现在只是他们如何使用它。在 KubeCon 的另一个传统中，新的 Stack 举办了一场现场煎饼早餐会，以反映 Kubernetes 的成熟度，特别是在数据持久性和存储方面。

新堆栈发布者 [Alex Williams](https://twitter.com/alexwilliams) 主持了今年的讨论，戴尔技术副总裁 [Itzik Reich](https://twitter.com/itzikr) ，戴尔高级首席产品经理 [Nivas Iyer](https://www.linkedin.com/in/nivasiyer/) ，以及煎饼常客 [云原生计算基金会](https://twitter.com/oicheryl)[生态系统副总裁 Cheryl Hung](https://cncf.io/?utm_content=inline-mention)。

[https://www.youtube.com/embed/rVNc_uT-r6w?feature=oembed](https://www.youtube.com/embed/rVNc_uT-r6w?feature=oembed)

视频

Williams 开始了这场讨论，反思了 Kubernetes 如何在过去 18 个月中成为事实上的容器编排者，以及当前云原生计算的挑战是关于该生态系统中的工具，尤其是围绕持久数据的工具。

Reich 也附和了这一观点，他评论说企业客户群已经真正成熟了。他们不是不确定容器和云，而是更了解他们想用什么。他看到开发人员特别不耐烦，他们现在希望利用工具来简化存储，将存储阵列与上层 orchestrator 集成在一起。

“他们希望像我们对待家中的电力一样对待储物。我们想要按下按钮，在即将发生的魔法中，你知道存储将基本上成为这些容器的持久存储。当然，为了实现这一点，存储需要超级智能，但也要超级简单易用，”他说。

Iyer 补充说，传统架构通常是三层的，第三层的安全性由存储或数据库管理员管理。现在发生的变化是，工作被分散到多个微服务中，开发人员希望并期望拥有更多控制权。

[kube con EU 2021](https://thenewstack.simplecast.com/episodes/data-persistence-and-storage-over-pancakes-at-kubecon-eu-2021)煎饼上的数据持久化和存储

他说，“现在你可以看到每个单独的小型开发团队都在微服务中管理他们自己的数据库，因此没有正在进行的集中数据卫生。因此，现在在 Kubernetes，我看到了一个巨大的机会…他们正在寻求按需存储，但同时它也需要是可用的、有弹性的、可靠的和可恢复的。”

大部分讨论都围绕着数据持久性。持久数据是核心数据，无论什么系统创建了它，什么实例在使用它，它都是存在的，并且可以一次又一次地检索，即使停电也是如此。

> “部署规模越来越大。它们变得越来越复杂。人们对他们的云原生基础架构有着更高的期望。”

谢丽尔·洪，CNCF

Hung 自 2017 年以来一直在关注持续的存储挑战，只是现在组织对尝试它并不那么恐惧。

她解释说:“我现在确实看到，组织已经到了这样一个地步，即考虑使用持久卷和持久工作负载来运行数据库和运行某些部分作为持久性已经不再可怕或不再可怕了。”。她确实注意到，对于转向多云运营的组织来说，持久存储仍然是一个问题。“跨云移动无状态应用程序并不困难，但移动数据和移动分析仍然非常非常困难，”她说。

我们可以跨云复制数据，但这当然会增加成本，并使数据合规性变得更加困难。Iyer 将它比作“用吸管喝数据”，这里的需求是允许您以高度压缩的格式移动数据，同时确保跨所有不同集群和云的数据一致性的工具。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>