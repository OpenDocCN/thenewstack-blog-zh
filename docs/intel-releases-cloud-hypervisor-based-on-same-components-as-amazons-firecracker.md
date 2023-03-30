# 英特尔发布基于与亚马逊鞭炮相同组件的云管理程序

> 原文：<https://thenewstack.io/intel-releases-cloud-hypervisor-based-on-same-components-as-amazons-firecracker/>

英特尔今天宣布了一款新的专用于云原生工作负载的 Linux 虚拟机管理程序，该程序基于 Rust virtual machine manager，即[Rust-VMM](https://github.com/rust-vmm)——亚马逊[鞭炮微型虚拟机基于](https://opensource.com/article/19/3/rust-virtual-machine)构建的开源虚拟机管理程序组件集。

在一个名为 Nemu 的项目下，英特尔去年开始从传统的企业虚拟机管理程序 QEMU 中剥离数十万行遗留代码。比如说，这种遗留代码是用来模拟软盘驱动器或键盘的。相反，他们将新的虚拟机管理程序集中在那些在云中有用的组件上，包括安全性、内存安全性、线程安全性和性能。

“我们已经意识到，云软件中使用的许多东西确实需要现代化，”英特尔软件和服务集团副总裁 Imad Sousou sou 说。“我们只是将企业使用的东西重新用于云和边缘，这可能不一定是正确的事情。”

## 现代、安全的虚拟机管理程序

据 Sousou 估计，去掉繁重的面向桌面和服务器的 Linux 仿真组件——大约 80%的原始 QEMU 代码——可以显著减少虚拟机的启动时间。结果是虚拟机表现得更像容器。它们旋转得更快，运行开销更少，但保留了进程隔离，这使它们比容器更安全。

Sousou said 说，当然，不是每个人都需要这样的安全。对于大多数工作负载，容器足够安全。但是，在一些专业行业或企业中，只有虚拟机能够提供满足严格的安全性和合规性要求所需的隔离级别。问题是虚拟机需要太多的时间来加载，并且由于这种为物理计算而设计的传统代码，大规模运行的效率和成本可能会低得多。

通过虚拟化提高容器安全性是英特尔多年来一直致力于解决的问题。到目前为止，他们为使容器更安全所做的努力已经导致了 [Kata 容器](https://thenewstack.io/kata-containers-secure-lightweight-virtual-machines-container-environments/)的产生，它本质上是将容器包装在一个 VM 中以实现进程隔离。Sousou 说，现在他们要回到问题的根源，虚拟机管理程序本身。

rust-vmm 项目是英特尔与其生态系统合作伙伴在许多软件项目上合作的更大努力的一部分，这些软件项目有助于确保他们的基础设施在英特尔硬件上良好运行。

Nemu 为 rust-vmm 奠定了基础，此后它吸引了阿里巴巴、亚马逊、谷歌和红帽的贡献。亚马逊为该项目贡献了部分鞭炮，谷歌贡献了 Chrome 操作系统的 VMM。

“我们所有人都有兴趣拥有一个适合现代使用的安全管理程序，”Sousou said 说。

## Rust-vmm 是虚拟化的 Yocto

rust-vmm 项目是一个组件集合，云提供商可以从中组装自己的专用虚拟机管理程序。例如，亚马逊可以通过自己的开源鞭炮项目使用这些组件在虚拟机中运行 FaaS，分析师[贾纳基兰 VMs 写道](https://thenewstack.io/how-firecracker-is-going-to-set-modern-infrastructure-on-fire/)“这项技术有可能颠覆当前的容器和无服务器技术。”

在这方面，rust-vmm 类似于英特尔针对嵌入式 Linux 的 [Yocto 项目](https://www.yoctoproject.org/)。有了 Yocto，用户可以从对他们最有用的操作系统组件中挑选并丢弃其余的组件，从而创建一个高性能的定制嵌入式 Linux 发行版，而不必每次都从头开始构建。借助 rust-vmm，用户可以从他们需要的虚拟化组件中挑选。其中包括 KVM API 包装器、基于 Virtio 的设备模型和虚拟机内存库等组件。

英特尔正在将这种模块化方法应用于软件堆栈的其他领域的架构和开源项目，包括云、边缘和人工智能工作负载。

英特尔为 BIOS 开发了全新的架构，例如，减少遗留代码，使其更适合云、edge 和 AI。Sousou 说，该项目还将致力于改变操作系统，以接管传统上由 BIOS 处理的功能。“这是一个完整的系统，可以在几毫秒内启动，更加安全，运行虚拟化，并可以更好地进行自我分区。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>