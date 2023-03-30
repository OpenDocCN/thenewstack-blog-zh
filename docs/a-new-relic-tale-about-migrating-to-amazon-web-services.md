# 一个关于迁移到 Amazon Web Services 的新老故事

> 原文：<https://thenewstack.io/a-new-relic-tale-about-migrating-to-amazon-web-services/>

从传统数据中心迁移到云原生平台绝非易事，但除了巨大的扩展机会和其他与迁移相关的好处之外，DevOps 团队几乎肯定会在这个过程中学到很多东西。

在这个 New Stack Makers 播客中， [New Relic](http://newrelic.com/?utm_content=inline-mention) 的工程总副总裁 [Wendy Shepperd](https://www.linkedin.com/in/wendy-shepperd-788790) ，描述了将 New Relic 的遥测平台迁移到[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)上的云原生环境的挑战。在这一集由 TNS 创始人兼发行人 Alex Williams 主持的节目中，Shepperd 讨论了 New Relic 向 AWS 转移的关键经验，以及转移后对可观测性的影响。

“在 New Relic，我发现了不同:一个是遥测数据平台的大规模，以及我们正在那里进行的迁移。此外，事情已经发生了很大的变化，所以 Kubernetes 不再是新的了，微服务也不再是新的了，”Shepperd 说。“因此，这不仅仅是迁移到这些东西，而是将负载从我们的内部数据中心转移到公共云中。”

[一个关于迁移到 AWS w/ Wendy Shepperd](https://thenewstack.simplecast.com/episodes/a-new-relic-tale-about-migrating-to-aws-w-wendy-shepperd) 的新遗迹故事

在某些方面，平台迁移的挑战没有改变。Shepperd 说，她保留的可追溯到大型机时代的关键“关键知识”之一是，任何平台迁移“总是会遇到意想不到的挑战”

“这通常需要大量的规划、投资、跨业务的协调，以及一定程度的开拓和进入未知领域。因此，从领导的角度来看，你真的需要预先明确你的使命，明确你将如何实现，并有某种类型的框架和伟大的计划方法，以设置检查点，并在前进的道路上迭代，”谢泼德说。“就像任何主要的复杂软件开发、项目或迁移一样，你真的需要边走边迭代和学习，并期待会有惊喜——不要计划快乐的道路，要计划会有惊喜。”

针对 New Relic 更具体的需求，Shepperd 描述了 New Relic 在一年多前开始计划迁移的过程。很明显，该公司在进行这一转变时不得不将其产能增加一倍以上。Shepperd 说，New Relic 当时只有一个 Kafka 集群，这“已经突破了作为大型集群运行的极限”。她说，New Relic 当时做出的一个关键变化是为其云部署实施了一个蜂窝架构，而不是依赖“一个巨大的 Kafka 集群”。

Shepperd 将蜂窝架构描述为一种在并行计算中非常突出的计算机架构，“基于大规模需要功率并行化的想法，并要求组件相互隔离以实现并行化，”她说。

“这几乎和‘黑客帝国’一样，对吗？因为在我们的架构中，我们部署 Kubernetes 来管理该架构中的所有组件。"所以，细胞内有容器."

谢泼德说，学到的主要经验之一是如何“观察跨多个细胞发生了什么”。New Relic 最初部署了一个单元，后来增加到 10 个，今年应该会超过 100 个。“你如何观察跨平台的健康状况？你如何确定集群整体的健康状况，”谢泼德说。“因此，在观察和理解每个细胞中发生的事情以及理解这些事情的总体意义方面，这些都是一些挑战。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>