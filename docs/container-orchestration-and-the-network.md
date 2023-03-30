# 容器编排和网络

> 原文：<https://thenewstack.io/container-orchestration-and-the-network/>

大规模设置容器时日益增加的复杂性是许多开发人员可能会遇到的挑战。特别是，他们可能会遇到技术差距，例如如何跨多平台堆栈将整个开发人员工具包和应用程序集成在一起。

在本期 [The New Stack Analysts](/tag/the-new-stack-analysts/) 播客中，我们将探讨网络和安全问题如何影响在生产中运行容器的企业，以及开发人员在将容器作为其基础设施的一部分时应该考虑的问题。New Stack 创始人 Alex Williams 采访了 IBM 云平台[的副总裁、研究员兼首席技术官 Jason McGee](https://www.linkedin.com/in/jrmcgee) ，为我们最新的[关于容器网络、安全和存储的电子书系列做准备。](https://thenewstack.io/networking-security-storage-docker-containers/)

[#109:容器编排与网络](https://thenewstack.simplecast.com/episodes/109-container-orchestration-and-the-network)

这段对话[也可能在 YouTube](https://www.youtube.com/watch?v=kIleKV4iSOg) 上听到。

随着编排工具现在被捆绑到 Docker 这样的容器平台中，这些工具如何影响一个人的网络的问题就出现了。特别是，将容器连接到专用网络的企业应该确保它们的传入和传出流量最终不会通过公共通道进行路由。McGee 指出:“任何引入的抽象概念，从定义上来说，都限制了你可以用网络做什么。”

理想情况下，IBM 的目标是减少设置障碍的数量，简化开发人员处理容器的方式。“我不知道技术差距和集成挑战有多大。客户拥有多样化的环境。他们不会都运行 Docker、Kubernetes 或 OpenStack。大多数应用程序必须将这些技术混合或集成在一起，”McGee 说。

“这些假设和抽象给你的生活带来了复杂性，因为现在你必须找出如何将事物联系在一起，”McGee 说。

McGee 进一步谈到了将[内置编排纳入 Docker 平台](https://thenewstack.io/dockers-built-orchestration-mean-kubernetes/)的问题，并继续解释说，确保个人网络不受外部流量影响对于开发人员来说是至关重要的。McGee 接着强调了今天的网络方法随着时间的推移而改变的方式，指出今天的开发人员不是拥有一个规范驱动的测试套件，而是针对 [Swagger](https://swagger.io/) 文件进行测试。

正是这些文化转变和更多的因素构成了今天集装箱、网络和集装箱安全所面临的问题。“我们看到了从以基础架构为中心到以应用程序为中心的转变。过去，有一个基础架构团队，他们控制如何设置网络、存储和计算，并且应用程序被设计为适合该环境。我们多年来看到的是，我们正试图颠覆这种模式，”McGee 说。

总的来说，集装箱安全的挑战仍然是一个必须不断解决的问题。McGee 指出，这些问题中的一些可能源于开发人员从未首先考虑它们。“还有很多其他问题是大多数开发人员没有想到的。他们没有考虑安全性、合规性、QOS，以及当某个应用程序消耗了整个管道并导致所有其他应用程序停止运行时会发生什么？所有这些深层的网络和存储问题不会因为我们转向以应用程序为中心的观点而神奇地消失。”

[IBM](https://www.ibm.com/cloud) 和 [Docker](https://www.mirantis.com/software/docker/kubernetes/) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>