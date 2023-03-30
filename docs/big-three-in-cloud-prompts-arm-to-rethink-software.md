# 云计算三巨头促使 ARM 重新思考软件

> 原文：<https://thenewstack.io/big-three-in-cloud-prompts-arm-to-rethink-software/>

英国芯片设计公司 ARM 在过去几年经历了艰难的日子:与 Nvidia 的合并失败，IPO 计划被搁置，因为半导体公司被夹在争夺芯片霸权的国家中间。

尽管遭遇挫折，ARM 公司在智能手机领域空前成功的推动下，仍在艰难前行，并慢慢进入服务器市场。ARM 曾经被认为是服务器的死穴，但随着三大云提供商将 ARM 处理器设计放在云原生环境中，情况发生了变化。

[ARM](https://thenewstack.io/arm-server-chips-get-a-boost-with-amperes-altra/) 现在正试图支撑其软件堆栈，这一弱点阻碍了其在服务器环境中的应用长达十多年。在最近的 [ARM DevSummit](https://devsummit.arm.com/flow/arm/devsummit22/home/page/lp/) 大会上，该公司概述了其未来两年针对云原生、服务器和嵌入式计算环境的软件开发工作。

## 设计方法，开发者体验

ARM 高管主题演讲的核心焦点是不断变化的计算环境中的应用设计方法和开发人员体验。

ARM 将其处理器设计授权给客户，然后客户将其放入物理芯片中。一些著名的被许可方包括苹果、亚马逊、三星、高通和谷歌。

ARM 在移动和边缘设备软件领域占据主导地位。Android 操作系统围绕 ARM，嵌入式应用程序被调整为在采用 ARM 处理器的高能效边缘设备上运行。但是在代码库很大程度上向 x86 架构倾斜的服务器中，情况就不同了。

ARM 现在正在进行一场旅程，该公司高管表示，这是其软件开发方式的一次根本性变革。该公司正在给软件选择硬件的控制权，应用程序应该在硬件上处理。

“作为软件开发人员，我们习惯于从一个问题开始，然后从那里解决其余的问题。但是我们正在颠覆传统的工作方式。软件选择特性，而不是硬件，”ARM 开源软件副总裁 Mark Hambleton 在一次主题演讲中说道。

英特尔(Intel)和英伟达(Nvidia)等芯片公司已经在采用软件定义的方法，这些公司在其芯片的同时提供大量的软件服务。英特尔的 OneAPI 和[英伟达的 CUDA](https://thenewstack.io/cuda-12-harnesses-a-nvidias-speedier-gpu-architecture/) 被调整以利用本土芯片。但 ARM 的软件开发工具不能有偏见，因为它的处理器是由许多公司授权的。

“我们不再定义硬件，然后硬塞进软件，并绕过任何规定的妥协。这反映了 ARM 生态系统中正在发生的彻底转变，”Hambleton 说。

## 开源、现成的

ARM 的软件方法在很大程度上基于开源标准，现成的操作系统提供丰富的中间件和 API，这些中间件和 API 由标准基础固件实现，并为平台内置的外设提供良好的上游支持。

但是开放标准方法有其复杂性——大部分应用程序开发工作都落在客户手中。ARM 现在正通过合作伙伴推出更多工具，让开发者更容易编写云原生代码。

“我们在 ARM 上的[工程](https://www.arm.com/solutions/infrastructure/works-on-arm)项目正在扩展，包括所有主要的云提供商。对于软件开发人员来说，这意味着轻松、开放地访问优秀的基于 ARM 的云服务，他们可以信任这些云服务将运行他们的应用程序，”Hambleton 说。

亚马逊的 AWS 在其名为 [Graviton](https://thenewstack.io/aws-pushes-forward-its-custom-chip-efforts-with-graviton3/) 的基于 ARM 的芯片上提供虚拟机。谷歌、微软和甲骨文正在提供基于 Ampere Computing 基于 ARM 的 Altra 和 Altra Max 处理器的虚拟机，这些处理器具有多达 128 个内核，用于云原生应用。HPE 也在其 ProLiant RL300 Gen11 旗舰服务器中使用 Ampere 的芯片，用于混合云环境。

[Ampere](https://thenewstack.io/arm-server-chips-get-a-boost-with-amperes-altra/) 是 ARM 服务器芯片为数不多的成功案例之一，拥有超过 100 个应用程序的运行列表，这些应用程序在谷歌、微软和甲骨文的虚拟机以及 Equinix 等裸机提供商上得到支持。软件支持列表包括 NGINX web 服务器、Memcached、Apache Cassandra、MySQL 和 [Hadoop](https://thenewstack.io/will-kubernetes-sink-the-hadoop-ship/) 。

Linux 基金会的 CNCF(云本地计算基金会)也与 ARM 合作，将 Kubernetes 系统推向边缘。

Works on Arm 计划支持 100 多个开源项目，包括 AlmaLinux 和 Alpine、KVM 和 Xen Project 等虚拟化工具、MariaDB 等数据库以及 Ruby 和 Python 编程语言。在部署到云中之前，开发人员可以使用这些工具来编写和测试应用程序。

该计划使用 DevOps，这是一种迭代开发管道，依赖于代码的快速改进和部署。基于云的开发工具适用于 ARM 的 Neoverse 平台，该平台专为云原生和高性能应用而设计。

该计划可以启动 ARM 服务器的高端应用开发，这在历史上一直是一个难题。十多年前，ARM 服务器作为英特尔和 AMD x86 芯片的一种可能选择出现，但这种处理器被认为对于传统的数据库、ERP 或其他大型应用程序来说不够强大。

Calxeda 和 AppliedMicro 等公司的早期 ARM 服务器是为运行在内部服务器上的 LAMP (Linux、Apache、MySQL、PHP/Perl/Python)堆栈而设计的。但 ARM 现在已经在云应用程序中找到了一个甜蜜点，其低功耗处理器提供了一种灵活的方式来扩展 web 应用程序，而没有耗电的 x86 处理器的开销。

微软 Azure 在 4 月份推出了其第一款基于 Ampere ARM 的虚拟机，称其提供了“比同类基于 x86 的虚拟机高 50%的性价比”谷歌云今年还首次推出了 ARM 虚拟机，推出了[Tau T2A](https://cloud.google.com/blog/products/compute/tau-t2a-is-first-compute-engine-vm-on-an-Arm-chip)。

## 有效的代码

但像英特尔和 AMD 一样，ARM 希望让编码变得简单，这样开发人员就可以编写不受硬件限制的代码。

“该团队正在寻找进一步抽象复杂性的方法，以确保无缝的开发人员体验。ARM 中央工程执行副总裁 [Gary Campbell](https://www.arm.com/company/leadership) 在一次主题演讲中表示:“这包括跨我们所有 IP 的通用工具链和跨 CPU、GPU 和 NPU 的编程、调试和分析框架。

开发人员可以编写可跨多种硬件环境移植的代码，这将减少为不同环境重写代码所涉及的成本和劳动。

“这对软件开发人员来说是一个巨大的挑战。我们花了太多时间反复做同样的事情，导致成本过高。该设备上运行的大部分软件都是为该设备定制的。这意味着没有机会扩大规模，”汉布尔顿说。

芯片设计师正在与合作伙伴一起进行“扩展”，以满足不同的工作负载。一些合作伙伴的领域包括 5G 系统、机器学习和边缘应用。许多软件开发将针对该公司的 ARMv9 架构，该架构将定义下一代服务器芯片。

“专用处理是新的标准载体，它将使我们超越更快、更好、更便宜的通用计算轨道。这就是为什么它是我们将在未来几年部署的 ARMv9 架构的实质性扩展的滚动计划的核心设计原则，”ARM 的坎贝尔说。

## 原生云，高性能计算

云原生和高性能计算环境通常有图形处理器来加速 AI。Nvidia 正在将其自主开发的基于 ARM 的 Grace 与基于 Hopper 架构的最新 H100 GPU 相匹配。ARM 还在其芯片设计中加入了扩展功能，以加速人工智能和数学应用。

坎贝尔说，云原生处理器的一种扩展称为[可扩展向量扩展](https://developer.arm.com/documentation/101726/0400/Learn-about-the-Scalable-Vector-Extension--SVE-/What-is-the-Scalable-Vector-Extension-#:~:text=Scalable%20Vector%20Extension%20(SVE)%20is,developed%20to%20target%20HPC%20workloads.)，这将“推动云到边缘性能效率的显著提升”。

SVE2 扩展将是未来 Neoverse 芯片的关键扩展。Neoverse 的路线图包括 2023 年和 2024 年用于高性能系统的 V 系列处理器，随后是 2025 年名为 Poseidon 的处理器设计。到 2025 年，N 系列芯片将专注于能效，E 系列芯片将具有快速的数据吞吐量，这对 5G 网络和人工智能应用非常重要。

ARM 还宣布了 [Windows Dev Kit 2023](https://learn.microsoft.com/en-us/windows/arm/dev-kit) 的可用性，也被称为 [Project Volterra](https://blogs.windows.com/windowsdeveloper/2022/10/24/available-today-windows-dev-kit-2023-aka-project-volterra/) ，这是一款用于 Windows 11 的原生 ARM 开发硬件。开发人员大多是手动移植 Windows 11 的 x86 代码，以便应用程序在 ARM 版本的操作系统上运行。

微软已经推出了其 ARM 原生工具链的预览版，包括 Visual Studio 2022 和。Net 7，将在未来几周发布。开发人员可以使用高通基于 ARM 的 CX 芯片为笔记本电脑编写人工智能应用程序，该芯片还包括神经处理器。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>