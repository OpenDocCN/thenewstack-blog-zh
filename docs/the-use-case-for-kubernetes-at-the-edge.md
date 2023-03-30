# Kubernetes 在边缘的使用案例

> 原文：<https://thenewstack.io/the-use-case-for-kubernetes-at-the-edge/>

[](https://twitter.com/sagarnangare)

[Sagar Nangare](https://twitter.com/sagarnangare)

[Sagar Nangare 是科技博客作者，专注于数据中心技术(网络、电信、云、存储)和边缘计算、物联网、机器学习、人工智能等新兴领域。他目前在浦那担任 Coredge.io 的产品营销总监。](https://twitter.com/sagarnangare)

[](https://twitter.com/sagarnangare)[](https://twitter.com/sagarnangare)

Kubernetes 是企业向数字优先业务转型的重要组成部分。根据 [VMware](https://tanzu.vmware.com?utm_content=inline-mention) 的“[Kubernetes 2020 年状态](https://k8s.vmware.com/state-of-kubernetes-2020/)”报告，Kubernetes 目前正在 59%的数据中心使用，以提高资源利用率并带来软件开发周期的敏捷性。重要的是，Kubernetes 可以在分布式云环境中管理和编排容器化的应用程序以及遗留虚拟机。不仅仅是对于纯粹的应用程序，Kubernetes 对于运行 AI/ML 和 GPU 工作负载也很有帮助。

除了数据中心之外， [Linux Foundation](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention) 的 [The State of Edge 报告](https://stateoftheedge.com/reports/state-of-the-edge-report-2021/)清楚地描述了 Kubernetes 是边缘云的首选平台，至少对于那些需要动态编排应用程序和集中管理工作负载的边缘来说是如此。

我们可以说，Kubernetes 正在将云原生计算软件开发模型提供的优势扩展到边缘，对跨越分散云环境的应用进行灵活和自动化的管理。

以下是 Kubernetes 在管理边缘应用和工作负载方面的一些关键进展。

*   最令人兴奋的基于 Kubernetes 的开源项目之一是 Akri。它由微软发布，旨在为 edge 提供高级功能，以连接到更小的“叶子设备”，如微控制器、相机、传感器，使它们都成为 Kubernetes 集群的一部分。从这些叶设备收集输出，Akri 基本上扩展了 [Kubernetes 设备框架](https://github.com/kubernetes/community/blob/master/contributors/design-proposals/resource-management/device-plugin.md)。
*   微软发布了另一个名为 [Krustlet](https://krustlet.dev/) 的开源项目，该项目运行 [WebAssembly](https://webassembly.org/) (WASM)模块来利用 Kubernetes 和容器。开发人员可以使用 WASM 从他们熟悉的语言(C，C++，C#，Rust，Go 等)中编译代码。这对于边缘计算非常重要，因为相同的代码库可以在多种设备上执行。
*   超融合(HCI)系统已经成为托管虚拟化和容器化应用的首选解决方案，这些应用在边缘需要较少的计算解决方案。《边缘状态报告》显示，超大规模云提供商正在将 HCI 系统与混合云环境相集成。这些 HCI 系统还与公共云 Kubernetes 服务集成，以部署和管理容器化和虚拟化的资源，并需要从中央云进行生命周期管理。
*   2020 年，谷歌、[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)、IBM 和 Azure 等云供应商推出了旨在构建边缘云的解决方案。Kubernetes 针对每个云供应商的服务被用来协调边缘的资源。
*   Linux Foundation Edge 项目 [Baetyl](https://www.lfedge.org/projects/baetyl/) 更新了对 Kubernetes 的原生支持。Baetyl 基本上运行在 Kubernetes 的边缘来管理和部署应用程序。Baetyl 还支持轻量级 K3S Kubernetes 平台 K3S。此外，所有 Baetyl 功能都可以作为 Kubernetes 服务，具有自我更新能力。
*   Linux Foundation Edge 的[项目 EVE](https://www.lfedge.org/projects/eve/) 支持边缘的任何应用和硬件的生命周期管理和远程编排。
*   面向边缘和物联网用例部署的开放基础设施 [StarlingX](https://www.starlingx.io/) 项目已经发展到在边缘运行容器来托管基础设施服务。StarlingX 基本上结合了 OpenStack 和 Kubernetes 来一起运行虚拟机和容器。此外，它还使得只在边缘运行利用 Kubernetes 轻量级组件的容器成为可能。

企业和电信运营商正致力于通过部署和测试 [Kubernetes at the edge](https://www.calsoftinc.com/resources/ebriefs/a-deep-dive-into-kubernetes-for-edge/) ，实现极大的灵活性、可观察性和动态编排。许多供应商，如 Canonical、 [Mirantis](https://www.mirantis.com/?utm_content=inline-mention) 和 Suse，都在 Kubernetes 的基础上构建了自己的开源平台来支持 edge 用例。超大规模云提供商正在将其边缘解决方案与本地 Kubernetes 服务相集成。这种趋势表明 Kubernetes 是采纳者的关键平台。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>