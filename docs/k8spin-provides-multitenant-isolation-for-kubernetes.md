# K8Spin 为 Kubernetes 提供多租户隔离

> 原文：<https://thenewstack.io/k8spin-provides-multitenant-isolation-for-kubernetes/>

如果超出您的需要，为什么要使用整个 Kubernetes 集群呢？

K8Spin 是一个在 Kubernetes 上提供多租户的项目，它为公司提供了一种将集群上的资源分配给不同部门或团队的方式。

“整个想法始于创造一种服务，让你可以在很多很多人之间共享 Kubernetes 集群。他们每个人都有这个集群的一小部分，” [SIGHUP](https://sighup.io/) 的 Kubernetes 工程师 [Angel Barrera](https://github.com/angelbarrera92) 说。Barrera 与管理 Kubernetes 提供商 [Giant Swarm](https://www.giantswarm.io/) 的解决方案工程师 Pau Rosello 一起创建了 K8Spin。

“基本上，我们希望避免专有接口，就像许多服务提供商一样。我们希望已经了解 Kubernetes 的人能够托管他们的小应用程序，而不必真正关心整个集群，”他说。

## 走向开源

这两位西班牙的自由职业者最初提供 K8Spin 作为软件即服务，但最近关闭了这项服务，转而将其作为一个开源项目，着眼于最终成为云本地计算基金会(CNCF)的项目。

他们说，Kubernetes 不是为多租户设计的，尽管它可以实现，尽管在许多层面上你需要改变或修改 Kubernetes，以允许多人共享同一个集群。

“但我们不想修改 Kubernetes 的代码。Barrera 说:“我们基本上想要做的是在协调器上自动配置所有这些对象，如限制范围和网络策略。

使用 [K8Spin 操作符](https://github.com/k8spin/k8spin-operator)，可以在三个级别上设置 CPU 和 Ram 等资源的边界:组织、租户和空间。集群管理员管理整个组织的集群，设置资源限制并分配角色和权限。租户管理员对该组也是如此，该组可以是一个团队或部门。租户还托管空间，这是一个位于名称空间之上的抽象层，拥有自己的配额和角色。

每个用户都有一个与其他用户完全隔离的空间，对可用资源设置了上限，防止任何用户占用分配给其他人的资源。

K8Spin [管理](https://gitlab.com/k8spin-open/documentation)一个名称空间的所有底层组件，比如主节点配置、内部和外部 SSL/TLS 证书、负载平衡器等。为此，它利用 Kubernetes 机制，如[网络策略](https://kubernetes.io/docs/concepts/services-networking/network-policies/)、[资源配额](https://kubernetes.io/docs/concepts/policy/resource-quotas/)和[限制范围](https://kubernetes.io/docs/tasks/administer-cluster/manage-resources/memory-default-namespace/#create-a-limitrange-and-a-pod)。为了增加安全性和隔离性，它依赖于 Google 开发的用 Go 编写的容器沙箱 [gVisor](https://github.com/google/gvisor) 。它包括一个名为 runsc 的[开放容器倡议](https://opencontainers.org/)运行时，提供了应用程序和宿主 Linux 内核之间的边界。

“我们在 Kubernetes 上使用的技术不是我们发明的。对吗？Barrera 说:“K8Spin 唯一的好处是它可以帮你管理所有这些事情。

Rosello 补充道:“我们想要提供的是一种超级简单的方式来提供配置的环境或可审计的环境，例如，为同一家公司，甚至不同的公司定义环境。我们确实知道如何手动操作。这是一种痛苦，因为有时你会忘记一些事情，一些事情会发生。所以提供一个超级简单的方法

适当地配置你的团队，你的工作，开发者的简单体验。"

## 不同的团队、环境

它也有 Prometheus 和 Loki 的多租户代理和 Grafana 的多租户操作器。今年早些时候，它与 oneinfra 整合，one infra 提供了一个一键式 Kubernetes 控制平面，两个项目继续合作。

“K8Spin 是一个超级强大的开源解决方案，可以在 Kubernetes 集群中实现多租户。SUSE 的软件架构师和 oneinfra 的创建者 [Rafael Fernández López](https://github.com/ereslibre) 说:“它让任何组织都能够轻松地划分给定的集群，从 RBAC 规则到配额，再到网络策略，这些都是非常容易设置和操作的 API 类型。

Barrera 说 K8Spin 还没有准备好投入生产，但是已经有客户在试用并提供反馈。

这不是唯一一个在 Kubernetes 集群上提供多租户的开源项目。其他包括:

来自 Kubernetes 上游项目的[分层名称空间控制器](https://github.com/kubernetes-sigs/multi-tenancy/tree/master/incubator/hnc)(HNC)；[亭子](https://github.com/kiosk-sh/kiosk)；还有[胶囊](https://github.com/clastix/capsule)。

“我想说，我们的解决方案可能是最简单的一个，因为其他解决方案试图做其他事情…他们还试图管理应用程序的部署和其他事情。根据我的经验，以及我们一直在谈论的客户，他们已经有了自己的部署方式，”Barrera 说。

“通常他们缺少的是如何隔离不同的工作负载。例如，有许多人在为多个客户端、多个客户一遍又一遍地运行相同的服务……这些客户端、客户连接在 Kubernetes 内部的同一个网络上。现在他们需要将两者隔离开来。所以他们只需要那一小块。这就是我们试图提供的。我们不会尝试重做整个 Kubernetes 体验。”

巴雷拉说，一些公司不得不在内部为 Kubernetes 建立一些多租户之王，但他们并不想真的这么做。他们真的更愿意使用社区中已经过测试的东西。

Barrera 说，展望未来，该团队希望实现的功能之一是对单个资源按分钟计费，不是从金钱的角度，而是应用分析，以便如果一个团队有不同环境(例如测试、QA 和生产)的空间，可以提供对每个环境使用情况的更多可见性。

巴雷拉说:“我认为我们还有很多想法需要实施，但最终，我们也会倾听用户的意见。”。“我已经知道其中一些公司在这个领域做了些什么，所以我们有一些想法，我们的项目可以放在哪里。”

其中一些公司带来了全新的东西。

“这让人大开眼界，因为它可以用于很多很多其他方面。例如，他们希望进行测试，但不想影响他们在同一群集中运行的其他测试。所以它有很多不同的用途，我们现在甚至都没有想到。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>