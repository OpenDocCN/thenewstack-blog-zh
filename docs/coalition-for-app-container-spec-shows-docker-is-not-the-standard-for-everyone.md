# 应用容器规范联盟显示 Docker 并不是所有人的标准

> 原文：<https://thenewstack.io/coalition-for-app-container-spec-shows-docker-is-not-the-standard-for-everyone/>

有竞争就有市场。也许我们不必求助于一些典型的科技媒体极端，并说战线已经拉开。但即使这一过程中有友好的骑士精神，集装箱市场也开始选择支持哪一方。

周一，在新兴的 Docker 领域之外，为建立 Linux 容器生态系统采取了几个主要步骤。CoreOS 是最初的最小化 Linux 系统之一，在其首届年度会议上宣布，谷歌、VMware、Red Hat 和混合云操作系统制造商 Apcera 正式加入支持 App Container(或 **appc** )的行业合作伙伴联盟，这是 CoreOS 为其 Rocket runtime 系统开发的规范。

也许出于商标的原因，CoreOS 现在将把它的产品拼写成不带元音的 **rkt** ，尽管它可能会继续发音为“rocket ”,它的标志也将是一个小火箭。

## 复仇者联盟

上个月， [Google Ventures 向 CoreOS 投资了 1200 万美元](https://thenewstack.io/coreos-tightens-fit-with-kubernetes-raises-12m-from-google-ventures/)，这立即导致 CoreOS 将 Google 的 Kubernetes 管理层整合到其代号为“构造”的基础设施平台的测试版中。现在，谷歌正在回报 CoreOS 对它的青睐，正式将这个平台——以前被称为 Rocket 并入 Kubernetes，并加入新兴的 appc 联盟。

两周前，随着 VMware 在其名为 Project Photon 的最小化 Linux 中对 appc 的支持，这一联盟已经变得更加强大。现在将 Red Hat 加入进来，因为 CoreOS 已经宣布它将接受 Red Hat 高级工程师和 Docker 的主要贡献者 [Vincent Batts](https://github.com/vbatts) ，作为该公司的 **appc** 的维护者。Batts 将加入[谷歌的 Tim Hockin](https://github.com/thockin) (另一个 Docker 维护者)和 [Twitter 的 Charles D. Aylward](https://github.com/cdaylward) 。

就其本身而言，Apcera 将于本周首次推出自己的 **appc** 实现，名为 Kurma，在早期阶段被描述为“在容器中运行应用程序的执行环境”

所有这些都可能是 CoreOS 区分 **rkt** 和 Docker 的下一步的前奏，除了去掉它的元音:它正在改造 Quay.io，它去年 8 月收购的私有、安全的 Docker 储存库主机[和它的 CoreOS Enterprise Registry 的基础，作为 **rkt** 图像和 Docker 的安全储存库。](https://coreos.com/blog/CoreOS-enterprise-docker-registry/)

正如 CoreOS 首席执行官 Alex Polvi 在给新堆栈的一份说明中所述，此举旨在使 Quay 成为 Docker Hub 的更有效竞争对手。

“Quay 的易用性和速度体现在我们平台独有的许多功能中，”Polvi 说。“由于我们新的构建缓存系统，Quay 构建图像的能力显著提高。我们的特性允许动态构建压缩的图像，这意味着在机器上部署容器比从其他注册表中正常提取要快得多。”

Docker 的运行时目前默认使用 Docker Hub 作为它的集中分发中心，虽然镜像名称可能会指定另一个位置。Polvi 向我们解释说，相比之下， **appc** 更像是 **git** :默认情况下是去中心化的。

“容器映像的发现，”文件写道，“应该是简单的，并促进联合名称空间和分布式检索。这为替代协议(如 BitTorrent)和部署到私有环境而不需要注册表提供了可能性。”

迄今为止，Quay 的主要卖点之一是“高级注册”。这个特征会消失吗？

“Quay 是 Docker 兼容的，Docker 需要一个注册表，”Polvi 告诉新堆栈。“拥有一个注册表确实增加了一些不错的功能，但代价是您必须运行一个注册表，从而增加了环境中的操作复杂性。 **appc** 的一个好处是，它不需要你运行一个注册中心，但是如果一个运营商选择拥有它，它也可以工作。”

## 反叛者选择他们的盟友

这是 CoreOS 新兴主题的一部分，一种革命之外的革命。在 appc 的自述文件中，作者建议去中心化应该是新规范的主要原则。

这一主题的基调是在去年 12 月发出的，当时 CoreOS 的 Polvi 发出了第一个 App Container 标准的战斗口号，该标准将要求实现 Docker 的最初目标，Polvi 认为 Docker 已经放弃了这些目标。

“我们认为 Docker 将成为一个我们都能认同的简单单位，”Polvi 当时写道。“不幸的是，一个简单的可重用组件并不是事情发展的方式……我们应该停止谈论 Docker 容器，而开始谈论 Docker 平台。它并没有成为我们预想的简单的可组合构件……我们仍然相信 Docker 引入的容器的最初前提，所以我们正在为此做些什么。”

这涉及到起草一个应用程序容器标准，非常奇怪的是，该标准为每个容器的多个进程提供了规范，这些进程作为一个应用程序一起工作，但仍然共享名称空间。这是一个关键的架构区别，非常值得注意的是，Kubernetes 管理平台也有同样的区别。

所以在五个月的时间里，反对平台开发的革命，开发了一个平台。

CoreOS 在 4 月 6 日发布的 architecture 上写道:“architecture 预打包了构建谷歌风格基础设施所需的所有组件，并增加了额外的商业功能，如工作流和仪表盘的管理控制台，构建和共享 Linux 容器的集成注册表，以及自动部署和定制滚动更新的额外工具。”

十二月和四月之间发生了什么变化？这是一个非常好的问题——事实上，这是 CoreOS 关于构造的常见问题中的第一个问题。答案估计了“没有平台”和“平台”之间的距离，并得出以下结果:“没有。”

“开发将会继续，我们希望看到所有开源项目作为独立组件继续繁荣发展，”FAQ 继续说道。

我问 CoreOS 的 Alex Polvi 关于 **appc** 将如何解决微服务架构师(包括谷歌的)在早期实现中遇到的一个问题:标记彼此相关的服务。Polvi 回应说 **appc** 不关心这个问题，有效地将它传递给平台上的服务发现层——他心里有一个想法。

“App Container 定义了图像格式、运行时环境和用于查找容器的发现协议，”Polvi 回应道。“这些问题在更高层得到了解决。例如，Kubernetes 本身就解决了服务发现的问题。

在周一的新闻稿中，Kubernetes 的联合创始人兼谷歌产品经理 Craig McLuckie 指出，CoreOS 的设计选择是他的公司支持 **appc:** “设计时考虑到了集群优先管理， **appc** 支持使开发人员能够通过相同的谷歌基础设施启发的编排框架使用他们首选的容器映像。”

随着微软领先的 Azure 工程师[上周三穿上 Docker 的 t 恤](https://thenewstack.io/docker-just-changed-windows-server-as-we-know-it/)并在其主要开发者大会上邀请 Docker 的首席执行官上台，容器化市场的形状和结构看起来不像是野餐，更像是棋盘。本周，Docker 和 rkt 搬出了他们的皇后。

CoreOS 和 Red Hat 是新堆栈的赞助商。

通过 Flickr Creative Commons 的特色图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>