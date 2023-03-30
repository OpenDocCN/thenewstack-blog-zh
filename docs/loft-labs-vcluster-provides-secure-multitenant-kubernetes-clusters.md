# Loft Labs 的 vcluster 提供安全的虚拟多租户 Kubernetes 集群

> 原文：<https://thenewstack.io/loft-labs-vcluster-provides-secure-multitenant-kubernetes-clusters/>

本周，Loft Labs 的 vcluster 成为经过认证的 Kubernetes 发行版，成为“第一个通过 100% Kubernetes 一致性测试的虚拟集群解决方案。”根据该公司的一份声明。

[Loft Labs](https://loft.sh/) 成立于两年前，其目标是使组织能够扩展对 Kubernetes 的自助访问，今年早些时候，[公司开源了](https://www.businesswire.com/news/home/20210419005152/en/Loft-Labs-Open-Sources-Virtual-Cluster-Technology-for-Kubernetes)该技术的一部分作为 [vcluster](https://github.com/loft-sh/vcluster) 。

Vcluster 允许工程师构建轻量级的虚拟 Kubernetes 集群，这些集群运行在底层 [Kubernetes 集群](https://thenewstack.io/what-does-it-take-to-manage-hundreds-of-kubernetes-clusters/)的名称空间内。这样，vcluster 不仅提供了一种更加节省资源的方式来启动多个集群，还提供了一种软多租户形式，无需向过多用户分发管理员凭据。

Loft Labs 首席执行官 [Lukas Gentele](https://www.linkedin.com/in/gentele/) 在一次采访中解释说，vcluster 直接源于该公司将 Kubernetes 访问从 10 名工程师扩展到 10，000 名工程师的主要目标，这源于开发人员以通常不允许的方式使用 Kubernetes 的需求。

“云原生应用越多，对你的工程团队就越重要，不仅仅是运营和生产团队，而是专注于开发的工程团队，尽早访问 Kubernetes，以选择正确的架构，以正确的方式构建工具，”Gentele 说。“从本质上说，这就是我们商业产品的来源，虚拟集群应运而生，因为我们需要做的不仅仅是名称空间。”

Gentele 解释说，工程师可能想要采取各种行动——从运行不同的 Kubernetes 版本到安装操作员和 CRD，再到更改权限——这些行动在没有管理权限的共享集群上是无法实现的。当然，问题是他们的行为可能会影响同一个集群上运行的其他应用程序和用户。答案是 vcluster，它使用最初由 Rancher 创建的轻量级 [k3s](https://k3s.io/) Kubernetes 发行版提供了一个虚拟集群，现在是由[Cloud Native Computing Foundation](https://cncf.io/?utm_content=inline-mention)(CNCF)开发的一个沙盒项目。

Gentele 说，Vcluster 的工作原理是“本质上部署一个单独的控制平面”。构建一个虚拟集群意味着创建一个有状态的集合，这就创建了一个包含两个容器的 pod。一个是 k3s，带有 k3s API 服务器(虽然 Gentele 说完整的 Kubernetes API 是为未来计划的)和控制器管理器，它负责处理副本号。第二个容器运行 syncher，它使用底层的 Kubernetes 集群创建必要的 pods，如副本号所示。Gentele 解释说，与您对虚拟化环境的预期相反，运行 vcluster 时不会影响性能，因为应用程序实际上是在底层集群上运行的。他说，你的实际应用程序运行起来“和你直接启动它们时完全一样”

鉴于本质上的差异，成为 100%符合 Kubernetes 的虚拟集群是一项艰巨的任务，但 Gentele 说，他认为这是一个重要的里程碑。

“我认为达到这一点非常重要，因为它向人们保证他们不仅可以在开发中使用 vcluster，”他指出。“如果您有一个受管产品，并且希望在不同的 v cluster 中托管不同的客户，您希望确保该集群是一个符合标准的 Kubernetes 集群，这不仅仅是因为它为您提供了某种基准，它还确保您可以在 v cluster 和真正的集群之间无缝过渡工作负载。所以我们做的事情没有局限性。它是 100% Kubernetes API，您可以在 vclusters 和 real clusters 之间来回移动工作负载。我认为确保这一点非常重要。”

vcluster 还处于早期阶段，只有 0.3 版，Gentele 表示该项目希望尽可能保持灵活性。他说 vcluster 将努力增加的一项功能是增加不同 vcluster 实例之间的通信，并提供共享服务的能力。虽然未来的具体功能可能尚未确定，但有一点是肯定的，Gentele 认为，一旦 vcluster 变得更加成熟，CNCF 就是它的未来之家。

Gentele 表示:“我们希望看到 vcluster 在 CNCF 的发展。“我坚信 vcluster 是 Kubernetes 多租户的一个重要组成部分，它解决了许多问题，甚至超出了使用案例的范围，因此它应该成为 CNCF 的一部分。我们肯定想让它成为一个沙盒项目。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>