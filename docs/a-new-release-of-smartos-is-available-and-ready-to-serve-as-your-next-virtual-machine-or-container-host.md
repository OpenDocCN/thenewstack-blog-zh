# 新的 SmartOS:准备好充当下一个虚拟机或容器主机

> 原文：<https://thenewstack.io/a-new-release-of-smartos-is-available-and-ready-to-serve-as-your-next-virtual-machine-or-container-host/>

SmartOS 远不如其他一些为虚拟机和容器构建的 UNIX 或 Linux 类操作系统知名。基于 [illumos](https://www.illumos.org/) (一个 [OpenSolaris](https://archiveos.org/opensolaris/) 的社区分支)，你会发现 SmartOS 中的许多特性使虚拟化和容器化不仅成为可能，而且健壮可靠。

SmartOS 从一开始就被设计为云本机和虚拟使用情形的理想之选。它可以用作:

*   虚拟机管理程序。
*   轻量级容器主机。
*   多租户部署。

SmartOS 支持两种不同类型的虚拟化:

*   操作系统虚拟机(也称为区域)是 SmartOS 的虚拟化实例，其行为类似于孤立的系统。
*   硬件虚拟机，这是一种更传统的运行虚拟机的方法。

这种开源操作系统的特点是在多租户环境中完全容器隔离；生产级网络(每个容器都有自己唯一的 IP 地址)；每容器安全、隔离、可调整大小的文件系统，等等。

SmartOS 的最新版本主要是关于错误修复，其中包括:

*   ring in clear_locks 修正为 release-20230209。
*   过分热衷于清理。
*   信号中的 pollhead 寿命太短。
*   pcieadm 将 PCIE_AER_CTL 错误地表示为 PCIE_AER_RE_CMD。
*   与 AER 共享 pcieb HP/LBW 中断会导致虚假报告。
*   MAC 应该更容易支持双个性设备。
*   在 in.routed/if.c.修复功能原型

完整的变更日志可以在这里找到。由于 SmartOS 基于 illumos，您还会在 SmartOS 中发现以下新功能:

*   支持快速 FC-641E 和 FC-642E。
*   目标模式执行节流。
*   G6 适配器的专用仲裁环路支持。
*   对启动器模式的序列级错误恢复支持。

完整的 illumos 变更日志可以在[这里](https://www.atto.com/software/files/notes/PRN_illumos_16Gb32Gb64Gb_v1.07_Rev01_31_23.pdf)找到。

SmartOS 中的一些功能包括 Crossbow(提供网络虚拟化)、 [DTrace](https://thenewstack.io/long-last-linux-gets-dynamic-tracing/) (用于解决内核和应用程序问题的动态跟踪框架)、 [bhyve](https://thenewstack.io/tidalscale-creates-single-ocean-dram-large-scale-applications/) (第二类管理程序)、 [KVM](https://thenewstack.io/kata-containers-secure-lightweight-virtual-machines-container-environments/) (内核的虚拟化模块)、 [ZFS](https://thenewstack.io/linux-creator-linus-torvalds-disavows-the-zfs-filesystem/) (具有卷管理的文件系统)和 Zones(x86 和 SPARC 系统的操作系统级虚拟化实现)。

将 SmartOs 视为轻量级容器操作系统和虚拟机管理程序的组合，并考虑到容器和云原生安全性进行了优化。使用该操作系统，您可以:

*   托管私有云。
*   托管硬件云。
*   内部私有云。
*   Node.js。
*   计算。
*   存储。

## 将 SmartOS 部署为虚拟机

将 SmartOS 部署为虚拟机不像使用 Linux 发行版那么简单。例如，为了在 VirtualBox 中成功部署 SmartOS，您必须执行以下操作:

*   将操作系统类型设置为“Solaris 11 64 位”
*   配置至少 2GB 的内存。
*   禁用音频。
*   在系统>处理器中启用 PAE/NX。
*   将网络适配器配置为“英特尔 PRO/100 MT 台式机”

除非您设置了上述选项，否则您将无法引导虚拟机进行安装。

就 [VMware](https://tanzu.vmware.com?utm_content=inline-mention) 而言，你需要下载[VWware tar.gz 文件](https://us-central.manta.mnx.io/Joyent_Dev/public/SmartOS/20230214T155114Z/smartos-20230214T155114Z.vmwarevm.tar.gz)。

## 如何使用 SmartOS 2023

SmartOS 适用于大型数据中心，但也可以像单独的服务器一样工作。SmartOS 不包括 GUI，并且确实有相当长的学习曲线。一旦您熟悉了这个操作系统，您可能会发现它是市场上最好的容器虚拟化解决方案之一。

鉴于每个容器区域或虚拟机都存在于一个独立的文件系统上，它提供了其他操作系统难以企及的安全性。由于它使用 ZFS 文件系统，容器区域和虚拟机可以拍摄快照、回滚，甚至发送到远程主机。

请记住，如果您是从 Linux 进入 SmartOS，或者您习惯于使用像 [Docker](https://thenewstack.io/docker-defends-desktop-pricing-says-support-led-to-faster-features/) 这样的容器，那么您将面临一个巨大的变化。对于任何希望测试或采用 SmartOS 的人，我强烈建议你[在开始之前通读 SmartOS 文档](https://www.tritondatacenter.com/documentation)，因为你工作流程的每个方面都会随着这个操作系统而改变。然而，考虑到它提供的更高的安全性，学习曲线是非常值得的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>