# SUSE 云应用平台将 Kubernetes 与 Cloud Foundry 捆绑在一起

> 原文：<https://thenewstack.io/suse-cloud-application-platform-bundles-kubernetes-with-cloud-foundry/>

企业 Linux 分销商 [SUSE](https://www.suse.com/) 将 Cloud Foundry 平台即服务软件与 Kubernetes 容器编排引擎捆绑在一起，旨在提供一个集成的开源软件包，帮助企业实现云原生架构。

SUSE 高级产品营销经理 [Jennifer Kotzen](https://www.linkedin.com/in/jenniferkotzen/) 表示:“我们希望将云铸造的先进生产力带到以 Kubernetes 为代表的现代基础设施中。“我们正在将这两个平台整合在一起。我们不仅仅是将它们放在一个盒子里，而是将它们整合在一起，让人们能够两全其美。”

Kotzen 说，企业已经对 Kubernetes 和 Cloud Foundry 进行了调查，并发现“没有一家能够满足他们的全部需求”。作为一个 PaaS，Cloud Foundry 虽然好用，但是有局限性。不过，将所有应用程序放到 Kubernetes 上可能需要相当多的专业知识。这个包的想法是提供一个环境，让程序员可以快速开发应用程序，同时 IT 运营可以尽可能保持灵活性。

本周， [Cloud Foundry Foundation](https://www.cloudfoundry.org/) 已经[指定](https://www.suse.com/c/suse-announces-cloud-foundry-certification-suse-cloud-application-platform/)Cloud Foundry 组件作为认证的 Cloud Foundry 发行版，确保工作负载与 PaaS 软件的其他认证版本兼容，目前已有 8 个认证版本。

Kotzen 指出，在这八个认证版本中，有六个是托管服务。在此版本之前，只有 [Pivotal](https://tanzu.vmware.com/) 提供完全支持的商业“纯”版本软件，可以在内部服务器上运行(当然，作为开源软件，可以免费下载，尽管用户必须负责维护和保养)。Kotzen 指出，SUSE 发行版现在在市场上提供了一些选择。

Kotzen 说:“市场上的这一新选择使 Cloud Foundry 更容易被一系列新用户所接受，这些用户的进入壁垒以前是禁止的。”

这也是第一个在容器上分发的 Cloud Foundry 认证版本——Pivotal 使用虚拟机。SUSE 高级产品经理 [Ron Nunan](https://www.linkedin.com/in/ronald-nunan-34924a/) 补充说，这种方法最大限度地减少了 Cloud Foundry 对服务器的占用。这也允许由 Kubernetes 管理 Cloud Foundry 部署，这可以用来更容易地扩展 Cloud Foundry，并为运行时带来更大的稳定性。

这个发行版的另一个好处是，与大多数 Kubernetes 部署不同，它不需要 [Bosh](https://bosh.io/docs/) ，这是一个经常用于设置 Kubernetes 的部署管理工具。她说:“(客户)不需要第二个复杂、学习曲线陡峭、难以管理的大型平台，这是个好消息，”她指的是波什。

Numan 说，对于这个平台，SUSE 本身将持有部署元数据的 Bosh 版本转换为 Kubernetes 编排部署模型，因此 Kubernetes 本身可以执行它们。

为了将 Cloud Foundry 容器化，SUSE 创建了[裂变](https://github.com/SUSE/fissile)，将 Bosh 版本转化为 Docker 图像。IBM 也使用开源的裂变来封装它的 Cloud Foundry 版本，也是在本周发布的。

SUSE 基于 Linux 的面向容器的 MicroOS，提供底层操作系统，而容器则配备了 [Suse Enterprise Linux](https://www.suse.com/products/server/) 。该公司使用自己的 [Kubernetes 发行版](https://www.suse.com/solutions/kubernetes/)来打包。

云铸造工作实际上起源于活跃状态“Stackato”发布。惠普[于 2005 年收购了](https://venturebeat.com/2015/07/28/hp-acquires-activestates-stackato-paas-business/)那家公司，并于 2017 年[将其云软件组件出售给 SUSE](https://www.zdnet.com/article/suse-acquires-hpes-cloud-assets/) 。“当我们接管技术和工程师时，我们使用标准的 Kubernetes 环境重建了控制平面，”Numan 说。

SUSE 于 9 月首次推出 SUSE 云应用平台，作为测试版。此次更新，版本 1.1 包括 Kubernetes 支持和容器化和认证云铸造。该公司在本周于波士顿举行的云铸造峰会上宣布了这一新版本。

[云铸造基金会](https://www.cloudfoundry.org/)和 [Pivotal](https://tanzu.vmware.com/) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>