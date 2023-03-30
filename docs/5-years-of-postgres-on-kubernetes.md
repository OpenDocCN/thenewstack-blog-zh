# Kubernetes 上的 5 年 Postgres

> 原文：<https://thenewstack.io/5-years-of-postgres-on-kubernetes/>

Kubernetes 的 Postgres 运营商的想法源于 2016 年与社区成员的一次对话。这是在 Kubernetes 的早期，在容器中运行数据库的想法是有争议的。

如今，人们可以使用一系列工具和技术在 Kubernetes 集群中运行稳定、高可用性和高性能的 Postgres 工作负载，包括 Crunchy Data 等公司的[操作员](https://www.crunchydata.com/products/crunchy-postgresql-for-kubernetes)。

在整个行业，我们看到越来越多的人成功地利用[运营商架构模式](https://thenewstack.io/kubernetes-when-to-use-and-when-to-avoid-the-operator-pattern/)来处理不同的工作负载。我的客户经历，以及与更大的社区的经历，让我对 Kubernetes 的 Postgres 世界有了细致入微的了解。今天，我想更广泛地分享这些经验教训，并对 Kubernetes 五年后的经验教训提出见解。

## 基础设施就是代码

从一开始，operators 背后的[概念就是它们会在功能上自动化你的 Kubernetes 应用程序。这意味着在 Kubernetes 空间中实现了基础设施即代码。这是 DevOps 长久以来的梦想——一个自我修复、版本控制、自我安排和声明式定义的平台。](https://thenewstack.io/the-runaway-problem-of-kubernetes-operators-and-dependency-lifecycles/)

随着 Kubernetes 的发展和 API 的成熟，在 Kubernetes 中交付一个完全声明性的 Postgres 操作符成为一个越来越容易实现的目标。我们也开始从我们的用户和客户那里听到他们希望看到项目采用一种更加声明性的方法。

幸运的是，这也是我们一直在思考的事情。这成为 Kubernetes 第五个主要版本 Crunchy Postgres 背后的关键驱动力。虽然我们在设计这个版本的 Postgres 操作符时有几个想法，但我们的主要目标是让 Kubernetes 的 Postgres 具有完全的声明性。这不是一个小任务；本质上，这是一次彻底的重建。从最新的现代 Kubernetes 功能开始，我们能够为 Kubernetes 开发一个新版本的 Crunchy Postgres，使用户能够简单地描述他们想要的最终结果，Kubernetes 的 Crunchy Postgres 会完成剩下的工作。

## 从存储开始

数据库不同于无状态应用，因为它们需要[持久存储](https://kubernetes.io/docs/concepts/storage/persistent-volumes/)。Kubernetes 提供了强大的自动化和许多有趣的功能，但我们知道我们需要一种方法来提供一致和有状态的存储，因为存储是数据库功能的基石之一。

存储需求最终促使我们将 Kubernetes 技术与运营商结合起来。

今天，运行在 Kubernetes 上的数据库可以利用一系列存储类型，如主机路径、网络文件系统(NFS)和动态存储。Kubernetes 的 Crunchy Postgres 与存储无关:它可以与任何支持的 Kubernetes 存储系统一起工作。尽管自动存储资源调配器确实存在，但您必须为主机路径和 NFS 配置持久卷。动态存储类允许用户请求持久卷声明，并为您创建[持久卷](https://kubernetes.io/docs/concepts/storage/persistent-volumes/)。有许多动态存储类的提供者可供选择。您需要配置适合您环境的内容，并确定物理卷和永久卷(PVs)的大小。

## Postgres 操作符，Kubernetes 中 Postgres 的简单按钮

早期，Kubernetes 的运营商模式是未知领域。在容器中运行有状态流程(比如数据库)是一个非常新的概念。operator 模式展示了简化 Kubernetes 上数据库的操作和管理的潜力。从我们的团队听到 CoreOS 的提议的那一刻起，我们就看到了希望。

在早期，关于操作符模式的适当使用以及操作符模式是否具有持久性，有相当多的争论。早期的一些人问了关于舵图和操作符之间的权衡的问题。剧透:它们是不同的，你可能两者都想要！

构建一个高度可用、自我修复的 Postgres 集群非常困难。您必须考虑备份、跨数据库的负载平衡、指标、数据库主机变化、存储以及正确调整所有这些服务的规模。您还必须确保这些服务一直在运行。你需要考虑如何处理版本升级、安全补丁等等。

Kubernetes 的 Crunchy Postgres 是 Kubernetes 上 Postgres 的首批运营商之一，其丰富的经验体现在简单的设置和高度灵活的架构上。让人们能够创建具有高可用性和内置自我修复功能的 Postgres 集群，这是 Kubernetes 团队在 Crunchy Data 的主要目标；然而，我们无法单独做到这一点。

## 倾向于 API

Kubernetes 自早期以来发展迅速，其 API 也是如此。底层 API 经常在不同版本之间变化，以增强新功能或巩固功能。Kubernetes 的 Crunchy Postgres 随着 Kubernetes APIs 一起发展，您可以在 Postgres 操作符的第五个主要版本中看到这些年工作的高潮。

通过使用运营商的 API 功能，团队感受到了 Kubernetes 的真正力量。这些 API 能够执行许多任务，如部署、添加用户、从失败的健康检查中恢复、运行备份、从备份中恢复等。当使用这些 API 时，团队开始升级。CI/CD 功能在团队中变得更加可重复，部署转移是一个自动化而不是手动的过程，因此每个数据库都统一运行，而不是作为边缘情况。

为了实现这一功能，必须将操作员的使用集成到许多其他系统中。例如，我们的客户将 API 级集成到了他们的票证系统、部署系统、分析团队、营销团队、运营团队和代码库。因此，Kubernetes 的 Crunchy Postgres 必须有稳定的 API，并得到一个考虑到兼容性的团队的支持。在所有的集成点上，部署带有流动 API 的操作符很快会成为一种负担。

## 展望未来

我相信我们最初支持 operator 模式来管理像 Kubernetes 中的 Postgres 这样的有状态服务是一个很好的选择。随着 Kubernetes 的成熟，操作符模式和 API 也在不断发展以加强这种方法，我们的 Postgres 操作符也随着社区的发展而成熟。早期，我们感受到了支持的浪潮，并对围绕这个多年前就有的想法形成的协作和社区表示赞赏。

我们对未来所看到的以及我们对运营商模式的进一步成熟和该模式的实现的想法感到兴奋。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>