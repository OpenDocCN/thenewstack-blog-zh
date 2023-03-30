# 集装箱安全供应商 NeuVector 瞄准网络

> 原文：<https://thenewstack.io/container-security-vendor-neuvector-zeroes-network/>

Docker 容器安全供应商 NeuVector 上个月悄然出现，宣布其以网络为中心的容器安全方法全面上市。

NeuVector 首席执行官[黄飞](https://www.linkedin.com/in/fei-huang-7990162)说:“我们来自传统的网络安全背景，我们很快意识到现有的方法不适用于集装箱环境——它们不能很好地转移，其他解决方案又慢又不完整。

黄说，他在 VMware 工作时迷上了容器，可以看到 IT 运营的重大转变，但发现缺乏安全性。为了创造一个更好的方法，他与曾在 Fortinet、Cisco 和 Altigen 管理开发团队的 Gary Duan 合作。这两家公司在安全、虚拟化和其他技术方面拥有多项专利。

他们想弄清楚如何在运行时保护容器，而不损失速度或规模。

据 NeuVector 产品管理和营销副总裁 Glen Kosaka(T7)说，他们的解决方案有三个方面:一是检测异常连接。第二个是运行时漏洞扫描。第三是威胁防护，因此如果通过网络有任何应用层攻击，如 DDoS、DNS 攻击或利用 SSL 漏洞，都会被实时检测到。

NeuVector 的技术本身就是一个容器——不涉及任何编码或代理。与您的容器一起部署的这个容器会自动学习该 IT 环境中容器的正常行为并将其列入白名单，以便能够对异常行为发出警报。NeuVector 在容器、应用和服务级别自动创建隔离分段。还可以添加黑名单规则。

[行为基线](https://techcrunch.com/2016/08/04/the-four-cybersecurity-terms-everyone-is-talking-about-at-black-hat/)是在 [Blackhat 2016 大会](http://www.blackhat.com/us-16/)、[Container Solutions’](http://container-solutions.com/)[Adrian Mouat](https://twitter.com/adrianmouat)之前在新堆栈中报道过[的行为基线](https://thenewstack.io/assessing-the-state-current-container-security/)，其中安全机制专注于理解应用或系统的正常行为，以检测异常。

他说，这通常是结合数据科学手动完成的，但由于容器的短暂性，需要自动化。

[在其关于将安全性集成到 DevOps 实践中的报告](https://www.gartner.com/doc/3463417/devsecops-seamlessly-integrate-security-devops)中， [Gartner](http://www.gartner.com/technology/home.jsp) 将白名单描述为“运行工作负载的最强大的信息安全控制之一”，并主张尽可能实现自动化。

它还指出了容器的一个基本限制:由于它们共享相同的操作系统，在没有其他工具的情况下，网络流量对所有托管的容器都是可见的。因此，对操作系统内核层的成功攻击会暴露所有容器。

根据 NeuVector 的说法，通过其应用层分段，可以自动检测和阻止异常连接，以免造成伤害。它可以阻止不允许的特定网络连接，但仍然允许“好”流量到达该容器，而不必杀死该容器或隔离它。

黄解释说，当大型应用程序被分解成容器时，它们唯一的通信方式是通过网络，比如 REST API。所以要保护容器，网络是你首先需要安全的地方。

他坚持认为，传统的网络安全产品是为虚拟机设计的，而容器安全领域的初创公司过于专注于图像扫描。

“您可以稍后扫描文件系统，但如果您的网络、内存中有什么东西，那就太晚了。运行时威胁根本不会进入文件系统；他们去网络。攻击者侵入图像，他们在内存中运行，所以扫描解决方案不起作用，”他说。

一系列供应商提供图像漏洞扫描，包括 Red Hat 的 [Atomic Scan](https://developerblog.redhat.com/2016/05/02/introducing-atomic-scan-container-vulnerability-detection/) ，IBM 的 Bluemix Vulnerability Advisor，CoreOS 的 [Clair](https://github.com/coreos/clair) ，Docker Inc .的 [Docker Security Scanning](https://blog.docker.com/2016/05/docker-security-scanning/) ，Aqua Security 的 Peekr，以及 Twistlock Trust 的。

黄说，但是对于容器来说，还涉及到一个额外的网络层。

“使用虚拟机，您只能看到部分通信。如果我有两个容器运行在同一个主机上，它们相互通信，我们称之为东西向流量。它根本不通过虚拟机。这完全是另一层虚拟化。这就是为什么如果你着眼于虚拟机，你不会看到大画面，你不会看到细节，”他说。

NeuVector 可以与流行的 CI/CD 工具一起使用，并与 Splunk、Nginx 和编排工具集成，如 [Kubernetes](/category/kubernetes/) 、Docker Swarm、Rancher 和 Red Hat [OpenShift](https://www.openshift.com/) 。

这家总部位于加州米尔皮塔斯的公司有一个 10 人的团队，并且发展迅速。

小坂说，它一直在与包括网络公司、银行和其他金融机构在内的企业密切合作，这些企业的试点项目“即将投入生产”。这些概念验证通常涉及一些包含 100 个或更少容器的节点。

它发现企业正在推动向 Docker 的转移，黄说，虽然这些公司很谨慎，但他们通常有一个新的功能或模块，他们希望在容器中推出。

“集装箱网络可能会变得复杂，因此我们使用 NeuVector 进行集装箱安全审计，以确定应用层和网络层到底发生了什么。我们还使用它来监控和保护微服务产生的所有东西向流量。软件设计、开发和咨询公司[cognition](http://cogniance.com/)的首席技术官 [Sergii Gorpynich](https://www.linkedin.com/in/sergiigorpynich/) 说。

[CoreOS](https://coreos.com/) 、 [Red Hat](https://www.openshift.com/) 和 [Twistlock](https://www.paloaltonetworks.com/prisma/cloud) 是新堆栈的赞助商。

特征图片:[埃舍尔](https://www.flickr.com/photos/bertknot/16750774555/in/photolist-rwd6FR-4zRBjv-8d4cXS-4mFePe-bun7u-6BK3ZE-kchD6Z-NkPy-BE96-4epZXR-7BDTEJ-8ykp6p-v1Tjy-aLHhTn-v1Td5-7SKg6G-2UPvQU-z7Q8Q-kchCPr-2bpo2B-oozbuJ-94SamP-kchCNK-kchDSt-eDXn-co7FGh-4ind12-5e9zHm-kchDpe-4irh1Y-339jD4-gRHFJh-4irgbu-4ikpWF-5Ns5RK-5e5e4X-4ikqfV-2E3Dxj-kchCsp-j7GYf8-gRHRNq-qYha2H-nJNdtJ-4irfGG-isgMs6-b9KdQT-ishPE1-cdggWy-BE4L-4ipxJL)(细节)由[伯特纳特](https://www.flickr.com/photos/bertknot/)提供，授权于**CC BY-SA 2.0**。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>