# 为什么容器是勒索软件攻击的甜蜜目标

> 原文：<https://thenewstack.io/why-containers-are-sweet-targets-for-ransomware-attacks/>

[为什么集装箱是勒索软件攻击的甜蜜目标](https://thenewstack.simplecast.com/episodes/why-containers-are-sweet-targets-for-ransomware-attacks)

勒索软件和其他[攻击正变得越来越常见](https://www.computerweekly.com/news/252459319/Cyber-attackers-favouring-stealthier-attacks-says-Darktrace)，因为黑帽子发现云原生和其他更新的平台如何成为软目标。最近披露的 [Docker runtime exploit](https://www.zdnet.com/article/doomsday-docker-security-hole-uncovered/) 作为一个可能出现严重错误的例子，安全提供商显然面临着保持领先的压力——但是为这个新的计算机保护世界找到正确的解决方案可能意味着一个蓬勃发展的架构，或者在最糟糕的情况下，一个组织的运营完全停止。

在本期 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中，由 New Stack 的创始人兼主编 Alex Williams 主持的 [Neil Carpenter](https://www.linkedin.com/in/neil-carpenter-a9419546/) 与 [Twistlock](https://www.twistlock.com/) 的解决方案架构师一起探讨了如何为原生云以及更成熟的无服务器平台寻找安全解决方案。

一个显而易见但有时被忽视的假设是，攻击者会寻找最容易的目标。此前，Carpenter 描述了在进入一些服务器环境之前，台式机如何特别容易成为勒索软件的目标，并在 2016 年和 2017 年在医疗保健和教育领域的特别邪恶的攻击中达到高潮。

“这是一种利用这些攻击赚钱的方式，”卡彭特说。

尽管如此，勒索软件攻击很难组织。卡彭特描述了攻击者如何试图在桌面上运行恶意软件，例如，为了加密所有的文件和数据，直到受害者用比特币或另一种加密货币支付赎金。

但是，在可以通过互联网连接访问的 Docker 服务器上找到一个具有未经验证的端点或未打补丁的漏洞的 Kubernetes 集群是一个特别有吸引力的目标。

“[作为一名攻击者]，我可以将我的 [crypto miner](https://www.webopedia.com/TERM/C/cryptomining-malware.html) 直接放在你正在运行的东西上，并安排它在你的 Kubernetes 集群上运行，然后我就不必再帮你想出如何购买比特币并把它交给我了。我只要运行我的 miner，它就会在你的 CPU 上运行并占用空间，”Carpenter 说。“我认为，对于攻击者来说，这很优雅，(这可能不是我真正想要的词)，但这很简单，比他们利用这种攻击赚钱的其他方法简单得多。”

卡彭特说，Twistlock 的[运行时应用程序自我保护(RASP)防御者](https://www.twistlock.com/2019/03/05/runtime-application-self-protection-protecting-apps-wherever-they-run/)，其想法是将安全功能嵌入应用程序中，而不是为运行在云原生环境中的 Kubernetes 和 containers 以及无服务器和其他平台提供外部保护，这种保护更加笨拙和低效。

“因此，我们的想法是，我们采取这些保护措施，而不是在您拥有的这些主机上运行它们，因为我们将它们烘焙到应用程序本身和您正在部署的代码中，因此无论在哪里运行，它都可以获得相同级别的保护和可见性，”Carpenter 说。“您可以在部署时将此自动化到您的管道中，然后保护这些工作负载。”

Carpenter 说，这样做的目的是限制开发人员将这一点嵌入代码本身的程度。

“因此，相反，这在概念上是他们正在部署的东西的包装，而不是必须真正改变你的开发过程和改变你正在采取的方法，”卡彭特说。“我们正在做的是为您提供工具，用 RASP Defender 包装这些东西，然后将它们随机部署到任何地方。”

### 在这个版本中:

[1:09:](https://thenewstack.simplecast.com/episodes/why-containers-are-sweet-targets-for-ransomware-attacks?t=1:09) 什么是 RASP Defender。
[6:17:](https://thenewstack.simplecast.com/episodes/why-containers-are-sweet-targets-for-ransomware-attacks?t=6:17) 如何使用 RASP Defender 作为 Fargate 任务的包装器
[10:43:](https://thenewstack.simplecast.com/episodes/why-containers-are-sweet-targets-for-ransomware-attacks?t=10:43) 对于不同的云服务，可以有不同的想法。
[12:22:](https://thenewstack.simplecast.com/episodes/why-containers-are-sweet-targets-for-ransomware-attacks?t=12:22) 在更加分布式的环境中部署容器？
[14:25:](https://thenewstack.simplecast.com/episodes/why-containers-are-sweet-targets-for-ransomware-attacks?t=14:25) 一些小技巧。
[18:21:](https://thenewstack.simplecast.com/episodes/why-containers-are-sweet-targets-for-ransomware-attacks?t=18:21) 如何看待 RASP 后卫？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>