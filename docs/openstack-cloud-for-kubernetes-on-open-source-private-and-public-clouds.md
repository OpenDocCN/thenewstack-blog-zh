# 开源私有云和公共云上面向 Kubernetes 的 OpenStack 云

> 原文：<https://thenewstack.io/openstack-cloud-for-kubernetes-on-open-source-private-and-public-clouds/>

OpenStack 基金会赞助了这篇文章。

 [克里斯·霍格

Chris 是 OpenStack 基金会的战略项目经理。他致力于 OpenStack 和容器开发社区之间的合作，包括 Airship、Kata Containers 和 Kubernetes。他还负责管理 OpenStack 基金会的商标项目，并在开放容器倡议(OCI)商标委员会拥有席位。此前，他在 Puppet Labs 担任 OpenStack 社区经理和开发人员，并为俄勒冈大学艺术与科学学院运营一个研究云。当不在开源云计算社区工作时，他喜欢长跑、跳舞和为他的边境牧羊犬投球。](https://www.openstack.org/) 

本周标志着面向 Kubernetes 的 t [he OpenStack 云提供商](https://github.com/kubernetes/cloud-provider-openstack)[第四次发布 1.13](https://github.com/kubernetes/cloud-provider-openstack/releases/tag/1.13.0) 版本。提供者是位于 Kubernetes 集群和 OpenStack 云之间的集成层。OpenStack 云提供商通过让应用编排层更深入地了解和控制 OpenStack 云中可用的底层计算、存储和网络资源，帮助您交付弹性云原生应用。这个版本与最近的 1.13 Kubernetes 版本一致，为了保持一致性，使用了匹配的编号。坚持缩短 Kubernetes 开发周期的主题，OpenStack 云提供商的这一版本专注于稳定性和优化。

OpenStack 云提供商的工作由 SIG-OpenStack 管理，这是 Kubernetes 社区中的一个特殊兴趣小组，致力于使 OpenStack 成为托管 Kubernetes 的最广泛部署的开源云。使用 SIG 成员构建的集成工具，可以构建一个完全开源的应用堆栈，从使用 OpenStack Ironic 的裸机配置到运行核心 OpenStack 组件的数据中心云，再到使用云提供商作为中介使用 Kubernetes 交付应用。

SIG-OpenStack 在构建 Kubernetes 生态系统集成方面有着悠久的历史。OpenStack 提供了首批在上游 Kubernetes 中发布的云提供商之一，然后继续为 OpenStack Cinder block 存储服务提供 OSI 兼容驱动程序，为 80 多种不同的存储后端提供支持。SIG-OpenStack 还使用标准的 Kubernetes 端到端和一致性测试，领导建立云提供商支持的集群的持续集成测试。

这项工作有助于通过 SIG-Cloud-Provider 融入更大的社区工作，SIG-Cloud-Provider 是一个特殊的利益集团，致力于为所有云提供商建立公平和中立的测试、开发和文档标准，包括 AWS、Azure 和 GCP。SIG-Cloud-Provider 由当前 SIG-OpenStack 负责人之一 Chris Hoge 共同创建和领导。这次签约培养了一种跨开源和商业云平台的开放协作精神。

在接下来的几个月里，您可以期待 SIG-OpenStack 继续提供出色的体验，在 OpenStack 上运行 Kubernetes，继续与云提供商合作，并与 [SIG-Cluster-Lifecycle](https://github.com/kubernetes/community/tree/master/sig-cluster-lifecycle) 一起进行新的开发。该 Kubernetes SIG 旨在简化 Kubernetes 的管理和操作，重点关注集群部署和升级。新的 Cluster-API 项目为集群的创建、配置和管理带来了声明性的、Kubernetes 风格的 API。通过由定制云提供商支持的单一 API，这项工作扩展了 Kubernetes，使其成为一个自我管理的应用程序平台。在未来几个月，SIG-OpenStack 将继续积极为这个重要的新项目构建提供商代码。

您有兴趣在 OpenStack 上开始使用 Kubernetes 吗？OpenStack cloud provider for Kubernetes 可以用作 open stack 上任何 Kubernetes 安装的插件。您可以在您的 OpenStack 云上尝试一下。如果你想在 OpenStack 上获得托管的 Kubernetes 体验，你现在就可以在受支持的开源公共云(例如，[vexhost](https://vexxhost.com)和 [Catalyst Cloud](https://catalystcloud.nz) )上尝试一下 [OpenStack Magnum](https://wiki.openstack.org/wiki/Magnum) 。Magnum 通过一个简单的 API 在 OpenStack 云上为您提供完全托管的 Kubernetes，允许您从头到尾管理您的集群生命周期。

SIG-OpenStack 很荣幸成为 Kubernetes 社区的一员，并对即将到来的提供商和集群 API 工作感到兴奋。我们是一个开放的社区，期待在 Kubernetes #SIG-OpenStack Slack 频道以及西雅图的 KubeCon 和丹佛的开放基础设施峰会等活动中与您见面。您可以在 SIG-OpenStack 发布的白皮书[“利用容器和 OpenStack”中找到更多信息和几个案例研究](https://www.openstack.org/containers/leveraging-containers-and-openstack/)

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>