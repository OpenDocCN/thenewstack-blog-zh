# KubeCon EU: Azure Kubernetes 服务获得临时磁盘

> 原文：<https://thenewstack.io/kubecon-eu-azure-kubernetes-services-gets-ephemeral-disks/>

任何云 Kubernetes 服务都是标准化和差异化之间的平衡行为。提供随处可用的相同 Kubernetes 功能意味着竞争的方式是关注该服务与同一公共云中其他服务的集成程度。对于 Azure 上的 Kubernetes，微软强调了“企业级体验”以及在本周虚拟举行的今年[kube con+CloudNativeCon Europe](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)上宣布的新的安全和延迟功能。

有些云特性是你肯定希望虚拟机具备的——比如在运行操作系统的硬件关闭、虚拟机不得不转移到另一台主机的情况下，自动将操作系统驱动器复制到持久存储——但这对 Kubernetes 来说毫无意义。由于容器不会保持状态，并且根据设计会在没有警告的情况下四处移动，因此将操作系统磁盘保存到远程 Azure 存储会增加不必要的成本和延迟。当您调配或横向扩展集群时尤其如此，因为重新映像和启动会更快，但会对所有读写操作产生轻微影响。[短暂的操作系统磁盘支持](https://docs.microsoft.com/en-us/azure/aks/cluster-configuration#ephemeral-os-preview)今年早些时候为 Azure 上的虚拟机推出，现在为 AKS 公开预览，让你选择使用本地 SSD 存储或通常的网络连接存储。

无论存储在哪里，AKS 集群中节点上的底层操作系统每周都会自动获得一次安全和内核更新，但直到现在，如果这些更新需要重新启动才能应用，您必须等到 AKS 升级或使用 kured([Kubernetes 重新启动守护程序](https://github.com/weaveworks/kured))来重新启动节点。有了新的 node [镜像升级特性](https://docs.microsoft.com/en-gb/azure/aks/node-image-upgrade)，你不需要安装额外的工具，所以你可以升级 node OS 来获得安全补丁，而不需要改变你正在运行的 Kubernetes 的版本；这是预览版之外的，一般都有。

如果您将虚拟机规模集与 AKS 一起使用，则节点映像更新有效。“你可以更新 AKS 资源定义，这反过来将更新 VMSS 映像规范来执行升级，就像 Kubernetes 升级一样，只是在这种情况下，只有主机操作系统保持不变，”Kubernetes 联合创始人兼微软 CVP Brendan Burns [在 Twitter](https://twitter.com/brendandburns/status/1295462417187532800) 上解释道。

如果你想了解你在 Azure 上的所有 Kubernetes 资源，你现在可以在 Azure 门户中查看它们(而不是使用 Kubernetes 1.19 中不推荐的 kube-dashboard 插件)，你已经可以使用 Azure Monitor 来查看部署状态，但是为了进行故障排除，你现在可以在 Azure Resource Health 中查看 AKS 资源以及所有其他 Azure 资源。这显示了长达 30 天的健康历史，包括问题和维护，因此您可以跟踪您看到的问题是 AKS 问题还是由 Azure 上的其他内容引起的。

Azure Key Vault 是存储和轮换凭证、证书和其他秘密的逻辑位置，AKS 现在与此集成也就不足为奇了。使用 Azure 资源的托管身份使用 Azure AD，但对于您自己的服务和应用程序的密钥和凭据，AKS 使用 Secrets Store 容器存储接口驱动程序与 Key Vault 一起工作。那是一个[开源 CSI 驱动](https://github.com/kubernetes-sigs/secrets-store-csi-driver)，HashiCorp 现在正用于 Vault(其他秘密商店可以为它创建提供者)。

Kubernetes 也正在转向使用 [CSI 存储驱动程序](https://github.com/container-storage-interface/spec/blob/master/spec.md)，而不是使用核心 Kubernetes 代码构建和发布的“树内”存储卷插件(这意味着添加新的存储系统意味着将代码签入主 Kubernetes repo，等待 Kubernetes 的下一版本发布，并给予卷插件与 Kubernetes 核心组件(如 kubelet)相同的权限)。在 Kubernetes 1.21 中，AKS 将过渡到 CSI 存储驱动程序，并且对 Azure 文件和 Azure 磁盘的 CSI 支持现已[公开预览](https://azure.microsoft.com/en-us/updates/public-preview-csi-storage-driver-support-in-azure-kubernetes-service/)。

像 AKS 这样的容器即服务产品是 Flexera " [2020 年云状态](https://info.flexera.com/SLO-CM-REPORT-State-of-the-Cloud-2020)"报告中增长第二快的企业云服务(仅次于物联网，仅次于机器学习)。在调查中，超过一半的企业将使用容器作为云的首要任务。

但是，四分之三的企业在云计算中最关心的是控制其现有云使用的成本。因此，微软也有理由强调针对 AK 的[新培训](https://docs.microsoft.com/en-gb/learn/modules/aks-optimize-compute-costs/)使用 scale to zero、折扣点节点定价和 Azure Policy add-on 来管理 CPU 和 RAM 配额，以便在没有意外高额账单的情况下获得 Kubernetes 在云中的优势。

云原生计算基金会、HashiCorp 和 KubeCon + CloudNativeCon 是新堆栈的赞助商。

来自 Pixabay 的空竹特写。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>