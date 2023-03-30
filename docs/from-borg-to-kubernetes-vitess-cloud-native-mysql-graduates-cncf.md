# 从 Borg 到 Kubernetes: Vitess 的云原生 MySQL 毕业生 CNCF

> 原文：<https://thenewstack.io/from-borg-to-kubernetes-vitess-cloud-native-mysql-graduates-cncf/>

用于 MySQL 横向扩展的数据库集群系统[已经在](https://github.com/cncf/toc/pull/306)[云原生计算基金会(CNCF)](https://www.cncf.io/) 达到了成熟的研究生水平，加入了之前的七个项目，包括 Kubernetes、Prometheus、Envoy、CoreDNS、containerd、Fluentd 和 Jaeger。CNCF 最近一直很忙，杰格毕业，云事件从沙箱推进到孵化，牧场主的长角牛加入沙箱。与此同时，其他几个项目目前正在通过 CNCF 技术监督委员会的尽职调查程序，并即将就准入、晋升或毕业进行投票，包括 [Falco](https://falco.org/) 、 [Harbor](https://goharbor.io/) 、 [Volcano](https://github.com/volcano-sh/volcano) 和 [gRPC](https://grpc.io/) 。

虽然 Vitess first [在不到两年前加入了 CNCF](https://thenewstack.io/cncf-host-vitess/) ，但该项目拥有比许多其他 CNCF 成员更早的云本地印记；正如 CNCF 在一份声明中指出的，Vitess“在 Kubernetes 达到 1.0 之前就支持 Kubernetes，现在它集成并利用了许多其他云原生项目，包括 etcd、gRPC 和 Prometheus。”Planetscale 和 Vitess 的联合创始人兼首席技术官 Sugu Sougoumarane 讲述了该项目早期处理云原生基础设施的经验，这是该项目从 2010 年诞生于 YouTube 的服务器转移到 2013 年在谷歌的前身 Borg 上运行的一部分。

“Vitess 是少数几个真正移植到 Google 的 Borg 中的项目之一，就像它是一个无状态的应用程序一样，这意味着 Borg 会重新安排你的时间，如果它重新安排了这个过程，你的主数据库可以在那里运行，它会擦除你的所有数据。Sougoumarane 解释说:“我们必须在这种类型的重新计划中生存下来，并确保我们永远不会丢失数据。“我们花了大约一年的时间来重新配置 Vitess，以便能够在那种环境中很好地生存，事实证明，我们所做的这些事情使 Vitess 云成为本地的。实际上，我们在 Kubernetes 写出来之前就已经准备好了。这是 Vitess 可以自称为云原生数据库的历史原因。”

> “实际上，在 Kubernetes 还没写出来之前，我们就已经准备好了。这是 Vitess 可以自称为云原生数据库的历史原因。”— [Sugu Sougoumarane](https://www.linkedin.com/in/sugu-sougoumarane-b9bb25) ，Planetscale 联合创始人兼首席技术官，Vitess 联合创始人。

## 一个新的版本带来了对可用性的关注

除了该项目与云原生架构的长期交易之外，随着上周[发布 vitesss 4.0](https://vitess.io/blog/2019-11-05-vitess-4.0-has-been-released/)，以及其毕业的消息，该项目的成熟度也得以展示。这个版本包括对 SQL 查询支持的改进，对 [VReplication](https://vitess.io/docs/reference/vreplication/) 的实验性支持，以及对新用户的可用性改进。除了成熟和年龄，Sougoumarane 说，毕业前的尽职调查过程是一次有价值的经历，可以真正确保项目真正准备好投入生产。

“这肯定是我们应该经历的事情，因为我们必须确保一个项目从所有可能的角度来看都是真正健康的。尽职调查真的会帮你度过难关，”Sougoumarane 说。“实际上，我们不得不回去修改文档和流程中的一些东西，才能让自己做好准备。所以我认为这真的是一个非常好和健康的过程，通过这个过程才能毕业。”

至于这个已有九年历史的项目的下一步会是什么，Sougoumarane 表示，onboarding 和可用性是该项目的两大重点，他解释说，迎合谷歌的需求确实带来了复杂性，可能会使新用户难以使用。

“随着时间的推移，随着我们对 Vitess 的调整，我们引入了大量的选项和标志，一个新加入的人可能会觉得这有点难以承受。我们现在所做的是简化一切，并确保您可以像运行一个极其简单的数据库一样与我们一起运行。这将是我们的重点，”Sougoumarane 说。“另一个原因是，因为它是一个分片系统，有些查询如果你直接发送到 MySQL 会有效，但如果你通过 Vitess，它会立即拒绝它们，因为这些查询在分片系统中可能没有意义。我们想让 Vitess 本质上成为一种替代产品。”

他解释说，现在，Vitess 可以处理 90%以上的应用程序，而不会发生变化，但他们希望这个数字达到 100%。至于采用 Vitess，他说目前有两种选择:[开源项目本身](http://vitess.io)或由 [PlanetScale](https://planetscale.com/) 提供的托管版本。

云计算原生计算基金会是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>