# WireGuard VPN 协议进入您身边的 Linux 内核

> 原文：<https://thenewstack.io/wireguard-vpn-protocol-coming-to-a-linux-kernel-near-you/>

虚拟专用网络(VPN)协议[即将进入 Linux 内核](https://lists.zx2c4.com/pipermail/wireguard/2020-January/004907.html)，这让 Linux 的创造者 [Linus Torvalds](https://github.com/torvalds) 非常高兴。

[![](img/e2bc9b7cfb9256a74f2a4170e529573f.png)](https://www.wireguard.com/)

“我能再一次表达我对它的爱，并希望它很快被合并吗？也许代码并不完美，但我浏览了一下，与 OpenVPN 和 IPSec 的恐怖相比，它是一件艺术品，”托瓦尔兹在 Linux 内核邮件列表上兴奋地说。

什么是 WireGuard？简而言之，WireGuard 是一个易于部署的第 3 层安全 VPN，并且可以说，它提供了比其他开源 VPN 包更干净的代码库，最终被合并到 5.6 版的 Linux 源代码树中。

## WireGuard 有何特别之处？

WireGuard 为自己取了这样一个名字的主要原因是，它比其他解决方案更容易配置(只需几行代码即可部署)，并且可以快速检查安全漏洞。事实上，整个 WireGuard 代码库由大约 4000 行代码组成(相比之下， [OpenVPN](https://openvpn.net/) 的代码超过 100000 行)。

WireGuard 特殊的另一个原因是它的功能。与更复杂的竞争不同，WireGuard 的工作方式与 SSH 相似——通过交换公钥。一旦交换了密钥并建立了连接，就不需要管理连接或守护进程，也不需要关心状态或幕后发生的事情。

对于那些对幕后发生的事情感兴趣的人来说，WireGuard 使用了[噪声协议框架](http://www.noiseprotocol.org/)、 [Curve25519](http://cr.yp.to/ecdh.html) 、 [ChaCha20](http://cr.yp.to/chacha.html) 、 [Poly1305](http://cr.yp.to/mac.html) 、 [BLAKE2](https://blake2.net/) 、 [SipHash24](https://131002.net/siphash/) 、 [HKDF](https://eprint.iacr.org/2010/264) ，并保护可信结构。现在 WireGuard 将存在于 Linux 内核中，它将更容易实现，也是 Linux 平台上最可靠的 VPN 之一。

### 为什么花了这么长时间？

安全从来都不是仓促之事，尤其是考虑到数据和网络保护的脆弱状态。正因为如此，上游的 Linux 加密开发人员选择将 wire guard designer[Jason donen feld](https://www.zx2c4.com/)的 [Zinc crypto API](https://lwn.net/Articles/770750/) 的元素合并到现有的内核加密堆栈中。

在此之前，有 34 个补丁提交到 crypto API 库，这使得解锁 WireGuard 以上传到 Linux 内核成为可能。不幸的是，这个时机使得将 WireGuard 引入 Linux 5.5 内核成为不可能。为此，VPN 协议已经成为即将到来的 5.6 内核版本的目标。

### 新标准

一旦 Linux 内核 5.6 发布，预计 WireGuard VPN 将成为 Linux VPN 技术中事实上的标准。占地面积小、速度快、简单和内核设计的结合应该很容易使它成为需要实现可靠 VPN 的 Linux 管理员的首选。

因为 WireGuard 将内置于内核中，所以不需要第三方解决方案。这相当于更快、更容易地为 Linux 部署一个经常被恶意中伤的解决方案。WireGuard 将使采用 VPN 成为名副其实的简单事。

Linux 基金会是新堆栈的赞助商。

来自 Pixabay 的 prettysleepy1 特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>