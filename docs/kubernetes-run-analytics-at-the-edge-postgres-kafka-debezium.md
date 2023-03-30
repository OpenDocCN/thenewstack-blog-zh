# 在边缘运行分析:Postgres，Kafka，Debezium

> 原文：<https://thenewstack.io/kubernetes-run-analytics-at-the-edge-postgres-kafka-debezium/>

[](https://www.crunchydata.com/)

 [乔纳森·s·卡茨

乔纳森·s·卡茨是可信的开源 PostgreSQL 技术的领先提供商 Crunchy Data 的云工程& Growth 的主管，负责其云产品，包括 PostgreSQL 运营商。Jonathan 还负责 PostgreSQL 全球开发小组的宣传和其他治理工作，并且是非营利性的美国 PostgreSQL 协会的董事会成员。Jonathan 喜欢用 PostgreSQL 构建应用程序，并热衷于展示 PostgreSQL 的所有精彩特性。在 Crunchy Data 之前，乔纳森是 VenueBook 的首席技术官，在此之前，他是 Paperless Post 的技术副总裁。在这两家公司中，Jonathan 利用 PostgreSQL 开发了健壮的平台，利用了它的许多特性，从复杂的数据类型到流逻辑变化的能力。Jonathan 毕业于塔夫茨大学，拥有计算机科学学士学位和数学学士学位。](https://www.crunchydata.com/) [](https://www.crunchydata.com/)

你不用看太远就会发现，云计算、物联网(IoT)和机器学习/人工智能等宏观趋势都在推动从数据中心到公共云再到互联设备的应用和计算需求的创建。我们现在看到用户在讨论将数据源扩展到应用程序和用户的能力，称之为“边缘计算”

边缘计算通过将应用程序和处理能力放在离创建或使用数据的设备和传感器更近的地方，帮助企业变得更加主动和动态，使他们能够更快地收集、分析大量数据流并将其转化为可操作的见解。各地的行业都在发现将边缘计算与云原生应用和云运营模式相结合可以为其业务创造的转型机会。

幸运的是，开源软件特别适合解决边缘计算用例所需的固有灵活性。

特别是，PostgreSQL、Apache Kafka 和开源数据更改捕获软件 [Debezium](https://debezium.io/) 可以使用 Kubernetes 上的 Kubernetes 操作符进行部署，以提供云原生数据分析解决方案，该解决方案可用于各种使用案例和跨混合云环境，包括数据中心、公共云基础架构和边缘。

## 边缘数据分析

基于 PostgreSQL 和 Kubernetes 构建的云原生数据分析服务的一个强大应用是联网车辆的空间数据分析。

联网汽车，无论是用于打车还是送货服务，都会产生大量的传感器数据，并受益于聚合和处理这些数据所产生的丰富分析。这些互联车辆以及制造和物流生态系统中的支持车队管理系统将从云原生数据分析服务中受益。

装有传感器的移动物体车队(又名“远程信息处理”)产生的原始数据量大且变化快。它还包含许多分析见解，可以使用将流处理与边缘数据库结合起来提取感兴趣的数据以整理和分析这些数据的系统来挖掘这些见解。

> PostgreSQL、Apache Kafka 和 Debezium 可以使用 Kubernetes 上的 Kubernetes 操作符进行部署，以提供云原生数据分析解决方案，该解决方案可用于各种使用案例和跨混合云环境，包括数据中心、公共云基础架构和边缘。

标准架构采用一系列原始位置，并将其校正为感兴趣的已知出行路径:街道网络。可以提取特定的数据片段，然后进行归纳。例如，一辆汽车的加速度计中出现的硬“Z 尖峰”可能是一个故障，但如果与多辆汽车的尖峰聚集在一起，则可能表明有需要维护的坑洞。尖峰可以从主流中提取出来，并在单独的边缘分析数据库中进行分析。

类似的系统可以采用聚合来分析大规模模式，如通勤运动，或小规模现象，如道路上持续的低速区域。关键是将中间过程数据从(巨大的、难以区分的)主数据流中移出，并移入边缘数据库，以进行交互式探索和可视化。

Kubernetes 上的开源[Crunchy PostgreSQL](https://www.crunchydata.com/products/crunchy-postgresql-for-kubernetes/)、Apache Kafka 和 Debezium 的结合，提供了一个从这些处于边缘的联网汽车到公共云或私有云数据中心的数据分析管道。

## 变更数据捕获的优势

微服务团队通过避免依赖(如共享数据库层或公共访问模型)来获得敏捷性。对于这种信息共享挑战，一种流行的解决方案是让每个微服务团队在其选择的中间存储中复制数据，并用其他团队拥有的数据填充它。

变更数据捕获(CDC)是一种为系统建立的完善的软件设计模式，它监视和捕获数据中的变更，以便其他软件可以响应这些变更。CDC 从数据库表中捕获行级更改，并将相应的更改事件传递给数据流总线。应用程序可以读取这些变更事件流，并按照事件发生的顺序访问这些变更事件。因此，变更数据捕获有助于在传统数据存储和新的云原生事件驱动架构之间架起桥梁。

[Debezium](https://debezium.io/) 是一组分布式服务，它捕获数据库中的行级变化，以便应用程序可以看到并响应这些变化。Debezium 构建于 Apache Kafka 项目之上，使用 Kafka 将变更从一个系统传输到另一个系统。

过去，数据保存在一个整体的数据存储中。较新的系统趋向于微服务，在微服务中，数据处理被分解成更小的离散任务。此时的挑战是确保每个微服务都有最新的数据副本。CDC 在这方面表现出色，因为它:

●使用预写日志来跟踪更改

●使用数据存储管理更改(离线时不要丢失数据)

●立即推动变革

使用 Debezium 捕获变更数据最有趣的一点是，它的核心是使用 CDC 来捕获数据并将其推送到 Kafka。源 PostgreSQL 数据库保持不变，因为我们不必添加触发器或日志表。事实上，PostgreSQL 拥有内置的本地 CDC 设施已经将近十年了！这是一个巨大的优势，因为触发器和日志表会降低性能。此外，PostgreSQL 管理更改的方式使得这些更改在重启或停机期间不会丢失。

这使得系统更加灵活。如果您想添加一个新的微服务，只需订阅 Kafka 中与该服务相关的主题。

## 边缘数据分析工具箱

在云原生应用程序中实施数据库和数据分析涉及几个步骤和工具，从数据摄取、初步存储，到用于分析和分析的数据准备和存储。一个开放的、适应性强的架构将帮助你更有效地执行这个过程。这种架构需要几项关键技术。Container 和 [Kubernetes](https://www.redhat.com/en/topics/containers/what-is-kubernetes) 平台为跨基础设施部署数据库、数据分析工具和云原生应用提供了一致的基础，并为开发人员提供了自助服务功能和集成计算加速。

PostgreSQL、Apache Kafka 和 Debezium 可以使用 Kubernetes 上的 Kubernetes 操作符进行部署，以提供云原生数据分析解决方案，该解决方案可用于各种使用案例和跨混合云环境(包括数据中心、公共云基础架构和边缘)的云原生应用程序开发和部署的所有阶段。

PostgreSQL 是一个强大的开源对象关系数据库系统，拥有超过 25 年的积极开发经验和强大的开发社区。虽然 Postgres 因其 SQL 合规性、可靠性、数据完整性和易用性而作为事务数据库而闻名并广受欢迎，但它也可以扩展到性能高级数据分析功能。当与 PostGIS(PostgreSQL 的地理空间扩展器)结合使用时，PostgreSQL 用户能够在 PostgreSQL 数据库中执行强大的空间分析。也就是说，为了从 Postgres 对边缘应用程序的丰富分析能力中获益，有必要将数据从边缘应用程序转移到 PostgreSQL。

[Crunchy PostgreSQL for Kubernetes](https://www.crunchydata.com/products/crunchy-postgresql-for-kubernetes/)允许企业在 Kubernetes 上部署生产就绪、可信的开源 PostgreSQL。由[开源 PGO 提供支持:Postgres 操作符](https://github.com/CrunchyData/postgres-operator)来自 Crunchy Data，Crunchy PostgreSQL for Kubernetes 以交钥匙方式提供了在企业级运行 PostgreSQL 的基本特性。其中包括配置、高可用性、灾难恢复(备份&恢复)、监控、高级安全控制等等。

Apache Kafka 已经成为这种复制类型的首选流技术。Kafka 因其性能、可伸缩性和重放流的能力而受到这些团队的重视，因此这些团队可以将他们的中间存储重置到任何时间点。这不仅有利于微服务团队，也有利于大量用例，包括网站活动跟踪、指标和日志聚合、流处理、事件源和物联网(IoT)遥测。随着越来越多的应用程序迁移到 Kubernetes，能够在同一平台上运行通信基础设施变得越来越重要。Kubernetes 作为一个高度可扩展的平台，非常适合 Kafka 等消息传递技术。Strimzi Kafka 操作符通过使用强大的操作符来简化 Apache Kafka 在 Kubernetes 上的部署、配置、管理和使用，使 Apache Kafka Kubernetes 的运行和管理变得本地化。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>