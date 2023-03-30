# Longhorn Kubernetes 块存储添加快照，ARM64 支持

> 原文：<https://thenewstack.io/longhorn-kubernetes-block-storage-adds-snapshots-looks-to-edge-deployments-with-arm64-support/>

本周，【Kubernetes 的分布式块存储解决方案 [Longhorn](https://longhorn.io/) 背后的人们发布了他们软件的 1.1 版本，这是在[正式发布](https://newreleases.io/project/github/longhorn/longhorn/release/v1.0.0)八个月之后，也是在[加入](https://thenewstack.io/rancher-donates-its-longhorn-kubernetes-persistent-storage-software-to-cncf/)云本地计算基金会(CNCF) 作为沙盒级项目一年多一点之后。在这段时间里，Rancher 领导的项目得到了迅速的采用和发展，而 Rancher 正在被 SUSE 收购。

“长角牛已经走过了漫长的道路。自从捐赠给 CNCF 以来，它每年都在以超过三位数的速度增长，它的最初目标是让有状态工作负载在 Kubernetes 上更受欢迎，”Rancher 前首席执行官、 [SUSE](https://www.suse.com/) 工程和创新总裁[盛亮](https://www.linkedin.com/in/shengliang/)说。“1.1 的范围其实挺大的。项目速度显著加快，它改进了一系列功能，包括特性、新平台、弹性、监控、维护以及支持边缘计算等新环境的能力。”

Longhorn 1.1 引入了对 ARM64 架构的支持，这提高了其在低功耗边缘设备上运行的能力，以及数据局部性等功能，这提高了在边缘情况下常见的不稳定网络条件下的弹性。自从 SUSE 收购 Rancher 以来，边缘计算对 SUSE 来说变得越来越重要，这也带来了对 [K3S 项目](https://k3s.io/)的管理，这是一个专门设计用于边缘的 Kubernetes 发行版。nene Longhorn 本身只用了 30，000 行 Go 代码编写，并且基于现有的 Linux 存储技术，这使它成为在边缘操作的主要候选。梁表示，虽然 Kubernetes 上的 edge 是一个新兴领域，在 edge 上的部署不到所有部署的四分之一，但它确实是该公司未来“一个重要的增长领域”。

“实际上，Longhorn 对边缘部署的需求越来越大，”梁说。当您在边缘部署这些 Kubernetes 群集时，以超融合方式在群集内部署存储非常重要

Longhorn 1.1 也提供了自我修复功能，梁说，这是 Longhorn 与 Kubernetes 直接集成的结果。

“当一个节点消失时，Kubernetes 会检测到它。除了恢复存储，Longhorn 还将与 Kubernetes 通信以恢复工作负载，只是更加可靠。这是将存储与 Kubernetes 集成在一起的好处，而存储只是一个独立系统的一部分，如传统的设备系统，”梁说。Longhorn 的集成实际上使工作负载恢复更加高效。"

Longhorn 1.1 还增加了许多其他功能，根据梁的说法，其中一个“最受欢迎的功能”是添加了“Readwritemany”，该功能允许随时跨多个容器读写卷。该版本还引入了开源监控系统 [Prometheus](https://prometheus.io/) 的默认集成，提供了存储健康的实时指标，以及通过[容器存储接口(CSI)](https://kubernetes-csi.github.io/docs/) 执行快照的能力，该接口最近扩展到包括直接在 Kubernetes 内进行快照和备份的挂钩。

梁说，进一步利用 CSI 的快照和备份功能是该项目未来的另一个重点。

“我们仍在开发的一项功能是将快照和备份与应用程序配置相集成。在 Kubernetes 中，应用程序的配置由配置映射、文件、机密等内容组成，所有这些内容都存储在 Kubernetes 的元数据存储中，”梁说。“如果您捕获了它，然后将应用程序配置元数据与应用程序数据备份结合起来，现在您就有了应用程序状态的完整备份。这使您可以非常轻松地进行灾难恢复和迁移等活动。”

图片由 Pixabay 的 Tony Wehrstein 制作。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>