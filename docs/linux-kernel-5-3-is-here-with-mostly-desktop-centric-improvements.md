# Linux 内核 5.3 主要是以桌面为中心的改进

> 原文：<https://thenewstack.io/linux-kernel-5-3-is-here-with-mostly-desktop-centric-improvements/>

Linux 内核 5.3 已经到来，这是一个混合的变化包，其中大部分将有利于桌面用户。当然，有一些改进和特性可能最终为云和大规模系统带来一些重要的步骤，但 5.3 应该主要被视为桌面世界的一个进步。

让我们来看看一些可能有利于企业服务器的改进。

## IPv4

将惠及企业(尤其是那些大规模部署云和容器的企业)的一个最重要的改进是增加了对 1600 万个新 IPv4 地址的支持。这是由于一个补丁允许 0.0.0.0/8 作为有效的 IP 地址范围。直到内核 5.3，0.0.0.0/8 范围被禁止有两个原因。第一个问题是与 BSD 4.2 的互操作性。这个问题在 BSD 4.3 中很快得到了解决，所以这个问题从 1986 年就不存在了。第二个问题是 0。X.Y.Z 地址最初被定义为 ICMP 数据报中的源地址。在 [RFC 0792](https://tools.ietf.org/pdf/rfc0792.pdf) 的第 19 页上，该问题被定义为:“该消息可能在 IP 报头 source 和目的地地址字段中的源网络为零的情况下发送(这意味着“该”网络)。回复 IP 模块应该发送带有完全指定的地址的回复。此消息是主机找出其所在网络号码的一种方式。”

这是对 Linux 内核的重要补充，因为 IPv4 仍在广泛使用。甚至服务站点仍然大量使用 IPv4 寻址(特别是考虑到大多数客户端节点还没有实现 IPv6 地址)。然而，应该注意的是，这些地址先前由于模糊/过时的原因而被保留。在 5.3 版本中，地址空间已经变得普遍可用。

## RISC-V 和 x86 赵信

除了额外的 IPv4 地址，任何在云中工作的人都可能感兴趣的功能将是对 [RISC-V](https://riscv.org/) 和新的 x86 赵信处理器支持的改进。根据 [Nextcloud](https://nextcloud.com/) 的联合创始人 Jos Poortvliet 的说法，“我个人认为 RISC-V 和新的 x86 赵信处理器支持的改进很有趣——英特尔/X86 统治着云，但也有其他人的空间！”

考虑到过去几年困扰英特尔处理器的问题，这一点尤其正确。随着云笼罩在这个星球上最大的 CPU 供应商的头上，如果其他硬件能够找到进入云和容器计算领域的方法，那就太好了。RISC-V 可能是硬件。在内核 5.3 中，RISC-V 现在具有:

*   巨大的页面。
*   图像头支持(基于 ARM64 内核图像头)。
*   初始页表现在分为两个阶段。
*   **CONFIG_SCO** 支持。
*   高分辨率计时器和动态刻度。
*   避免在 RAM start 和内核 **setup_bootmem()** 之间预留内存。
*   移除了长期废弃的门区域存根。

至于赵信处理器支持，这是一个由威盛和上海市政府合资创建的中国处理器。该技术基于 VIA 的 Isaiah 设计，并利用了 VIA 的 x86 许可证。

### 文件系统改进

在文件系统领域有一些改进，*可能会对企业级用户感兴趣。其中一项改进可能会影响各种规模的企业。这种变化表现为对 EXT4 更快的不区分大小写的查找。这个特性最初是在内核 5.2 中引入的，但是现在由于临时缓存，性能显著提高，查找速度提高了大约 30%。对于任何依赖于 Samba 等技术的企业来说，kernel 5.3 应该会给这个特定的子系统带来速度上的显著提升。*

### 物联网得到提升

对于那些在物联网领域工作的人来说，有一些新的闪亮的东西正在向你走来，其形式是对 [ACRN 小内存虚拟机管理程序](https://projectacrn.org/)(也称为“大小虚拟机管理程序”)。这款占地面积小的参考虚拟机管理程序旨在用于嵌入式开发，包括实时功能和对多个客户操作系统的支持。

### 其他变化

还有许多更小的变化，所有这些加起来就是一系列令人印象深刻的改进。该清单包括:

*   允许 NFS 客户端使用新的 **nconnect=X** mount 选项建立到服务器的多个 TCP 连接。
*   [利用夹紧](https://lwn.net/Articles/791682/)(用于不对称型芯)。
*   支持 [AMD NAVI](https://www.techradar.com/news/amd-navi) 显卡。
*   原生 [F2FS](https://wiki.archlinux.org/index.php/F2FS) 交换文件支持。
*   [EROFS](https://www.usenix.org/conference/atc19/presentation/gao) 的 LZ4 就地减压。
*   在 [UBI 文件系统](http://www.linux-mtd.infradead.org/doc/ubifs.html) (UBIFS)中支持 Zstd 文件系统压缩。
*   英特尔 [UMWAIT](https://www.felixcloutier.com/x86/umwait) 支持。
*   Broadcom 片上系统的 Raspberry Pi CPUFreq 驱动程序。
*   英特尔速度选择支持。
*   支持[英伟达基于图灵的 TU116](https://www.techpowerup.com/gpu-specs/nvidia-tu116.g902) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>