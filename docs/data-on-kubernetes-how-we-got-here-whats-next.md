# Kubernetes 上的数据:我们如何来到这里，下一步是什么

> 原文：<https://thenewstack.io/data-on-kubernetes-how-we-got-here-whats-next/>

底特律——虽然 Kubernetes 不是为处理有状态应用程序而设计的，但超过四分之三(76%)的参与者在 Kubernetes (DoK)社区的数据调查中使用 Kubernetes 上的数据库。

这只是从对 500 名 Kubernetes 用户的调查中获得的[发现之一，不仅在过去的一年中，K8s 在数据工作负载方面的使用有了相当大的飞跃，而且在分析和机器学习方面的使用也有所增长，并且相信使用 Kubernetes 进行数据处理会对他们的组织产生变革性的影响。](https://thenewstack.io/more-database-analytics-workloads-ran-on-kubernetes-in-2022/)

在 kube con+CloudNativeCon North America 的同地活动之一 [DoK Day](https://dok.community/dok-day-north-america-2022/#:~:text=The%20DoK%20Day%20Experience&text=DoK%20Day%20is%20where%20the,Kubernetes%20is%20created%20and%20shared.) 上，一个小组讨论了我们如何走到这一步、学到的经验教训以及在数据项目中使用 Kubernetes 的起点。DoK 社区成立于 6 月，拥有 4000 多名成员，在全球举办了 100 多次聚会。

小组成员是 VMware 的技术主管[邢阳](https://www.linkedin.com/in/yangxing/)；[加布里埃尔·巴托里尼](https://www.linkedin.com/in/gbartolini/)副总裁，云 EDB 本地人； [Patrick McFadin](https://www.linkedin.com/in/patrick-mcfadin-53a8046/) ，DataStax 的开发者关系副总裁； [Bhavin Shah](https://www.linkedin.com/in/bhavin04890/) ，Pure Storage 公司高级技术营销经理；以及戴尔首席开发人员 Ryan Wallner。

首先:为什么用 Kubernetes 做数据？

杨指出，基本上，公司不想运行两种不同的基础设施。

**她说:“他们希望能够像管理应用程序一样管理数据层，使用相同的工具，而且，借助 Kubernetes，您可以轻松部署和扩展 SQL 工作负载。”。**

 **巴托里尼说，不同的人物角色可能会有不同的原因:“如果你是一名开发人员，你可能会对 Postgres 等数据库为你提供的功能感兴趣，你希望将它们引入 Kubernetes。如果您是 Kubernetes 管理员，您可能会对声明性配置基础结构代码感兴趣。所以你在寻找一个可以帮助你以这种方式管理数据库的运营商。”

但他说，他最喜欢的原因是 DevOps 作为一种文化，可以打破开发人员和管理员以及数据库管理员之间的障碍，并将数据库与 Kubernetes 内的应用程序放在一起。

McFadin 坚持认为，如果你在 Kubernetes 之外运行一个数据库，你不能称自己为云原生的。您在两个不同的地方运行您的基础架构。

“在我们有更好的编排框架之前，Kubernetes 是赢家。…这是我们努力构建的未来，它是高度自动化的基础设施，只做我们需要做的事情。但是我们现在已经到了这样一个阶段，我们的基础设施将符合我们的应用程序，而不是我们的应用程序符合我们的基础设施。

“那我们怎么去呢？我们需要能够公开地、定制地做事情。现在数据库还不是这样。当你安装一个数据库时，你就创建了这个每个人都必须向其祈祷的大厦，你做出承诺……你在人类中创造了这些神，他们被称为数据库管理员。那个时代已经结束了。我们需要停止这样做。所有的基础设施都是基础设施。”

Shah 指出了 Kubernetes 可以为数据库带来的日常好处，如高可用性、处理 pod 中断和预算以及执行无中断滚动升级的能力。

作为主持人，Ryan 随后问大家他们从 Kubernetes 的哪里来，以及他们对未来的看法。

麦克法丁谈到了与 Cassandra 的合作，并试图用 bash 尽可能多地实现自动化。然后 DevOps 出现了，Kubernetes 显然是下一个延伸。

“但一直困扰我的是，每次我们在 DevOps 中做一些事情时，数据库从未被包括在内。我一直从事数据基础设施方面的工作，这似乎是个问题。仅仅是在 Cassandra 社区工作，很明显人们在尝试和失败，或者尝试和成功…[但是]我一直想要这样的东西。我们在这里；我们终于有机会了。我们有这个。我们这次真的可以做到这一点，而不必运行安装脚本，”他说。

巴托里尼说，大约 10 年前，他开始与波斯特格里斯谈论德沃普斯。

“我真正喜欢的是 Kubernetes 是数据库和应用程序之间的唯一权威。这就是为什么我说 Postgres 是在 Kubernetes 上的数据库，而不是在 Kubernetes 上的 T2。…如果他们在一起，同一个机构可以控制应用程序、路由和数据库。当我发现 Kubernetes 时，我发现这是可能的。在我看来，到目前为止，这是你能从 Postgres 数据库中获得的最佳体验，”他说。

杨谈到了【容器存储接口】【CSI】和[的演进，生块卷支持](https://thenewstack.io/qa-kubernetes-storage-sig-chair-on-the-state-of-state-in-k8s/)。

谈到 CSI，她说，“它有一些基本的功能，比如创建卷、附加散列装载和卸载。它允许不同的存储系统通过公共 API 将存储链接到容器。

“measure 的一个特性是 CSI 拓扑，它允许 Kubernetes 进行智能调度。这样就可以在运行 pod 的最佳位置动态配置持久卷，并允许您跨不同的域和不同的故障域部署和扩展应用程序。”

Bartolini 说，本地持久性卷的增加是一个游戏规则的改变。沃纳补充说，拥有轻松进行故障转移的能力也很重要。

“我们早些时候从一些会谈中听到，我们运行数据库，有机会，但这不是最好的体验。所以……进化就是社区变得更好，”他说。

沙阿补充道:“如果你在谷歌上快速搜索，比如，为什么要有状态应用程序，或者为什么要使用数据库和 Kubernetes，你不会看到今天早些时候发生的辩论，为什么要在 Kubernetes 的数据库上运行有状态应用程序。(这些会议)展示了情况是如何改善的。”

所以下一个问题是关于经验教训。

“我认为我能给出的最好建议是从第一天开始，”巴托里尼说。“从零开始，规划数据库或基础架构。这是 Kubernetes 的优势之一，通过配置，您实际上可以选择拓扑结构。…因此，我认为下一个挑战是找到一种更好的方法来管理 Kubernetes 集群中的资源。但除此之外，您可以与其他工作负载或专用节点共享一个 Postgres 集群，甚至是运行单个 Postgres 实例的裸机。这些都是通过声明完成的。我觉得很神奇。有很大的灵活性。”

杨敦促人们尽可能使用通用的 API，并了解 Kubernetes 的自愈特性。

麦克法丁指出了三个基本要素:人员、流程和技术。

“对人们来说，最重要的是你不会带着昨天的东西去那里。这并不意味着你必须解雇人。你只需要重新思考你做基础设施的方式。这是一个巨大的变化，它将阻止你在云原生世界中成为你想要成为的人。…流程。我们已经谈过技术了。我认为大多数人需要理解的是，技术可能看起来是一样的。它可能会像鸭子一样嘎嘎叫。但绝对不是鸭子。

“我给你举几个例子。云原生技术现在正在向对象存储靠拢。块存储正在消亡；它会死的，克服它。Flink，Pulsar，Spark，Cassandra 项目——我们现在正在研究——都将使用对象存储。容量存储不会成为块存储。块存储很难。是多方面的。这是我们都必须走的一条路。我们要去未来。挺住。”

参与者都提到了书籍、YouTube 等在线网站和 [DoK 社区播客](https://podcasts.apple.com/us/podcast/data-on-kubernetes-community/id1524821862)等丰富的资源，以帮助 Kubernetes 的新用户了解如何在 K8s 上开始他们的数据项目。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**