# 电信公司联合起来虚拟化和开源他们的网络堆栈

> 原文：<https://thenewstack.io/telecoms-band-together-virtualize-open-source-network-stacks/>

一群电信公司和他们的软件提供商走到一起，将[网络功能虚拟化](https://thenewstack.io/de-ossify-the-network-with-function-virtualization/)引入他们的数据中心。NFV 是行业开发的电信网络虚拟化框架。

这个组织是在 T2 欧洲电信标准协会 T3(ETSI)的保护下成立的，名为 OSM，代表开放源码 MANO。MANO 代表管理和协调，是 NFV 框架的一部分，由协调软件、虚拟化网络功能管理器(VNFM)和虚拟化基础设施管理器(VIM)组成。

OSM 有八个创始成员，包括 Telefónica、BT、Canonical、Intel、Mirantis、RIFT.io、Telekom Austria Group 和 Telenor，此外还有 15 个初始参与者，如 Benu Networks、Brocade、Comptel、Dell、Indra、Korea Telecom、Metaswitch、RADWare、Red Hat、Sandvine、SK Telecom、Sprint、Telmex、xFlow 和 6WIND。

西班牙电信网络虚拟化战略和技术主管安东尼奥·埃利宗多说，MANO“是网络虚拟化架构中的一个重要组成部分”。“通过加入这个社区，我们旨在加速 MANO 的开发，同时认识到开源实现 NFV 的价值以及协调各方努力的必要性。”

OSM 社区将提供一个符合 ETSI NFV 信息模型的开源 MANO 堆栈。这个堆栈是在 Apache Public License 2.0 下发布的。

“OSM 的目标是提供一个开源模型和框架，能够以厂商中立的方式编排复杂的 NFV 用例，”OpenStack 厂商 [Mirantis](https://www.mirantis.com/) 的产品营销副总裁 Kamesh Pemmaraju 在一封电子邮件中写道。该框架将提供支持端到端 NFV 使用情形的所有关键功能，并以整体、协调和自动化的方式支持 VNFs[网络虚拟功能]的服务级协调和底层基础架构资源(包括 sdn)的资源级协调

硬件供应商已经提供了这种级别的端到端解决方案，但它们是专有的，通常会导致供应商锁定。OSM 打破了厂商的锁定，成为了一种开源技术，而这种技术正是由使用它的社区——服务提供商——开发的。

NFV 是由 ETSI [创建的，目的是让网络运营商对他们的堆栈有更多的控制权](https://thenewstack.io/opensource-virtual-network-functions-part3/)，因为传统上网络供应商提供他们自己的专有软件来管理网络，这导致了供应商锁定、互操作性、可扩展性和弹性问题。NFV 实质上是虚拟化网络，并通过软件提供控制。

这听起来可能类似于 SDN(软件定义网络)，但事实并非如此。他们都迎合两种不同的观众。两者都利用虚拟化，随着数据中心网络运营商需要能够按需提供大量动态网络供应，虚拟化变得越来越流行。

但 SDN 的创建是为了迎合数据中心这些运营商的需求；为他们提供数据中心内网络基础设施的灵活性、敏捷性、可编程性和集中控制。另一方面，NFV 迎合服务提供商。它使服务提供商能够加快新网络服务的部署，以实现更快的收入和增长计划。

“SDN 和 NFV 的相似之处在于，它们都利用行业标准的大容量服务器、交换机和存储，这些都可以位于数据中心，”Pemmaraju 写道。“不同之处在于，SDN 侧重于网络基础设施的灵活性和控制，而 NFV 侧重于服务灵活性，并将所有网络功能用于特定的服务提供商使用案例，如 vCPE 或 VEPC、vIMS 等。

“NFV 和 SDN 是两个独立的软件产品，”Red Hat 的 OpenStack 总经理 Radhesh Balakrishnan 说。“虽然 NFV 以虚拟化用户在专用硬件上运行的软件为中心，但它也可以利用 SDN 技术。SDN 技术实际上执行网络虚拟化。”

Pemmaraju 写道:“虚拟化网络功能的编排和服务链可以通过 NFVO 完成，通常是在 Open Contrail 或 ODL 等底层 SDN 的帮助下。”他补充说，Mirantis 已经通过 OpenStack 认证了许多 SDN 解决方案，并且正在认证个别 VNF 作为其 NFV 合作伙伴生态系统的一部分。

OSM 旨在通过开发统一的部署模式和多用例网络服务，以更低的成本为运营商带来更多的控制权。

OSM 使用来自 [Telefonica 的 OpenMANO 项目](http://www.tid.es/long-term-innovation/network-innovation/telefonica-nfv-reference-lab/openmano)、Canonical 的 Juju generic VNF 管理器和 Rift.io orchestrator 的现有开源模块。OpenStack 已经成为 ETSI 建筑和 OSM 的虚拟基础设施管理者(VIM)。

Canonical 的 John Zannos [在一篇博客文章](https://insights.ubuntu.com/2016/02/22/canonical-becomes-founding-member-of-open-source-mano-osm-group/)中说:“Canonical 的 Juju，开源通用 VNF 管理器，提供通用应用建模，使 OSM 编排和 VIM 层能够专注于行业特定的编排挑战，并且是 OSM 项目堆栈的核心。Juju 使行业能够在性能、安全性和集成方面进行协作和众包专业知识。”

当被问及 Mirantis 在 OSM 所扮演的角色时，Pemmaraju 表示:“Mirantis 已经拥有大量服务提供商客户，他们目前正在使用 Mirantis OpenStack 处理 IT 工作负载。对于这些服务提供商来说，将 OpenStack 用作 NFV 和物联网用例的通用平台是有意义的。Murano 可以在资源编排方面增加独特的价值，并为 OpenStack 提供一个干净的接口，open stack 是 NFV 基础设施事实上的底层 VIM。”

据西班牙电信称，OSM 的项目范围包括资源和服务协调，以允许所有组件的自动部署和互连，既用于 NFV 网络场景，也用于网络服务生命周期的管理。

Mirantis 将通过 OpenStack 项目 Fuel 增强资源编排(RO)和服务编排(SO)。除此之外，Mirantis 还将贡献 Murano 应用程序目录模型以及目前用于 NFV 生产部署的开源软件，以帮助加速 OSM 的资源和服务协调。

英特尔和红帽是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>