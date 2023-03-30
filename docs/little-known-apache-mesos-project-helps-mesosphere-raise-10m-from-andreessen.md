# 鲜为人知的 Apache Mesos 项目帮助 Mesosphere 从 Andreessen Horowitz 筹集了 1000 万美元

> 原文：<https://thenewstack.io/little-known-apache-mesos-project-helps-mesosphere-raise-10m-from-andreessen/>

Mesosphere 是一家试图围绕鲜为人知的开源项目 Apache Mesos T1 开展业务的公司，刚刚获得了安德森·霍洛维茨公司 1000 万美元的投资。这就是它吸引这么多现金的原因。

据 Mesosphere 的首席执行官兼联合创始人 Florian Leibert 称，Mesos 是一款用于自动缩放的软件，实际上是在大约 5 年前开发的，已经在 Twitter 的 5 万多个内核上使用。EBay、AirBnB、网飞和 HubSpot 也是它的粉丝。

虽然这些大型网络公司已经发现了 Mesos，但这项技术在企业中并不广为人知。但它可以满足那些试图在其内部数据中心的公共云中采用一些可用技术的公司的需求。

Mesos 管理机器集群，根据需要自动扩展应用。它需要在每台机器上安装一点软件——根据 Liebert 的说法，该软件使用零处理能力和“可忽略不计”的内存——与主调度程序协调。每台机器上的软件向调度程序报告虚拟机或裸机服务器的容量信息，调度程序将作业分配给可用的机器。

“如果一项任务中断，并且没有报告，主控器知道重新安排它，并且知道它在哪里有资源，”Mesosphere 的高级副总裁 Matt Trifiro 说。

Mesos 可以自动扩展各种作业，包括 Hadoop 数据库、运行 Ruby on Rails 的节点和 Cassandra。

Liebert 说，使用 Mesos，Hubspot 将其亚马逊网络服务账单削减了一半。这是因为 Mesos 高效地将工作负载分配给可用的机器。

然而，451 Research 的分析师杰伊·莱曼(Jay Lyman)表示，Mesos 可能对那些试图在内部创建类似 AWS 的环境的企业最具吸引力。AWS 提供了一些自动缩放的[工具](http://aws.amazon.com/autoscaling/ "AWS")。但许多企业仍不愿在公共云基础设施上运行一切。同时，他们不想阻止他们的开发人员利用 AWS 等公共云中的可用功能。他们希望在自己的私有云上提供这些功能。

“你会看到 AWS 式战略的界面遇到了传统的守卫、指挥、控制和稳定，”他说。

Mesos 可以在私有云和 AWS 中运行，为企业提供了最有效地使用内部云和在需要扩展时转移到 AWS 的机会。

然而，Mesos 在这方面有一些缺点。例如，它不运行任何 Windows 或 SAP 等传统应用程序。

然而，“如果一个团队正在考虑云，他们可能已经对 Linux 相当深入了，”Lyman 说。

将来，中间层有可能支持 Windows。莱曼指出，最初，像 Puppet 和 Chef 这样的技术也只支持 Linux。“这说明了中间层的早期性质。现在还很不成熟，”他说。

Mesosphere 的目标是许多企业，他们正在开发越来越多的运行在 Linux 和现代编程语言上的应用程序，以及像 Twitter 和网飞这样的第一代 Web 2.0 公司，这些公司在最初推出时没有像 Mesos 这样的技术。“这是两种最常见的早期用户特征，”特里费罗说。

在今年年底之前，Mesosphere 希望发布带有文档的商业产品，从支持和许可中获得收入。它构建了一个名为 Marathon 的大规模编排工具，并支持 Docker 集成。它目前免费提供打包的 Mesos 发行版，希望能为市场播种。

Mesosphere 目前也在与少数早期客户合作。它帮助 HubSpot 开始使用 Mesos。

Mesosphere 并不是唯一一个追求这个用例的人。现在归戴尔所有的 Rightscale、Scalr 和 Enstratius 都提供某种版本的扩展或云管理技术。Mesosphere 认为，Mesos 和该公司自己的技术超越了市场上的产品，创造了本质上作为一台机器运行的服务器集群。安德森的新投资可能会帮助它获得动力。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>