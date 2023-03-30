# VMware Photon 将展示“Kubernetes 即服务”

> 原文：<https://thenewstack.io/vmware-photon-present-kubernetes-service/>

那些仍然认为 VMware 的目标包括宣传“vSphere Everywhere”的人周二再次收到了一个严峻的提醒，即该公司的基础架构战略远不止销售其管理员平台。

在巴塞罗纳举行的欧洲版 [VMworld 2016](http://www.vmworld.com/en/europe/index.html) 大会上，VMware 首席技术战略官 [Guido Appenzeller](http://guido.appenzeller.net/) 正式宣布，任何将公共云和私有云虚拟基础架构置于 vSphere 监管之下的战略都是“糟糕的选择”

这是该公司宣布其第四季度对[光子平台](https://thenewstack.io/vmware-open-sources-photon-controller/)——其独立集装箱化系统——的更新的一部分，不仅支持 [Kubernetes](/category/kubernetes/) 容器编排软件，而且使管理员能够在多租户方案下同时为多个用户提供 Kubernetes 的专用实例。

![](img/571797731e1beb1f696390aa08eef049.png)“你们中的许多人已经开始原生地使用云——这里的‘原生’这个词带来了很大的不同，”Appenzeller 告诉与会者，并确保包括“引号”

“例如，如果您正在以原生方式构建 Amazon，您将不再使用 vSphere API 或 ui 来调配工作负载，但现在您正在以 Amazon 的方式进行。例如，您使用的不是 vSphere，而是[*Amazon Web Services 的*]EC2；或者不使用 VSAN，而是使用[ *AWS* ]弹性块存储。还有许多服务具有在云中不可用的内部[ *版本* ]。如果你想使用高可用性或实时迁移，或高度灵活的 IP 寻址，你不能再这样做了[*仅在公共云上 T16。但另一方面，你也有像[*AWS*]S3 这样的服务，这种服务通常没有相应的本地服务。"*

## vSphere 停止的地方和其他东西开始的地方

Appenzeller 谈到企业需要弥合公共云平台(如弹性存储和灵活的数据库服务)和私有云平台(如安全性和策略控制)之间的服务差距。上周[宣布的 VMware 与亚马逊 AWS 的合作关系](https://thenewstack.io/vmware-aws-partnership-provides-container-onramp-cloud/)消除了弥合这一差距的最大政治障碍，只剩下技术障碍。

但是，尽管该协议为 NSX 网络虚拟化平台扩展到亚马逊的公共空间铺平了道路，但它并没有立即将所有以前的应用管理和部署技术变成“云原生的”

当然，VMware 正在寻找一种“拥抱和扩展”容器化的方式，而[vSphere Integrated Containers(VIC)将是其将现有 VSP here 平台扩展到容器领域的方式](https://thenewstack.io/vmware-integrated-containers-may-introduce-docker-enterprise/)。但 Photon 代表了该公司对那些需要扩展的遗留基础设施较少(或没有)的组织的吸引力。虽然 Appenzeller 在 9 月份告诉 New Stack，他与之交谈的光子可能适用的客户比例在一位数范围内，但今天承认这些客户现在告诉他的事情表明，他们的情况可能是无可辩驳的。

“自然使用云是不同的，”CTSO 说。“如果你回去告诉你的开发人员，‘停止所有这些，把所有东西都移回 VSP here’，这不仅非常不受欢迎，我认为这对企业来说也是一个糟糕的选择。因为对于某些应用，这些原生云实际上具有真正的优势，我们应该使用它们。”

也就是说，VMware 的营销部门一定会将 vSphere 宣传为其“通用应用程序平台”，不仅扩展到虚拟机管理程序驱动的虚拟机和容器化的工作负载，还扩展到 Hadoop 作业。

VMware 软件定义的数据中心(SDDC) [的 VMware 高级总监 Mark Chuang](https://www.linkedin.com/in/chuangmark) 在谈到新的体系时表示:“我们使用[ *短语*来具体描述我们围绕 vSphere 的战略。因此,‘通用应用平台’这个术语更多地是指运行时细节。从运行时的角度来看，无论是 3D 图形、大数据、云原生、机器学习、内存数据库、Web 横向扩展应用，还是所有的应用，我们的目标都是在 vSphere 上提供最高的性能和最佳的运行时体验，同时认识到不同的应用类型具有不同的基础架构[*和*]计算要求。”

## 毕竟这是个小世界

虽然我们在新的堆栈中倾向于称之为“容器生态系统”是围绕着应用程序协调进行的，但 Chuang 认为这一级别的协调实际上是与基础架构管理分开的一个主题。因此，从这个角度来看，vSphere 确实支持 Kubernetes。

[英特尔的乔纳森·唐纳森讨论 Kubernetes](https://thenewstack.simplecast.com/episodes/intels-jonathan-donaldson-discusses-kubernetes)

“因为它涉及到像 Kubernetes 或你知道，中间层或——我不知道，我能把 Swarm 也归入这一类吗？—我们认为，它们可以在不同的层面上运作，”庄说。“我们确实有计划支持 Kubernetes，我们的目标是，如果请求进入 Kubernetes，然后当 Kubernetes 将其传递到 vSphere 集群时，我们的分布式资源管理功能将接管。所以我们实际上认为它们是非常互补的，你实际上可以将这些不同的调度器分层。”

vSphere 环境使用[Distributed Resource Scheduler(DRS)](https://www.vmware.com/products/vsphere/enhanced-app-performance.html)作为其调度组件和负载均衡器，因此是容器编制器的对等物。当 [VMware 在去年](https://thenewstack.io/vmwares-photon-platform-and-how-it-treats-containers/)首次推出 VIC 和 Photon 时，对两者之间区别的混淆(甚至在首次解释它们的人中)导致许多人，包括客户，想知道应用程序编排如何在任何 VMware 品牌的环境中工作。

几周前，在拉斯维加斯的 VMworld 大会上，该公司明确表达了自己的意图。VMware 需要一个全容器环境来满足*新*数据中心的可扩展性需求，而这一需求将由 Photon 来满足。

“想想这些不同的产品，比如运营工具中的 NSX[和 VSAN](http://www.vmware.com/products/virtual-san.html) ，以及光子；VMware 负责云原生应用的总经理 Paul Fazzone 在向与会者发表演讲时表示:“请将 Photon 视为利用底层产品，但公开一个单一的编程 API。”。光子计算、光子网络、光子容器、光子存储、光子安全。现在，通过这个 API，IT 可以划分基础设施可用性区域。随着时间的推移，这种模式将允许您将私有云环境扩展为公共云环境。

“但它也允许你向你的开发团队公开这个 API，”他继续说道，“这样你就可以进入并向开发团队和租户预先提供一个资源池。该租户与一个业务线相关联，每个业务线都有自己的开发团队。您可以将它们分别设置为一个单独的租户，然后每个租户可以拥有特定于租户的单独项目。这些项目——一个可以运行 Pivotal Cloud Foundry，另一个可以运行 Kubernetes，还有一个可以运行 Mesos。我们的目标是让 it 组织为他们的开发团队提供这种水平的服务变得非常简单。”

这就是“Kubernetes 即服务”理念的由来。一个应用编排器可以被委派给每个开发团队，开发团队可以按照自己的方式运行和管理它。然后，网络运营商可能会自动配置 Kubernetes 环境(或任何其他 orchestrator，但 VMware 选择 Kubernetes 作为其模型)，甚至在不再需要时关闭它。

## 快乐的房客

该计划当然抛弃了摧毁孤岛的整个概念，以便在单一平台下将组织内不同的部门连接在一起。但这种计划有可能更容易被那些不希望在每次采用新方法生产新产品时又一次文化变革的企业接受。

“我们实际上将支持原生的、开源的 Kubernetes、Mesos、[*和*]最终 Docker Swarm，”Fazzone 告诉新的 Stack。“就像您现在可以在 vSphere 上进行 API 调用或 UI 调用来创建新的虚拟机一样，使用 Photon，您将能够进入，进行简单的 API 调用，创建一个租户环境，并在该租户环境中说，‘给我一个 Kubernetes 集群。’然后，您可以在裸机上运行的 Kubernetes 集群内部执行的任何操作都将通过该集群的北向接口公开。因此，您在该环境中的可移植性将更多地取决于 Kubernetes 框架支持什么，而不是 Photon 在幕后做什么。"

VMware 显然相信开发人员和运营商之间的友好关系能够持续下去。这不是 DevOps *本身*，两个团队挤在一起，被告知合作或其他，但这是一种工作关系，其中一个解决另一个的需求。更重要的是，VMware 希望提供自动化地址和响应流程的系统，因此它希望客户公司的社会和业务结构保持基本不变。

“现在比以往任何时候都更需要 IT 部门，”VMware 的 Appenzeller 周二在巴塞罗那表示。“但在云时代，我们的做法会发生变化。”

[英特尔](https://www.intel.com/content/www/us/en/it-management/intel-it/it-managers.html)是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>