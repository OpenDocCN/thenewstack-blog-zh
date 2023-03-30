# Upbound.io:一种聚集所有库本内特星团的方法

> 原文：<https://thenewstack.io/upbound-io-one-way-to-herd-all-those-kubernetes-clusters/>

如果您可以使用 Kubernetes 来管理世界各地和跨各种云的 Kubernetes 集群，会怎么样？

这就是总部位于西雅图的 Upbound.io 正在采取的方法，以创建一个单一的控制平面，使用户能够将所有这些环境视为一个整体。

创始人兼首席执行官 [Bassam Tabbara](https://github.com/bassam) 表示:“随着越来越多的公司跨区域运营，无论是出于合规性原因、延迟还是 GDPR，随着人们开始跨云运营，人们不仅要在这些环境中进行交互，还需要自动化和控制器来帮助他们管理跨云环境的基础设施和服务。”。

“当我们与客户和业内人士交谈时，会产生共鸣的一点是，下一个级别的挑战不在节点级别。Kubernetes 本质上已经成为集群操作系统。下一个层面是如何思考一个全球操作系统。”

它来自于 [Rook](https://rook.io/) 存储项目背后的团队，该项目专注于 Kubernetes 上的有状态工作负载。今年早些时候，它与[云本地计算基金会](https://www.cncf.io/) (CNCF)合作，成为了一个[初始阶段的项目](https://thenewstack.io/cncfs-rook-project-brings-storage-capability-cloud-native-workloads/)。他提到了欧洲核子研究中心的工程师们的 KubeCon Europe talk，他们在 Kubernetes 的多个公共云中运行 212 个集群，以便 3300 个用户可以处理来自大型强子对撞机和其他实验的粒子数据:

[https://www.youtube.com/embed/2PRGUOxL36M?feature=oembed](https://www.youtube.com/embed/2PRGUOxL36M?feature=oembed)

视频

假设你在 Azure 有一个集群，在 Google 有一个集群，在 Amazon 有一个集群，但是你也可以把它想象成一个云提供商内的多个区域——美国东部、美国西部等等。当您想到开发、暂存和生产时，它也是多集群。许多公司都有多个集群。如今，他们将它们视为独立的筒仓。他说，他们最终会在它们之间移动东西，但今天没有人支持这种做法。

“我们正在打造一项服务，让您能够将集群整合在一起，然后在这些云环境之上运行服务。想象一下，如果您在云中或您的内部数据中心的多个区域运行该数据库的各个部分。这些服务现在将能够通过一个公共控制平面进行部署、平衡、管理、扩展和优化，即使它们运行在不同的区域和云环境中，”他说。

5 月初，该公司宣布获得由 GV(前谷歌风投)领投的 900 万美元 A 轮投资。它计划在今年晚些时候或明年初发布。

Tabbara 坚持认为，虽然有各种各样的多云管理工作正在进行中，但他知道没有其他人专注于单个控制平面。

当被要求深入研究其技术时，Tabbara 简单地说，“我们使用 Kubernetes 来管理 Kubernetes。

“我们正在努力在这个领域运行[多集群联盟](https://medium.com/google-cloud/planet-scale-microservices-with-cluster-federation-and-global-load-balancing-on-kubernetes-and-a8e7ef5efa5e)。我们是整个 Kubernetes 扩展模式的忠实用户。这是我们作为 Rook 的一部分帮助驾驶的东西。我们非常关注有状态的工作负载，尤其是在多云堆栈方面。”

他引用了一个健康的生态系统，围绕着构建多云端服务的人们，无论是数据库、消息队列还是跨区域运营的大数据系统，他认为这是该项目的一个重要方面。

“我们正在建设 Kubernetes。我们不会让人们去构建新的抽象或新的工具。我们使用 Kubernetes 来管理 Kubernetes 中的集群，然后我们为希望运行多云的软件供应商建立一个真正健康的生态系统。我们相信这两者对于在这个领域取得成功至关重要，”他说。

[云本地计算基金会](https://www.cncf.io/)是新堆栈的赞助商。

专题图片:[杨梅摄影](https://www.flickr.com/photos/arbutusridge/)拍摄的[放牧](https://www.flickr.com/photos/arbutusridge/8673576150/in/photolist-edsm1o-6owWys-46U3xe-6AFD1-62iWAf-wfCAMU-KbTUuZ-jcYBva-6JwMpv-4PuRW9-X4EByY-6oVGVq-pZuvx4-nn1fqz-2KyxyE-miudgR-6osLBV-bnsBh2-eaQGSP-8canra-oyu3Ei-4ZzGoz-KhPjv-bTVhMk-9cYCG-c6QbHU-24AT8L7-SGR49s-pFszqN-coYkmJ-7m7YQN-sk29Dm-F1SdiH-6PwB4d-Sijrtk-rQRqa1-om8Mkk-9gLbAd-KdErFq-etk48A-4FDrka-5oHt9P-mqmNq-6FnLjY-J2BiqH-aE6nbG-9aGCTh-9HUTrH-aey9Dr-6srGVY)，经 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>