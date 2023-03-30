# Kubernetes 的 Postgres:自我管理还是管理服务？

> 原文：<https://thenewstack.io/postgres-with-kubernetes-self-managed-or-managed-service/>

[](https://twitter.com/prlaurence)

 [保罗劳伦斯

保罗劳伦斯是可信开源 Postgres 的领先提供商 Crunchy Data 的联合创始人。](https://twitter.com/prlaurence) [](https://twitter.com/prlaurence)

如果您正在使用 Kubernetes 进行新的开发项目，启动应用程序现代化工作，或者参与数字化转型，[您可能需要一个数据库](https://blog.crunchydata.com/blog/using-kubernetes-chances-are-you-need-a-database)和 [Postgres 可能是答案](https://twitter.com/monkchips/status/858433502181822464?ref_src=twsrc%255Etfw)。

Kubernetes 为运行应用程序提供了许多好处，包括效率、自动化和基础设施抽象。这些优势继续推动组织在 Kubernetes 上标准化应用部署。然而，关于 Kubernetes 是否为数据库“做好准备”,仍然有一个常见的问题。

在 PGO 中有一个成熟的 Kubernetes 操作者，在 Kubernetes 操作者的帮助下有一个新的选择来运行 Crunchy Bridge。

那么，哪种部署模式适合您呢？像往常一样，看情况。

## Postgres 运营商:Kubernetes 上的自我管理的 Postgres

Kubernetes 的特性使其成为一个很好的应用程序平台，也可以用来帮助您部署高可用性数据库和扩展，从而在数据库增长时更容易管理数据库硬件。

当与操作员结合使用时，Kubernetes 可以提供特定于数据库的工具，使您能够统一地扩展节点，这也有助于在数据库增长时管理数据库的硬件。Kubernetes 的特性如[节点关联](https://kubernetes.io/docs/tasks/configure-pod-container/assign-pods-nodes-using-node-affinity/)、[容忍](https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration/)和 [pod 拓扑分布约束](https://kubernetes.io/docs/concepts/workloads/pods/pod-topology-spread-constraints/)允许管理员决定在哪里部署 Postgres 实例。

这些工具相结合，使数据库工作负载能够受益于[高可用性](https://access.crunchydata.com/documentation/postgres-operator/latest/architecture/high-availability/)或特定硬件。围绕这些数据库的这些功能的成熟以及声明性和 [GitOps 友好工作流的潜力](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/)激发了很多 [PGO v5](https://blog.crunchydata.com/blog/the-next-generation-of-kubernetes-native-postgres) ，来自[易碎数据](https://www.crunchydata.com/)的开源 [Postgres 操作符](https://github.com/CrunchyData/postgres-operator)。

因此，越来越多的用户开始在 Kubernetes 上采用本地数据库。[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)提供了大量关于 Kubernetes 采用情况的数据。其[云原生调查 2020](https://www.cncf.io/blog/2020/11/17/cloud-native-survey-2020-containers-in-production-jump-300-from-our-first-survey/) 显示，55%的受访者在生产中使用容器中的有状态应用。Crunchy Data 拥有许多在 Kubernetes 上成功运行 Postgres 的客户。

像 [Helm](https://helm.sh/) 和 [Kustomize](https://kustomize.io/) 这样的操作器和工具都有助于减轻管理负担，但是与 Kubernetes 相关的自动化和流程编排并不是免费的。

尽管有自动化的好处，在 Kubernetes 上本地运行数据库仍然需要您运行您的数据库，并且被描述为“更接近全操作选项”在 Kubernetes 上运行 Kubernetes 和应用程序，伴随着管理需求。

在 Postgres 的上下文中，问题似乎可以归结为用户是否足够重视 Kubernetes 的好处以维持增量管理。

## Kubernetes 的完全管理的 Postgres

Postgres 的[完全托管数据库选项](https://www.crunchydata.com/products/crunchy-bridge/)怎么样？

托管服务是部署数据库的一个有吸引力的选项，使托管服务提供商能够为您处理大量数据库管理任务，包括备份、修补和扩展。

Kubernetes 操作员和托管数据库服务的结合使您能够维护您的 Kubernetes 标准化工作流程，同时受益于第三方的数据库管理实践经验。通过使用像 [Crunchy Bridge](https://www.crunchydata.com/products/crunchy-bridge/) 这样的“云不可知”托管数据库服务，您可以从拥有数十年运行大规模 Postgres 数据库和您选择的云提供商的数据库即服务经验的工程师那里获得完全托管 Postgres 的好处。

我们很荣幸能与 [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 合作，通过新服务[Red Hat open shift Database Access(RHODA)](https://cloud.redhat.com/blog/simplifying-database-cloud-service-access)帮助简化对 Kubernetes 上数据库服务的访问。

对于对维护数据库服务器不感兴趣的用户来说，托管 Postgres 是一个很好的选择。

## 那么，你应该怎么做呢？

好消息！决定使用 Postgres 是一个很好的开始；我们认为这是一个正确的开始。关于如何最好地部署它，有几种选择。

这样做与其说是一个非此即彼的决定，不如说是一个何时何地的问题。与各种规模的企业都倾向于使用的混合云相似，Postgres 用户通常会根据其团队的需求和组织标准选择这些部署模型的组合。

选择归结为给定项目使用哪个模型，而不是所有应用程序都使用哪个模型。

对于本地用户，或者需要更多实践部署的用户，Kubernetes 带有 Postgres 操作符的本地 Postgres 是一个很好的选择。对于许多项目来说，如果用例需要“一劳永逸”的 Postgres 部署，那么使用托管服务效果会很好。

和所有事情一样，每个决定都有权衡，但是只要你从“答案是 Postgres”开始，你就不太可能偏离正确的道路太远。如果您需要帮助，Crunchy Data 可以提供帮助。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>