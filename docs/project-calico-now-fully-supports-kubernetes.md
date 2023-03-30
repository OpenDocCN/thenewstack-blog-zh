# 项目 Calico 现在完全支持 Kubernetes

> 原文：<https://thenewstack.io/project-calico-now-fully-supports-kubernetes/>

上周五， [Project Calico](http://www.projectcalico.org/announcing-1-0-calico-cni-integration-for-kubernetes/) ，一个开源的虚拟网络堆栈，发布了它的 1.0 版本的 Kubernetes 插件——据该项目的首席宣传员 Andy Randall 称，这是一个信号，表明该插件已经过良好的测试，并准备投入生产。

“我们看到 Kubernetes 有很大的发展势头。因此，推出 1.0 版本将标志着人们可以从概念验证进入部署阶段。这对 Project Calico 很重要，但整个行业刚刚开始采用这些解决方案，而不仅仅是一项实验性技术，”Randall 说，他也是赞助商 Metaswitch 公司网络业务部门的总经理。

Calico 项目旨在大规模地建立简单的网络。传统上部署的类似 LAN(第 2 层)的方法使用桥接和隧道覆盖网络来配置多个工作负载，这种情况在规模上变成了一个老鼠窝。它可能需要应用程序开发人员和数据中心操作员可能不具备的网络知识。

Calico 项目的灵感来自互联网本身——它称之为 L3 方法——让每台服务器都充当其托管的容器的路由器。Linux 内核充当 IP 流量转发机制，每个容器上的代理监控网络图中的任何变化，并在下一次连接之前重新检查与之相关的策略。【T2![Calico](img/8c1a792b66286464cca86175c2ccbdc1.png)

新插件使用容器网络接口(Container Network Interface，CNI)，这是配置容器网络的开放标准，并继续支持实验性的基于注释的策略。

随着去年 8 月 Calico 1.0 的发布，它宣布[与 OpenStack Neutron](http://www.projectcalico.org/announcing-calico-v1-0/) 完全集成，并与 Docker、Kubernetes 等进行概念验证集成。它支持 IPv4 和 IPv6 流量，并与云协调系统集成，以支持虚拟机、容器或裸机工作负载之间的安全 IP 通信。

它还提供了一个灵活的安全策略，使用允许流量的白名单和“预定”访问控制列表。它在 12 月宣布了与 CoreOS constructive 星团的整合。

Randall 说创建 Kubernetes 插件解决了许多问题:

“Kubernetes 内部发生了变化。它已经从 1.0 版本升级到 1.1 版本，所以它一直在支持接口的发展。另一件事是，Kubernetes 一直在稳步提高规模目标。第一个版本只针对 100 个节点。[Version] 1.1 显著地将这个数字增加到了几百，实际上我们看到这个数字将增加到 1000 以上。

“因此，在这一点上，对于很多企业来说，生产规模非常重要。我们一直在做的很多事情都在推动我们的测试达到那个规模。这是一回事，是的，我们可以启动几个容器，您可以从一个容器 ping 到另一个容器，但实际上是在真正的工作负载下大规模执行，真正的变动——拆除容器、添加新容器——这是编排系统和网络的负载。这是我们一直在做的重点，”兰德尔说。

总部位于纽约的裸机云提供商 Packet 就是它的客户之一。Randall 说，大型金融公司最初是其主要客户，但后来扩展到了大型 SaaS 供应商、公共云提供商和零售客户，但没有提到他们的名字。

他说，安全政策将是未来 Calico 项目的一个主题。

“我们正在努力将安全策略与 Kubernetes 整合在一起。当前版本还处于实验模式。在 Kubernetes 上有很多关于这个界面和框架应该是什么样子的讨论。所以这是我们渴望推进的事情。

“我们所做的安全方面的工作将是明年的一大推动力。人们越来越感兴趣的是应用程序开发人员和网络或数据中心运营商定义安全策略的能力。对于应用程序开发人员来说，‘这是我的微服务，它需要以下网络服务。它需要与这些容器对话。并在网络结构中强制执行，”他说。

“这就是卡利科要去的地方。不仅仅是执行它，而是报道正在发生的事情。因此，当您看到潜在的恶意工作负载时——无论它是受损的容器还是有人只是犯了一个编程错误——您看到了不应该发生的流量，您检测到它，您阻止它，您报告它，您停止对这些工作负载进行数据包捕获。你用沙箱保护他们。这些是人们想要的不仅仅是网络的高级功能，”他说。

“我说这真的很简单。我们所要做的就是将数据包从 A 发送到 B，然后阻止数据包从 A 发送到 B。传统上，这被视为两个完全独立的问题。您将虚拟网络安装到位，然后安装防火墙。我们认为最好是描述您想要实现的整个网络，既包括我想要的连接方式，也包括我想要的关于谁可以与谁对话的规则，并在一个地方实施这些规则——这就是我们所做的。”

*专题图片:* [曼谷交通](https://www.flickr.com/photos/fischerfotos/7457906740/in/photolist-cn2HQY-66jTKz-4aMfee-mL9TG-bv1NqZ-6yLKJH-9d2zXu-6VFTEM-bM6rhr-dq2jud-6Wmw9-t6sJJP-9cxtun-9rPxcR-9Ca4T-51fRaz-9UYgmL-iUPRe4-qqYgSS-bMZ5LK-oSiLB2-j15uNV-7PAweF-rrKj4y-4Tbgjc-9UYgRu-7Vp3La-9HC8zn-8vfgZT-bJPrVB-xjcCiK-4vtbmL-8CVMug-3i3mA4-fr1NAJ-pe8fV6-jvWXgR-yJSFHu-aHafX-eitxPj-789Mm4-c4Ttfy-cXEcpJ-6wQkLY-bPEJ-aXsiN8-ciBBuC-qAFkV6-6QbfBa-fbY3MF)由[马克菲舍尔](https://www.flickr.com/photos/fischerfotos/)由 CC BY-SA 2.0。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>