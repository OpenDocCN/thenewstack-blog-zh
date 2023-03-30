# OpenStack 如何为 AI/ML 工作负载提供可扩展、可重用的基础设施

> 原文：<https://thenewstack.io/how-openstack-provides-scalable-reusable-infrastructure-for-ai-ml-workloads/>

[红帽](https://www.openshift.com/)赞助本帖，新栈独立撰写。

根据 OpenStack Foundation 的定义，“基础设施”是指“在整个数据中心访问的计算、存储和网络资源”。通过虚拟化，我们抽象出了这些不同的组件，以支持基础架构即服务(IaaS)和基础架构即代码，这两者都使服务器供应和管理等任务自动化成为可能，这使我们想到了可扩展和可重用的[人工智能/机器学习(AI/ML)](https://thenewstack.io/category/machine-learning/) 工作负载基础架构。AI/ML 非常流行，在这方面很特别，因为它通常需要特殊的硬件来处理特定的工作负载，而不是其他工作负载。

例如，推理是训练模型的行为，这一任务很像为考试而学习。像视觉对象识别这样的任务的推理可能需要比以后实际识别这些对象所需的更多的特定类型的处理能力。为此，图形处理单元(GPU)可以让这些工作负载持续存在。唯一的问题是，我们又一次遇到了这样一种情况:我们希望尽可能高效地使用相对稀有、昂贵且耗电的硬件。因此，虚拟化通过隔离工作负载并将这些专用处理器分配到虚拟 GPU(vgpu)中，再次挽救了局面。

### 通过虚拟化抽象基础架构

虚拟化允许我们划分硬件资源，从运行在其上的软件系统中抽象出物理资源。在今年早些时候的[开放基础设施峰会](https://www.openstack.org/summit/denver-2019/)上，人们可以指出许多主题——边缘计算、裸机、混合和多云、基础设施即服务和 5G 网络——是会议的核心，而每个主题的核心都是虚拟化。如今，虚拟化被用于[众多不同的领域](https://www.kelsercorp.com/blog/the-7-types-of-virtualization)，例如，让用户能够[在他们自己的](https://www.digitaltrends.com/computing/best-virtual-machines/)内模拟不同的操作系统，或者在没有网络硬件的情况下提供网络功能。随着过去十年向云计算的稳步发展，我们看到虚拟化的方法和目的不断扩展，通常是为了抽象堆栈层以实现自动化。

[open stack Foundation](https://www.openstack.org/summit/berlin-2018/summit-schedule/speakers/3660)的首席运营官 Mark Collier 将最近支持人工智能/人工智能工作负载的努力与云的早期进行了比较，当时的态度是超越专用硬件，转而进行虚拟化和水平扩展。然而，现在发生了另一轮硬件专业化，GPU 已经成为硬件的最低公分母，然后根据需要进行虚拟化、共享和再利用。

“我们在过去几年中看到的情况就像云的早期一样，当时每个人都说这将是最低的公分母-我们将拥有最便宜的 CPU、硬盘内存，它只会水平扩展，这将是硬件专业化的终结，”Collier 说。“最近几年，我们看到了不同硬件(如 GPU)价值的回归。作为云结构的一部分，您可以从数据中心中获得很多好处，这意味着 OpenStack 已经发展到可以实现这些功能。vGPU 是最近几个版本中包含在 Nova 中的东西，它更像是一种复杂的以云为中心的方式，在虚拟机内部公开底层 GPU 硬件。我们肯定会看到这种趋势，即在云中支持不同的硬件架构。”

同样，OpenStack 还支持现场可编程门阵列(FPGAs)，即设计为由用户在制造后配置的芯片，作为通用云资源提供，Collier 指出这是虚拟化硬件协助现代 AI/ML 工作负载的另一种方式。

“这个想法是，在处理器出厂后，你可以很好地更新和改变处理器的功能，这不是普通处理器的工作方式。在芯片上定制和创建独特功能的能力非常有趣，这些功能在芯片设计者构建时并不存在。有一些特定的工作负载真正有助于 FPGAs 的性能特征，特别是在推理的机器学习领域，这是训练过程的前端，”Collier 说。“当你训练时，你会收集大量数据。例如，在自动驾驶汽车中，它从所有的摄像头和传感器收集数据。它不断地试图把它变成数学，相对简单的数学，但是你想重复数百万或数十亿次的数学。这是一种在 FPGAs 上比在 GPU 或 CPU 上执行效率更高的东西。”

[Red Hat 的 OpenStack 产品专家 Erwan Gallen](https://erwan.com/en/) 在开放基础设施峰会期间发表了一篇关于[如何使用 OpenStack](https://www.openstack.org/summit/denver-2019/summit-schedule/events/23694/face-recognition-within-5-minutes-with-openstack) 快速实现面部识别的演讲，探讨了使用 vGPUs 和其他硬件加速的历史、当前使用情况和潜力，以及不同的机器学习算法和架构，可以在下面完整查看。

[https://www.youtube.com/embed/KSE4BzP6y6k?feature=oembed](https://www.youtube.com/embed/KSE4BzP6y6k?feature=oembed)

视频

在演示过程中的某一点上，使用 CPU 和 vgpu 之间的差异变得很明显，发现 CPU 每秒能够处理 3.3 幅图像，而 GPU 每秒能够处理 158 幅图像。

在给新堆栈的一封电子邮件中，Gallen 写道，vGPUs 目前正在[Red Hat open Stack Platform(RHOSP)14](https://www.redhat.com/en/blog/red-hat-openstack-14-now-generally-available)的技术预览中，但预计将在今年晚些时候在 RHOSP 15 中获得全面支持。通过添加 vgpu 和 GPU 直通，Gallen 还评论说，OpenStack“旨在扩展”，因为它“允许在一个 API 调用中提供数千个部署了特定 AI/ML 工作负载的虚拟机。”特别是，Gallen 指出 vGPUs 是提高效率的一个举措。

“GPU 直通和 vGPU 是可重复使用的资源，您可以获得这些加速器每个团队每月的使用统计数据和配额。vGPU 允许你更多地使用每个 GPU，”Gallen 写道。“一些客户希望使用 vGPU，因为他们只使用了 50%的 GPU 帧缓冲内存。对于一些工作负载，如推理和有限的训练，他们可以提高其投资的使用率。”

### 工作负载隔离及其他

[Red Hat 人工智能卓越中心的高级主管 Daniel Riek](https://www.linkedin.com/in/danielriek/) 花时间解释了虚拟机(VM)不仅仅是为单个硬件提供多个访问点，还提供了安全目的的工作负载隔离等好处。例如，OpenStack Foundation 项目 Kata Containers 就是为此而构建的轻量级虚拟机——虚拟化在多租户环境中提供安全隔离，例如在使用容器和 Kubernetes 等容器编排系统时经常遇到的那些环境。

“当您希望与多个虚拟机安全共享 GPU 时，您需要 VGPUs 当您需要虚拟机对多路复用硬件进行安全隔离时，或者当您希望运行多个操作系统或不同内核时，您需要 VGPUs。出于同样的原因，你需要一个虚拟机，你需要一个 vGPU 来复用 GPU。如果您希望多个用户能够与同一个硬件对话，您不能安全地拥有一个而不拥有另一个。如果你想用 GPU 安全地运行虚拟机，你就需要 vGPUs，”Riek 解释道。“你也可以使用 VGPUs，即使你在裸机上运行容器。你可以用 OpenStack 编排裸机，在上面部署 OpenShift，在上面运行机器学习。如果您想多次访问 GPU，仍然可以从 vgpu 中获益。使用 Openshift，您不需要使用虚拟机来复用硬件，您只需要使用容器来共享它。这是分时度假与虚拟化的对比。”

当然，有一种古老的方法可以解决所有这些问题，随着虚拟化的发展，这种方法已经转向了一个新的方向。对于希望确保充分利用场景中所有可用计算资源的组织来说，裸机通常是最佳选择。最终，IaaS 将基础架构的重新配置自动化，在实现商品化的同时赋予裸机性能优势。与 vGPUs 相结合，如今的组织比以往任何时候都更有能力将基础架构视为可重用的，同时享受虚拟化提供的效率。

OpenStack 基金会是新堆栈的赞助商。

来自 Pixabay 的 simplyelke 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>