# Kubernetes 本地数据库的兴起

> 原文：<https://thenewstack.io/the-rise-of-the-kubernetes-native-database/>

云计算革命激发并受益于多个相互关联的趋势。自助式公共云基础架构的可用性有助于推动微服务架构和开发运维实践的采用，包括自动化和可观察性。

容器化和容器编排的趋势导致 Kubernetes 作为管理云原生应用的环境被广泛采用。

但这场革命中的一个滞后领域是数据和数据基础设施。很长一段时间以来，数据一直存在于 Kubernetes 之外，这导致开发人员在部署云原生应用程序时付出了大量额外的努力，也增加了复杂性。

在 Kubernetes 的早期，一个经常重复的公理是它还没有为有状态工作负载做好准备。令人欣慰的是，一个重大的转变已经悄然发生，事实上已经成熟。

这种转变开始时进展缓慢，首先是努力将现有的数据库容器化。对于运行在单个计算节点上的小型数据库，或者在云环境中设计的数据库，如 Apache Cassandra 和 DynamoDB，这种方法相对来说效果不错，但挑战依然存在。

在过去的两到三年中，新一代的数据库已经出现。这些“Kubernetes native”数据库是为在这个开源编排系统上运行而从头开始设计的。

在这里，我们将定义使数据库成为 Kubernetes 原生数据库的品质，以及采用 Kubernetes 原生数据库的好处。为了做到这一点，我们将查看两个声称拥有 Kubernetes 原生标签的数据库:TiDB 和 DataStax Astra DB。

## 带有 TiDB 的 Kubernetes 原生 MySQL

