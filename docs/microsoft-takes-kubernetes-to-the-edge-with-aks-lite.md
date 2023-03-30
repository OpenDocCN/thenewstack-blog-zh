# 微软用 AKS Lite 将 Kubernetes 推向了边缘

> 原文：<https://thenewstack.io/microsoft-takes-kubernetes-to-the-edge-with-aks-lite/>

在本周的 Ignite 用户大会上，微软举办了一场 Kubernetes 盛宴，软件和服务巨头凭借 [AKS lite](https://www.zdnet.com/article/microsoft-readies-kubernetes-public-preview-for-windows-iot-devices/) 将 Kubernetes 推向了边缘。

微软宣布，Windows 物联网和 Windows 设备上的 [Azure Kubernetes 服务(AKS)](https://thenewstack.io/how-the-azure-kubernetes-service-makes-developers-more-productive/) 的公开预览版，即 AKS lite，将于 11 月推出。

AKS lite 是一个轻量级的 Kubernetes 平台，能够在边缘实现大规模的快速应用程序现代化，该项目的主要项目经理 Jason Farmer 说。

## 基于 AKS 构建

[AKS](https://azure.microsoft.com/products/kubernetes-service/) 是微软托管的、[云本地计算基金会(CNCF)](https://thenewstack.io/future-cloud-native-computing-foundation/) 兼容的 Kubernetes 平台，可运行 Linux 和 Windows 容器应用程序。

与此同时，“AKS lite 建立在这个稳定的平台上，以提供一个轻量级的 Kubernetes 发行版 K8S 和 K3S，可以轻松地部署在任何 Windows PC 级设备上，以及 Windows 10 和 11 物联网企业、企业和专业设备上，”Farmer 在一篇博客文章[中说。“除此之外，对于在轻量级操作技术边缘使用 Windows Server 的情况，您也可以使用 AKS lite。AKS lite 简化了本地 Kubernetes 集群的管理、部署和维护，使其易于开始托管 Linux 和 Windows 容器。”](https://techcommunity.microsoft.com/t5/internet-of-things-blog/taking-azure-arc-and-kubernetes-to-the-edge/ba-p/3650599)

微软最初在 5 月份的公司 [Build 2022](https://thenewstack.io/microsoft-demos-ai-development-at-build-using-openai-codex/) 大会上介绍 AKS lite 为“ [Project Haven](https://learn.microsoft.com/en-us/events/build-2022/od144-project-haven-kubernetes-embedded-edge) ”。

Farmer 表示:“云原生输入处理、人工智能和现代应用要求 Kubernetes 在更小、资源受限的边缘设备上能够扩展和管理数百个分布式节点上的工作负载。“这在规模方面提出了不同的挑战。operational edge 不需要在几个大型 K8S 集群上运行数千个容器，而是需要数千个分散的集群，每个集群运行几个容器。这凸显了简化管理和提高部署可见性的必要性。”

## 特点、优势

AKS lite 设计用于在受限设备上运行，具有 2 个 vCPUs 和 4 GB RAM 的最低计算和可用内存要求。

其他功能包括:

*   每个 Kubernetes 集群都在自己的 Hyper-V 隔离虚拟机中运行，并包含许多功能来帮助保护您的容器基础架构
*   微软为工作节点维护的 Linux 和 Windows 映像–工作节点运行微软创建的 Linux 和 Windows 虚拟机映像，以遵守安全最佳实践。微软还每月用最新的安全更新来刷新这些图像。
*   PowerShell cmdlets 和代理简化了安装体验，支持虚拟机和基础架构的配置和控制。您可以通过诸如 Azure Arc for Server 或 Microsoft Endpoint Configuration Manager 之类的设备管理工具在本地或远程运行这些 cmdlets。
*   除了主机操作系统更新，微软将为您的 Kubernetes 部署提供自动更新。

AKS lite 用户的主要优势包括与原生 Windows 应用程序的互操作性，从内核到云的完全支持的堆栈以及边缘的云服务支持。

## 混合期权

“当你的 AKS lite 集群连接到 Azure Arc 时，它将 Azure 平台扩展到具有核心服务(如治理、监控、应用程序、ML 和数据服务)的边缘，”Farmer 说。“它还有助于将 DevOps 实践带到任何地方，并使用 GitOps 和 Flux 进行迭代构建，以无缝管理应用部署。”

此外，借助新的 AKS 混合部署选项，在 preview 中，用户可以将云扩展到边缘，因为他们可以在 Windows 设备、Windows IoT、Windows Server 2019/2022 和 Azure Stack HCI 上集中部署和管理 Azure Arc 支持的 AKS。

微软首席执行官[塞特亚·纳德拉](https://www.linkedin.com/in/satyanadella/)在该活动的主题演讲中表示:“随着 Kubernetes 的采用，你可以使用 Arc 在 Azure Stack HCI、Windows Server、Windows 设备和 Windows IoT 上运行带有 AK 的容器化应用，从而在 Azure 内部和边缘实现一致的体验。“未来，我们将让 AKS 在更多平台上运行。”

一位分析师对这个想法印象深刻。

Enterprise Management Associates 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk/) 说:“对于许多害怕站起来管理自己的 K3s 集群的企业来说，提供可以在同一台机器上运行 Windows 和 Linux 的托管 K3s edge 集群是一个有趣的价值主张。“最重要的是，这使微软能够将其更高级别的云服务(如 NoSQL、数据分析、机器学习和无服务器功能)定位为易于部署的拼图，以增强并最终转变已经通过 Azure 平台管理的 K3s edge 应用。”

## Ignite 上的更多 Kubernetes

微软还宣布了[Azure Kubernetes Fleet Manager](https://aka.ms/aks/ignite)preview，它使用户能够管理 Kubernetes 集群的车队，运行多集群工作负载和服务，并确保其 Kubernetes 环境中的一致配置、访问和治理。

此外，在 Ignite 上，微软指出 ISV 现在可以创建一键 Kubernetes 应用程序。 [Kubernetes apps](https://azure.microsoft.com/en-us/updates/public-preview-kubernetes-apps-on-azure-marketplace/) ，现在处于预览阶段，是一个专门为 Kubernetes 解决方案提供的 Azure Marketplace。ISV 现在可以通过计费模式在 Azure Marketplace 中创建、发布和管理商业 Kubernetes 产品。客户可以浏览解决方案目录，并选择一个解决方案，通过自动化 Azure 计费一键部署到 AKS。该公司表示，这项功能将是第一个专门为 Kubernetes 提供的 Azure Marketplace 中的自动部署和计费功能。

“微软提供轻量级 Kubernetes 发行版作为托管服务，与 PowerShell 和整个 Azure 云原生世界集成，这是有意义的，”Volk 补充道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>