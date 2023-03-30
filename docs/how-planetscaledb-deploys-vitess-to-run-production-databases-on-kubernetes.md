# PlanetScaleDB 如何部署 Vitess 在 Kubernetes 上运行生产数据库

> 原文：<https://thenewstack.io/how-planetscaledb-deploys-vitess-to-run-production-databases-on-kubernetes/>

[](https://www.linkedin.com/in/jitenvaidya/)

 [吉滕·瓦伊迪亚

吉滕·瓦伊迪亚是 PlanetScale 的联合创始人兼首席执行官。Jiten 拥有超过 25 年的软件工程师和经理经验。他是第一批从谷歌调到 YouTube 的工程师之一。他为 YouTube 开发了一个寻呼机，并围绕 MySQL 建立了稳定性和自动化。他还在美国数字服务公司和 Dropbox 工作过。Jiten 喜欢在业余时间阅读和徒步旅行。](https://www.linkedin.com/in/jitenvaidya/) [](https://www.linkedin.com/in/jitenvaidya/)

我们都很熟悉在操作系统虚拟化环境中使用的术语“容器”。但这个词最初是用来描述标准形状的集装箱，它彻底改变了航运。标准化集装箱有许多好处:可以跨多种运输方式高效装卸和堆叠，并且可以使用起重机和叉车等机械化系统进行操作。虽然集装箱在第二次世界大战前就已经存在，但战争的后勤需求使其效用更加明显，并导致其广泛使用。

在新冠肺炎之前，支持操作系统虚拟化并构成编排框架的构件的容器(如 Kubernetes)已经无处不在。然而，新冠肺炎是一个独特的分水岭时刻，类似于第二次世界大战。对社会隔离的需求以及随之而来的数字化转型的加速推动了 Kubernetes 的日益普及。

Kubernetes 已经成为计算资源的事实上的操作系统，无论是在您自己的数据中心还是在公共云中。Kubernetes 抽象出特定于云的需求，让您专注于特性开发和统一部署。在 Kubernetes 上开发和部署还允许您使用为 Kubernetes 平台开发的整个工具生态系统。因此，Kubernetes 已经成为从数据中心向云迁移的主要推动者。

到目前为止，公司一直不愿在 Kubernetes 中部署数据库，因为在编排框架内的容器中运行有状态服务(如数据库)具有挑战性；您不能想当然地认为运行主数据库的 pod 会长寿。Vitess 解决了这些问题。

Vitess 是 YouTube 开发的一个开源项目，现在是云计算原生计算基金会(CNCF)的一个毕业项目，在 YouTube 高速增长的几年里，它被开发用来横向扩展 YouTube 的数据库。YouTube 需要将其 MySQL 数据库迁移到 Borg 下运行，Borg 是谷歌用于管理自己的数据中心的内部容器编排系统，也是 Kubernetes 的蓝图。Vitess 通过开发快速副本修复、透明服务发现和卓越的可观察性解决了这些问题。

在 [PlanetScale](https://www.planetscale.com/) ，当我们考虑在 Vitess 上构建我们自己的托管数据库即服务的选项时，我们很早就决定在 Kubernetes 上运行它，因为 Vitess 本来就是为在 Kubernetes 上工作而构建的。我们做出的一个技术选择是使用 CoreOS 发明的 operator 模式，并构建操作脚手架来部署、管理和监控 Vitess 数据库集群，以开发我们自己的 Vitess 操作符。这使我们能够处理托管的 Kubernetes，抽象出托管的 Kubernetes 服务(如 EKS、GKE 和 AKS)之间的差异，并处理跨多个云提供商的地区，从而为我们的客户提供真正的多云体验。

当我们开发操作符时，我们意识到这种抽象 Kubernetes 集群之间差异的能力也允许我们将我们的控制平面用于客户的 Kubernetes 集群，于是 Kubernetes 的 PlanetScaleDB 诞生了。

PlanetScaleDB for Kubernetes 允许客户配置指向他们自己的 Kubernetes 集群的定制区域，然后使用 PlanetScale 控制平面将 MySQL 兼容的 Vitess 数据库部署到该 Kubernetes 集群中。这确保了数据永远不会离开公司的网络边界，并且符合安全策略。用于 Kubernetes 的 PlanetScaleDB 提供了在 Kubernetes 中运行数据库的所有好处，并且没有管理它的麻烦。

要为 Kubernetes 启用 PlanetScaleDB，我们需要解决两个问题。首先是理解和处理 Kubernetes 环境之间的差异，比如存储类别、可用性区域和异构硬件配置。例如，对于高可用性，我们检测可用性区域，并跨可用性区域部署给定数据库的主数据库和副本数据库。第二个也是更困难的挑战是数据库的持续管理，以确保在面对 pod 驱逐、Kubernetes 主机管理以及在数据库和 Kubernetes 层应用补丁时的高可用性。

我们在 PlanetScaleDB 操作器中构建了这些挑战的解决方案，我们用它来驱动 PlanetScaleDB 云。同一个操作员在客户的 Kubernetes 集群中运行，并为 Kubernetes 提供 PlanetScaleDB。

随着我们过渡到一个远程工作变得普遍的世界，几乎所有的 IT 工作负载都转移到云，带来了 Kubernetes 提供的标准化和通用基础架构的效率，允许公司大规模随身携带他们的事务数据库比以往任何时候都更重要。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>