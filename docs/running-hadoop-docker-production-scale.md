# 在 Docker 上、生产中和大规模运行 Hadoop

> 原文：<https://thenewstack.io/running-hadoop-docker-production-scale/>

当您的业务不仅依赖于在多租户配置中可靠、大规模地运行 Hadoop，还依赖于从系统中获取最后一点效率时，您会怎么做？对于专门针对 Hadoop 工作负载的 Hadoop 即服务产品提供商 Altiscale 来说，答案很简单——在容器和 Docker 上运行 Hadoop。

简单，但肯定不容易，Altiscale 的 Nasser Manesh 解释道，他是该公司的编排产品负责人，在上周的 Strata + Hadoop World conference 上分享了该公司运行 Hadoop 和 Docker 的经验。

在生产中运行 Docker 是最先进的。在 Docker 上运行该公司的 Pb 级 Hadoop 集群，在生产中，是一个完全不同的野兽，当他们 18 个月前开始他们的旅程时，几乎没有蓝图。

## 为什么是 Docker？

作为一种特定于工作负载的平台即服务(PaaS)产品(这是我的话，不是他们的话)，Altiscale 数据云提供了该公司所谓的“Hadoop dialtone”。用户能够通过各种面向批量和事件的机制和 API 将数据加载到 Hadoop 分布式文件系统(HDFS)中，并部署 MapReduce、Pig、Hive 和其他应用程序来直接操作这些数据，而无需部署或配置 Hadoop。

虽然该公司确实允许用户根据基础设施指标(如内存和 CPU 消耗)来监控工作性能，但它在其他方面抽象出了节点、集群和其他基础设施级问题的概念。这使得公司能够根据自己的判断划分和分配资源。事实上，获得正确的资源分配是公司利润的关键决定因素，因此至关重要。因此，优化公司技术平台的这一方面是一项业务任务。

虚拟化已经很好地解决了云提供商的分区/分配问题，但它带来的开销对 Altiscale 的利润来说是致命的。

> Manesh 说:“进入虚拟机管理程序的每一个 CPU 周期都是浪费金钱。"同样，RAM 的每个字节."

输入 Docker。像 Docker 这样的容器技术对 Altiscale 很有吸引力，因为它们能够提供轻量级隔离和虚拟化，从而降低开销，加快部署和重启，并简化迁移。

## Hadoop 上的 Docker 还是 Docker 上的 Hadoop？

Altiscale 工程师需要做出的第一个决定是在 Hadoop 中运行 Docker 还是在 Docker 上运行 Hadoop。

在 Hadoop 环境中运行 Docker 将允许该公司利用 YARN，这是 Hadoop 2.0 中引入的数据处理框架。这将是理想的，因为 Altiscale 团队非常了解 YARN，并且是开源项目的贡献者。YARN 日益强大的资源管理功能将允许 Altiscale 系统简单地请求 Hadoop 来启动和管理容器，从而消除大量的架构复杂性。不幸的是，正如团队所了解到的，让 Docker 在 Hadoop 上工作需要 YARN 和 Docker 的支持，这需要时间来实现。

另一方面，在 Docker 容器中运行 Hadoop 为公司提供了一个直接的机会，无需依赖于向任何一个项目添加新功能。虽然在不利用 YARN 的情况下，最终的解决方案会更加复杂——Altiscale 系统需要直接供应和管理 Docker 容器——但 Manesh 和他的团队发现这是可重复和可自动化的。

Docker 上的 Hadoop 方法允许 Altiscale 将 HDFS 的 DataNode 和 YARN 的 NodeManager 进程(传统上在其 Hadoop 集群中的每个从节点上配对)移动到单独的容器中。将这些进程部署为容器将为 Altiscale 提供许多重要的好处，包括让公司在跨其基础架构分配这些进程时具有高度的灵活性，允许独立管理分配给每个进程的计算和内存资源，以及支持更大的整体弹性和突发能力。

## 码头工人的不足之处

Altiscale 在启动和运行该架构并保持其大规模运行方面遇到了挑战。根据 Manesh 的说法，其中许多都是操作问题。

> “虽然 Docker 从开发和 DevOps 社区获得了很多可见性，但它的运营成熟度仍有许多不足之处，”Manesh 说。“这不利于操作。”

“我们遇到的大多数问题都源于这样一个事实，即与开发中的应用程序相反，Docker 并不是为支持生产系统所需的长期运行的容器而设计的。支持是不存在的。”

Manesh 概述了 Altiscale 遇到的一些挑战:

*   Docker 需要独立的编排、供应和自动化，而不是在 YARN 之上运行。
*   在分布式 Docker 环境中，日志记录很困难。您期望工作的事情——比如使用 syslog 来收集日志——没有工作，因为特定于容器的日志条目没有与主机操作系统的日志条目完全分开。
*   社交网络是彻头彻尾的痛苦。Docker 使得管理 IP 地址和使用 iptables 这样的标准 Linux 网络任务变得困难。Altiscale 工程师在 Docker IP 堆栈试图分配事物的方式中发现了许多竞争条件，导致了令人沮丧的体验，有些时候事情可以工作，但有些时候不行。

“由于这些问题，我们经历了几次重大挫折，”Manesh 说。“我们不得不三次重新构建节点的启动过程。"

> “我们遇到的一些问题是开发人员在笔记本电脑上看不到的，”他补充道。“它们只出现在具有真实 BIOS、12 个磁盘驱动器、3 个网卡等的真实服务器上。，然后他们开始以一种真实的方式出现。发现并解决这些问题需要相当长的时间。”

## 生产之路

大约九个月前，Altiscale 发布了第一批集装箱节点投入生产。随着公司逐步推出新的架构，与物理节点相比，容器化节点的百分比目前仍然很小。

Manesh 指出，虽然大量的工作已经投入到这个项目的启动和运行中，但 Altiscale 的工程师并没有对 Docker 核心进行修改，这些修改仍然是专有的。

“我们试图远离这种情况。Docker 将继续发展和前进。我们不想维持自己的分叉。”

相反，公司工程师是 Docker 开源项目的积极贡献者，他们已经将自己创建的一些脚本和工具贡献给了这个社区。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>