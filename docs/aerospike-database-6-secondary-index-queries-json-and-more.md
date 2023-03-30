# Aerospike 数据库 6:二级索引查询、JSON 等等

> 原文：<https://thenewstack.io/aerospike-database-6-secondary-index-queries-json-and-more/>

[](https://www.linkedin.com/in/rbotzer/)

[Ronen Botzer](https://www.linkedin.com/in/rbotzer/)

[Ronen 是 Aerospike 公司的产品总监，此前他在该公司担任解决方案架构师。Ronen 在多家湾区技术公司担任工程师和建筑师已有 20 年的经验。](https://www.linkedin.com/in/rbotzer/)

[](https://www.linkedin.com/in/rbotzer/)[](https://www.linkedin.com/in/rbotzer/)

[我们最新的数据库服务器版本 Aerospike Database 6](https://aerospike.com/products/database/) 于 4 月 27 日正式发布，其中包含了许多激动人心的开发人员特性。

两年前，我们在 Aerospike Database 5 中发布了一个大幅改进的跨数据中心复制(XDR)子系统。它使我们的客户能够创建高性能、地理分布的应用程序，并对其数据的分布进行精细控制。我们最新的数据库版本建立在这些功能之上，反映了我们对查询的日益关注。结合 Aerospike Connect for Spark 和 Aerospike Connect for Presto(Trino ), Aerospike 数据平台使我们的客户能够针对其大型数据集处理低延迟事务和分析工作负载。

在这篇博文中，我们将讨论三个主要功能。首先，我们将讨论 6.0 版本中的新查询功能。其次，我们将通过文档 API 和我们的二级索引工作来了解对文档数据模型的支持，最后，我们将完成批处理操作，包括批处理写入，以便通过流水线操作来提高效率。

服务器版本 6.0。历经 7 个候选版本，是 14 个月工程努力的顶点。Aerospike Database 6 是一个重要的版本，包含了突破性的变化。请查看与新存储格式和新二级索引查询功能相关的[发行说明](https://enterprise.aerospike.com/enterprise/download/server/notes.html)和[特殊升级说明](https://docs.aerospike.com/server/operations/upgrade/special_upgrades)。

## **分区二级索引查询**

通向新查询子系统的道路始于 Aerospike Database 5 的最后两个版本。

服务器版本 5.6 增加了[集合索引](https://docs.aerospike.com/server/architecture/set-indexes)，这是一种可选的索引类型，它的[为一种特殊的查询提高了性能](https://aerospike.com/blog/set-index-performance/)。使用集合索引可以实现对大型名称空间中的一小组记录的低延迟访问。另外，和主索引一样，设置索引支持[快速重启](https://docs.aerospike.com/server/operations/manage/aerospike/fast_start)。Server version 5.7 将二级索引消耗的内存减少了 60%，并提供了一个新的高效垃圾收集系统。查询性能和吞吐量也得到了提高。

Aerospike Database 6 建立在这些变化的基础上，采用了与[主索引](https://docs.aerospike.com/server/architecture/primary-index)的设计相一致的新架构方法。每个 Aerospike 名称空间中的数据平均分布在 4096 个逻辑分区上，这些分区又平均分布在集群节点上。每个分区的数据存储在称为 sprigs 的多个主索引子树中，并在本地进行索引，这使得主索引(PI)查询(以前称为扫描)能够大规模并行化。

PI 查询可以针对所有分区、一组分区或单个数据分区。利用这种能力，Spark 和 Presto (Trino)连接器可以将一个 PI 查询拆分成成百上千个分区查询，并行地将数据提供给成千上万的工作人员，并通过水平扩展来完成快速处理 TB 级数据的任务。这种方法非常适合这些分析系统的架构。这种结合创建了下一级分布式计算数据平台。

在 6.0 版之前，开发人员只能在节点级别并行执行辅助索引查询。这意味着，如果一个集群有 40 个节点，Spark 和 Presto (Trino)连接器可以使用的最佳并行化是 40 个工作线程。由于我们的客户在生产中使用了具有数千个内核的 Spark 集群，让它们中的大多数处于闲置状态是不可接受的，因此这些连接器没有实现对二级索引查询的支持。

在 6.0 版中，二级索引已经过重新设计，可以单独索引每个分区。这支持大规模并行化二级索引(SI)查询，并支持分页，如 PI 查询。此外，6.0 版中的 SI 查询可以容忍[重新平衡](https://docs.aerospike.com/server/architecture/data-distribution#automatic-rebalancing)，不受集群大小变化时发生的自动数据迁移的影响。因此，Spark 和 Presto (Trino)连接器将以与它们当前执行 PI 查询相同的方式实现 SI 查询支持。这为 Aerospike 的运营商打开了大门，他们可以选择用内存来换取性能的提高。通过向具有正确基数的集合添加辅助索引，SI 查询的运行速度可以比同等的 PI 查询快几个数量级。

辅助索引体系结构的变化反映在服务器的查询子系统中，该子系统现在统一了两种类型的查询—主索引和辅助索引。这种变化深入到标准执行层、已被合并和重命名的指标、客户端 API 中，客户端 API 不再使用 Scan 类，而是从单个查询类向 PI 和 SI 查询提供同样丰富的功能。

分区查询通过客户端-服务器协调实现，需要新的客户端版本，如 Java 客户端 6.0.0、C 客户端 6.0.0、Go 客户端 6.0.0、C#客户端 5.0.0 或 Python 客户端 7.0.0。使用这些客户端的早期版本的应用程序可以在 server 6.0 上运行，但不会受益于重新平衡容差。同样，新客户端可以与 server 5.0 x 和 server 6.0 节点通信，但需要完成集群升级才能解锁新功能。

## **Aerospike 数据库即将推出的查询功能 6**

Aerospike 提供了更好的查询性能、更低的索引内存占用、查询稳定性和更高的查询吞吐量。Aerospike Database 6 的后续版本将为查询添加更多的功能和操作改进。

在 Aerospike Database Community Edition(CE)中，主索引和辅助索引存储在进程内存中。它们必须在相对较长的冷重启中重启后重建。

在 Aerospike Database Enterprise Edition(EE)中，默认情况下，主索引保存在共享内存中，也可以选择保存在永久内存或闪存设备中。这使得 Aerospike EE 服务器能够经历热(快速)重启，这明显更快。服务器版本 6.1 将增加在共享内存中存储二级索引的能力，允许 Aerospike 守护程序(asd)在存在时热重启。更高版本将支持将二级索引存储在永久内存中，甚至存储在闪存设备上。

目前，可以在地图数据结构的顶级关键字上构建二级索引。这通常用于索引 JSON 文档的顶级字段，这些字段作为映射存储在 Aerospike 中。Server 版将增加索引任意深度嵌套元素的功能。

## **存储、索引和查询 JSON 文档**

自从引入地图和列表集合数据类型(CDT)以来，开发人员已经将 JSON 文档存储在键排序地图中，并将 Aerospike 用作文档数据库。开发人员在多操作事务中使用丰富的 Map 和 List APIs 在服务器端自动查询和操作文档数据。文档(地图)存储在节省空间的 [MessagePack](https://msgpack.org/index.html) 二进制序列化中，便于快速访问。

2021 年年中推出的 Aerospike 文档 API 库，增加了使用流行的 JSONPath 查询语言存储、修改和查询文档的能力。文档 API 基于原生 Map API 将这些查询分解到服务器端执行，并通过 JSONPath 库进行了扩充。

文档 API 可以作为 Java 客户端的包装器和 Aerospike gateway(也称为 REST 客户端)中的接口使用。文档 API 库将通过 Aerospike 客户端移植到其他编程语言。Aerospike Database 6 具有索引深层嵌套元素的能力，增强了使用文档模型方法的应用程序的开发。结合强大的一致性和 Aerospike 扩展到数 Pb 的数据和数千亿个对象的能力，同时保持亚毫秒级的事务延迟，它产生了大规模的文档数据库。

## **批什么东西**

从一开始，客户机就支持一个简单的 batch get 命令，允许根据一个键列表一起检索多个记录(或其中的 bin)。类似地，batch 命令从指定的键列表中一次检查多个键是否存在。

后来，客户端添加了使用 batch operate 命令对一组键并行执行相同的多操作事务的能力，但是将事务中的操作类型限制为只读。

在 server 6.0 中，添加了批量写命令(删除、操作事务，而不限制写操作)，使开发人员能够[批量处理应用程序中的任何内容](https://docs.aerospike.com/server/guide/batch)—读取、写入、更新、删除或用户定义的函数(UDF)。逻辑上相关的操作可以一次发送到数据库集群。

批量写入比在服务器上异步启动一系列命令更有效。使用批处理:

*   减少完成所有操作所需的往返时间(RTT ),从而降低整体延迟。
*   减少网络流量，使用更少的连接并将操作合并到更少的 IP 数据包中。
*   提高并行性，支持更快的数据接收。

用于繁重写入或混合工作负载的应用程序开发人员应该考虑从异步写入转换为批处理，以获得更好的性能和更稳定的集群。

## **安全增强措施**

Server 6.0 为基于角色的[访问控制](https://docs.aerospike.com/server/operations/configure/security/access-control)增加了三种新的细粒度权限:

*   index-admin 权限授予用户添加和删除辅助索引的能力。
*   udf-admin 权限授予用户添加和删除 udf 模块的能力。

以前，这些权限只能通过 data-admin 权限获得，而一些用户不愿意广泛授予这些权限。截断权限现在是一个独立的权限，不再是写入权限的一部分。代表执行截断的应用程序的用户应该被授予其角色之一的截断权限。

## **突破性变化**

服务器版本 6.0 中的重大变化包括:

*   作为升级的一部分，存储格式的改变(向每个记录添加一个 4 字节的结束标记)要求永久存储设备(PMEM 除外)被擦除。原始 SSD 设备的标头(前 8mb)必须归零。参见 [SSD 初始化](https://docs.aerospike.com/server/operations/plan/ssd/ssd_init)。
*   几个配置参数已被重命名或删除:
    *   少量配置参数已被重命名。
        *   扫描最大完成到查询最大完成
        *   scan-threads-limit to query-threads-limit
        *   background-scan-max-rps 到 background-query-max-rps
        *   单扫描线程到单查询线程
    *   已删除以下查询配置参数。
        *   查询线程
        *   查询工作线程
        *   查询-微基准
        *   查询批量大小
        *   事务线程中的查询
        *   查询长度最大值
        *   查询优先级
        *   查询-优先级-睡眠-用户
        *   查询记录计数绑定
        *   查询线程中的查询请求
        *   query-short-q-max-size
        *   查询阈值
        *   查询-未跟踪-时间-毫秒
    *   无摘要批处理配置参数已被删除。
*   需要向使用截断的应用程序授予截断权限。它不再是写入权限的一部分。
*   删除了长期被否决的谓词过滤(PredExp)。使用[过滤表达式。](https://docs.aerospike.com/server/guide/expressions)
*   jobs: info 命令的“扫描”模块已被删除。请改用“查询”模块。
*   请注意，与扫描和查询相关的[指标](https://docs.aerospike.com/reference/metrics)已经改变。我们将发布一个单独的博客来详细介绍这些变化。

## **弃用通知**

*   jobs: info 命令最初在 server 5.7 中被弃用，计划在六个月后删除。使用查询-显示。
*   scan-show info 命令现在已被弃用。使用查询-显示。
*   现在不推荐使用 scan-abort info 命令。使用查询中止。
*   scan-abort-all 命令现在已被弃用。使用 query-abort-all。

## **了解更多信息**

[*获取关于气塞数据库 6.0*](https://developer.aerospike.com/blog/config-metric-info-changes-in-database-6) 中配置、指标和信息变更的详细信息

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>