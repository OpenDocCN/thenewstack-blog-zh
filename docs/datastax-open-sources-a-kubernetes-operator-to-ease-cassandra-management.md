# DataStax 开源了一个 Kubernetes 运营商来减轻 Cassandra 的管理

> 原文：<https://thenewstack.io/datastax-open-sources-a-kubernetes-operator-to-ease-cassandra-management/>

开源的 Apache Cassandra NoSQL 数据库的所有者 DataStax 已经开源了一个 T2 的 Cassandra Kubernetes 操作器，试图让这个数据库成为在 Kubernetes 上进行云原生开发的首选。 [Kubernetes operator](https://kubernetes.io/docs/concepts/extend-kubernetes/operator/) 是一种打包、部署和管理 Kubernetes 应用程序的方法，虽然这不是 Cassandra 的第一个 operator， [DataStax](https://www.datastax.com/) 的首席战略官 [Sam Ramji](https://www.linkedin.com/in/sramji/) 表示，该公司希望通过这一补充来巩固努力。

“我们非常兴奋地看到社区正在以不同的方式使用 Cassandra 并使其成为云原生的。有六个 Kubernetes 运营商，所以我们贡献我们的，开源它，然后努力让每个人都参与到同一个项目中，并找到一种方法来拥有一个伟大的 Kubernetes 运营商，任何使用开源 Cassandra 的人都可以部署它，”Ramji 在接受新堆栈采访时说。

DataStax 的开发者关系副总裁 Patrick McFadin 也表达了同样的观点，他说这个社区真的需要团结起来，让 Cassandra 成为 Kubernetes 的默认网站。

“我们并不是说这是唯一正确的方法。每个人都有同样的问题，管理卡珊德拉会很困难。运行大型集群需要一定的专业知识。我们正试图通过 Kubernetes 来解决这个问题，”麦克法丁说。“有很多项目都在使用 Kubernetes，我们一直在与它们进行交流。运行 Cassandra 的人超级聪明，如果我们合作，我们可以很快解决这个问题，但我们必须合作。”

虽然 Kubernetes 运营商可以帮助用户更容易地将 Cassandra 带到他们的 Kubernetes 环境中，但 McFadin 也强调了在这种部署中运行在 sidecar 中的[管理 API](https://github.com/datastax/management-api-for-apache-cassandra) ，他说这真正使 Cassandra 成为云原生的。

“真正的魔力在于管理 API 中的那个辅助工具，它可以完成繁重的工作。当你运行一个 Cassandra 集群时，每个节点都是独立运行的，但是每个节点都非常重要。那里发生的许多事情都是由边车管理的，启动、关闭、向群集添加新节点、缩小群集。所有这些通常都是非常困难的操作，”麦克法丁说。“sidecar 将消除人类在命令行上键入内容的需要。不幸的是，这就是你现在必须管理 Cassandra 集群的方式。这是非常操作密集的。有了云原生，一切都有了 API。这为 Cassandra 添加了一个管理 API，从而将其带到了 cloud native。”

Ramji 说，之前的部分问题是用户需要提供他们的数据存储以达到最高性能。换句话说，如果您有一个 100 个集群的环境，您可以提供一个能够处理该级别流量的数据存储，但是如果您的 Kubernetes 规模缩小，数据就不能随之扩大。“这是对 Kubernetes 环境的供应，我认为这是当今许多技术的发展方向。挑战在于，什么样的数据环境可以与 Kubernetes 一起横向扩展，一起纵向扩展，一起发展？这一点做得并不好。这是因为这是一个难以置信的难以解决的技术问题，”拉姆奇说。

最终，Ramji 说 Cassandra 是 Kubernetes 的一个更好的数据库选择，部分原因是它是一个多主复制数据库，不需要每次添加一个数量级的数据时都进行分片。

“它会为你处理所有的事情。所以你只要跟它说话，问它同样的问题，写下你一直做的同样的数据。这意味着您可以完全按照 Kubernetes 的方式进行扩展，”Ramji 说。“这就是最大的区别。你不必围绕分片重写你的应用逻辑，因为卡珊德拉不一定要分片。”

DataStax 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>