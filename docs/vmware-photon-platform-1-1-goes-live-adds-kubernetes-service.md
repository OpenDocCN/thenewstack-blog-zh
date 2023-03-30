# VMware Photon Platform 1.1 上线，增加了“Kubernetes 即服务”

> 原文：<https://thenewstack.io/vmware-photon-platform-1-1-goes-live-adds-kubernetes-service/>

为了兑现去年 8 月的承诺，即开发一个完全容器化的平台来支持开发人员的利益，VMware 于周一发布了 Photon Platform 的开源版本 1.1，这是一个以容器为中心的工作负载管理系统。

随之而来的是对编排机制的支持，VMware 将其描述为“ [Kubernetes-as-a-Service](https://thenewstack.io/vmware-photon-present-kubernetes-service/) ”，有效地让开发人员、开发运维专业人员和管理员从一个[完全改造的光子门户](https://vmware.github.io/photon/)供应和部署 Kubernetes 驱动的环境。最早由谷歌开发的 [Kubernetes](/category/kubernetes/) 是一款开源软件，用于协调许多通常相互关联的容器的操作。

这样，开发人员可能会被鼓励向他们的 [DevOps](/category/devops/) 团队请求 Kubernetes 环境，而不是自己组装。VMware 的既定目标之一是加强其客户组织的最佳实践，其中之一是将数据中心资源的控制权交还给 it 部门。

## 集装箱生态系统，迎接光子经济

两周前，在西雅图的 KubeCon 大会上，VMware 负责云原生应用的首席技术官 Jared Rosoff 向与会者展示了这项功能。他展示了一种光子架构的演进形式，其中平台组件似乎可以选择性地控制软件支持层中的某些 VMware[ESXi](http://www.vmware.com/products/esxi-and-esx.html)虚拟机管理程序，而不是同时控制所有虚拟机管理程序。该结构似乎考虑到了大多数部署 Photon 的客户希望其以容器为中心的环境与预先存在的 VMWare vSphere 环境共存的可能性。

Rosoff 说，Photon 的分布式控制平面将 Photon 的 API 扩展到整个虚拟化平台，为其托管的软件提供了软件基础设施的单一、统一的视图。虽然承认 VMware 的 NSX 网络虚拟化平台既不是免费的也不是开源的，但他告诉与会者，光子 1.1 将在没有 NSX 的情况下运行，并且只使用 ESX 虚拟机管理程序的免费版本。

他讲述的故事将运营商或管理员描述为基础设施的最终所有者，其主要工作是在自己的组织内建立经济。在这种经济中，有各种类型的用户，包括数据科学家、分析用户和软件工程师，他们都对基础架构有不同的要求和独特的需求。罗塞夫将这些群体描绘成供求体系中的阶级，只要他们保持独立，每个人都可以被单独安抚。

“你们两个都在操作这个硬件，”罗索夫说，他指的是作为管理员的“你”以及这些不同的消费群体。“作为基础架构管理员，您的工作是[*与企业内部的*这些客户群打交道。你必须考虑，‘我如何保护这些组中的每一个？我如何确保他们能够获得所需的资源？他们不会过度消耗基础设施？“我的大数据团队总是践踏我的工作负载，因此我如何阻止他们在底层架构中使用过多的容量？”"

作为 KubeCon 的客人，Rosoff 当然意识到他在和“他们”以及“你”的成员说话——和那些帮助建立 Kubernetes 社区基础的开发者说话。

## 哪个位置是头奖？

Rosoff 解释说，开发人员类的成员将有一个修改过的光子门户，他可以用它来创建 Kubernetes 集群。

“光子实际上知道 Kubernetes 星团看起来像什么，”他告诉与会者。“控制平面内发生的事情，[*是，它*实际上正在创建一个新的群集对象，并且正在进行一系列工作—它就像控制平面内的一台大型 Plinko 机器，它正在创建虚拟机和磁盘以及 [**etcd**](https://github.com/coreos/etcd) 节点和 API 主机，并实际调配所有底层虚拟资源来运行该群集。”

Rosoff 说，在 Photon 提供集群之后，开发人员可以使用他已经熟悉的 **kubectl** 命令行工具直接与集群通信。但与典型的 IaaS 平台不同，他继续说道，Photon 将跟踪控制平面中的某些虚拟机(在其命令下选择的虚拟机)组成该集群的事实。因此，Photon 可以跟踪集群创建时配置的所有节点的健康状况。如果集群中的一个节点死亡，Kubernetes 通常知道重新安排受影响的 pod。但是在这种情况下，Photon 首先做出反应，用一个新提供的节点替换死节点。

“因此，这些类型的操作，如组成 Kubernetes 集群的任何虚拟机或网络或磁盘的丢失，”他说，“将由光子控制平面自动纠正——在大多数情况下，无需任何人工干预。”

Kubernetes 社区中的许多人已经接受了他们的平台，将其作为软件基础设施的核心协调者。他们中的一些人是开发人员，他们建立了独立于雇主系统的基础设施，有时是在裸机上。一些人仍然建议 Kubernetes 的裸机部署更有效，更像 Google 最初打算的架构。虽然 [CenturyLink 正式退出服务器托管和主机托管业务](http://www.datacenterknowledge.com/archives/2016/11/04/centurylink-sells-colo-business-fund-level-3-deal/)，但该公司的工程师早在三月份就证明了 [Kubernetes 在裸机上提供的延迟比在虚拟机中托管时少三倍。](https://www.ctl.io/developers/blog/post/kubernetes-bare-metal-servers)

但 VMware 的情况是，裸机不是信息经济的基础。从他们的角度来看，大数据工程师将更喜欢在 Hadoop 或 Spark 引擎上运行的批处理驱动的并行任务环境；营销将需要他们的单片 CMS 开发者会坚持使用容器化的平台。在 VMware 将 vSphere 发展成“各得其所”的平台以维护传统的同时，该公司也在以同样的目标发展 Photon，以用于更现代的技术。

根据[最新发布说明](https://github.com/vmware/photon-controller/releases/download/v1.1.0/release-notes-for-pc-1.1.pdf)，最新的 Photon Controller 1.1 仅支持 ESXi 虚拟机管理程序的版本 6.0(补丁版本 4)，尚不支持版本 6.5。VMware 的 [Lightwave](https://vmware.github.io/lightwave/) 版本 1.0.1 提供了身份和访问控制。每次部署时，Photon Controller 将在 ESXi 的每个实例中安装代理，并且虚拟机管理程序和控制器之间的通信将通过 SSL 加密。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>