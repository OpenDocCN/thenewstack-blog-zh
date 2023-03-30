# 易碎的数据给 Postgres 带来了一个 Kubernetes 操作员

> 原文：<https://thenewstack.io/crunchy-data-brings-kubernetes-operator-postgres/>

Crunchy Data 的新 Kubernetes 操作符允许用户自动创建 PostgreSQL 数据库和集群。

CoreOS 于去年 11 月在 CloudNativeCon 引入了操作符 T1 的概念，作为使用本地 API 管理外部资源 T3(包括数据库)的一种手段 T2。

CoreOS 的首席技术官 [Brandon Philips](https://github.com/philips) 在[发布概念](https://thenewstack.io/coreos-contributes-operators-containers-configure-kubernetes/)时解释道:“运营商是一个软件，它本质上知道很多运营最佳实践，不管运营商是为什么软件构建的，并且可以在 Kubernetes 的基础上以良好的配置部署该软件，然后随着时间的推移保持它的健康。”。

Crunchy Data 数据架构师 Jeff McCormick 表示，他一直在等待 Kubernetes API 成熟到足以支持 Postgres 操作符。它的操作程序是一个名为“pgo”的命令行实用程序，可以在 Kubernetes 1.5 及更高版本上运行。

“我们想做一些本地的东西，这是 Kubernetes API 的本地特性。它利用了第三方资源和正在大力开发的新的 Golang Kubernetes 客户端 API。

Crunchy Data 是一家提供开源 Postgres 商业版本的供应商，它的初始版本使用户能够做三件事:创建 Postgres 数据库，创建 Postgres 集群，通过命令行备份数据库和数据库恢复。

术语“操作员”是 CoreOS 创造的一个术语，指的是人类操作员所做的操作，特别是对于需要人工干预的数据库，如备份或恢复。但它只是一个应用特定的控制器，你可以像 pod 或任何其他应用程序一样运行，他说。

“这件事的独特之处在于，这些运营商摆脱了第三方资源的概念，这是 Kubernetes 的概念，允许像我们这样的人在 Crunchy 定义我们自己的 Kubernetes 资源类型，而不仅仅是拥有 pod 或服务，”他说。“这为非 Kubernetes 应用程序提供商打开了大门，他们可以创建自己的资源集，这对他们的领域很有意义。”

CoreOS 最初推出了监控技术运营商[普罗米修斯](https://github.com/coreos/prometheus-operator)和键值存储 [etcd](https://github.com/coreos/etcd-operator) 。其他运营商已经为流媒体技术 [Kafka](https://github.com/krallistic/kafka-operator) 、 [Elasticsearch](https://github.com/upmc-enterprises/elasticsearch-operator) 、存储厂商 Rook 和监控工具[探照灯](https://github.com/appscode/searchlight)而打造。SAP 也为 OpenStack 构建了几个[。](https://github.com/sapcc/kubernetes-operators)

操作员被编码为监听那些要被创建、更新或删除的第三方资源。

“如果我创建一个 Postgres 数据库资源实例，操作员会注意到这一点并采取行动。当它看到时，它会出去创建一个 pod 和一个服务，这就是我所说的 Postgres 数据库。它还将创建一个持久的卷来存储数据，”他解释说。

资源本身只是关于用户希望它创建什么的一点元数据，所以它处理低级的 Kubernetes API 代码来创建 pods 或服务。

您可以将它安装在任何可以创建 Golang 二进制文件的设备上，它会连接到 Kubernetes 集群。Pgo 为用户使用 Postgres 操作符提供了一种简单的方法，并且它还提供了您所创建的所有内容的视图。你可以说，“给我看看我的 Postgres 数据库。”你不必直接与 Kubernetes 互动。

麦考密克说，该公司计划在最初三种功能的基础上，以四至六周为增量推出新版本。对开源版本 OpenShift Origin 的支持将在第二个版本中推出，该公司正在与 Red Hat 合作，在今年夏天推出的企业版 OpenShift 3.5 中支持它。

Crunchy Data 最近还公布了 PostgreSQL 安全技术实施指南(STIG) 。它由国防部发布，旨在帮助用户了解如何部署和配置已有 20 年历史的开源数据库，以满足政府系统的安全需求。Crunchy Certified PostgreSQL 还获得了通用标准评估保证级别(EAL) 2+认证，这是一项计算机安全认证的国际标准。据该公司称，这两个都是开源数据库的第一次。

红帽是新堆栈的赞助商。

特征图片: [mkreul](https://www.flickr.com/photos/4krichards/) 的[脆脆](https://www.flickr.com/photos/4krichards/12822126373/in/photolist-kx3Ksn-qQEuNX-odukMR-ehTcUw-57kEGC-5eLzQq-ihUt5v-8dHQ5b-ySHL3-79rFk3-omm6uD-8Lib71-oCBtgq-chrCZ-NEpAw-83o2fT-EYjapt-omm6Te-9FzJKc-oEA2XZ-TjQh3w-aTVggk-65hmZo-q8E8eT-PEbXKi-qAsDNM-TrPZRL-4RwEHf-nGN8mK-HC5va-dVF5vx-7gFvrN-omkhdN-dbo7Du-oCBtz1-sFoiS-6QX6nf-s9LrKu-dtZMZw-FhvwD-oCGGyM-35wuF7-r5nioo-rwHCHN-nn1bpf-3M2gwV-Beirk-rVbzwS-6JXsoJ-aicWX6)，授权**的 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>