# 嵌入式 Linux 系统的引导加载程序

> 原文：<https://thenewstack.io/bootloaders-for-embedded-linux-systems/>

这是将 Linux 用于嵌入式系统系列文章的一部分。要获得本系列的其他文章列表，请查看

[the introductory post](https://thenewstack.io/an-introduction-to-using-linux-in-embedded-systems/)

.

Linux 基金会赞助了这篇文章。

 [约翰·博尼西奥

John 是 Linux 基金会的 Linux 讲师。](https://www.linkedin.com/in/johnbonesio/) 

嵌入式 Linux 系统几乎总是包含一个引导装载程序。从技术上来说，它不是 Linux 的一部分，但是 bootloaders 是嵌入式 Linux 体验的一个重要部分。

虽然从技术上讲，让嵌入式系统在复位后立即开始运行 Linux 内核是可能的，但这通常是不可行的。嵌入式系统通常将执行初始启动代码和加电自检(POST)的职责从操作系统中分离出来，并放入单独的引导加载程序中。

当嵌入式系统通电时，CPU 运行初始代码——这是一个引导加载程序。引导加载程序将初始化必要的硬件，然后找到下一个要运行的程序，将该程序加载到内存中，并跳转到该程序中执行它。此时，bootloader 代码将不会再次运行，因此它将从内存中被丢弃。

下一个要运行的程序可以是任何东西。让引导加载程序加载下一个引导加载程序并不少见，下一个引导加载程序又会加载另一个引导加载程序。最终，为了使系统有用，它最终加载操作系统代码——在本例中是 Linux 内核。一个简单的系统会在 CPU 复位后运行 bootloader，然后加载运行操作系统。

拥有一个独立的引导装载程序，而不是直接运行内核，提供了灵活性；现在内核可以驻留在不同的位置，由引导装载程序找到并装载。这使得从嵌入式系统的早期开发到生产都可以使用相同的引导程序，只需在引导程序中存储不同的配置。比如早期开发，嵌入式平台可以完全从网络引导；而在以后的开发中，它可以从 SD 卡启动，生产系统可以从 NAND 闪存启动。

基于硬件配置，参数也可以传递给内核，我们现在可以在基于相同平台的不同嵌入式硬件系统上运行相同的内核二进制文件。

## **U 型靴**

嵌入式 Linux 系统最常见的引导程序是 [U-Boot](https://www.denx.de/wiki/U-Boot) 。U-Boot 正式命名为 Das U-Boot，但大家只是叫它 U-Boot。它支持许多 CPU 架构，包括 68k、ARM、MicroBlaze、MIPS、Nios、SuperH、PPC、RISC-V、x86 等。它还包含支持许多现有嵌入式开发板的代码。

U-Boot 是一个开源的引导加载程序。对于您的定制嵌入式系统，可以修改 U-Boot 代码来支持您的特定硬件。

U-Boot 也有很多驱动，这意味着它可以从许多不同的位置找到内核。U-Boot 有 FTP、NAND flash、MMC、i2c 等驱动。它还包含 FAT、ext2/3/4、Cramfs、Squashfs、JFFS2、UBIF、ZFS、btrfs 等的文件系统驱动程序。这意味着内核二进制文件可以驻留在许多位置中的一个位置——包括介质上的这些文件系统中的一个——并且 U-Boot 会找到它。

U-Boot 的引导配置以环境变量的形式存储。U-Boot 通常将这些环境变量存储在闪存中，它们的值可以在重新启动后保持不变。当 U-Boot 运行时，它会查找名为“bootcmd”的环境变量。然后 U-Boot 扩展这个变量并运行其中的任何命令。

U-Boot 包含一个具有类似 Unix 语法的命令行。在这个命令行环境中，您可以修改环境变量并将新值存储在闪存中，以便在后续引导中使用。

在实践中，可以在早期开发中使用 U-Boot；例如，配置为使用 NFS 作为根文件系统，通过 TFTP 引导内核。当你接近发布的时候，你可以用 ext4 把它改成通过 MMC 从 SD 卡引导。随着生产的临近，您可以使用 UBIFS 将 U-Boot 更改为从主板内部的 NAND 闪存启动。

U-Boot 的另一个重要特性是支持设备树。设备树是一种向内核描述硬件的新方法。嵌入式系统很少有运行时可发现的硬件。内核不能只查询硬件来找出可用的。必须告诉内核存在什么设备。内核可以读取描述硬件的设备树并加载适当的驱动程序，而不是硬件信息被硬编码。这允许相同的内核二进制文件在基于相同架构的不同主板上运行。

正如您所看到的，U-Boot 对设备和文件系统的巨大支持，加上它的灵活性，是嵌入式系统的一个简单选择。要获得更多关于 U-Boot 的信息，你可以去该项目的网站:[https://www.denx.de/wiki/U-Boot](https://www.denx.de/wiki/U-Boot)

## **其他盗号者**

虽然 U-Boot 很常见，但是嵌入式系统也可以使用其他引导加载程序。虽然信息太多，无法涵盖所有可能的情况，但我会提到一些其他常见的开源 bootloaders。

[Barebox](https://www.barebox.org/) 是 U-Boot 的衍生产品。它有很多和 U-Boot 一样的灵活性，但是努力变得更像 Linux。它使用了一个类似于 Linux 内核的驱动架构，并使用了一个内部文件系统，包括/dev 中的设备节点。

[RedBoot](https://sourceware.org/redboot) 是来自红帽的引导加载器。它在内部使用 eCos RTOS 技术，并通过串行电缆或以太网为调试应用程序提供支持。

这些是嵌入式 Linux 系统上引导加载程序的一些常见选项。虽然它们在技术上是 Linux 本身的一部分，但不得不构建和配置引导装载程序的情况并不少见。这至少应该对嵌入式引导加载程序的世界有所介绍。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>