首先，让我们以关系为重点来考察一个数据库:[TiDB](https://www.pingcap.com/)(Titanium Database 的简称)。TiDB 是由 PingCAP 构建的开源系统，它提供了一个与 MySQL 兼容的[数据库](https://thenewstack.io/tidb-brings-distributed-scalability-sql/)以及一个支持混合事务和分析处理的列数据库(简称为 HTAP)。

如下图 1 所示，TiDB 具有微服务设计，其中 TiDB 查询层、TiKV MySQL 数据库、TiFlash 列数据库、Spark 节点和元数据管理都作为可扩展的微服务部署在各自的集群中。这种设计将计算密集型工作与存储密集型工作分开，因为查询层和数据库层可以独立扩展。

TiDB 创建者做出的一个重要承诺是数据库只能在 Kubernetes 上运行。这足以使它成为库伯内特土著吗？让我们再深入一点。首先，TiDB 由 Kubernetes 运营商使用[定制资源](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/) (CRDs)进行部署和管理。TiDB CRDs 包括 TiDBCluster，它使您能够指定每个微服务的扩展和配置，以及数据库层组件如何通过 Kubernetes 持久性卷使用存储。其他 CRD 用于部署监控工具和管理操作任务，如备份和恢复。

TiDB 还有一个可选的调度程序扩展，它与默认的 K8s 调度程序接口，以做出更多应用程序感知的调度决策。这种对使用现有 Kubernetes 功能的强调是 Kubernetes 本地数据库的标志。

## Kubernetes 本地卡桑德拉与 DataStax 阿斯特拉数据库

现在让我们看看另一个 Kubernetes 原生数据库，并注意一些相似之处和不同之处。 [Cassandra](https://thenewstack.io/an-apache-cassandra-breakthrough-acid-transactions-at-scale/) 是一个高度可扩展的 NoSQL 数据库，它是第一批声称是云原生的数据库之一，但是在 Kubernetes 中部署 Cassandra 会是什么样子呢？ [DataStax Astra DB](https://dtsx.io/3irqQ5S) 是 Cassandra 的一个版本，已经被分解到微服务中，如图 2 所示。

与 TiDB 类似，该数据库包括与查询处理和数据存储有关的微服务，以及身份和访问控制、数据修复和备份/恢复服务。数据服务在使用[存储](https://thenewstack.io/apache-cassandra-persistent-data-storage-for-scalable-microservices-applications/)方面特别有趣，Kubernetes 持久性卷仅用于缓存，对象存储用于长期持久性。将压缩分离到自己的服务中，使这种计算密集型处理能够在后台进行，而不会影响为读写流量提供服务的数据服务的性能。

Astra DB 作为托管服务在多个云区域提供。每个区域都包含一个由上述服务组成的数据平面，由 Kubernetes 运营商管理，以及基础设施服务，包括用于可观测性的 [Kube-Promethus](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack) 堆栈和用于元数据管理的 [etcd](https://etcd.io/) 。数据平面由控制平面管理，控制平面可以在一个或多个云中运行，以执行诸如管理客户帐户和数据库以及在新区域中配置 Kubernetes 集群等任务。

Astra DB 的一个新颖之处在于其多租户架构，其中多个用户数据库可以共享相同的微服务和支持基础设施，从而降低了小规模用户的单位经济性。随着用户应用程序的增长，他们可以选择转移到专用资源，以实现最佳的大规模性能，这一切都基于“[按需购买](https://dtsx.io/3GUaixE)”的原则。

## Kubernetes 本地数据库原则

根据我们对 TiDB 和 Astra DB 的观察，我们可以得出一些关于什么使数据库成为 Kubernetes 本地的想法。其中许多都符合云原生数据的原则列表，我在之前的文章[中描述过:](https://containerjournal.com/kubeconcnc/why-a-cloud-native-database-must-run-on-k8s/)

*   **可组合的微服务架构:**首先，一个被分解成多个组成微服务的数据库使每个服务能够独立扩展。对于真正的无服务器解决方案，某些类型的计算密集型处理甚至可以扩展到零，尤其是在与多租户设计结合使用时。
*   **将计算、网络和存储视为商品:**由 Kubernetes 原生数据库组成的微服务应最大限度地利用 Kubernetes APIs 来管理云原生应用程序的基础资源:计算资源，如用于管理工作负载的 StatefulSets 和 deployments、用于存储的持久性卷子系统、Kubernetes ingress 和用于公开对数据的网络访问的服务等。这包括利用 Kubernetes 中已经存在的功能(如 etcd)进行元数据管理，而不是带来具有重复功能的组件。
*   **利用 Kubernetes 最佳实践:**遵循 Kubernetes 应用程序的通用模式将产生多种运营优势，例如，公开每个微服务的活性和就绪性检查以帮助可用性，以及通过 Prometheus PromQL API 公开指标以实现可观察性。默认情况下，Kubernetes 本身为数据库如何保证安全树立了一个很好的榜样:使用 Kubernetes 的秘密来分发安全凭证，只在需要时公开端口等等。
*   **通过操作符的声明式管理:**Kubernetes 原生数据库应该通过操作符和定制资源体现 Kubernetes 声明式管理的原则，而不是依赖于遗留的数据库管理 ui 和 CLI。必要时，可以使用 Kubernetes 扩展点(如调度程序扩展)来添加特定于应用程序的行为。目标是将数据平面功能(管理数据)与控制平面功能(管理数据库)完全分离。

忠实采用这些原则的数据库和其他数据基础设施将带来诸多好处，包括在各种规模下以最优成本实现高性能、降低运营复杂性从而加快上市时间，以及符合标准的解决方案满足当今的高可用性和安全性需求。

## Kubernetes 本地数据基础设施的未来

仍然有很多进展要做，而且不仅限于数据库。Kubernetes 的原生原则可以应用于其他类型的数据基础设施，包括流媒体、分析和机器学习。

Kubernetes 本地解决方案将继续在多集群和多云部署方面取得进展，以便在全球范围内进行扩展，并将采用多租户和无服务器原则来实现更好的成本优化。Kubernetes 本身在为 StatefulSets 增加更多灵活性和支持多集群联邦方面还有改进的空间。

持续进步的关键是开放的合作。Kubernetes 社区上的[数据是一群非常活跃的数据极客，他们聚集了数据密集型应用程序的构建者和支持这些应用程序的基础设施。](https://dok.community)

加入我们来讨论一些想法，比如开发可以管理多个数据库的可重用操作符，或者为备份/恢复和数据加载等概念定义一组通用的 CRD。我们将一起继续推进云计算的发展，造福全人类。

*本文基于 Jeff Carpenter 和 Patrick McFadin 所著的《在 Kubernetes 上管理云原生数据》一书的第 7 章“Kubernetes 原生数据库”。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>