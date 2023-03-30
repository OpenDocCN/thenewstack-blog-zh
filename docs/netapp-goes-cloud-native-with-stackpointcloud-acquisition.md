# NetApp 通过收购 StackPointCloud 实现云本地化

> 原文：<https://thenewstack.io/netapp-goes-cloud-native-with-stackpointcloud-acquisition/>

随着上个月对 StackPointCloud 的收购，存储服务和系统提供商 [NetApp](https://www.netapp.com/us/index.aspx) 将处于为有状态应用程序提供多云 Kubernetes 支持的独特地位。

NetApp 高级副总裁兼负责公司云业务的总经理 [Anthony Lye](https://www.linkedin.com/in/anthonylye/) 表示，此次收购是一项更大战略的一部分，该战略旨在成为“唯一一家能够在云、多云和混合云世界中提供有状态应用程序级管理的供应商”。

NetApp 一直以其 NFS(网络文件系统)而闻名，大约两年前，该公司开始将其移植到主要的云服务，并扩展 NetApp 操作系统 OnTap 以处理这些新环境。今天，NetApp 为 Azure 和 Google 云平台的 Windows 服务器环境提供了 NSF 和 SMB(服务器消息块),这是由这两家公司各自提供的。它还通过亚马逊网络服务市场提供 NSF 和 SMB。

一年前，Netapp [收购了](https://www.crn.com/news/storage/300090706/netapp-bought-icelands-greenqloud-to-fill-data-fabric-need-for-cloud-automation-orchestration.htm) Greenqloud，并希望将其用于 Greenqloud 的 orchestrator，该公司此后一直使用该 orchestrator 来消费、部署、监控、维护和升级公共云上的 Netapp 服务。Lye 说:“在我们制定这一战略时，我们认为 NetApp 必须将其存储连接到计算层，以便为云用户提供应用程序级别的流程编排。这项工作变成了 [NetApp 云数据服务](https://cloud.netapp.com/home)，在公共云上部署、运行、监控、维护和管理服务。

但是，当 NetApp 组装这一堆栈时，缺少了一部分。该公司需要一个用于基础设施协调的控制平面，以支持集装箱化操作，到此时，该行业似乎已经在很大程度上决定由 Kubernetes 来处理这项任务。

输入 StackPointCloud。

## 交钥匙管理

StackPoint 成立于 2014 年，其理念是为所有主要云服务提供统一的基础设施服务，StackPointCloud 首席执行官兼创始人 Matt Baldwin[表示。该公司于 2016 年在 CoreOS Fest 2016 上正式推出，此后积累了 1 万名用户。它的服务部署股票开源组件。虽然是一家小公司，但它已经在其使用的技术上游做出了贡献，特别是 Kubernetes 和最近的 Istio service mesh。这使得该公司能够跨多个云进行一致的部署。](https://twitter.com/baldwinmathew)

StackPointCloud 的想法是，无论用户使用哪个云提供商，他们都将获得一致的 Kubernetes 界面。

StackPointCloud 这样的小公司能够提供这种服务给 Lye 和他的团队留下了深刻的印象，同时 StackPointCloud 是一种实际的服务，而不仅仅是最终用户必须自己编译的一组服务，这是云服务的标准。“Amazon 不会让您的文件系统保持有保证的吞吐量。这就是我们想要做的，”Lye 说。

“Matt 构建了一个真正的软件即服务产品。这为我们提供了一个不断更新的软件版本，以及一个可扩展到企业的服务。没有任何人可以安装或升级的软件，”他说。

Baldwin 承认，使用 StackPointCloud 处理有状态工作负载很棘手。但是 NetApp 在这方面做了很多工作。

NetApp 的计划是将 StackPoint 与其自己的[Trident](https://github.com/NetApp/trident)container orchestrator、 [Cloud Volumes](https://cloud.netapp.com/cloud-volumes) 云服务网络文件系统以及相关的 [Cloud Volumes ONTAP](https://cloud.netapp.com/ontap-cloud) 操作系统进行集成。

“事实证明，容器和 Kubernetes 最大的问题是储存。人们想要编写的大多数应用程序都是有状态的，Kubernetes 并没有真正很好地处理有状态应用程序开发，”Lye 说。

今后，StackPointCloud 的用户将能够使用 NetApp 协议在公共云上部署集群，默认情况下使用 trident 存储驱动程序。StackPointCloud 还将与 NetApp 云数据服务集成。

Lye 说:“这两者的结合将为客户提供同类最佳的容器功能，以及利用应用程序级服务部署、管理和维护有状态应用程序的能力。”该公司还在研究私有云“超融合”包，该包将允许组织在自己的防火墙后建立基于容器的应用程序和服务，以及完整的状态存储。

“我们认为，客户越来越多地在公共云上定义他们的 IT 基础设施，而不是从 IT 到公共云，”Lye 说。

毫无疑问，在下周于拉斯维加斯举行的年度用户大会 [NetApp Insight 2018](https://insight.netapp.com/) 上，我们将听到更多关于 NetApp 云原生战略的信息。

专题艺术:Matt Baldwin，Kubecon Copenhagen 2018。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>