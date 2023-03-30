# Cloudlets、平台分析和新一代云应用管理

> 原文：<https://thenewstack.io/cloudlets-platform-analytics-new-generation-cloud-app-management/>

[](https://www.morpheusdata.com/)

 [布莱恩·惠勒

布莱恩·惠勒在 Morpheus Data 监管技术团队。在 Morpheus 之前，Brian 创办了一家软件开发咨询公司，为各种行业设计和开发解决方案，包括电网管理、票务系统、在线交易、社交网络和游戏、SOX 合规性和电子商务。Brian 拥有波莫纳学院的化学学士学位。](https://www.morpheusdata.com/) [](https://www.morpheusdata.com/)

每个人都在谈论云的可扩展性有多好。正如 [Timothy Prickett Morgan](https://twitter.com/tdaytonpm) 在 [The Next Platform](http://www.nextplatform.com/2016/08/15/getting-cloud-fugue-state/) 中所写的，当你在 AWS 云上拥有几十个实例的简单 n 层应用时，情况确实如此。然而，在未来几年，这将是一个明显的非典型云场景。

在现实世界中，应用程序将继续扩展，增加复杂性和相互依赖性。目前用于管理日益复杂的相互关系的工具往往专注于无状态和有状态应用程序和数据的特定方面。

编排旨在将所有工具缝合成一个无缝的整体。考虑到以云为代表的不断增长的系统和设备范围——特别是物联网——合并这样一套独特的独立资源，实际上来说，几乎是不可能的。

## 持续部署适用于平台和应用程序

所有关于将应用程序和数据从它们在传统 IT 模式中所处的孤岛中解放出来的讨论都忽略了让系统的所有关键组件都存在并得到考虑的管理优势。您知道资源位于何处，它们的功能如何，以及(通常)它们与哪些其他组件进行了互操作。

既然您的应用程序、数据和其他数字资源已经从数据中心解放出来，管理它们就变成了捉迷藏的游戏。它留给开源工具，如 [Chef](https://www.chef.io/products/chef-infra/) 和 [Puppet](https://puppet.com/product/capabilities/orchestration) 来定位组成应用程序或数据库的所有部分，无论它们位于云中的什么地方，然后将它们缝合在一起，按需交付给客户。

在 TechTarget 2016 年 8 月[的一篇文章](http://searchsoftwarequality.techtarget.com/ehandbook/Corporate-culture-influences-selection-of-best-ALM-tools)中，分析师 Tom Nolle 描述了编排现在如何包含构成应用管理的所有四个不同的工具集和流程:在开发端是版本控制和开发管理，在运营端是部署和应用生命周期管理。流程编排自动化并集成了以前四个独立的流程。

在前端，应用和数据必须灵活适应任何平台或网络类型，并且必须根据设备、环境(时间和地点)和当前需求的独特情况进行个性化。在后端，系统必须支持完全虚拟化的基于微服务的组件，这些组件构成了现代云原生应用。

## 厨师和木偶短缺的地方

TechTarget 的 Nolle 指出，Chef 和 Puppet 这两个最流行的编排工具现在都支持资源的模块化声明，尽管 Chef 本身是命令式的，而 Puppet 是声明式的。每个 orchestrator 都允许以虚拟和模块化的方式定义组件和服务部署。这是第二代工具如 Red Hat 的 Ansible 和 [SaltStack](https://saltstack.com/) 从一开始就提供的功能。

不可避免的是，行业将转向单一、连续的生命周期流程，而不是专注于集成和协调所有这些独立的 [DevOps](/category/devops/) 流程和服务的工具，诺尔称这是应用开发跟上不断发展的业务流程的唯一方式。

RightScale 最新[云状态](https://www.rightscale.com/lp/state-of-the-cloud)报告的[结果](https://www.zdnet.com/article/iaas-in-2016-who-can-challenge-amazon/)表明 Docker 在 IT 经理中的受欢迎程度，35%的 IT 经理计划在未来一年使用 Docker for DevOps。相比之下，19%的人打算用 Chef，18%的人会用 Puppet。根据 RightScale 的调查结果，容器编排工具[、Kubernetes](http://kubernetes.io/) 、 [Swarm](https://docs.docker.com/swarm/) 和 [Mesospher](https://mesosphere.com/) 、T10【e】也越来越受欢迎。

## 从头开始重新设计组件编排

随着越来越多的组织计划通过将其整个 IT 运营转移到云来全力以赴，管理构成现代应用程序的许多元素和资源的零敲碎打的方法根本行不通。正在努力创建一种方法/平台来无缝管理不断发展的生命周期流程。

三个这样的提议来自于一家由 AWS 前高管创立的新公司；来自卡内基梅隆大学的研究人员，以“云”的形式；Linux 基金会最近采用了名为网络数据分析平台(PNDA)的开源项目。

这三个概念中最雄心勃勃的是 Fugue，根据 Next Platform 的说法，它旨在成为“真正的云操作系统”。Fugue 联合创始人 Josh Stella 从他在 AWS 的多年工作中了解到，随着应用程序规模的扩大和相互依赖的层的增加，它们会变得更加复杂。Fugue 使得所有的云组件都是可编程的，因此整个系统可以像软件应用程序一样被开发、更新和删除。

实现这一目标的工具包括 Fugue 云管理堆栈:部署；生命周期和虚拟基础设施管理；和监视应用程序实例，以确保没有不必要的实例正在运行。Fugue 不会取代 Linux 或 Windows Server，因为它管理的是 API 而不是设备。

## 创建“云”

在集中式超大规模公共云中运行的云原生应用程序的优势已经被充分利用。正如甲骨文高管 Robert Shimp 在 InfoWorld 的一篇文章中所写的，云原生应用有三个共同特征:它们被编写为微服务，打包在容器中，并经过编排以向客户交付成品应用。

然而，并不是所有的应用程序都适合这种集中式云方法。一些应用在网络边缘的分布式环境中蓬勃发展，特别是那些需要参与(人而不是过程)和控制(在智能设备中实时进行)的应用。关键是组织要尽可能靠近网络端点，以便更好地捕捉连接到那里的人和设备。Shimp 表示，从云的中心吸引人和连接到设备变得更加困难。

这就是 cloudlets 发挥作用的地方。[卡耐基梅隆大学](http://elijah.cs.cmu.edu/)的研究人员开发了这个概念，作为三层系统的中间层，将顶层的智能设备与底层的云连接起来。Shimp 确定了四个关键的 cloudlet 属性:

*   小型、廉价且基于云标准的免维护设备设计
*   安全、可连接且功能强大
*   仅用于微服务和容器，因此仅保持软状态
*   位于网络边缘附近，便于与设备通信

cloudlet 的概念使得企业在网络边缘拥有数千个临时的移动前哨成为可能。这有点像按需呈现，您可以在任何给定时间尽可能靠近您的客户及其许多设备可能在的任何地方。

cloudlet 还可以作为一个额外的冗余层来防止中断:如果网络的任何部分出现故障，您组织的其他 cloudlet 会自动重新配置自己来恢复丢失的连接。

## 大数据分析获得新的开源平台

正如 cloudlets 旨在让企业更接近客户一样，根据 Datacenter Dynamics 的一篇文章，Linux 基金会提议通过 PNDA 将分析直接转移到底层网络基础设施，该文章是关于最初的 PNDA 实现在[发布的。](https://github.com/pndaproject)

PNDA 引擎基于 Apache 组件 Spark、Kafka、ZooKeeper 和 Grafana。据 Smolaks 称，它结合了日志数据、指标和网络遥测，所有这些都以“最原始的形式”存储，以促进实时和批处理模式下的流数据分析。PNDA 被其支持者视为补充软件定义网络、网络功能虚拟化以及 OpenDaylight 和 OPNFV 等网络协调项目的一种方式。

当然，通过将您的应用迁移到我们的 [Morpheus](https://www.morpheusdata.com/) 云应用管理平台，您可以实现 Fugue、cloudlets 和 PNDA 等项目承诺的诸多优势，而无需等待。Morpheus 可让您在几秒钟内在任何服务器或云上配置数据库、应用和应用堆栈组件，无论它们位于内部还是私有、公共或混合云中。

Morpheus 不存在供应商锁定的问题，它通过一个直观的仪表板支持与任何应用程序、任何数据库和任何云的 API 连接。Morpheus 是满足您云管理需求的简单、高效且可扩展的解决方案。

由[卡伦·艾姆斯利](https://unsplash.com/@kalenemsley)通过 [Unsplash](https://unsplash.com/photos/_LuLiJc1cdo) 拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>