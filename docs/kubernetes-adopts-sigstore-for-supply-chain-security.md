# Kubernetes 采用 Sigstore 实现供应链安全

> 原文：<https://thenewstack.io/kubernetes-adopts-sigstore-for-supply-chain-security/>

随着 5 月 4 日 Kubernetes 1.24 的发布，第一次有超过 500 万的 Kubernetes 开发者可以验证他们正在使用的发行版是他们所声称的。这是因为在这个版本中，Kubernetes 采用了 [Sigstore](https://www.sigstore.dev/) 来签署工件和验证签名。这是 Kubernetes security 在[迈出的一大步。](https://blog.sigstore.dev/kubernetes-signals-massive-adoption-of-sigstore-for-protecting-open-source-ecosystem-73a6757da73)

众所周知，集装箱[供应链安全已经成为一个关键问题](https://thenewstack.io/supply-chain-attacks-and-cloud-native-what-you-need-to-know/)。软件组件经常中毒，在其上构建的每个程序都会随之枯萎死亡。去年推出的 [Sigstore 是一个免费的软件签名服务](https://thenewstack.io/linux-foundations-sigstore-aims-to-more-easily-secure-software-supply-chains/)。它通过简化对发布文件、容器映像和二进制文件的加密签名，提高了软件供应链的安全性。签名后，签名记录保存在防篡改的公共日志中。sigstore 将免费供所有开发者和软件提供商使用。这给了软件工件一个更安全的监管链，可以保护和追溯到它们的来源。

## 一大步

开发者安全公司 Chainguard 的开源负责人 Tracy Miranda 解释说，这是“保护 Kubernetes 生态系统完整性的重要一步，表明由于供应链攻击的增加，大规模代码签名是可能的，也是必要的。”

这里重要的是易用性。我们早就知道加密签名和验证编程元素是很安全的，但大多数早期的加密签名工具要么太麻烦，要么太混乱，无法使用。如果没有易于使用的工具来对他们的代码进行数字签名，很少有开发人员会去费心。这就是 Sigstore 的用武之地。

正如谷歌员工软件工程师和 Sigstore 项目创始人 Bob Callaway 所说，“我们把 Sigstore 做得简单、免费、无缝，这样它就会被广泛采用，保护我们免受供应链攻击。Kubernetes 选择使用 Sigstore 就是对这项工作的证明。"

## SLSA 合规

Kubernetes 发布团队看到了这项工作的重要性。2021 年初，工作人员开始探索软件工件的[供应链级别，(SLSA](https://slsa.dev/) ，发音为 salsa)合规性，以提高 Kubernetes 软件供应链的安全性。SLSA 是一个安全框架，包括一个标准和控制清单，以防止篡改，提高完整性，并保护您的项目的包和基础设施。Sigstore 是实现 SLSA 2 级标准的关键项目，也是实现 SLSA 3 级标准的开端，Kubernetes 社区希望在今年 8 月实现这一目标。

## Sigstore 优势

Sigstore 还为 Kubernetes 社区带来了各种好处，包括:

*   Sigstore 的无密钥签名为开发人员提供了良好的体验，并且消除了痛苦的密钥管理需求。
*   [Sigstore 的公共透明日志(Rekor)](https://github.com/sigstore/rekor) 和 API 意味着 Kubernetes 的消费者可以轻松验证签名的文物。
*   Sigstore 对标准的使用，例如对任何开放容器倡议(OCI)工件(包括容器、舵图、配置文件和策略包)和 OpenID Connect (OIDC)的支持，意味着它可以与其他工具和服务无缝集成。
*   活跃的、开源的、厂商中立的 Sigstore 社区给人一种信心，即该项目将很快被采用，并成为事实上的行业标准。

“安全是一个永无止境的旅程，但降低攻击者破坏我们供应链完整性的能力的每一步都很重要，”VMware 开源技术中心和 Kubernetes 指导委员会负责人[蒂姆·佩珀](https://www.linkedin.com/in/tim-pepper-b0017a4/)说。Kubernetes 在下一个版本中采用 Sigstore 是向前迈出的一大步。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>