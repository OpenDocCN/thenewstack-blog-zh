# Prisma Cloud 为云原生安全性重塑防火墙

> 原文：<https://thenewstack.io/prisma-cloud-reinvents-the-firewall-for-cloud-native-security/>

最新版本的 [Prisma Cloud，](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention)Palo Alto Networks(PANW)云本地安全平台，现在包括该公司所说的“业界最精确的 web 应用防火墙(WAF)功能”

云本地 WAF 保护任何种类的云工作负载。它还提供了当今保护您的 web 和 API 免受应用层攻击所需的所有层。它智能地检查流量，阻止攻击，抵御僵尸程序，并停止自动攻击过程，如帐户接管僵尸程序或网页抓取程序。API 保护也适用于微服务之间的南北和东西流量。

“今天，您的资产都在云中。其中一些运行在容器或无服务器的短命函数上。全面保护这些应用程序对应用程序安全团队来说是一项挑战。到处都部署着集群。一些工作负载运行在公共云、私有云或内部，”PANW 高级杰出研究工程师和知名云安全专家 [Ory Segal](https://twitter.com/orysegal) 解释道。“因此，当今的企业需要针对云原生架构进行优化的 web 应用防火墙。你需要想出一种新的新颖方法，这就是我们试图用 Prisma Cloud 做的事情。”

在 PANW 的新外观网络应用防火墙中，几种不同的功能结合起来保护你的云服务。其 WAF 将应用程序编程接口(API)安全性、运行时保护和 bot 防御平台结合在一起，为云原生应用程序提供了强大的防御。

Segal 解释说，Palo Alto Networks 在构建其下一代 web 应用防火墙时面临三大挑战。“其一是无法在现代云中部署传统防火墙。在协调的云容器和无服务器中，部署一个设备简直是不可能的。你不能将过时的防火墙作为服务添加到云中。”因此，“我们需要一种云原生的东西来支持云原生架构，并支持微服务来检查东西向流量。

“第二个问题是云原生应用的自动扩展特性，”Segal 继续说道。“容器上下旋转，无服务器功能运行，然后消失。要管理来自数百个(如果不是数千个)实例的流量峰值，您必须构建容量规划。这意味着它必须与应用程序及其无服务器功能和容器一起伸缩。

最后，PANW 需要将 web 应用安全与云安全状态管理、[身份和访问管理(IAM)](https://thenewstack.io/best-practices-for-securing-identity-and-access-management-on-amazon-web-services/) 安全和数据防止丢失(DLP)相集成，以扫描虚拟机(VM)、容器和/或功能。Segal 补充说，“你不能指望客户从多个不同的供应商那里购买许多单点解决方案。我们认为这种分裂是网络安全领域的一个严重问题。我们想要的是无所不包的东西，你知道，一站式解决你所有的云安全问题。”

保护工作由[防御代理](https://docs.paloaltonetworks.com/prisma/prisma-cloud/prisma-cloud-admin-compute/install/defender_types)完成，它们运行在每个主机容器、无服务器功能或虚拟机中，无论是在云中还是在内部。这些报告返回到控制台，在那里您可以管理它们，并且您可以大规模地管理它们。

Segal 解释说，这使得“保护任何类型的云工作负载都变得非常容易，因为我们本质上是依附于工作负载本身的。无论您有多少个实例，都不会有瓶颈或自动伸缩问题。完全支持该架构。我们支持所有大型云安全提供商和所有主要的无服务器、Kubernetes 和容器环境。”

[Ory Segal——保护云原生服务的防火墙新方法](https://thenewstack.simplecast.com/episodes/ory-segal-a-new-approach-to-the-firewall-for-protecting-cloud-native-services)

## 超越防火墙:Prisma 云的新特性

新的 Prisma 云产品不仅仅是 WAF。通过其模块，如主机安全、容器安全、Web 应用和 API 安全(WAAS)，它包括各种云工作负载保护功能。保护措施包括:

*   **Bot 风险管理**:Prisma Cloud Web Application and API Security(WAAS)客户现在可以管理 web bots，并决定如何处理不同 Bot 类型的访问。用户拥有可定制的可见性和保护，涵盖已知、未知和用户定义的僵尸程序。
*   **通过自定义合规性策略实现主机安全性** : Prisma Cloud 通过对操作系统、编排器和运行时配置进行自定义合规性检查，增强了虚拟机的合规性。
*   **具有增强的 Kubernetes 集群感知和 CRI-O 合规性检查的容器安全性** : Prisma Cloud 现在与增强的 Kubernetes 集群感知进行了更深入的 Kubernetes 集成。这使得通过 Kubernetes 集群过滤器获得快速可见性、管理安全策略和查看运行时审计变得更加简单。对于 CRI-O，Prisma Cloud 跨容器、映像和主机配置将 25 个特定的合规性检查映射到 CRI-O。
*   **高级拒绝服务(DOS)保护** : Prisma Cloud WAAS 现在包括通过应用速率控制来防御应用层 DoS 攻击的能力。

PANW 的 DoS 保护特别有趣。它不是简单地计算一个 IP 在五秒钟内发出多少请求——例如，这些 API 的任何客户端都不应该每秒发送 500 个请求——而是需要一种更具分析性的方法。如今，世界并没有那么简单。

Segal 解释道，“你不想仅仅因为用户与一些烂苹果共享同一个 IP 或网关就惩罚他们。因此，我们所做的是切换或允许我们的客户不仅基于 IP，还基于[第七层应用](https://www.networkworld.com/article/3239677/the-osi-model-explained-and-how-to-easily-remember-its-7-layers.html) [级别](https://www.networkworld.com/article/3239677/the-osi-model-explained-and-how-to-easily-remember-its-7-layers.html)应用速率控制。所以我们跟踪用户会话；HTTP 会话本身；网络会议；和特定的会话 cookie。这使得 DevOps 能够“为费率核算做更精细的工作。”这样，“例如，我们可以防止来自 NAT 网关后的恶意黑客的尖峰流量。”

此外，Segal 继续说道，除了能够提醒、记录或阻止可疑的网络活动，“我们还提供了一个非常酷的技巧，我们称之为‘ban’这基本上是一个禁区。一旦我们检测到攻击者、用户或客户端正在进行恶意操作，系统管理员可以决定禁止恶意用户进入惩罚框五分钟。现在，攻击者每五分钟就必须停下来继续攻击，这不仅令人恼火。这也是一个非常酷的保护层。因为大多数时候攻击者不会从他们最复杂的攻击负载开始，他们会从发送侦察探测器开始，而这些探测器已经触发了禁止操作，我们将把他们放在一边五分钟。然后，不管他们是否拿出大枪或大伎俩或复杂的攻击，这些都将被自动和明确地阻止，因为他们在禁区内，这也是对这种攻击的很好的防御。"

这是一种有趣的方法，花了几十年的时间研究网络安全，它真的可以破坏典型的自动化僵尸网络攻击。

## WAF 在更大的云本机安全图景中

PANW 负责 Prisma Cloud 的高级副总裁 [Varun Badhwar](https://www.linkedin.com/in/vbadhwar/) 表示，云原生用户希望获得尽可能多的保护，同时他们也希望在云原生连续体中尽可能简单地提供保护。这意味着“在运行时和整个应用程序生命周期中保护主机、容器和 Kubernetes 以及无服务器功能。许多组织正在向云迁移，需要端到端地保护应用程序，从基础架构开始，一直到应用层。”Badhwar 总结道:“Prisma Cloud 提供了同类最佳的全面解决方案，旨在保护这些组织免受第三方攻击。”

如果这听起来很复杂，即使 PANW 正在尽最大努力让它变得简单，你是对的。确实是。与过去相比，云中的安全性要复杂得多，那时您只需担心后台的服务器。但是，考虑一下 2020 年[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)【CNCF】[调查](https://www.cncf.io/wp-content/uploads/2020/11/CNCF_Survey_Report_2020.pdf)的结果。CNCF 发现:

*   **集装箱使用量持续上升:**自 2016 年以来，生产中的集装箱使用量增长了 300%，仅去年一年就增长了 84%。
*   **Kubernetes 比以往任何时候都更主流:**整整 91%的 CNCF 受访者报告使用 Kubernetes，其中 83%的人在生产中使用 Kubernetes。
*   **继续采用无服务器:** 30%的受访者表示目前在生产中使用无服务器技术。
*   **CI/CD 技术对云原生用户至关重要:**超过 80%的受访者在生产中使用 CI/CD 管道。

换句话说，随着我们越来越快地转向云原生 IT 世界，我们需要云智能安全程序等安全解决方案来保护自己。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>