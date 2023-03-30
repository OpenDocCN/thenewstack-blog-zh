# Linux 内核 5.8 将是小补丁的大发布

> 原文：<https://thenewstack.io/linux-kernel-5-8-will-be-a-big-release-of-small-patches/>

Linux 内核的创造者和维护者 Linus Torvalds 对即将发布的 5.8 内核的[声称](https://lore.kernel.org/lkml/CAHk-=whfuea587g8rh2DeLFFGYxiVuh-bzq22osJwz3q4SOfmA@mail.gmail.com/)“它与 v4.9 不相上下，这是我们长期以来提交数量最多的最大版本。”

围绕 5.8 的讨论是显而易见的，因为它是一个非常全面的版本。这个组合中没有一个改变游戏规则的特性:根据托沃兹的说法，5.8 的开发“无处不在”。本周发布了内核的第一个候选版本，完整的版本应该会在接下来的几个月内准备好。

可能 5.8 内核上最值得注意的工作是已经完成的大量基本清理工作。在 5.8 合并窗口中，内核源代码库中的所有文件修改了 20%。这是一个相当大的百分比。内核中有一个显著变化的部分是 [IOCTL Write](https://www.tldp.org/LDP/lkmpg/2.4/html/x856.html) (IOW)。对于这个特性，有超过 14，000 个非合并提交，大约 800，000 个新行，超过 14，000 个文件被更改。

但是这个新的 Linux 内核的特性、变化和改进呢？这里有一个你可以期待的例子。

## CPU 和虚拟化

在 5.8 内核中，已经为处理器做了大量的工作。新功能和改进包括:

*   微软 Hyper-V 虚拟化平台的更新。
*   对直接呈现管理器(DRM)子系统的改进(如 mdp5 kms 分配失败时的 mdp5 init 错误路径)。
*   IBM Power PC 的修复和改进。
*   众多 x86 CPU 更新。
*   增加了互连提供商 DT 节点和热区，为 ARM 芯片提供节流支持。
*   用于 ARM 芯片的 PMIC VBUS 升压器的 DTS 节点。
*   ARM KVM 引入抢断时间上限。
*   引入了在 ARM KVM 的 time_get_snapshot 中识别时钟源的机制。
*   为 ARM KVM ptp 增加了 hypercall 服务。
*   增加了支持硬件 DBM 的基本功能。
*   支持 KVM 的嵌套 AMD 实时迁移。
*   龙芯 3 CPU 现在支持 KVM。
*   幽灵缓解修复。
*   CPPC/CPUFreq 驱动程序增强支持。
*   PCIe NTB 冰湖至强服务器。
*   增加对 RISC-V 的 kexec/kdump 支持。
*   RISC-V defconfig，Kconfig:启用 CPU 电源管理。
*   增加了为 RISC-V 提供自定义 IPI 操作的机制

## 文件系统

文件系统最大的增加来自三星和微软的 exFAT 驱动程序。除了常见的错误修复和代码清理，exFAT 条目缓存功能已经过优化，并添加了一个新功能，即引导区域验证(一种对引导扇区进行校验和检查的方法)。其他 exFAT 变更包括:

*   散点图邻接检查的改进。
*   修复了 exynos_ufs_init()中的返回值检查。
*   修复了 hw_random 中的引用计数泄漏
*   增加了对 UFS HCI 的支持。
*   修复了 mic_pre_enable 中的 ref 计数泄漏
*   简化的 exfat_utf8_d_has 和 exfat_utf8_d_cmp()。
*   优化的 exfat 条目缓存功能。

除了 exFAT 改进之外，其他文件系统变化包括:

*   增加了对 fscrypt 的内嵌加密支持。
*   添加了修复，以避免在 EXT2 无效的内存访问。
*   向 e2fsck 添加了许多修复(例如并行 fsck 到 e2fsck pass1 的引入以及 e2fsck 上下文合并代码的简化)。
*   修正了在 EXT4 中从磁盘读取旧元数据时的不一致性。
*   修复并记录了 e2fsprogs 中的 stable_inodes 功能。
*   修复了 ext4_mb_new_blocks 中可抢占代码中 smp_processor_id()的一个 bug。
*   SMB3 Xen 9pf 的性能优化(大型 I/O)。
*   添加了 EXT4+XFS DAX 支持(用于永久内存存储上的直接访问)。
*   v5.8-rc1 中 gfs2 预读回归的 Btrfs 修复。
*   添加了用于调试 btrfs 的 sysfs 接口。
*   Btrfs 变通办法耗尽了匿名块设备池。
*   检测并修复了 qgroup 泄漏数据为 btrfs 保留的空间。

## 杂项添加

还有许多其他的、杂项的补充，包括:

*   哈瓦那实验室高迪支持。
*   增加了对非 x86 系统上的 thunderbolt 接口的支持。
*   添加了对 DragonBoard 845c 的内嵌加密支持。
*   增加了对 fscrypt 的内嵌加密支持。
*   增加了对 UFS 的内嵌加密支持。
*   返工 test-klp-{callbacks，shadow_vars}以进行实时修补。
*   增加了 AMD 安全加密虚拟化加密状态(SEV-ES)支持。
*   内核并发杀毒软件已经与 KCSAN 合并。
*   大量调度程序优化(例如每条目负载跟踪增强和 CFS 带宽处理修复)。
*   为 SELinux 引入了 CAP_CHECKPOINT_RESTORE。
*   修复了 SELinux 的初始 SID 处理。

这只是为 5.8 版本改进 Linux 内核的工作的一部分。关于这个版本的更多信息，请阅读关于即将发布的内核的 Linux Torvalds 官方声明。

Linux 基金会是新堆栈的赞助商。

特征图像由[杆长](https://unsplash.com/@rodlong?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)放在 [Unsplash](https://unsplash.com/s/photos/big-penguin%5C?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上。

*目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特[或脸书](https://twitter.com/thenewstack)[访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈:](https://www.facebook.com/thenewstack/)[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>