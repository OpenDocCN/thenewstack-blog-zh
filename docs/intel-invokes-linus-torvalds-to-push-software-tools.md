# 英特尔调用 Linus Torvalds 推出软件工具

> 原文：<https://thenewstack.io/intel-invokes-linus-torvalds-to-push-software-tools/>

Linux 传奇人物莱纳斯·托沃兹在英特尔首席执行官 T2·帕特·基尔辛格的主题演讲中明显不自在的出现成为本周该公司在 T4 举行的创新大会的头条新闻。

在与格尔辛格的一次谈话中，托瓦尔兹回忆起 1991 年使用一台带有 386 芯片的个人电脑创建了一个最终成为 Linux 的操作系统。这次谈话达到了预期的效果——它表明在 1991 年 x86 上的软件开发很重要，现在仍然如此。

## 致力于开放

“我们谈到了我们对开放的承诺——系统、软件和硬件标准。当我们实现开放、选择和信任时，我们作为一个行业的集体潜力就会得到释放，”Gelsinger 在介绍 Torvalds 之前说道。

托瓦尔兹回忆说，他将 Linux 写入 386 CPUs，这是当时 PC 中的主要芯片。今天的机器变得更加多样化和复杂，CPU 将人工智能和分析等应用程序卸载到 GPU、[FPGA](https://thenewstack.io/developers-fpgas-cloud/)和 ASICs 等擅长此类任务的加速器。

在为期两天的展会上，Gelsinger 和英特尔高管反复推动“开放式加速计算”的概念，即软件开发人员可以消除向特定芯片或硬件写入数据的想法。

该公司宣布了其 [oneAPI](https://thenewstack.io/intel-pushes-cross-architecture-support-in-oneapi-toolkits/) 编程工具包的 2023 版本，通过在 CPU、GPU 和其他加速器之间自动执行代码，确保编码人员不必担心硬件。

“我们有一种单一的通用编程语言，可以编写一次，在任何地方运行。这是一个非常关键的概念。英特尔首席技术官格雷格·拉文德在第二天的主题演讲中说:“这从根本上说是 Java 带来的突破性变化。

今年早些时候，英特尔[收购了 Codeplay Software](https://thenewstack.io/intel-grabs-codeplay-as-it-repositions-for-a-diverse-chip-future/) ,因为它重新定位于不仅仅是 CPU 的多样化芯片未来。Codeplay 主要以其围绕 SYCL 并行编程模型的工作而闻名，该模型包括工具、运行时和执行模型，因此标准 C++代码可以适用于跨 CPU、GPU 和其他处理器的并发执行。

oneAPI 编译器取 SYCL 源代码，只是 C++，为属于 Intel 等硬件公司的 GPU、CPU、FPGAs 生成代码。英特尔的方法与英伟达采用的闭源方法不同，英伟达的 [CUDA](https://thenewstack.io/cuda-12-harnesses-a-nvidias-speedier-gpu-architecture/) 专有编程框架将开发人员锁定在该公司的 GPU 上。

## OneAPI 2023

oneAPI 的 2023 版本拥有 42 种不同的工具，并支持第四代可扩展至强芯片家族，其代号为 [Sapphire Rapids](https://www.intel.com/content/www/us/en/newsroom/opinion/updates-next-gen-data-center-platform-sapphire-rapids.html#gs.dfz8g3) 。英特尔预计将在明年年初推出蓝宝石 Rapids 芯片，此前由于芯片验证方面的障碍而推迟。

oneAPI 工具可以将 CUDA 源代码自动迁移到 SYCL C++语言中。“我们称之为 SYCLomatic。就像洗衣机，把它从专有洗到开放，”拉文德说。

英特尔还开放了 oneAPI 的治理，贡献者现在可以参与该规范的决策过程。在编码和控制他们自己的环境方面，开放治理应该给开发者更多的效率。

“到目前为止，在 oneAPI 的初期阶段，我们一直是由社区驱动的，并且在社区拉动请求和支持方面有很好的记录。但最终，我们是规范管理机构的作者。英特尔软件产品&生态系统副总裁&总经理乔·柯利[在接受新堆栈采访时表示:“通过转向开放治理，所有获得地位的贡献者都有能力投票表决变更并决定规范。](https://www.linkedin.com/in/joe-curley-12965a2/)

oneAPI 规范有多个组件，包括 Khronos 驱动的 SYCL 语言、标准化的库绑定和开发人员编写代码的工具。

## 英特尔开发人员云

英特尔还宣布了[英特尔开发者云](https://www.intel.com/content/www/us/en/developer/tools/devcloud/services.html)，它将提供对尚未发布的英特尔芯片的基于云的访问，包括 Sapphire Rapids 和 Gaudi 2 AI 芯片。我们的目标是为开发者提供一个编写代码的平台，这样当芯片开始批量出货时，软件就已经准备好了。

开发人员云将提供对 oneAPI 和 SYCL 层最新版本的访问，因此开发人员可以在异构环境中部署标准 C++应用程序。另一个目标是帮助开发人员编写云原生应用程序，最终可以部署到谷歌云、AWS 或微软 Azure，例如使用英特尔即将推出的芯片。

SYCL 正在成为英特尔代工战略的一个重要组成部分，该战略涉及为客户制造芯片，在一个紧凑的芯片封装中包括 CPU、GPU 和其他加速器。英特尔以前为自己生产 x86 芯片，但在向客户开放工厂后，开始采用 ARM 和 RISC-V 架构。

## 差异化 IP

英特尔希望为客户制造在单个芯片封装中混合 ARM、x86 和 RISC-V 内核的芯片。英特尔寄希望于 SYCL，这样客户就可以编写出不管芯片封装的组成如何都能运行的代码。

英特尔代工服务 RISC-V 支持高级总监 [Gary Martz](https://www.linkedin.com/in/garyamartzjr/) 在一次分组会议上向与会者概述代工服务战略时表示:“核心是差异化的 IP 和软件服务、多指令集架构选择以及顶层的 oneAPI。

并行性在标准 C++中并不是一等公民，尽管改进即将到来。英特尔认为 SYCL 中有许多特性可以提供更高级别的加速计算特性。最终，该公司希望这些特性中的一部分能在未来的标准 C++版本中实现，尽管可能不会很快实现。

“有……一些有趣的提议没有在 [C++ 23](https://en.cppreference.com/w/cpp/23) 上实施。26 很可能是拦截，我们认为作为一个行业，我们有很多工作要做，”英特尔的柯利告诉新的堆栈。

OneAPI 与包括 Python、OpenMP 和 Fortran 在内的语言和编程模型兼容。

## 其他新项目

英特尔还宣布了 Getti，这是一个计算机视觉人工智能软件包，供开发人员快速开发人工智能模型。英国皇家布朗普顿医院(Royal Brompton Hospital)是早期接入合作伙伴之一，旨在帮助在没有任何人工智能专业知识的情况下识别罕见的呼吸系统疾病。该团队可以快速分析医学图像，这有助于对患有严重呼吸系统疾病(如囊性纤维化)的患者进行诊断和治疗。

该芯片制造商还宣布了[项目琥珀](https://www.intel.com/content/www/us/en/newsroom/news/vision-2022-project-amber-security.html#gs.dg1sib)的新功能，这是一种保密的计算服务，可以确保数据在设备之间移动时的可信度。

证明服务在数据离开源计算设备时生成代码，该代码需要由目标设备来匹配。如果代码匹配，目标设备会将数据放入一个可以执行任务的安全区域。如果代码不匹配，数据就不会进入。

英特尔首席技术官办公室负责系统架构和工程的副总裁兼总经理 Anil Rao 表示,【Amber 项目消除了人们对数据在分布式云中沿途各点执行的担忧。

这对于人工智能和机器学习来说尤为重要，这些数据来自多个来源，包括传感器，在让其进入学习模型之前，需要验证其真实性。

琥珀项目的一个新功能是 TDX 指令，它创建了一个编码的安全虚拟机层。TDX 指令包含在即将推出的蓝宝石芯片中。Rao 说，当进入或退出虚拟机中的应用程序时，TDX 会将虚拟机管理程序从信任边界中移除。

证明服务已经采用了 SGX，它已经在英特尔芯片中，以在内存中创建一个安全的执行层。Amber 项目将支持混合云环境和多个云服务提供商的证明。

“当你进入不同种类的云时，你不需要像一个企业那样有不同的认证机制，”饶说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>