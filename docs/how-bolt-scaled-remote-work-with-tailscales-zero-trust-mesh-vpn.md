# Bolt Scaled Remote 如何与 Tailscale 的零信任网状 VPN 配合工作

> 原文：<https://thenewstack.io/how-bolt-scaled-remote-work-with-tailscales-zero-trust-mesh-vpn/>

当[还在](https://boltfinancial.wpengine.com/wp-content/uploads/2021/06/Feb-1-2022-Bolt-Fact-Sheet.pdf)读高中的时候，[博尔特](https://www.bolt.com/)的创始人[瑞安·布雷斯洛](https://www.linkedin.com/in/ryantakesoff/)就开始为各种规模的企业建立电子商务网站。没过多久，他就意识到这个世界需要一个更好的结账平台:首先，用户体验(UX)需要更快、更简单。

快进到他在斯坦福大学计算机科学项目的日子，到该公司在 2014 年成立，在 2016 年推出支付步骤，并在 2018 年正式推出支付和结算平台。

如今，Bolt 已经从最初的 10 人团队——包括来自谷歌、脸书、Twitter 和 Airbnb 的技术成员——发展到 600 多名团队成员和全球数百家零售商。

Bolt 的结账平台捆绑了零售商支付处理、支付网关和欺诈检测所需的所有工具，以及计算优惠券、税收和运输成本等结账流程。这一点，加上其他几项改进，加快和简化了 UX。一旦购物者加入 Bolt 网络，他们只需点击一下就可以从参与的零售商处结账。零售商和内容创作者可以将他们的店面扩展到任何数字表面，如社交媒体源、聊天和数字出版物。

## **传统 VPN 不容易扩展**

2021 年，博尔特的增长加速甚至更快。但当时它的虚拟专用网络(VPN)是一个典型的、单一的运行 OpenVPN 访问服务器的亚马逊网络服务 EC2 实例，无法轻松扩展以跟上增长的步伐。

由于公司员工完全远程办公，可伸缩性无疑是一项需求。

Bolt 的平台和基础设施主管 Roopak Venkatakrishnan 表示:“我们想要指数级的改进，而不仅仅是微小的改进。“因此，问题是我们如何设置我们的网络来做更多、更快的事情，并提供更好的用户体验。”

他们还考虑了其他替代方案，包括 [AWS 客户端 VPN](https://aws.amazon.com/vpn/client-vpn/) 、[星云客户端 VPN](https://www.defined.net/) ，以及扩展其现有的 OpenVPN 访问服务器。“最初，我们只是想修复我们的 VPN，但后来我们意识到 VPN 只是一个起点，我们想做的不止这些，”他说。

Bolt 的站点可靠性工程师[杰克·爱丁顿](https://www.linkedin.com/in/jedgington/)说，如果不对 Bolt 的网络设计做出重大改变，例如在 AWS 内的虚拟专用云(VPC)之间添加对等连接或中转网关，或者甚至仅仅依赖公共网络来实现其所有的跨区域或跨云连接，当前的解决方案将无法扩展。

“Tailscale 网状网络正好处理了所有这些复杂性，”他说。"这种物有所值的效果与我们通过缩小规模所能获得的效果相去甚远。"

## **网状拓扑提供更高的吞吐量和更大的可扩展性**

Venkatakrishnan 最初建议尝试 [Tailscale](https://tailscale.com/) 的 VPN，因为他已经在家里将其用于自己的个人项目，例如在他的个人 Tailscale 网络上连接他的服务器和 Raspberry Pi。

[Tailscale 的成立是为了给开发人员提供一个安全、可扩展的传统 VPN 替代方案:小型、可信、人类规模的工作网络，其中网络上的每个人都可以访问其他每个人的设备和应用程序，但拒绝网络外的任何人访问。](https://thenewstack.io/tailscale-a-virtual-private-network-for-zero-trust-security/)

这个想法就是简单地扩展系统，而不是处理扩展这些系统所需的开销，或者开发环境中的麻烦。Tailscale 的服务也可用于企业和商业，以降低内部网络的复杂性，或授予在家工作的员工远程访问权限。

Tailscale 的网状拓扑结构创建了一个对等网络，将每个设备直接连接到所有其他设备。这与通过中央网关发送网络流量的传统中心辐射型 VPN 网络体系结构形成对比。对等网状网络产生更低的延迟和更高的吞吐量，并且即使在切换到不同的网络(例如从有线到 WiFi)时也能保持现有的连接。

爱丁顿说:“我把 Tailscale 的最终目标描述为完全颠覆了通常的网络设计方式。”。“设备位于何处是不可知的，比如不同的云或用户位置，因为网状网络，这不再重要。”

对于 Bolt 来说，Tailscale 的子网路由器使得从传统 VPN 过渡到网状网络更加容易。“我们能够将我们的网络分成更小的子网，并为每个子网部署子网路由器，”他说。

## **更好的安全性，更少的麻烦**

传统的 VPN 通常只有一个或少数几个进入网络的入口点。这些入口点需要非常广泛的网络接入，以便所有网络用户能够访问所有部分。

Edgington 说，随着越来越多的 VPC、区域，甚至多个云被添加到全球网络中，需要大量的繁重工作来连接这些专用网络。“有了 Tailscale，我再也不用担心这些了。我可以在任何网络、任何 VPC、任何地区或任何云中旋转一个新的 Tailscale 节点，它连接到我们的私有 Tailscale 网络。”

Tailscale 网络的[零信任](https://thenewstack.io/cisa-lays-out-security-rules-for-zero-trust-clouds/)方面对 Bolt 的决策过程也非常重要。

Edgington 说:“传统的 VPN 解决方案通常要求你为 VPN 服务器本身提供非常广泛的网络访问，然后在 VPN 连接点限制用户或组的访问。

但 Tailscale 的网状拓扑意味着，如果网络访问控制策略允许，网络上的每个节点、每个设备都可以直接通信。因此，在网络边缘没有单一的可信点，就像传统的 VPN 一样，从安全的角度来看，这样更好。他说，“如果一个设备被入侵，在网络中横向移动会困难得多，因为你没有同等水平的完全开放的网络访问。”

Tailscale 还简化了开发和部署。“在任何地方安装 Tailscale 都很容易——EC2 实例、GitHub 操作、CircleCI 运行程序或 Kubernetes 集群中的容器，”Venkatakrishnan 说。“我们能够使用 Tailscale GitHub 动作在几分钟内连接我们现有的一些 GitHub 动作工作流。”

## **安全连接外部 SaaS 工具**

吸引 Bolt 团队使用 Tailscale 的另一个原因是它与软件即服务工具的无缝协作程度更高，“基本上任何运行在其他人的网络或硬件上的东西，这是我们现有的 VPN 不容易实现的，”Edgington 说。

他说，由于“Tailscale 可以非常容易地将运行在几乎任何云或任何网络上的任何东西安全地连接到我们的私有网络”，Bolt 还将 GitHub Actions 等 SaaS 工具连接到其 Tailscale 网络。

起初，Bolt 从一个较小的产品开始，后来扩大了规模。“我们从单子网路由器开始，”Venkatakrishnan 说。“之后，我们在不同的可用性分区和区域中添加了多个子网路由器，包括子网路由器故障转移以实现高可用性。然后，我们开始使用访问控制列表来控制用户对特定子网的访问。”

就像传统的 VPN 一样，Bolt 使用 Tailscale 为其所有员工提供对内部网络资源的安全访问。一名员工在安装 Tailscale 后发消息称，它已经[改变了她的生活](https://twitter.com/roopakv/status/1456466252914778119)。

“现在我已经开始使用 Tailscale，我再也回不去了，”她写道。“登录是下拉列表中的第一个操作，我只需点击一下就完成了！不需要 SSO。它加载速度很快。我不合理地喜欢这个，我可以在网络中看到你们所有精彩的[人]。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>