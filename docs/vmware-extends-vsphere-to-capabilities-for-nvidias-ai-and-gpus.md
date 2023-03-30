# VMware 将 vSphere 扩展到 Nvidia 的人工智能和 GPU 功能

> 原文：<https://thenewstack.io/vmware-extends-vsphere-to-capabilities-for-nvidias-ai-and-gpus/>

VMware 的 [VMware vSphere 7 Update 3](https://www.vmware.com/products/vsphere.html) 版本旨在通过自助式 API 选项进一步解锁对 Nvidia vGPUs 和 AI 的访问，同时还为在虚拟机(VM)、容器或 Kubernetes 中或其上运行的应用程序提供了许多新的 vSphere 功能。

该公司今天还发布了 [VMware vSAN 7 Update 3](https://www.vmware.com/products/vsan/whats-new.html) ，以改进对 VMware vSAN 环境的基础架构支持。

这两个版本都反映了 [VMware 的](https://tanzu.vmware.com?utm_content=inline-mention)雄心，即简化和进一步自动化 CI/CD、基础架构管理以及开发人员和运营团队在不同环境(包括多云)中的 IT 需求。

在 vSphere 发布之前，vSphere 用户自 4 月起可以直接访问 GPU 巨头 [Nvidia 的 AI Enterprise](https://www.nvidia.com/en-us/data-center/products/ai-enterprise-suite/) 套件，以帮助扩展 AI 应用及其跨多云虚拟基础设施的开发。根据两家公司之间的许可协议条款，vSphere 此后一直支持英伟达的人工智能框架、CUDA 应用程序、模型和 SDK。

随着 Update 3 的推出，开发人员和 DevOps 人员将能够使用 Kubernetes 命令在配有[vgpu](https://www.nvidia.com/en-us/data-center/virtual-solutions/)、VMware 产品营销高级总监 [Sheldon D'Paiva](https://www.linkedin.com/in/sheldondpaiva) 的主机上配置虚拟机。这项功能还将帮助用户使用自助服务模式在支持 GPU 的硬件上构建和运行他们的人工智能应用。

“当结合我们在 Update 2 中引入的所有与 GPU 相关的增强功能时，开发人员将拥有强大的能力，”D'Paiva 说。“在此功能出现之前，开发人员必须向 IT 团队请求能够运行应用的 GPU 系统。这一过程通常缓慢而官僚，需要几天甚至几周才能收到他们需要的东西。这显然会降低开发速度，并最终缩短新应用的上市时间。”

人工智能和面向开发者的基础设施包括:

*   面向 vGPUs 的 vSphere VM 服务支持。通过 Kubernetes API 使用 VM 服务，开发人员可以为他们的 AI/ML 工作负载提供利用底层 GPU 硬件资源的 VM(如上所述)。
*   简化 vSphere with Tanzu 的设置:“通过更少的步骤和输入，更快、更轻松地设置网络，从而缩短价值实现时间，”D'Paiva 说。

扩展方面的改进包括提高 vSphere 中持久性内存系统的弹性和监控能力。德派瓦说，这包括 NVMe/TCP 对“一种快速、简单且经济高效的方式来充分利用现有存储投资”的支持。VMware 与戴尔技术部门合作，为这一功能提供支持。

德派瓦说，简化的操作包括从 vSphere Client 中“更轻松地设置”NSX 安全性，以及[分布式资源调度器(DRS)](https://www.vmware.com/products/vsphere/drs-dpm.html) 配置增强，以帮助“尽可能避免移动(从而中断)更大或更关键的工作负载”。

D'Paiva 表示，vSAN 7 Update 3 旨在提高 VMware 基础架构解决方案的可用性、安全性和灵活性，并帮助运营团队“使用新工具快速轻松地”对其 vSAN 环境进行故障排除。德派瓦传达的新功能包括:

*   增强云原生应用程序的可用性，通过额外的“容错级别”提高边缘的弹性，以保持数据在边缘和扩展集群中可用。"
*   简化的故障排除和补救，包括新的“运行状况检查”，以提供新的指标来提高连接 vSAN 主机的交换机结构的可见性，从而帮助“确保整个集群中更高级别的一致性”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>