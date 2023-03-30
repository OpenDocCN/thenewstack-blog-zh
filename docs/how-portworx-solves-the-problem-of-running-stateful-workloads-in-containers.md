# Portworx 如何解决在容器中运行有状态工作负载的问题

> 原文：<https://thenewstack.io/how-portworx-solves-the-problem-of-running-stateful-workloads-in-containers/>

当引入容器时，它们还不能运行有状态的工作负载，比如数据库和内容管理系统。Docker 最终添加了卷等功能，试图通过将主机的文件系统暴露给容器来解决这个问题。

当您开始使用像 Kubernetes 这样的容器编排器时，运行有状态工作负载的挑战会成倍增加。虽然在 Kubernetes 中扩展无状态容器非常容易，但是管理数据库的正常运行时间却很复杂。Kubernetes 试图通过 StatefulSets 来缓解这一问题，stateful sets 是一种专门构建的控制器，它将复制集的易用性带到了有状态工作负载中。StatefulSets 包含 Pods，这些 Pods 遵循服务发现的明确定义的、可预测的命名约定。作为 Kubernetes StatefulSet，很容易运行主/从设置。这打开了将遗留数据库工作负载移植到容器的大门。诸如主/从、主动/被动等现有拓扑可以很容易地映射到 Kubernetes StatefulSet。

Kubernetes StatefulSets 主要关注服务发现和 pod 的健康状况。例如，如果集群中运行的一个 MySQL 节点死亡，Kubernetes 控制器可以恢复与故障 Pod 同名的故障 Pod。主节点重新发现节点，并开始复制数据。

Kubernetes StatefulSets 没有解决底层存储的可用性问题。当 StatefulSet 控制器处理计算的调度问题时，它将存储编排留给底层引擎。

> Portworx 从一开始就被设计成一个容器原生的、支持编排的存储结构。它聚合底层存储，并将其作为软件定义的可编程块设备公开。它做了 Amazon EBS 对 Amazon EC2 实例所做的事情，但是是针对容器的。

最初，客户使用 GlusterFS 或 NFS 作为跨越 Kubernetes 集群所有节点的分布式存储层。因为存储在任何节点上都是可用的，所以 Pod 可以获得对数据的访问，而不管它在哪里被调度。尽管这种拓扑使数据在整个集群中可用，但它不能满足在生产环境中运行的数据库工作负载的高吞吐量和 IOPS 要求。

另一个挑战是存储操作和存储管理任务是在 Kubernetes 之外完成的。传统存储管理员不理解 Kubernetes 的基本原理，而云原生开发人员和开发人员发现很难处理传统存储。

## **Portworx 作为容器原生存储平台**

Portworx 从一开始就被设计成一个容器原生的、支持编排的存储结构。它做了 Amazon EBS 对 Amazon EC2 实例所做的事情，但是是针对容器的。它聚合底层存储，并将其作为软件定义的可编程块设备公开。与 EBS 类似，容器开发人员和操作人员不需要知道物理存储是如何管理的。他们使用熟悉的工作流来定义持久卷控制(PVC)并在 pod 内使用持久卷(PV)。

作为 DaemonSet 部署，Portworx 将自己安装到集群的每个节点中。它会发现可用的存储，以创建容器本机数据块存储设备。

Portworx 可以聚合现有的 SAN 或特定于云的块存储，将其作为容器原生存储。例如，运行三个节点的 Google Kubernetes 引擎集群可以公开一个来自连接到每个节点的持久性磁盘的聚合存储池。如果每个节点都连接了一个 100GB 的 SSD 磁盘，Kubernetes 将看到 300GB 的原始存储，可用于 PVC 和 PVs。

使用 Portworx 的主要好处之一是数据的高可用性。为工作负载创建存储类时，您可以指定定义数据集冗余的复制因子。写入卷的每个数据块都将自动复制到群集的其他节点。这种机制在整个集群中维护一致的数据镜像。当 Kubernetes 控制器删除并重新创建一个 Pod 时，无论调度哪个节点，Pod 都可以访问数据。这种架构有效地将数据从计算中分离出来，使有状态 pod 能够享受与无状态 pod 相同的灵活性。

去年，Portworx 以 [STORK](https://portworx.com/stork-storage-orchestration-kubernetes/) 的形式为 Kubernetes 引入了一个定制调度程序，这是一个针对 Kubernetes 的存储编排运行时。该调度程序帮助 Kubernetes 将 Pod 放置在已经存在相关 PVC 的节点中。STORK 将 DevOps 团队从创建复杂的注释和标签对中解放出来，以实现 pod 的节点关联。借助 STORK，即使在灾难性故障期间，有状态的工作负载也总能找到正确的节点。

Portworx 有效地弥合了传统存储管理和云原生开发操作之间的差距。它为传统存储操作提供了本机原语，例如扩展卷、备份、恢复卷、迁移数据，甚至为卷定义 QoS 策略。

下次当您发现自己在生产中运行有状态的工作负载时，不要依赖像 NFS 或 GlusterFS 这样的遗留分布式文件系统。评估 Portworx 一致的、容器本地的、集成编排的存储处理方法。

在即将发表的一篇文章中，我将演示如何使用 Portworx 实现不同 Kubernetes 集群之间的数据可移植性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>