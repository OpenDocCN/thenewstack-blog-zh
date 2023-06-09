# 满足实时数据架构中的规模和 SLA 需求

> 原文：<https://thenewstack.io/meet-scale-and-sla-demands-in-real-time-data-architectures/>

公司已经将多年的数据收集到一个令人难以置信的信息库中，新的数据以惊人的速度流入。

 [斯里尼·斯里尼瓦桑

Srini Srinivasan 是 Aerospike 的创始人兼首席技术官。他拥有二十年设计、开发和运营大规模基础设施的经验。他还在数据库、web、移动和分布式系统技术方面拥有十多项专利。他共同创立了 Aerospike，以解决他在雅虎担任高级工程总监期间遇到的互联网和移动系统的扩展问题。](https://www.aerospike.com/) 

但是，在将所有这些数据用于人工智能、机器学习和实时应用的爆炸中的竞赛中，许多组织遇到了两个重大障碍:在波动和不断增长的规模下运营，以及要求更快性能以进行即时、实时决策的服务交付服务级别协议(SLA)。

很容易构建适合少数人或少量数据的东西。但确保大规模运营现在成了赌注。只是规模上没有慢滚。每个公司都在竞相构建应用程序，并以最快的速度向数百万用户提供实时交易和卓越的用户体验。随之而来的是对性能、正常运行时间和服务交付的苛刻 SLA。

这个世界渴望信息和答案。现在，任何延迟或停机都会对运营利润、创收和客户满意度产生直接影响。风险很高。

让我们看看为要求苛刻的实时应用程序提供大规模高吞吐量所需的各种手段，包括大规模并行性、索引和互操作性。

## **大规模并行**

拥有多级并行是现代大规模数据架构的基本原则。在平台方面，您需要一个分治策略，将数据空间划分为多个可以独立处理的分区。为边缘和核心系统使用单独的数据库集群。并使其独立运行，但又相互协调。

这意味着使用集群中的多个节点作为集成的分布式系统，在集群节点中使用多个可并发访问的驱动器，以在集群中的一个节点内和多个节点之间提供并行执行线程。

除了数据架构的数据处理方面，您还需要查询层和流管道层的并行架构。此外，除了跨多个节点和节点内的多个驱动器进行横向扩展之外，通过使用具有 CPU 和 NUMA(非统一内存访问)固定的多线程在单个节点上进行纵向扩展以充分利用现代处理器也很重要。

## **二次分度**

在处理大量数据的分布式系统中，很难有足够的网络带宽让所有数据在边缘、核心、所有云以及当今数据部署固有的分布式特性之间来回传输。当查询扫描表中的每个文档或条目时，扫描大量数据会花费大量时间并对性能产生负面影响，这会消耗带宽和计算资源。

为了解决这个问题，公司通常会在更大的容量和计算能力上投入巨资。但实际上，提高带宽和计算性能的答案在于将大规模并行查询处理与二级索引相结合，从而减少或消除需要在系统组件之间移动的数据量。

二级索引是一种数据结构，它根据记录中的字段值定位命名空间或其中的一个集合中的所有记录。当记录中的任何索引值更新时，辅助索引会自动(自动)更新。

第一次构建二级索引可能需要一段时间，但是保持记录更新几乎不需要额外的工作，从而使使用二级索引的任何结果查询变得更快—在某些情况下快几个数量级。

您可以通过特定的配置进一步提高二级索引的性能，包括 Aerospike 平台中的一些配置。辅助索引可以存储在动态随机存取存储器(DRAM)中，以便快速查找。它们与集群中每个节点上的主索引条目位于同一位置，因此可以同时在所有节点上并行执行辅助索引查询。

每个二级索引仅包含对节点本地记录的引用，允许存储和查找优化，从而实现高效的存储利用率以及极快的查找和更新时间。

## **生态系统**

随着数据“民主化”到更多的人、合作伙伴和应用程序，并且越来越需要满足实时需求，所有旧的集中式技术堆栈都在向新的模式转移，这些新的模式越来越需要更高的速度和更大规模的稳定性。

最成功的数字化转型努力使用增强策略，在这种策略中，他们保留旧系统用于某些应用，但引入新系统，如用于新应用的[气塞](https://aerospike.com?utm_content=inline-mention)。通过这种方式，许多合规性和报告机制(已有数十年历史)可以不受影响地继续运行，同时组织可以使用新系统来加快新应用的构建，这些新应用对于改善整体用户体验和在快速变化的世界中保持竞争力至关重要。

我们研究的大部分内容都是在数据平台(或网络)层面。但是数据平台不是一个孤岛。它们在一个新的实时软件堆栈中运行，包括从输入(使用 Kafka 的流到使用 Spark 的 AI/ML 处理)到使用一系列 SQL(如 Presto)和其他数据访问标准的查询的所有内容。

当您按规模构建时，您会希望了解这些关键的相关系统如何在大规模下处理性能。

公司面临着越来越大的压力，要求用户手中有更多的应用程序。构建最小可行产品是诱人的，也是常见的，但我希望您从一开始就开始构建处理大规模的系统，避免因需求激增而导致平台迁移和错过 SLA 的痛苦和惩罚。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>