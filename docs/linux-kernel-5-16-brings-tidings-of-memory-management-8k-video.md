# Linux 内核 5.16 带来了内存管理的福音，8K 视频

> 原文：<https://thenewstack.io/linux-kernel-5-16-brings-tidings-of-memory-management-8k-video/>

![Linux logo](img/cdea7865bb63b657937b28574a847b6e.png)Linux 内核版本 5.16 的发布遭遇了轻微的延迟。说延迟是圣尼克和假日季节。这是相当典型的，因为在 11 月和 12 月期间，Linux 内核的开发确实变慢了。对此，Linux 管理员莱纳斯·托沃兹[写道](https://lore.kernel.org/lkml/CAHk-=wixe1NPqC0PmgUbV0Xoa8D0Pbyu7X_0sfABYMG+ocLdbQ@mail.gmail.com/T/#u):

*随着假期的到来，开发和测试方面的事情可能会放缓，因此，我预计我也会将[release candidate]系列延长一周，不是因为这是必要的(现在说还为时过早，但我并不这么认为)，而是因为没有人想在新的一年里立即打开下一个合并窗口。*

所以，如果你希望圣诞老人会在你的袜子里给你留下一个闪亮的新内核，你会失望地发现这个仓库有点空。

不要担心，新内核将在假期后很快出现。

但是它承诺了什么呢？实话实说，在这个版本中没有节目停止。也就是说，kernel 5.16 不会被忽视。为什么？因为有很多新的硬件支持和特性值得期待。

让我们打开礼物，看看在闪亮的纸下面藏着什么。

## CPU 的变化和增加

关于处理器，真的没有什么值得兴奋的。最大的补充是，英特尔的高级矩阵扩展支持终于稳定。这一新的扩展(针对 x86 芯片组)引入了一种独特的高性能矩阵运算方法，这是一种线性代数运算，常用于展示 GPU 的高性能能力。当然，这一增加应该会对依赖 GPU 技术运行更重负载的云原生开发产生相当大的影响。

虽然与 CPU 没有直接关系，但有一个新的功能叫做 Memory Folios，这是一个新的内存管理系统，它提供了一个更有效和类型安全的方法来指定一组页面的头而不是页面指针、 `compound_head(`和朋友。[据 Oracle 开发人员和长期 Linux 内核贡献者 Matthew Wilcox](https://lkml.org/lkml/2021/10/30/263) 称，Memory Folios 将“允许文件系统和页面缓存以比 PAGE_SIZE 更大的块来管理内存”，Wilcox 补充道，“真正的工作负载(例如构建内核、以稳定状态运行 Postgres 等。)似乎受益 0–10%。”

其他以杯子为中心的补充包括:

*   RISC-V 架构的关键更新将支持开源的新 NVIDIA 驱动程序。
*   第一个补丁是为英特尔的下一代 Raptor Lake CPUs 推出的。
*   支持 Raspberry Pi 计算模块 xxx，无需添加单独的驱动程序即可实现主线内核支持。
*   ARM 架构的重大改进。
*   苹果 M1 PCIe 和 GPIO 驱动程序已经成为主线，这使我们比以往任何时候都更接近 M1 苹果硬件上的 Linux。
*   三星的 ExynosAutov9(用于车辆)首次引入内核。
*   增加了对 Rockchip RK3566 和 RK3688 SoC 板的支持。

## 制图法

添加到内核中的更令人兴奋的新功能之一是添加对下一代 GPU 的支持，该 GPU 最终将采用 DisplayPort 2.0，这是一种支持高分辨率(8k)视频显示的新视频标准。当然，这只是对这项技术的初步支持。同样值得注意的是，镭龙 RX 6000 和英特尔都有这方面的暗示(因为英特尔开发人员已经发布了一些补丁，为他们的驱动程序提供 DisplayPort 2.0)。这意味着 DisplayPort 2.0 有望在明年的某个时候在 Linux 上开花结果。

其他增加/改进包括:

*   对阿尔德湖图形的支持现在稳定了。
*   现在支持面向英特尔 DG1 的 PCI IDs，并增加了面向 DG2 显卡的初始工作(英特尔 DG2/Alchemist 显卡将于 2022 年推出)。
*   已经引入了对 AMD 显卡 USB4 的支持。
*   AMD 黄色鲤鱼和青色技巧鱼的最新更新。
*   视频核心 Next (VCN)优先处理(AMD 的下一代视频解码和编码加速器)。
*   AMD 推出了一种新的识别硬件的方法，从传统的 PCI ID 转移到一种更加基于 IP 表的方法。
*   增加了英特尔的受保护 Xe 路径(PXP)支持。

## 杂项更新/改进

Linux 5.16 内核的其他添加/改进令人兴奋不已，包括以下内容:

*   更好的支持索尼 Playstation 5。
*   改进了对 HP Omen 笔记本电脑的支持。
*   许多华硕主板现在都有通过 HWMON 工作的传感器。
*   苹果魔术键盘 2021 支持。
*   System76 为他们的笔记本电脑添加了补丁，以提高风扇速度、性能和功能键。
*   增加了对联想 ALC897 平台上耳机麦克风的支持。

与往常一样，新内核也有许多修复，涵盖了广泛的问题，如修复总线:`mhi: pci_generic`的设备恢复失败问题，修复`nvmet-tcp`的意外命令失败可能导致的列表损坏，修复 NVMe 内存控制器断开重新连接控制时的释放后使用，避免由于为`selftests: KVM`保留 HyperTransport 区域而导致的故障，修复用于跟踪的`__create_synth_event()`错误路径中可能的内存泄漏， 修复释放 RDMA/mlx5 的 dereg MR 流中未分配的内存，修复 RDMA/irdma 的“`irdma_prm_add_pble_mem()`”中潜在的内存分配问题，等等。

## 结论

按照通常的警告，虽然您很快就可以下载并安装这个新内核，但是对于生产机器来说，最好的办法是推迟，直到您的发行版维护人员在他们的存储库中提供它(这样您就可以确保一切都按预期运行)。最重要的是，如果你自己编译内核，它将不能通过你的发行包管理器进行升级。

关于 Linux 5.16 内核的更多信息，请通读整个[变更日志](https://lore.kernel.org/lkml/CAHk-=wixe1NPqC0PmgUbV0Xoa8D0Pbyu7X_0sfABYMG+ocLdbQ@mail.gmail.com/T/#u)。一旦完整版发布，你就可以从 kernel.org 下载了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>