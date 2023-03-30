# CoreOS 加入 Docker，向云本地计算基金会捐赠一个容器运行时

> 原文：<https://thenewstack.io/chess-games-cloud-native-world/>

在现代，一个软件的普及程度取决于它的创造者能在多大程度上公开它。周三深夜， [CoreOS](https://coreos.com/) ，其分布式容器环境的开发者，[在一篇博客](https://coreos.com/blog/rkt-container-runtime-to-the-cncf.html)中宣布其打算将其核心容器运行时包 [**rkt**](https://github.com/coreos/rkt) 捐赠给[云本地计算基金会](https://www.cncf.io/)。

CoreOS 的声明是在 Docker Inc .[周三早上向世界宣布其打算](https://thenewstack.io/docker-donate-container-runtime-containerd-cloud-native-computing-foundation/)向 CNCF 捐赠其开源核心容器运行时包 [**containerd**](https://github.com/docker/containerd) 几个小时后发布的。两者都在两周一次的会议上提交给了 CNCF 技术监督委员会，以考虑纳入 CNCF。

CoreOS 将其努力描述为与 Docker 一起的一个组合提案。在周四对新堆栈的一份声明中，Docker Inc .的发言人否认了 CoreOS 努力的联合性质，称其他公司的举动是一个单独的问题，将由 CNCF 成员在一项单独的动议中进行表决。

随着集装箱化在过去几年中的迅速发展，集装箱技术的词汇一直在努力跟上。资深的新堆栈读者可能会对 **containerd** 和 **rkt** 感到困惑，因为在 2015 年， **[runC](https://thenewstack.io/declaring-format-wars-over-docker-slips-a-universal-runtime-into-all-containers/)** [被描述为 Docker 的容器运行时](https://thenewstack.io/declaring-format-wars-over-docker-slips-a-universal-runtime-into-all-containers/)，而**[lib container](https://thenewstack.io/docker-donates-container-format-and-runtime-code-joins-coreos-to-form-standards-group/)**[被描述为 Docker 的“容器格式和运行时”](https://thenewstack.io/docker-donates-container-format-and-runtime-code-joins-coreos-to-form-standards-group/)**[appc](https://github.com/opencontainers/runc/tree/master/libcontainer)**

这是一个烂摊子，对随之而来的烂摊子的任何解释都必须为一点清理工作让路。

在当前的 Docker 环境中， **containerd** 是位于每个容器内部的守护进程，负责监督容器的执行、管理以及与容器的通信。它使用 gRPC 与外界联系(gRPC 本身是本月早些时候捐赠给 CNCF 的)，它向在早期被称为“执行者”或命令执行者的人发送命令。这个元素就是 [**runC**](https://thenewstack.io/ready-docker-containers-runc-runtime-riddler/) ，在捐赠给[开放容器倡议](https://www.opencontainers.org/) (OCI)之前，它确实被称为“运行时”。因此 [**runC**](https://github.com/opencontainers/runc) 是它启动的容器的宿主进程。尽管 Docker 容器的格式偶尔会被错误地称为“runC 格式”，但现在称之为“Docker 图像格式”和“OCI 格式”是合适的(目前，这两种格式彼此略有不同)。

**containerd** 守护进程是一个开源组件，基于 Docker 的容器引擎的原始模型。[**lib container**库](https://github.com/opencontainers/runc/tree/master/libcontainer)是 Docker 的命令集，用于与 **containerd** 接口交互。

相比之下， [**appc**](https://github.com/appc) 是 CoreOS 对其容器化系统的图像格式的规范。早期的文档提到 **appc** 指定了图像格式和容器运行时，但是后来的草案已经背离了这一立场。CoreOS 的“运行时”现在被更正式地称为“容器引擎”。

在架构上，它的官方名称是 **rkt** ，但读作“rocket”，是 Docker 的 **runC** 的对应，而不是 Docker 的 **containerd** 。此外， **appc** 被认为是无守护进程的，不像 **containerd** 。

这可能会让 CoreOS 周三晚间的举动更加扑朔迷离。

## 选择或其他

在周四对黑客新闻的评论中，CNCF 执行董事 Dan Kohn 承认他一直在与 CoreOS 和 Docker Inc .合作，分别致力于最终将他们的组件捐赠给基金会。在内部讨论之前，CNCF 参与者暂时拒绝就这些问题向新的 Stack 发表评论。

然而，CoreOS 首席技术官 Brandon Philips 愿意与我们分享他的见解。首先，我们问他，他预见到在 CNCF 开发两种集装箱引擎会有什么好处，有些人可能认为这两种引擎基本上可以互换。

“这两个项目都是建立和验证工业开放容器倡议(OCI)标准，都是为运行容器而设计的，”飞利浦回应道。作为具有不同体系结构的两个独立实施，它们都有不同的目标使用情形

Philips 指出了让实现者选择“他们希望如何运行他们的容器，并最终运行他们的应用程序”的好处。一个问题的解决方案不一定适合另一个问题。”

他接着说，在 CNCF 的管理下，为了多样性的利益，这两个项目的*独立的*发展道路不仅会得到维护，而且会得到保证。他说，两个项目的共存会给他们各自的参与者提供共享代码、库和协作建议的机会。

但是飞利浦承认了两个组件可互换性的一个要素:即，在使用一个或另一个引擎旋转容器时配置管理系统的要求。至于可能涉及的任何其他架构风险，CTO 表示，“没有风险，因为 **containerd** 和 **rkt** 都使用 OCI 建立的标准，这确保了容器化的应用程序可以在两者下运行。这意味着应用程序开发人员可以放心地构建 OCI 映像，然后基础架构工程师可以根据他们的需求挑选使用哪个容器引擎。”

那么，如何期望这些工程师做出选择，尤其是当配置管理系统认为两者是等同的时候？

“它们没有被完全等同对待，”飞利浦回应道。“尽管它们可以互换(一旦 OCI 1.0 发布)，但每种实现都强调容器基础设施的不同方面。在决定使用哪个容器引擎进行部署之前，架构师应该适当地权衡什么对他们是重要的。 **Rkt** 的架构是一个可行的选择，因为它对于寻求大规模运行应用程序的系统管理员来说很舒适。他们理解并欣赏 **rkt** 的架构决策，特别是对安全性的关注，如 VM 容器、工具的无守护进程特性以及通过插件进行组合的方法。"

最后，我们问了飞利浦这个问题:如果 Kubernetes 有一个像 IBM 的沃森一样的声音，并且它可以对此事发表意见——由与 CoreOS 关系密切的人开发——他认为它会做出什么评论？

“Kubernetes 希望看到的是一个稳定、易于升级、社区领先的容器引擎，能够履行 Kubernetes CRI 合同，”飞利浦回应道。“今天， **rkt** 接近实现这些目标；鉴于其在实现 CRI 上游全面覆盖方面取得的强劲进展，我们希望将其置于 CNCF，使其成为更具吸引力的选择。然而，Kubernetes 没有发言权，而是由一个试图做一个伟大项目的大型社区组成。说到底，CoreOS 只是希望看到 Kubernetes 在一个强大的容器运行时支持下取得成功。”

## 或者不捐赠(这是个问题)

虽然 CNCF 发言人向新堆栈确认将对 **containerd** 和 **rkt** 贡献进行单独投票，但将这些提交的内容付诸表决可能需要经过一次法律程序。在他的黑客新闻消息中，CNCF 的 Kohn 确认这两个项目的权利人必须公开他们各自的商标，并同意这些交易可能需要在法律上被称为“贡献”而不是“捐赠”

“但这是一个非常面向开源的形而上学概念，”Kohn 写道，“通过放弃对项目的一些控制，发起项目的公司有望带来更多的贡献者，最终增加项目的总价值和对他们的价值。”

另一位与会者不同意，他说，因为 Docker 和 CoreOS 都不期望他们的交易得到回报，所以“捐赠”是一个更合适的术语。这个问题可能不仅仅是语义上的:人们普遍认为，专有技术可能依赖于开源组件，但不会变成非专有的(否则，使用 SSL 的所有东西都会突然免费)。但是在过去， [Docker 的贡献者提出了一个案例](https://github.com/opencontainers/image-spec/issues/24),背离 Docker 早期方法的 OCI 格式的演变可能对 Docker 不公平，或者至少对使用 Docker 的人不公平。

《OCI》的撰稿人 Timothy Hobbs 在《黑客新闻》中提出了这个早期的争议，作为这种形而上学争议确实可能发生的证据。他的意见促使 Docker Inc .的工程师贾斯汀·科马克声明，从技术上来说，Docker 没有[向 OCI 捐赠其容器图像规范，尽管当时](https://thenewstack.io/docker-donates-container-format-and-runtime-code-joins-coreos-to-form-standards-group/)声称。相反，他说，“许多人决定对 Docker 已经在做的事情做一个大致的规范，使它正式化，并同意尽快做 1.0。创建一个全新的规范并不是一个标准，至少在最初是这样。有很多现有的映像，所以增量更改和向后兼容性很重要。”

2010 年温哥华冬奥会上，[队横扫](https://commons.wikimedia.org/wiki/File:2010_Winter_Olympics_-_Curling_-_Women_-_GBR-SWE.jpg)队，击败瑞典队的后卫罗克队的图片，由 Jonathan Pope 创作，获得知识共享许可。

云本地计算基金会和 CoreOS 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>