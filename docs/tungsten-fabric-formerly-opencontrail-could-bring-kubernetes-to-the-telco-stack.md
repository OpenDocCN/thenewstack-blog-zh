# 钨织物，以前的 OpenContrail，可以将 Kubernetes 带入电信堆栈

> 原文：<https://thenewstack.io/tungsten-fabric-formerly-opencontrail-could-bring-kubernetes-to-the-telco-stack/>

就在 [Juniper Networks](https://www.juniper.net/us/en/) 决定将其 OpenContrail SDN 控制器平台更名为[钨架构](https://github.com/tungstenfabric/website)的几天后，一位公司高管和集装箱化运动的长期关键人物之一(可追溯到他在 EMC 的任职期间)告诉新的堆栈，电信提供商可能很快就会在数据中心方面落后于他们的同行，并采用 Kubernetes 作为他们的网络功能协调者。

Juniper 负责云技术和战略的副总裁[兰迪·拜斯](https://www.linkedin.com/in/randybias/)说:“我看到的是，人们现在已经对复杂的项目产生了一定程度的疲劳，他们真的想把事情做好。因此，我看到更多的是从 OpenStack 向 Kubernetes 等产品的迁移。”

## 重新思考替代方案

按照架构师对未来电信网络功能的设想，面向客户的云(自然是多租户)和面向内部的云之间存在明显的差异。正如 Bias 指出的，后一种结构具有单租户的优点。Kubernetes 从一开始就是单租户；事实上，为 Kubernetes 实现多租户是其他公司(如 Project Calico)惯用的伎俩[已经竭尽全力实现了](https://www.projectcalico.org/giantnetes-how-we-use-calico-to-enable-multi-tenant-kubernetes/)。

“如果你知道自己在做什么，你可以选择完成一个非常安全的 OpenStack 部署，”Bias 说。“但违约可能并不严重。”

鉴于 OpenStack 与今天 NFV 5G 平台的领先候选人 OPNFV[之间明显增长的合作伙伴关系，Bias 的区别非常重要，op nfv 也是 Linux 基金会项目](https://www.opnfv.org/community/upstream-projects/openstack)。OpenStack 过去已经将自己的策略应用于容器编排，称为 Magnum。但是甚至在去年，OpenStack 的主要支持者们似乎更关注于在一层甚至三层采用 Kubernetes，一位工程师称之为“俱乐部三明治”

Bias 解释说，当今电信网络的高度异构、天生不可扩展的状态，本质上要求使用虚拟机管理程序作为安全的抽象层。他承认，电信公司可能不会心甘情愿地接受 Kubernetes，或者就此而言，任何单一的解决方案，部分原因是他们仍然在裸机上部署服务，而不是在平台上。但他认为，5G 的出现等其他令人信服的驱动因素可能会为电信公司采用市场其余部分已经采用的解决方案提供催化剂。

“那就像一个不用动脑筋的问题，”贝斯说。“当我可以保持简单时，我为什么要带上虚拟化堆栈和所有其他组件？”

## 我们在说什么？

在电信网络的深处，一个至关重要的层正在形成:*网络功能虚拟化* (NFV)。这是将客户服务、网络维护功能和无线接入网络(RAN)本身表示为虚拟机的方式。

由于电信公司、设备制造商和政府机构仍在讨论管理第五代全球无线技术(5G)的标准，因此普遍认为必须建立某种类型的云平台来处理网络功能的虚拟化和便携性。到目前为止，该协议为开源组件建立该平台铺平了道路。

但是到底是哪些组件仍然是一个悬而未决的问题，两年多前，T 公司的一位首席执行官[在一次重要的开源会议](https://thenewstack.io/att-moves-nfv-platform/)上宣布，他们等不起超过 18 个月的时间。

运行中的一个选项是 OpenContrail，这是一个商业 SDN 控制器的开源版本，最初由一家名为 Contrail Systems 的公司生产，该公司于 2012 年被瞻博网络公司收购。此后，控制器与服务协调器配对。2013 年，Juniper 首次在开源许可下生产 OpenContrail。但从那时起，随着关于 NFV 和 SDN 在 5G 中的地位的讨论升温，OpenContrail 发现自己越来越边缘化。尽管该公司在去年 11 月重组了 Contrail 的高层领导，并在接下来的一个月将开源项目捐赠给了 Linux 基金会，但该平台发现自己被描述为“失败者”。

## 你交的朋友

如果钨织物将有任何机会重新注入到目前正在建设的最重要的全球网络的对话中，那么它需要将其众所周知的明星挂在更强大和更有吸引力的马车上。Juniper 的 Randy Bias 将这辆马车视为 Kubernetes，而不是与 Kubernetes 挂钩的其他东西。

“在短期内，当你在边缘而不是其他地方运行 Kubernetes 时，可能会有额外的复杂性，”他告诉我们，他指的是电信公司可能会选择在离客户更近的地方部署 orchestrator 的场景。

“但你肯定会在应用程序层看到，即使运行在 OpenStack 或公共云或 VMware 之上，也有越来越多的人倾向于将 Kubernetes 作为其云原生应用程序的基础架构管理框架，”他继续说道。“因此，无论何时任何人考虑将他们的 VNF[*虚拟网络功能*]重构为容器友好的，即使它将在核心中，他们几乎总是默认使用 Kubernetes，因为它在公众中有效地赢得了容器编排之战。真的没有任何竞争对手了。从长远来看，我认为使用 Kubernetes 管理所有应用程序和服务的可能性非常高，我不知道需要多长时间。”

Randy Bias 的观点尤其重要，因为他是 OpenStack 基金会的首任董事之一。在此之前，他是最初的 CloudScale Networks 多云平台的创建者，并在后来被亚马逊 AWS 收购之前领导了 GoGrid API 的开源工作。在 2014 年 DevOps Chicago 的一次会议上，Bias 被认为是[发明了用于管理虚拟服务器的“宠物对牛”比喻](https://www.slideshare.net/randybias/pets-vs-cattle-the-elastic-cloud-story)。

[Linux 基金会](https://www.cncf.io/)是新堆栈的赞助商。

专题图片:Randy Bias [在 2017 年 9 月 27 日德克萨斯州奥斯汀举行的软件定义大会暨博览会(SDxE)上做主题演讲](https://www.youtube.com/watch?v=ufwxPN6Z-ug)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>