# 数据库操作员给 Kubernetes 带来了有状态的工作负载

> 原文：<https://thenewstack.io/databases-operators-bring-stateful-workloads-to-kubernetes/>

去年，红帽正式推出了 [Operator Framework](https://thenewstack.io/coreos-says-red-hat-will-help-introduce-openshift-to-operators/) ，这是一种为特定应用定制 Kubernetes 的 API 的方式。在 T2 被红帽收购之前，运营商框架最初是由 CoreOS 开发的，用户可以使用所有特定的设置和依赖关系启动应用程序，并让 Kubernetes 处理所有的供应和扩展。

现在我们开始看到更多的独立软件厂商(ISV)使用 Operator 框架来包装自己的应用。特别是，数据库管理系统提供商正在使用该技术来解决与 Kubernetes 合作的最困难的问题之一，即管理[有状态应用](https://thenewstack.io/strategies-running-stateful-applications-kubernetes-persistent-volumes-claims/)。Kubernetes 为此提供了[有状态集](/strategies-running-stateful-applications-kubernetes-pet-sets/)和[持久卷](/strategies-running-stateful-applications-kubernetes-volumes/)技术，但我们不断听说，运营商使管理后端数据库的过程变得更加容易。

Sebastien Pahl 在去年 10 月于北卡罗来纳州罗利市举行的 All Things Open 会议上介绍了这项技术，他指出，一个运营商将一个具有复杂的供应和维护问题的复杂程序转变为一项易于运行的服务。

实际上，[操作符格式](https://github.com/operator-framework)为软件开发人员提供了一个模板，告诉 Kubernetes 如何部署和维护应用程序，包括如何构建和部署该应用程序的详细说明。打包成独立容器的操作者将配置细节打包成 Kubernetes 可以理解的 YAML 定义的定制资源定义(CRD)。相关联的控制器确保所得到的集群由运营商规范来维护。

操作符涵盖了依赖项、安全权限(通过内核内置的名称空间支持)。相关的[操作员生命周期管理器](https://github.com/operator-framework/operator-lifecycle-manager)，也是由 Red Hat 开发的，为管理员提供了管理多个操作员的能力。该框架还包括从运营商构建的集群中[监控和收集指标](https://github.com/operator-framework/operator-metering)的能力。

运算符可以用 Go 编程语言、Helm 或 Red Hat 的 Ansible 自动化软件编写。

去年年底，Couchbase 为 Kubernetes 发布了 Couchbase Autonomous Operator，简化了管理分布式数据库的过程。我们最近采访了 Crunchy Data，该公司自 CoreOS 时代以来一直使用运营商来管理 Kubernetes 部署中的 PostgreSQL 数据库，还采访了 PingCap，该公司使用运营商模式来打包其 TiDB 数据库，以便它可以作为云提供商的服务来使用。

## 平滑算子

一个数据库系统供应商已经进入运营商的行列，那就是 [Couchbase](https://www.couchbase.com/) ，它在去年年底为 Kubernetes 发布了 [Couchbase 自主运营商。](https://www.couchbase.com/products/cloud/kubernetes)

Couchbase 是一个分布式数据平台，为支持社交媒体参与开辟了一个市场，调整为聊天、维护个人资料和移动功能等用例，Couchbase 工程副总裁戴夫·芬利在接受采访时说。

几年前，由于维护有状态存在的限制，大多数用户对在容器中运行数据库犹豫不决。Finlay 说，随着越来越多的企业和初创公司将他们的数据平台容器化，这种观点很快被推翻。

“数据库是最有状态的应用程序，”Finlay 说。“当人们写入数据时，他们希望当他们回去检索数据时，数据还在。”

当您在数据库集群中丢失一个节点时，如何恢复数据？芬利说，Kubernetes 本身没有自然的方式做到这一点。

Couchbase 有内置的复制功能，数据分布在多个节点上。它还具有在主节点出现故障时故障切换到备份节点的本机功能。但是 Kubernetes 通过使用 Autonomous Operator，可以在系统中找到新的硬件来使该集群恢复到其最大能力，所用的时间比让管理员来做要少得多。

“如果系统中有非常重大的故障，Kubernetes 可以比人类更快地做出反应，”Finlay 说。

Couchbase Server 的产品管理总监[阿尼尔·库马尔](https://www.linkedin.com/in/anilkumar29/)补充道，拥有 Kubernetes 控制的 Couchbase 部署也有助于组织在微服务架构上实现标准化。在许多情况下，一个公司可能已经将所有无状态的组件转移到这样一个容器化的架构中，将数据库隔离在自己的竖井中。

“有了这家运营商，我们正在弥合这一差距，”他说。

[Crunchy Data](https://www.crunchydata.com/) 五年来一直在提供一个容器化版本的 [PostgreSQL](https://www.postgresql.org/) 关系数据库管理系统，Crunchy Data 的通信主管[乔纳森·凯兹](https://info.crunchydata.com/blog/author/jonathan-s-katz)说。 [Crunchy Container Suite](https://github.com/CrunchyData/crunchy-containers) 是一个由大约 20 个容器组成的开源套件，拥有运行生产级 Postgres 部署所需的所有微服务，包括监控和高可用性。

大约两年前，Crunchy 开始考虑将这个包扩展到 Kubernetes。该公司没有采用 StatefulSets，这在当时被认为是处理有状态应用程序的最佳方法。相反，Crunchy 研究了 CoreOS 正在开发的一种当时处于实验阶段的模式。

如今，成千上万的部署使用了 2017 年 3 月推出的用于 Kubernetes 的[Crunchy PostgreSQL](https://www.crunchydata.com/products/crunchy-postgresql-for-kubernetes/)包，该包基于该公司的 PostgreSQL 操作符，是首批部署的操作符之一。

这不仅仅是有一个固定的参考来发送和查询数据，运营商解决了许多复杂的部署问题。它可以处理复杂的任务，如制作和保存副本，以及事务日志。它可以安排复制任务，例如确保数据库的两个副本不在同一个节点上。

“也许你想让一个实例运行在一个具有超高速磁盘阵列的节点上，而让另一个实例连接到一个较慢的存储卷上——这与有状态集所允许的不同，”Katz 说。

“实际上，运营商所做的是让我们能够在整个 Kubernetes 集群中执行大规模部署命令，”Katz 说。

Crunch 发现，Kubernetes 名称空间也能提供安全优势。通过使用 Kubernetes 标签，用户访问可以被隔离到特定的名称空间，即数据库系统。新的数据库管理员可以被限制在他或她监管的用户应用程序范围内。名称空间也有助于升级。

你不需要 Crunchy 的商业支持合同来享受运营商。一家财富 100 强公司正在使用 Crunchy 操作器运行 200 多个节点的 PostgreSQL 集群。它只在需要额外支持时才联系该公司。

“你仍然需要评估，”卡茨说。“但是技术已经成熟。应该在讨论中。”

## 数据库即服务

PingCAP 正在向云提供商推出 TiDB，这是一个开源的分布式可扩展混合事务和分析处理(HTAP)数据库。该公司希望跨不同的云实现可预测且简单的部署模式。所以它转向 Kubernetes 和它自己的自定义操作符模式。例如，谷歌云平台[刚刚开始在其市场上提供 TiDB](https://console.cloud.google.com/marketplace/details/pingcap-public/pingcap-tidb-operator?pli=1) 。

最终，TiDB 本身可以简化系统环境，因为它不再需要建立数据仓库和 ETL 系统来传递数据。但是，PingCAP 全球战略和运营总经理[许海波](https://www.linkedin.com/in/kevinsxu/)承认，由于它本身有许多活动部件，安装起来可能有点复杂。

该公司实际上在几年前就开始了在 Kubernetes 上简化部署和自动化部署的工作，使用有状态集和持久卷，尽管“我们必须做很多黑客工作才能让它工作，”徐说。

输入 [TiDB 运算符](https://github.com/pingcap/tidb-operator)。

“我们认为这个抽象的运营商层有助于提供良好的客户体验，”徐说。值得注意的是，它跨不同的云提供了一致的用户体验。由于 TiDB 是实时分析能力和在线交易处理的混合体，因此运营商可以提供细微差别，将每个组件扩展到各自的最佳水平，彼此独立。

徐说，运营商“对于以正确的方式提供我们的产品和体验至关重要”。“运算符之所以出色，是因为它能够降低有状态应用程序的复杂性，在有状态应用程序中，您必须跟踪大量状态。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>