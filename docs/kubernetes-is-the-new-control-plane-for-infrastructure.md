# Kubernetes 是基础设施的新控制平台

> 原文：<https://thenewstack.io/kubernetes-is-the-new-control-plane-for-infrastructure/>

[](https://portworx.com/)

 [Murli Thirumale，Portworx 联合创始人兼首席执行官

Murli Thirumale，Portworx 联合创始人兼首席执行官，曾担任 Ocarina Networks，Inc .联合创始人兼首席执行官。他还担任 Citrix Systems，Inc .高级解决方案集团副总裁兼总经理。Thirumale 拥有西北大学凯洛格管理研究生院的 MBA 学位，是 F.C. Austin 杰出学者。](https://portworx.com/) [](https://portworx.com/)

Kubernetes 很快成为事实上管理容器中应用的方式。它的用途现在也扩展到管理底层基础设施。首席信息官应该关注这一发展，因为 Kubernetes 可以简化 IT 运营、降低成本并提高整个数据中心的灵活性，而不仅仅是运行在容器中的一小部分应用程序。这对于充分发挥现代应用程序开发的价值也至关重要。

使用 Kubernetes 管理基础设施不仅仅是一件好事，它对于充分实现云原生计算的好处至关重要。近年来，应用开发发展迅速，底层基础设施需要随之发展，以支持 Kubernetes 带来的快速扩展、自动化和敏捷性。否则，基础架构将成为 it 现代化的瓶颈。

Kubernetes 能够使您的基础设施与您的应用程序现在能够实现的功能保持一致。使用 Kubernetes 扩展，您可以根据扩展应用程序来扩展计算、网络和存储，并在多个公共云和私有云之间以统一的方式管理基础架构。简而言之，现代应用程序使用 Kubernetes 来编排和管理 IT 基础架构，以及管理容器，以便整个堆栈，端到端和自上而下，获得敏捷性和成本降低的好处。

这在今天的现实中是什么样子的？Kubernetes 社区开发了大量的接口、插件和附加组件，扩展了 Kubernetes 的功能，提供了一整套基础设施功能和服务。其中包括容器存储接口(CSI)和容器网络接口(CNI ),前者可以根据需要自动提供和删除存储卷(它已经为许多供应商提供了驱动程序),后者为网络连接提供了类似的功能。还有用于监控、跟踪、日志、负载平衡等的 Kubernetes 附加组件。

Kubernetes 扩展也为虚拟化环境带来了云的优势。例如，KubeVirt 提供了云原生虚拟化，使得在 Kubernetes 管理的环境中高效运行虚拟机成为可能。它将成熟虚拟化管理的精华与 Kubernetes 中的敏捷应用程序编排相结合。

与其他 Kubernetes 扩展一样，Kubevirt 也提供了一个开源的、基于标准的专有产品替代方案，例如 VMware 的 Project Pacific。这使得 Kubernetes 能够跨任何供应商的任何类型的存储和计算设备以及任何公共云或私有云管理基础架构。

重要的是，Kubernetes 并不局限于管理集装箱化的环境。它还可以管理虚拟机中运行的传统非容器化应用的基础架构。因此，即使只有 20%的企业应用程序被容器化，Kubernetes 也能为所有应用程序提供管理硬件和网络资源的单一环境，这意味着团队不需要处理多个管理框架。使用这些 Kubernetes 扩展，供应商现在可以提供虚拟化底层存储或网络的存储或网络覆盖，但将其置于 Kubernetes 的管理之下。这使企业能够保留其存储资本支出投资，但使用 Kubernetes 管理它们。

这里最重要的想法是创建一个由您的应用程序需求定义的基础架构，而不是底层硬件的需求。换句话说，重点需要从网络和存储管理员执行的手动配置转移到基础架构能够感知应用程序并根据最终用户定义的需求自动配置的环境。这就是 Kubernetes 所能做到的。

简而言之，使用 Kubernetes 来控制基础设施，将最初吸引首席信息官的优势——智能自动化、快速扩展、降低成本和敏捷部署——带到了底层基础设施中。这对于防止基础设施成为现代应用层快速改进的瓶颈至关重要。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>