# Tailscale:零信任安全的虚拟专用网

> 原文：<https://thenewstack.io/tailscale-a-virtual-private-network-for-zero-trust-security/>

在创办他们的公司之前， [Tailscale](https://tailscale.com) 的创始人就知道他们想要实现的目标:为开发者提供小型、可信、人性化的工作网络，网络上每个人的设备和应用都可以互相访问，而且只能互相访问。

这当然是虚拟专用网络(VPN)应该做的。但是[的 VPN 安全问题](https://dh2i.com/press/dh2i-pre-pandemic-state-of-virtual-private-networks-vpns-survey-reveals-inadequate-security-number-one-vpn-pain-point/)在疫情之前就已经出现了。自那以后，由锁定引发的远程工作的大幅增长只是揭示了他们有多脆弱。

即使是企业级 VPN 也充满了安全问题。事实上，Zscaler [对网络安全专家的调查](https://info-zscaler.com/resources-industry-reports-vpn-risk-report-cybersecurity-insiders)发现，93%的组织仍然使用 VPN，即使他们知道这些服务已经成为网络罪犯的目标。

因此，三分之二的企业正在寻找传统 VPN 的替代方案来进行远程访问。由于与 VPN 相关的安全风险越来越大，72%的企业开始关注采用零信任安全实践。

因此，与联合创始人首席技术官[大卫·克劳肖](https://www.linkedin.com/in/david-crawshaw-92253714/)和首席运营官[大卫·卡尼](https://www.linkedin.com/in/dfcarney/)一起，首席执行官[埃弗里·彭纳伦](https://www.linkedin.com/in/apenwarr/)希望给开发者一个安全、可扩展的传统 VPN 替代方案。

“我们的大愿景是帮助开发者合理控制规模，”前谷歌工程师彭纳伦说。他说，尽管大型科技公司的影响力促使许多企业为最大规模构建一切，“软件开发的长尾大多是由小团队使用的小项目”。“你为 10 亿用户设计的方式与你为更少的用户设计的方式非常不同，即使是为 100 万用户。”

这意味着创建小规模的网络，不需要开发人员纠结于安全问题或解决开销问题，这样他们就可以把时间花在开发上。该公司的指导原则包括“小即是美”和“它必须‘管用’。”"

## 人类规模的私有网络

曾几何时，组成互联网的互联网络包括 Tailscale 提供的那种小型、可信、人类规模的网络。许多这样的用户通过私有的、分布式的点对点通信联系在一起，这是对互联网未来发展的早期设想。

最终，这些小型网络和大型网络在公共互联网中相互连接，现在可能包括全球的每个人。但始于 20 世纪 90 年代的对恶意软件的安全担忧导致到处设置防火墙，这意味着公共互联网上的点对点连接再也不可能了。

无处不在的防火墙也带来了在安全上花费更多员工时间的需求。为了创建开发团队需要的小型、可信、分布式网络，“你要么在局域网上运行，人们无法远程访问，要么在公共互联网上运行，然后花所有时间将其锁定，”Pennarun 说。

受防火墙保护的 VPN 的传统安全模式被称为[“城堡”方法](https://thenewstack.io/beyondcorp-google-ditched-virtual-private-networking-internal-applications/)。这是有问题的，因为一旦攻击者突破边界，内部的一切—网络、设备和应用程序—都可能受到威胁。

这种模式经常与[零信任安全模式](https://thenewstack.io/cisa-lays-out-security-rules-for-zero-trust-clouds/)形成对比，后者现在在整个行业和联邦政府中逐渐流行。与网络上的任何人都有权在那里的旧假设——“信任但不验证”——不同，零信任要求相反的假设:“永远不信任，永远验证。”

从技术上讲，Tailscale 的 VPN 服务是一个零信任网络。但是 Pennarun 不喜欢这个词，因为它是负面的。“人们想要的是能够信任，”他说。“在一个由人或计算机组成的小型网络中，如果你能在他们之间建立信任，那么大多数安全问题都会迎刃而解。与开放互联网上的数十亿潜在攻击者相比，你们这一小群人的危险性要小得多。”

## 开发人员需要构建小型

如今，只有云提供商拥有不受防火墙保护的公共 IP 地址。“即使你只为 10 个人运行你的服务，你仍然必须在公共互联网上托管它，然后你必须想出如何保护它，”Pennarun 说。" Tailscale 的目的是跳过所有这些."

当创始人观察开发人员如何工作时，他们发现他们的大部分时间不是花在解决客户问题上，而是花在开发环境中的障碍上，如基础设施问题和不必要的复杂性。“例如，Kubernetes 可以无限扩展，但如果我不需要在 1000 台机器上运行，我就不需要扩展，”Pennarun 说。"在 Kubernetes 上开发非常复杂."

Pennarun 说，他们的答案是创建一个开发者基础设施公司，这样开发者就可以在大大小小的团队中构建小项目，为“比互联网上所有人都小的客户群”服务。“让我们让构建和运行简单的东西变得容易，这样您就可以在真正需要时转移到较难的部分。”

这个想法是为了扩展系统，而不是为了保护它们或处理开发环境中的麻烦所涉及的开销。

根据 Tailscale 网站的说法，“开发人员可以使用 Tailscale 向他们的团队发布实验服务，而没有配置防火墙规则和网络配置的麻烦。”

当然，企业也可以使用这项服务，让在家工作的员工进行远程访问，或者降低内部网络的复杂性。

## 直接分布式连接

与通过中央网关发送网络流量的传统星型 VPN 网络架构不同，Tailscale 创建了一个对等网状网络。这个[网状拓扑](https://www.geeksforgeeks.org/advantage-and-disadvantage-of-mesh-topology/)将每个设备直接连接到所有其他设备。

星型架构比网状架构简单，但也有一些缺点:对远程用户来说延迟更长，不允许单个节点之间的直接连接，更难扩展，并且提供了可能破坏整个网络的单点故障。

相比之下，对等网状网络导致更低的延迟和更高的吞吐量，并且消除了手动配置端口转发的需要。它还允许连接迁移:即使切换到不同的网络，如从 WiFi 到有线网络，现有的连接也会保持不变。

网状虚拟专用网的想法已经存在一段时间了，主要用于利基用途。资深作家卢西恩·康斯坦丁[在 CSO Online](https://www.csoonlinecom/article/3575088/mesh-vpns-explained-another-step-toward-zero-trust-networking.html) 上写道，但是基于云的基础设施的出现，加上远程工作人员的增加，使得组织更加关注他们。

为了实现加密的点对点网状连接，Tailscale 的服务建立在开源的 [WireGuard 第三层安全 VPN 协议](https://www.wireguard.com)之上。

WireGuard 因使用最先进的加密技术而闻名；VPN 连接是使用简单的公钥建立的。它比其他解决方案更容易配置，只需要几行代码。整个代码库[只有大约 4000 行代码](https://thenewstack.io/wireguard-vpn-protocol-coming-to-a-linux-kernel-near-you/),相比之下，OpenVPN 有超过 100000 行代码。

Pennarun 说，安装 Tailscale 最简单的方法是下载并安装在两台设备上，然后将它们连接起来。正如 Tailscale 网站上的主页所描述的那样，这项服务是“一个安全的网络。零配置 VPN。在几分钟内安装到任何设备上，为您管理防火墙规则，并在任何地方工作。”

“是的，用户必须相信 Tailscale 本身会做正确的事情，在提供这项服务和软件时，我们将承担确保我们整个系统和供应链安全的开销，”Pennarun 说。“但是，如果您信任我们，那么我们会创建一个安全的网络，在这个网络中，您的其他软件是否安全并不重要，因为我们已经将坏人挡在了第一位。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>