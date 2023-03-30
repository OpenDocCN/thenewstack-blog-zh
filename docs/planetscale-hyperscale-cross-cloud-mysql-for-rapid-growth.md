# PlanetScale:超大规模、跨云 MySQL 实现快速增长

> 原文：<https://thenewstack.io/planetscale-hyperscale-cross-cloud-mysql-for-rapid-growth/>

2010 年，YouTube 在可扩展性方面迅速碰壁。作为临时解决方案，它为写流量创建了一个主 MySQL 数据库，为读流量创建了一个副本数据库。但随着猫视频的高度流行，这只是对读取副本的临时修复。写数据库也很快变得不堪重负，导致 YouTube 团队决定，如果对单个 MySQL 实例的需求变得太大，就有必要进行分片。所以它创造了 [Vitess](https://vitess.io/) ，软件[来扩展 MySQL 数据库](https://thenewstack.io/cncf-host-vitess/)到单个服务器之外。

“以这种速度发展基础设施以支持这种流量增长而不损害用户体验真的很难，”T4 联合创始人兼首席执行官吉滕·瓦伊迪亚说。“如果你在云中，你可以为 CPU 和应用程序级别做这件事，你可以开始调配越来越多的机器，你可以开始调配越来越多的进程。所以对于无状态服务来说，很简单。对数据库做同样的事情是困难的，”他说，并补充说 Slack 能够在九天内用 Vitess 将数据库容量增加一倍，而不是像这样的项目通常需要八到九个月。

## **托管 vites**

Vaidya 和 PlanetScale 的联合创始人兼首席技术官 Sugu Sougoumarane 是谷歌创建 Vitess 的 YouTube 团队的成员。他们的公司 PlanetScale 现在提供 Vitess 的管理版本。

在谷歌将该项目捐赠给云计算原生计算基金会后，他们于 2018 年 2 月剥离了这家总部位于加州山景城的公司。Vitess 成为第八个于 2019 年 11 月[毕业](https://www.cncf.io/announcement/2019/11/05/cloud-native-computing-foundation-announces-vitess-graduation/)的 CNCF 项目，加入了 Kubernetes、Prometheus、Envoy、CoreDNS、containerd、Fluentd 和 Jaeger。Vitess 第 6 版于 4 月发布。

该公司首先为 Vitess 提供商业支持，推出了云交易数据库即服务 PlanetScaleDB。最近，它发布了面向 Kubernetes 的 PlanetScaleDB 测试版，使组织能够在云中运行其数据库和应用程序，同时确保所有数据都保留在客户的网络边界内。

他说，测试版提供了应用程序和数据库之间的低延迟，因为它们在同一个 Kubernetes 集群中。PlanetScale 处理软件升级、硬件故障、网络分区，并且因为您的数据保持在您公司的网络边界内，所以公司可以继续遵守它们的安全政策。 ****

PlanetScale 的客户包括 [Slack](https://www.cncf.io/blog/2019/11/25/how-slack-leverages-vitess-to-keep-up-with-its-ever-growing-storage-needs/) 、 [Square](https://developer.squareup.com/blog/sharding-cash) 、 [Pinterest](https://www.youtube.com/watch?v=1cWWlaqlia8) 、GitHub 和 [HubSpot](https://www.youtube.com/watch?v=ZjTraLkMjYM) 。

## **库伯内特土著**

从根本上说，Vitess 是一个分片中间件系统，位于您的应用程序和 MySQL 数据库的分片之间。它让您的应用程序认为它只是在与单个整体应用程序对话，因此您的应用程序不必担心跟踪哪个碎片保存了被查询的数据。为此，它使用内置的成熟的 MySQL 解析器，以及支持的 MySQL 二进制协议。所以它只是将自己作为 MySQL 服务器呈现给应用程序。

它将具有公共记录 id 的数据分组在同一个碎片上，并提供连接池以减少内存开销，从而使平台能够处理高并发性。解析查询后，它会根据需要使用查询限制器，判断查询是需要转到特定的片上还是以其他方式收集数据。

Vaidya 说，它还内置了许多强大的工作流程，用于充电等，因此它也有助于在一台主机下运行数千台主机。

最初设计在裸机上运行，当 YouTube 在 2013-14 年迁移到谷歌云时，Vitess 被迁移到 Kubernetes 的前身 [Borg](https://kubernetes.io/blog/2015/04/borg-predecessor-to-kubernetes/) ，支持 PlanetScale 的断言，即 Vitess 在 Kubernetes 存在之前就准备好了 Kubernetes。

根据 Vaidya 的说法，Vitess 的卖点是 NoSQL 数据库的巨大可扩展性，同时保持 MySQL 的一致性模型。

“在 YouTube 上，最大的一块是 256 个碎片。当然，每个孩子都有一个主人，80 到 120 个复制品分布在世界上的 20 个数据中心。因此，如果您计算一下，就会发现有[25，000]到 30，000 个节点作为单个数据库进行管理，应用程序甚至不需要担心有这么多副本，您的读取会在这些副本之间进行负载平衡，任何应用程序磁盘问题、读取和写入都会发生正确的事情，”他说。

“我们已经构建了一个像 MongoDB 一样可扩展的系统，但是具有完整的关系语义。这是一个完整的事务性系统，因此您可以获得二级索引、事务，并且能够基于您的模式在碎片中共同定位您的数据。我们扩展了关系模式的概念。

他说:“所以我们不会随机地将数据分散到不同的位置，我们会给你很大的控制权，让你决定如何将数据放在一起。”。

他说，与此同时，HubSpot 在 Kubernetes 运营着大约 700 个关于 Vitess 的数据库。它们都是单切片的。所以他们并不是用它来水平分割数据，而是用它来运行 Kubernetes。

HubSpot 的高级软件工程师[Alex Charis](https://www.linkedin.com/in/alexcharis/)说:“Vitess 为我们在 Kubernetes 上统一我们所有的数据存储基础设施和微服务基础设施铺平了道路，它为我们在 Kubernetes 上的其他数据存储提供了蓝图。

PlanetScale 运行在亚马逊网络服务、谷歌云平台和微软 Azure 上，各有四个区域，并自称是真正的多云，使客户能够跨不同的云传播母版和副本。您可以让主服务器在 AWS 上运行，大部分副本也在 AWS 上运行，但是有一个或两个副本在 GCP 上运行，用于灾难恢复和灾难恢复目的，或者从一个云迁移到另一个云。

使用自定义分片功能，您可以根据国家代码、邮政编码或电话国家代码分发您的数据，以遵守 GDPR 等法规。

Vaidya 说，展望未来，该公司计划专注于迁移工具，并使开发分片模式的过程尽可能简单。虽然它现在支持 MySQL 和 MariaDB 数据库，但它计划增加对 Postgres 的支持，但那是以后的事了。

亚马逊网络服务和云计算原生计算基金会是新堆栈的赞助商。

图片由 Free 提供-照片来自 Pixabay

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过[推特](https://twitter.com/thenewstack)或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>