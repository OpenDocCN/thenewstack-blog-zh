# KOST 堆栈:一个开源云本地混合数据库堆栈

> 原文：<https://thenewstack.io/the-kost-stack-an-open-source-cloud-native-hybrid-database-stack/>

[](https://www.linkedin.com/in/kevinsxu/)

 [许海波

许海波是 PingCAP 全球战略和运营总经理，也是 TiKV(一个云原生分布式键值存储和 CNCF 成员项目)的贡献者。他在斯坦福大学学习计算机科学和法律。](https://www.linkedin.com/in/kevinsxu/) [](https://www.linkedin.com/in/kevinsxu/)

这些年来，出现了许多技术栈，使软件开发人员的生活变得更加轻松和高效——更好的开发效率，更清晰的软件选择。其中最引人注目的是 [LAMP](https://en.wikipedia.org/wiki/LAMP_(software_bundle)) stack (Linux，Apache HTTP server，MySQL，PHP)，它帮助无数开发者将他们的伟大想法变成了大公司，也许没有比马克·扎克伯格创建脸书更大的了。最近，利用 Javascript 的流行 web 开发模式，如 [MEAN](https://thenewstack.io/deploy-a-mean-web-app-with-google-kubernetes-engine-portworx/) stack (MongoDB，Express.js，Angular，Node.js)及其近亲 MERN(将 Angular 换成 React)和 MEVN(将 Angujar 换成 Vue.js)，大大缩短了创意上市时间。

然而，随着云计算成为消耗基础设施资源的默认方式，仅仅启动并运行应用程序已经不足以应对下一波创新——不仅一个想法需要快速进入市场，它还需要从一开始就针对规模**进行架构**以应对快速增长，并且最好没有任何形式的供应商锁定。

为了满足这种需求，一种新的基础设施模式正在兴起，称为 KOST 堆栈( [Kubernetes](/category/kubernetes/) 、 [Operator](https://coreos.com/blog/introducing-operator-framework) 、 [Spark](https://en.wikipedia.org/wiki/Apache_Spark) 、 [TiDB](https://en.wikipedia.org/wiki/TiDB) )。这套开源技术和框架提供了一种模式，允许开发人员使用关系数据库管理系统消费任何混合(公共、私有或混合)的云计算资源，该系统可以高效地处理混合的事务和分析处理工作负载，即所谓的 [HTAP](https://en.wikipedia.org/wiki/Hybrid_transactional/analytical_processing_(HTAP)) 。这些技术之间的原生集成使得在任何周末黑客马拉松中都可以构建“KOST 集群”——无论您是希望成为“云原生”的传统 IT 部门的一员，还是希望推出“下一件大事”的单个开发人员

## 成分

### 库伯内特斯

Kubernetes 是一组开源的容器编排 API，已经成为部署、运行和管理容器化工作负载的工具集。自 2014 年被谷歌开源以来，它的发展、受欢迎程度和采用率以惊人的速度增长——一些人甚至将其称为云的操作系统。Redmonk 联合创始人兼分析师 Stephen O'Grady 说[这是最简洁的](https://redmonk.com/sogrady/2018/11/07/vmware-heptio/)，“…这是 Kubernetes 的世界，我们只是生活在其中…”

虽然其他容器编排层确实存在(例如 [Docker Swarm](https://en.wikipedia.org/wiki/Docker_(software)) 、 [Apache Mesos](https://en.wikipedia.org/wiki/Apache_Mesos) 、 [OpenStack](https://en.wikipedia.org/wiki/OpenStack) )，但云计算世界已经围绕 Kubernetes 融合在一起。一个恰当的例子是，所有主要的公共云平台都提供自己的托管 Kubernetes 引擎(亚马逊 Web 服务上的[亚马逊弹性 Kubernetes 容器服务](https://aws.amazon.com/eks/)，微软 Azure 上的 [Azure Kubernetes 服务](https://azure.microsoft.com/en-us/services/kubernetes-service/)，谷歌云平台上的[Kubernetes 引擎](https://cloud.google.com/kubernetes-engine/)，以及阿里云上的[Kubernetes 容器服务](https://www.alibabacloud.com/product/kubernetes)，以及大量在内部或跨不同云提供托管 Kubernetes 解决方案的供应商——[open shift](https://www.openshift.com/)

Kubernetes 是所有云计算工作负载的共同点，也是实现私有云或多云架构的基础，这对于那些不想被一家公共云供应商所束缚，或者出于安全性、合规性或数据治理原因而必须管理自己的云基础架构的大型企业来说尤其具有吸引力。

### 操作员

操作符是一种打包、部署和管理 Kubernetes 应用程序的方法。它是为运行更容易管理和操作的*有状态*工作负载而设计的，这是 vanilla Kubernetes 的相对弱点(迄今为止大多数 Kuberentes 生产工作负载都是*无状态*)。Operator 模式由 CoreOS 首创，在[收购 CoreOS](https://www.redhat.com/en/about/press-releases/red-hat-acquire-coreos-expanding-its-kubernetes-and-containers-leadership)后由 Red Hat 支持和培养，并在不同的数据库技术中获得了流行[，寻找以所谓的“云原生”方式交付其解决方案的方法，这在某种程度上已经成为“Kubernetes-native”的同义词。由于这个原因，Spark 和 TiDB 都有自己的开源操作实现。开源数据库的领先企业支持、服务和咨询提供商 Percona 也宣布了两家运营商，分别负责 XtraDB 集群和 MongoDB 产品。](/databases-operators-bring-stateful-workloads-to-kubernetes/)

这是 KOST 堆栈中的一个关键层，因为在云中运行 HTAP 数据库堆栈需要仔细管理数据状态，以确保数据高度一致，并可供近实时分析使用。此外，在运行数据库的过程中，还必须执行其他一些例行但重要的操作任务，如横向扩展容量、备份和恢复。所有这些任务都可以编码并在操作员内部半自动完成。它本质上是你的 SRE 团队的[编码扩展。](https://coreos.com/blog/introducing-operators.html)

### 火花

[Apache Spark](https://spark.apache.org/) 于 2009 年首次在加州大学伯克利分校的 [AMPLab](https://amplab.cs.berkeley.edu/) 创建，是一个广泛使用的分布式集群计算框架，擅长大数据分析——经典的在线分析处理(OLAP)工作负载。它后来不断发展，用 Spark Streaming 支持数据流的组件，用 Spark SQL 查询结构化和半结构化数据，用 Spark MLlib 进行机器学习。

Spark 有[自己的](https://github.com/GoogleCloudPlatform/spark-on-k8s-operator)操作符，可以和各种分布式存储系统接口来聚合数据，包括 [Alluxio](https://www.alluxio.io/) 、 [HDFS](https://hadoop.apache.org/docs/r1.2.1/hdfs_design.html) 、 [Cassandra](http://cassandra.apache.org/) 、 [AWS S3](https://aws.amazon.com/s3/) 、 [OpenStack Swift](https://wiki.openstack.org/wiki/Swift) 和 [TiKV](https://tikv.org/) ，这是一个分布式事务键值存储，也是云计算原生计算基金会(CNCF)成员项目。

### TiDB

Spark 提供了一个强大的分析引擎，TiDB 则完成了事务方面的工作，让 HTAP 在云中成为现实。 [TiDB](https://thenewstack.io/chaos-tools-and-techniques-for-testing-the-tidb-distributed-newsql-database/) 是一个开源的 NewSQL 数据库解决方案，它使用 MySQL 协议并保证强大的数据一致性。这个项目在它最初开始的中国有着巨大的吸引力，利用这个国家互联网经济的巨大规模来测试自己。行业分析公司 [451 Research](https://cdn2.hubspot.net/hubfs/4466002/451_Research_PingCAP_Report_08MAY2019.pdf) 最近指出，TiDB 在东南亚和印度也正经历着强劲的增长，在欧洲和北美也是如此。

TiDB 有自己的操作符实现，称为 [TiDB-Operator](https://github.com/pingcap/tidb-operator) ，与 TiKV 一起工作，提供一个类似 MySQL 的关系数据库，可以在不放弃事务一致性的情况下进行水平扩展。(TiDB 和 TiKV 最初都是由商业公司 [PingCAP](https://www.pingcap.com/en/) 创建和维护的，在 TiKV 成为 CNCF 的成员项目之前。还有一个由 PingCAP 维护的名为 [TiSpark](https://github.com/pingcap/tispark) 的开源 Spark 插件。)

## 野生的云原生 HTAP

传统上，交易和分析在两个不同的数据库上运行(通常设计为非常适合其中一个)，并且通常由两个不同的团队管理，如果您是一个足够大的企业，甚至可以位于两个不同的大楼中。该架构是整体式的(与基于微服务相反)，难以水平扩展，并且数据只能通过管理单独的 [ETL(提取、转换和加载)](https://www.sas.com/en_us/insights/data-management/what-is-etl.html)管道进行分析，该管道每天运行一次或几次，可能由第三方团队完成。

虽然这种传统方式在某些行业仍然有效，但零售/电子商务等竞争激烈的垂直行业正在采用云原生 HTAP 方式和 KOST 堆栈，以提供“智能定价”、更好的库存管理、欺诈检测等功能，以及“在线购买，店内提货”等新体验所有这些创新的购物方式都需要一个灵活的数字基础设施，如 KOST 堆栈所支持的那样，它可以快速扩展、轻松操作、增强数据的一致性，同时无需 ETL 管道即可进行聚合和分析。

KOST 堆栈绝不是静态的，因为每个组件都是开源的、可扩展的，并且在合适的用例召唤时可以与其他软件很好地集成。通常情况下，基于 Redis 的缓存位于顶层，以提高速度和性能。开源服务网格层，如 [Istio](https://istio.io/) 、 [Kong](https://thenewstack.io/kong-at-1-0-a-service-control-platform/) 或 [Linkerd](https://linkerd.io/) ，也倾向于位于 KOST 之上，管理一组微服务来支持您的应用。

因为 KOST 只由开源软件组成，如果你的团队愿意操作它，它是完全免费的——允许大型企业数字化发展，同时放弃专有替代品的昂贵许可证。如果 DIY 不是你的风格，每个组件至少有一个商业供应商准备支持它。

虽然栈模式有时可能会无意中挑选出技术赢家，惹恼某些对特定软件的流行感兴趣的供应商，但开发人员通常不会介意。作为技术选择的[新国王制定者](https://www.amazon.com/New-Kingmakers-Developers-Conquered-World-ebook/dp/B0097E4MEU)，开发人员正变得越来越老练，他们过滤掉厂商的炒作，转而支持开源技术，这些技术拥有活跃的社区，与其他软件配合良好，并解决了真正的技术难题。就像 LAMP 为第一波 web 开发铺平了道路，MEAN/MERN/MEVN 推动了移动开发的边界一样，KOST 将通过实时数据洞察缓解使用云计算来扩展数据库操作的痛苦——让开发人员和企业家能够做他们最擅长的事情:构建。

红帽是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>