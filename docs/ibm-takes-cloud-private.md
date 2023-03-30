# IBM Cloud Private 向云原生世界引入了企业 Java

> 原文：<https://thenewstack.io/ibm-takes-cloud-private/>

IBM 推出了一项名为 IBM Cloud Private 的新服务，它将允许组织在自己的数据中心运行云原生工作负载，使用 [Kubernetes](https://kubernetes.io/) 容器编排引擎、哈希公司的 [Terraform](https://www.terraform.io/) 基础设施管理软件，以及最终的 [Istio](https://istio.io/) 服务网格。

有了这项新服务，IBM 确信由云本地计算基金会管理的开源项目 Kubernetes 已经赢得了云管理之战。

“这几乎成了事实上的标准。我认为围绕它的生态系统很棒，因为它在入口和出口方面有正确的可插拔点，”IBM 研究员兼云服务平台首席技术官 Bala Rajaraman 说。"这使得创建 Kubernetes 的企业版变得很有吸引力."

为了帮助它的客户实现云原生化，IBM Cloud Private 提供了一条将 WebSphere 应用程序引入容器的途径，允许它们插入 Kubernetes 底层。这意味着 Kubernetes 和 Terraform 可以轻松地管理大型的传统 Java 应用程序，它们带来了日志记录、监控、故障转移和备份等功能。

## 微服务帮助

IBM Cloud Private 产品还包括 [Cloud Foundry](https://www.cloudfoundry.org/) 作为应用程序平台，支持应用程序的跨云兼容性，以及[微服务架构](/category/microservices/)。

“许多应用程序都构建在现有的数据和分析功能中间件之上。看看像 WebSphere 这样的东西:有许多应用程序建立在其上，但没有一条更新中间件基础的道路，因为它们是有状态的应用程序，并且它们对底层基础设施做出了假设，”Rajaraman 说。

“我们可以将这些组件放入一个基于容器的平台。Rajaraman 说:“我们采用中间件，如 WebSphere MQ，并逐步将它们转移到 Kubernetes 的底层。这将帮助客户避免完全重写他们的应用程序。

虽然在传统 IBM 基础设施上运行的传统应用程序可以被引入新的 IBM Cloud Private，但该平台也旨在为现代应用程序提供好处。这些不仅是由 Kubernetes 提供的，最终也是由 Istio T1 提供的。虽然 Istio 仍然是一个非常年轻的项目，但 Rajaraman 表示，它最终将成为 IBM 私有云的治理和控制平台。

“我们认为 Istio 支持服务网格，这将是不仅分解为微服务，而且分解为微架构的明显结果。它支持虚拟机和容器，这使得它很有吸引力。它还有证书管理和断路器管理。就企业级微服务而言，这些东西将变得必不可少。

虽然单个控制平面很有吸引力，但容器及其管理与传统的 Java 做事方式有点相反，在传统的 Java 方式中，单个应用服务器被调整、优化，并一直运行所有的工作负载。

“我怎么才能消除这种感觉，”拉贾拉曼问道。“应用服务器不一定是一件坏事，它是如何打包的，以及如何在其上构建应用程序。我们已经将 WebSphere 及其有状态特征分解到共享存储中。这就是我们喜欢 Kubernetes 的原因:许多现有系统的吸引力在于可管理性。”

几年前，这种管理和内部云解决方案属于 [OpenStack](https://www.openstack.org/) 的权限范围。然而今天，由于相对简单的架构，Kubernetes 似乎已经接管了 mindshare。

“我认为这是一个逐渐成熟的市场。OpenStack 试图提供一种特殊类型的服务:基础设施即服务。它的深度和广度都在增长，相关的管理复杂性也在增长。Kubernetes 更容易，因为在基础设施和如何用容器构建之间有一个明显的解构，”Rajaraman 说。

Kubernetes 平台在相关插件和 Helm Charts 等外部服务的帮助下，提供了灵活性、高可用性和自动控制状态的能力。“我能想到的最好的类比就是 Linux 内核，它又轻又快。你可以插入不同的文件系统或驱动程序，”拉贾拉曼说。

对于企业云的未来，Rajaraman 看到了一个复杂的服务水平协议(SLA)世界的出现。他希望 IBM 可以帮助管理员和首席信息官管理不同 SLA 之间可能出现的复杂差异。

“我们正走向这样一个领域，在那里，单个服务将不再重要，但服务的集成将变得重要。我认为 SLA 的定义将会变得更加复杂。“企业不仅需要服务级别协议工具，还需要管理低于这些服务的 SLO[服务级别目标]的工具。围绕数据和数据移动性有许多技术上具有挑战性的问题，但我认为这是我们正在逐步走向的方向。”

[云铸造基金会](https://www.cloudfoundry.org/)、[云本地计算基金会](https://www.cncf.io/)和 [OpenStack 基金会](https://www.openstack.org/)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>