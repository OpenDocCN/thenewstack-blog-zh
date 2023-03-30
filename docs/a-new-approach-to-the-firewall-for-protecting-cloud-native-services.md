# 一种保护云本地服务的防火墙新方法

> 原文：<https://thenewstack.io/a-new-approach-to-the-firewall-for-protecting-cloud-native-services/>

随着 Web 应用防火墙的发布，Palo Alto Networks 正在提供一种保护 API 和 Web 应用的新方法，这是其 [Prisma Cloud 云本地安全平台](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention)的扩展。

由新堆栈的创始人和发行人 [Alex Williams](/author/alex/) 主持，本期[新堆栈制造商](/podcasts/makers)播客的特色是 [Ory Segal](https://il.linkedin.com/in/orysegal) ，帕洛阿尔托网络公司的高级杰出研究工程师，讨论了 WAF 模块和 Prisma 如何在当今高度分布式云本地环境中解决安全性问题。

[https://www.youtube.com/embed/xEohY1owWA8](https://www.youtube.com/embed/xEohY1owWA8)

视频

在 Prisma Cloud 中，传统的防火墙安全概念不再适用。事实上，虽然防火墙以前适用于保护具有封闭边界的环境，如局域网(LAN)，但 Palo Alto Network 的所谓防火墙保护完全不同。

“部分功能实际上是一个网络应用防火墙，这与我们的听众可能习惯的很不一样，”Segal 说。“‘防火墙’这个词有点过时了，但是正如您将看到的，我们在这里提出的概念是全新的，并且适用于全新的现代环境。”

在云原生环境中，由于“不再有任何边界”，Segal 表示，安全包括保护云资产，包括容器、无服务器和其他短暂的分布式环境。Segal 说:“您可以在一个或另一个地区部署集群，一些工作负载在私有云或本地云上运行，而一些工作负载在公共云中运行。“因此，在传统意义上部署传统防火墙已不再可行，您需要想出一种全新的方法。”

[Ory Segal——保护云原生服务的防火墙新方法](https://thenewstack.simplecast.com/episodes/ory-segal-a-new-approach-to-the-firewall-for-protecting-cloud-native-services)

除了 API 保护、访问控制、文件上传控制、检测未受保护的 web 应用程序和其他功能之外，WAF 还为攻击者提供了一个“惩罚箱”，可以根据需要“禁止”攻击者的访问。

“因此，一旦我们检测到攻击者或用户或客户端正在进行恶意操作，用户可以决定以禁令的形式采取行动，这将使恶意用户在内部被罚五分钟。现在，它不仅让攻击者感到烦恼，因为他们必须每五分钟停下来继续攻击，它还是一个非常酷的保护层，因为大多数时候攻击者不会从他们最复杂的攻击有效载荷开始，而是从探测和发送侦察探针开始，”Segal 说。

“那些探测器已经触发了‘禁止’行动，我们将把它们放在里面五分钟。然后，如果他们拿出大枪或大诡计或复杂的攻击，也没关系，因为这些将被自动和明确地阻止，因为他们在禁区内，这也是对这种攻击的很好的防御。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>