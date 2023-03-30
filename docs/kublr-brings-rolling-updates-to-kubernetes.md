# Kublr 为 Kubernetes 带来滚动更新

> 原文：<https://thenewstack.io/kublr-brings-rolling-updates-to-kubernetes/>

新发布的 [Kublr](https://kublr.com/) 1.16 是一个有助于部署企业级 Kubernetes 集群的工具，是第一个为开源容器编排引擎提供滚动更新的多云多平台 Kubernetes 平台，该公司是该技术的幕后声称。

Kublr 首席技术官 [Oleg Chunikhin](https://www.linkedin.com/in/olegch/) 表示:“无论您是想确保基础设施、应用程序或生产组件及时升级，还是想在安全修复和补丁发布后立即应用以避免漏洞，这项功能都是必不可少的。

滚动更新功能之前的典型流程是，IT 专业人员需要部署不同的集群并复制应用程序，以便在更新原始集群的同时一致地提供服务。但是，这个新特性节省了时间和资源，因为不需要运行并行集群。

“在一个 Kubernetes 和云原生世界，这种能力比以往任何时候都更重要，”他说。“生态系统正在快速发展，组件也在快速变化。想想 Kubernetes 的季度更新吧。然后是所有其他组件，每个组件都有自己的发布时间表。这与传统的硬件/虚拟机基础架构相去甚远，在传统的硬件/虚拟机基础架构中，更新的发布速度要慢得多。您的 ops 和 DevOps 团队希望立即利用新功能，每次都关闭集群来实现这一点是不可行的。"

“虽然云提供商已经提供滚动更新有一段时间了，”Chunikhin 说，“但对于允许您在自己的基础设施中部署集群的提供商来说，情况并非如此。Kublr 能够在不停机的情况下在所有支持的环境(无论是云环境还是本地环境)中统一升级集群，这使得 IT 运营团队能够在不牺牲灵活性和运营敏捷性的情况下进行扩展。”

## 新功能是如何工作的？

Kublr 在其网站上发布了一篇博客，对如果[决定利用](https://kublr.com/blog/kubernetes-rolling-upgrades-zero-downtime-cloud-and-on-prem/)滚动更新，IT 团队可以期待什么给出了一些见解。

在升级过程中，Kublr 自动从与被更新的节点相关联的节点重新调度正在运行的应用程序。这种方法意味着用户可以根据自己设置的细节来最小化运行实例的总数。然后，该应用程序在不导致停机的情况下为客户端提供服务。

无论公司是在内部环境中运营还是依赖亚马逊网络服务(AWS)、谷歌云平台(GCP)或微软 Azure，1.16 版都支持它们。Kublr 还提供了裸机和气隙环境的兼容性。用户应该期望群集和基础架构升级在所有这些环境中都同样顺利。

虽然其他 Kubernetes 产品允许执行更新，但 Kublr 在提供这些滚动更新方面是独一无二的，因为它是第一个提供这些更新的独立 Kubernetes 引擎。还不是 Kublr 客户的人可以免费部署这个工具，看看它如何为他们工作，并尝试这个新选项。

### 滚动更新可以与基于角色的访问控制(RBAC)集成

对基于角色的访问控制(RBAC)的支持是 Kublr 提供的另一个最新发展，最早出现在 1.15 版本中。在访问 Kublr 用户界面时，人们可以选择该公司的 RBAC 或与 Kubernetes 相关的 RBAC。Kublr 的 RBAC 允许系统管理员[设置不同用户组的集群访问级别](https://kublr.com/blog/enterprise-grade-rbac-management-for-kubernetes/)。RBAC 允许决定一个人是否可以创建或更新一个集群的基础设施或与该集群相关联的 Kubernetes 版本。

然后，Kubernetes 提供的 RBAC 允许配置与不同用户组相关的人在集群中可以做什么的权限。例如，在系统中具有适当权限的人可以编辑和管理集群的资源，包括其资源和对象。

Kublr 用户界面简化了 RBAC 的顾虑。不管一个集群使用的是 Kublr 的 RBAC 还是 Kubernetes 的，用户都可以在一个地方访问所有的集群，这样可以减少混乱。此外，这种设置增强了安全性，因为它允许经过授权的 Kublr 用户验证每个集群的适当权限是否有效。此外，还有一个集中式 RBAC 功能，可以将任何 RBAC 权限扩展到集群收集的日志。

在宣布滚动更新功能时，Kublr 宣布其 RBAC 功能仍然适用于使用 1.16 版本的用户。

## Kubernetes 的使用率正在上升

It 团队应该很容易理解为什么与 Kublr 相关的滚动升级和 RBAC 功能可以简化他们公司使用 Kubernetes 的方式。消除与集群部署和管理相关的不必要步骤至关重要，尤其是考虑到越来越多的各种规模的公司都在使用 Kubernetes 集群。

根据云计算原生计算基金会(Cloud Native Computing Foundation)2019 年的一项调查[，78%的受访者表示他们正在生产中使用 Kubernetes。这一比例比前一年的调查结果增加了 20%。此外，处于评估阶段的人数减少了近一半(48%)，因为许多以前的评估人员都进入了生产阶段。](https://www.cncf.io/wp-content/uploads/2020/03/CNCF_Survey_Report.pdf)

大多数使用 Kubernetes 的受访者表示，他们有 2-5 个集群在生产，43%的人选择这个数量。与此相关的是，有 10%的缔约方表示他们在生产 2-10 个集群。

这些统计数据强烈地表明，越来越多的 IT 决策者认为 Kubernetes 是他们的明智选择。随着他们对 it 的采用率持续上升，像 Kublr 提供的那些功能可能会变得越来越相关和受欢迎。

### 更简单的集群管理

"我们的最终目标是成为真正的元云，Chunikhin 说. "一种新型基础架构，具有灵活的云原生企业级模块，包括存储、网络、数据管理和 BCDR，可跨不同的公共云、私有云及内部基础架构进行部署。这是相当雄心勃勃的——我们知道这一点。这也反映在我们广泛的路线图中，随着每一次迭代，我们都更加接近目标，这非常令人兴奋。"

他说:“我们将扩大 IT 运营团队的能力，以可靠和治理良好的方式在整个组织中提供 Kubernetes。”计划的功能包括:

*   维护 Kubernetes 和其他组件的版本对等
    Kubernetes 是极少数支持最新发布的 Kubernetes 版本的企业 Kubernetes 解决方案之一
*   支持外部供应的集群(例如云管理的 Kubernetes 和其他 Kubernetes 供应和管理工具)。这个特性将把 Kublr 的操作特性，如集中式日志收集、监控、安全和 RBAC 扩展到非 Kublr 配置的集群。
*   广泛的治理政策，允许 IT 运营定义软件开发团队使用和操作 Kubernetes 集群的治理规则和限制，包括网络、访问控制、资源配额等。
*   与多站点(多云、多区域、混合)Kubernetes 部署相关的高级功能，包括网络连接、联合、数据复制、多站点协调和灾难恢复。
*   众多应用程序包和合作伙伴集成，如 CI/CD (Spinnaker，Jenkins)、服务网格(Istio，Linkerd)、FaaS (OpenFaaS)、安全(NeuVector)、存储(Ceph/Rook、Portworx、Yugabyte、HDFS)、数据科学(Spark)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>