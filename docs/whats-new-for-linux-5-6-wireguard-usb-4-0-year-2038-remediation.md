# Linux 5.6 的新特性:WireGuard、USB 4.0、2038 年修正

> 原文：<https://thenewstack.io/whats-new-for-linux-5-6-wireguard-usb-4-0-year-2038-remediation/>

Linux 5.6 内核即将推出，可能在 2020 年 4 月发布。即将到来的更新包括一段时间以来最令人兴奋的功能之一，即包含支持 WireGuard 虚拟专用网络(VPN)的软件。此外，更新后的内核还将支持 USB 4.0 版本、闪存友好文件系统(F2FS)数据压缩，以及针对 2038 年错误的保护。

### 虚拟专用网络

在 5.6 内核中， [WireGuard](https://www.wireguard.com/) VPN 将默认加入。为什么这对所有 Linux 管理员如此重要是因为 WireGuard 不仅使建立 VPN 变得非常容易，而且比一般的解决方案更安全。WireGuard 不依赖复杂的(通常不太安全的)VPN 密钥，而是使用最先进的加密技术(如噪音协议框架、Curve25519、ChaCha20、Poly1305、BLAKE2、SipHash24、HKDF 和安全可信连接)。

除了使用更安全的加密之外，WireGuard 的实现只需要很少几行代码。事实上，WireGuard 代码库包含大约 4000 行代码。另一方面，OpenVPN 有大约 100，000 行代码。由于 WireGuard 的工作方式类似于 SSH(交换公钥进行身份验证)，这种新的 VPN 技术的实现将会更加简单。

### USB4 支持

USB4 支持终于进入了 Linux 内核。这一新协议将使最大 USB 总带宽增加一倍，并支持多种同步数据和显示协议。

USB4 规范于 2019 年 9 月发布。一个月后，英特尔的开源部门为 USB4 支持添加了初始补丁。Linux 内核中的 USB4 实现(大约 2000 行代码)基于 Thunderbolt 协议规范，但也将向后兼容 USB 2.0、USB 3.0 和雷电 3。

### F2FS 数据压缩

5.6 内核的另一个重要特性是闪存友好文件系统(F2FS)数据压缩。这种本机无损压缩算法(LZO/LZ4)专注于通过减少磁盘写入和 I/O 拥塞来优化 SSD 和闪存的寿命。

随着这个新的实现而来的是 **compress_algorithm** 挂载选项，用于指定磁盘挂载模式。

### 2038 年发行

又是 [Y2K 重演](https://thenewstack.io/how-the-y2k-bug-returned-on-jan-1-2020/)。Linux 以 32 位有符号整数格式存储时间，最大值为 2147483647。一旦超过这个数字，值将存储为负整数。这意味着，在 32 位系统上，日期不能超过 2038 年 1 月 19 日。

幸运的是，5.6 内核包含了一个修复，所以一旦 2038 年 1 月 20 日太阳升起，32 位系统不会崩溃。

### 其他功能

像往常一样，有许多新的功能和修复可以找到。其中一些功能(不会引起 WireGuard 支持人员的注意)包括:

*   更广泛的无线外设支持。
*   AMD k10temp 驱动程序的改进(用于温度/功率报告)。
*   支持开源的英伟达 RTX 2000“图灵”GPU。
*   FSCRYPT 内嵌加密。
*   对 ARM SoCs 的更广泛支持。
*   Ingenic X1000 SoC 支持。
*   英特尔 MPX 已被完全删除。
*   面向英特尔冰湖架构的更快 memmove()。
*   阿尔法支持 AMD Zen 3。
*   AMD 波洛克支持。
*   EXT4 性能修复。
*   Zonefs 文件系统支持分区数据块设备。

Linux 基金会是新堆栈的赞助商。

来自 Pexels 的 Igor Starkov 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>