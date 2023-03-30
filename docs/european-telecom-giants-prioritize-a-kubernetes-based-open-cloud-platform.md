# 欧洲电信巨头优先考虑基于 Kubernetes 的开放云平台

> 原文：<https://thenewstack.io/european-telecom-giants-prioritize-a-kubernetes-based-open-cloud-platform/>

[](https://twitter.com/sagarnangare)

[Sagar Nangare](https://twitter.com/sagarnangare)

[Sagar Nangare 是科技博客作者，专注于数据中心技术(网络、电信、云、存储)和边缘计算、物联网、机器学习、人工智能等新兴领域。他目前在浦那担任 Coredge.io 的产品营销总监。](https://twitter.com/sagarnangare)

[](https://twitter.com/sagarnangare)[](https://twitter.com/sagarnangare)

最近，五家欧洲电信运营商(Deutsche Telecom、Orange、Telefonica、TIM S.p.A .和 Vodafone)签署了一份谅解备忘录(MoU ),以推动 Open RAN 行业范围接口标准的创新，该标准允许来自不同供应商的无线电接入网络设备和软件进行通信。

总的来说，欧洲电信[发布了](https://hellofuture.orange.com/app/uploads/2021/05/Open-RAN-Technical-Priorities-Executive-Summary-Final-version.pdf)一份“技术优先级文件”,旨在列出构建 Open RAN 架构的技术优先级/要求。本文件设定了五家电信运营商在未来几年部署 RAN 时的技术偏好。它可作为 RAN 解决方案供应商的指南，帮助他们关注开放式 RAN 架构的特定优先事项，从而进一步加快在欧洲的市场部署。该要求列表将简化具有通用管理框架的完全分散的多供应商 RAN 的部署。

开放式 RAN 架构包含构成开放式基础设施的构建模块，以交付软件 RAN: O-Cloud(开放式云软件平台)、O-CU(开放式中央单元)、O-DU(开放式分布式单元)、RIC (RAN 智能控制器)和 OFH(开放式前端单元)，等等。O-Cloud 是基于软件的基础设施，支持 O-RAN 硬件和软件分解。O-Cloud 允许 O-RAN 软件应用和容器化网络功能(CNF)在基于通用处理器(GPPs)的商用现货(COTS)硬件上运行。

O-Cloud 的实现将基于 Kubernetes 框架来支持 RAN 软件。它将承载 O-RAN 功能，如 O-CU、O-DU 和近实时 RIC。这意味着 Kubernetes 将成为管理基于软件的 O-CU、O-DU 和 RIC 的生命周期的关键编排框架。此外，为了实现应用的高吞吐量和低延迟，他们打算在裸机上托管 CNFs，并使用基于 Kubernetes 的 O-Cloud 进行协调。这是 Kubernetes 在电信领域的重大发展。

## **为什么 Kubernetes 对电信运营商很重要？**

在最近的 KubeCon Europe 上，[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)调查评估了 Kubernetes 在边缘的部署。根据调查[报告](https://www.cncf.io/wp-content/uploads/2021/05/KubernetesEdge_Survey_Report_2021_v2.pdf)，最受欢迎的使用案例是制造业/工业物联网。继第一个用例之后，下一个用例是电信/移动边缘计算。

这清楚地表明了电信运营商如何开始使用 Kubernetes 来管理部署在基于软件的网络中的应用程序。重要的是，这项调查只显示了边缘的结果。Kubernetes 不仅在边缘有用，而且在电信网络的每个部分都有用。Kubernetes 可以管理部署在数百个核心数据中心(称为近边缘)和数千个远边缘的应用程序，并协调后台应用程序(OSS/BSS)。

现在，这份技术优先事项文档显示，O-Cloud 平台将部署在 Kubernetes 上，这将进一步帮助他们在 K8s 集群中推动更多工作负载。电信运营商的主要优势包括:

*   Kubernetes 可以对与部署在虚拟机中的应用程序一起打包的应用程序执行生命周期管理。它有助于消除为虚拟机配备单独协调器的需求，并有助于逐步过渡到完全容器化的应用程序。
*   在分布式云环境中，Kubernetes 提供了一个策略驱动的标准平台来管理部署在不同云环境中的 CNFs 和 VNFs。这进一步有助于拥有一个集中的管理层来管理电信云。
*   有许多开源的 Kubernetes 框架可以帮助启动电信边缘、OSS/BSS 应用程序等的应用程序编排。Kubernetes 的普通版本可以与必要的插件一起实现，以添加与网络接口、pod 发现等相关的新特性。以普通形式部署 Kubernetes 时不需要软件许可证。这有助于电信运营商节省资本支出。
*   大多数电信工作负载应该部署在裸机基础设施上，如 RAN 硬件和远程边缘服务器。随着虚拟化层的消除，虚拟层可以获得的开销减少，从而进一步降低了延迟和敏捷自动化。

## **结论**

当我们谈到现代软件开发的容器和云原生堆栈时，Kubernetes 是唯一一个能够满足任何数据中心的动态应用生命周期管理要求并提供所有优势的框架。Kubernetes 是推动运营商拥有[云原生开放 RAN](https://www.calsoftinc.com/resources/ebriefs/open-ran-cloud-native-software-aspects-for-end-to-end-orchestration-automation/) 和现代 4G/5G 网络其余核心的关键工具。

对于电信公司来说，Kubernetes 是一项突破性技术，有助于从传统虚拟化层过渡到容器化应用程序工作负载的路线图，传统虚拟化层有基础架构开销，仍然需要更多投资来托管应用程序。有了 Kubernetes，他们可以通过保留传统基础设施开始他们的旅程。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>