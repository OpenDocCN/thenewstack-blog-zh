# DockerCon 2015:游戏开始

> 原文：<https://thenewstack.io/dockercon-2015-game-on/>

很久没有一个年轻的技术供应商——在这个例子中，才两岁——召开过一次会议，其结果对日常业务有如此大的影响。Docker Inc .制造的关键产品旨在帮助数据中心避免在云平台上管理虚拟机的潜在灾难性复杂性。原则上，容器管理要简单得多。实际上，情况并非总是如此。

Docker 有很多东西需要证明，不仅是如果它打算让 DockerCon 2016 以同样的幅度覆盖的话。它必须克服一个巨大的障碍，这关系到获得广泛的采用。是的，确实有调查数字表明了 Docker 所获得的兴趣水平。本周早些时候发布的一项调查显示，虽然 254 名受访者中有 234 人至少对 Docker 进行了某种程度的调查，但只有 103 人在生产级别部署了容器化，只有 49 人在其他虚拟化环境(如 vSphere)之外部署了容器化，该调查由容器数据管理工具制造商 ClusterHQ 委托 DevOps.com 进行。

这项调查表明，虽然 Docker 技术可能正在快速发展，Docker press 可能正在以极快的速度发展，但企业对它的实际采用率却出奇地正常。这也意味着 Docker 可能会陷入困境:如果其技术战略过度发展，并且 Docker ideal 与常见的数据中心服务架构有太大区别，Docker 可能永远不会真正渗透超过五分之一的数据中心。

根据 DevOps.com 的调查，大约 73%的受访者表示，他们正在一个自身虚拟化的环境中运行 Docker，换句话说，不是应该作为 Docker 之家的裸机。这是一个问题。下周 DockerCon 将会有供应商出售虚拟机环境中的组织，以保持这种状态。

我将 Docker Inc .及其合作伙伴需要在 6 月 22 日(周一)和 6 月 23 日(周二)于旧金山举行的 DockerCon 大会上展示的关键证据归纳为三大类:

**1。Docker 将如何调和它的无状态架构和日常世界的有状态需求？**我们看到集装箱化支持者之间的分歧越来越大。有一种新观点认为，某种程度的国家地位将无限期地继续存在下去。

随着本周早些时候 ClusterHQ 推出 Flocker 1.0 ，我们看到了这场对话如何在 DockerCon 爆发的初步迹象。该公司首席执行官马克·戴维斯的语气可能被一些人理解为真正的异议，他说，“实际上没有无状态应用这种东西。”他的观点是，数据库需要与容器有一些持久的联系，RESTful 架构通过 API 将容器与数据库完全分离的应用程序架构是一种白日梦。

然后我们从 Shippable 那里听说,[正在再次革新其连续交付平台](https://thenewstack.io/shippable-formations-is-a-container-cicd-without-devops-style-scripts/)，这一次是围绕持久容器的概念——远没有 Docker 想象的那么“短暂”的虚拟化组件。

这并不完全是 Docker 社区为了一个共同的目标而齐步走在一起。或者，从另一个角度来看，也许共同的目标是在这一点上广泛采用，Docker Inc .实现这一目标的途径可能不是其他人正在绘制的补丁。如果 Docker Inc .希望摆脱 DockerCon 作为容器化领导象征的角色，它需要表现出灵活性和开放的思想，重新考虑将无国籍状态作为容器化应用程序的最终理想状态。

**2。Docker 会为集装箱展示一个安全的虚拟网络模型吗？这个模型足够强大，足以让风险经理相信投资是值得的吗？**关于那些在虚拟机中运行的 Docker 环境，有一点我们绝对可以肯定:其中的容器没有按照它们在生产环境中应该的方式联网。因此，无论是谁在这些虚拟机中构建 Docker 环境，都不是为了生产目的。

我们听到的一个错误是，企业担心安全性。嗯，是啊，企业总是担心安全性，但这不是重点。一方面，Docker 没有为典型的恶意用户提供传统的“攻击面”,也没有为典型的安全供应商或安全服务提供传统的平台。

现在，无论是容器化、虚拟化还是在脸书的裸机服务器上，所有的安全都不再是加固端点的问题，而是维护网络中所需的连接状态的问题。此时此刻，即使经过几年的快速发展，一旦架构争论得到解决，我们也不知道一个容器化的网络会是什么样子。

当 Docker Inc .在去年 3 月收购 SocketPlane 时，Docker 开发社区收到了它发出的关于 Docker 网络安全未来的消息，并为此欢欣鼓舞。外界听到的是，“我们刚刚聘请了一个超级聪明的三人开发小组，他们是真正聪明的孩子，可以改变世界，”这听起来像是不断制作的流行漫画超级英雄电影中的一句话。

当[微软和 Docker 在舞台上联手](https://thenewstack.io/docker-just-changed-windows-server-as-we-know-it/)时，世界非常重视这种伙伴关系。这是两个平等的品牌，另一个是全新的。Docker 需要在周一和周二进行类似的伙伴关系演示(复数)，以引起重视。

**3。Docker Inc .计划与其他容器模型竞争还是“拥抱和扩展”它们？** CoreOS 是被称为“Docker 家族”的重要组成部分之一但是现在，它运行了一个竞争的注册中心，并且为一个竞争的容器标准做出了贡献。

将 appc 描述为不是真正与 Docker 的 libcontainer 竞争，而是扩展容器市场，就像 59 名左右的共和党总统候选人之一说其他 58 名不是真正的竞争对手，而是有额外利益的支持者。嗯哼。虽然从直接开销的角度来看，其他容器规范可能被视为失败者，但甚至有讨论的事实(以及谷歌有兴趣支持各方以延长讨论)表明 Docker 的未来尚未确定。

亚历克斯·威廉姆斯、萨姆·查林顿和我将于下周一和周二从旧金山为您报道。在我对我们的报道的贡献中，我将回到这三个关键问题，并且我将在会议结束后进行总结，以了解 Docker Inc .是如何摆脱困境的。这一周请和我们呆在一起，看看堆栈在迄今为止最大的压力下表现如何。

CoreOS、Docker 和 Shippable 是新堆栈的赞助商。

专题图片:[罗伯特·文特雷](https://www.flickr.com/photos/robie06/)的《[加州街-三藩市](https://www.flickr.com/photos/robie06/5270876051/in/photolist-92LBPi-pPuVMg-qX8sJm-2U97nc-pNWxRf-dHwyHh-dVht75-rsMLsH-e9bSSB-pkj3K4-hn2uCD-j9rNYG-6pZx39-dHcAn7-2VDWFV-ccT7d3-4heGvv-4856y6-ssmVd3-3MjYDX-aCxmok-rs5i9w-nqgSDG-a64shG-hGSWWQ-48orSL-5U3DGN-aMbTY-5rR4Aa-dMd81Y-fbAA1w-7bxkts-jfSLd-fdnFp5-k358za-at5uUd-8gihrC-rqYCUR-jFuCT-jbupC-atrVSQ-hDDLuc-eBcFvt-fecDj5-egqpch-mcGjG7-9t3w-c1Lk1f-7ogFh6-tYRi5)》获得 [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>