# CNCF 接受 Docker 的 containerd 和 CoreOS 的 rkt 作为孵化项目

> 原文：<https://thenewstack.io/separate-votes-cncf-adopts-dockers-containerd-coreos-rkt/>

在周三柏林 KubeCon 期间结束的一致投票过程中，[云原生计算基金会的](https://www.cncf.io/) [技术监督委员会](https://www.cncf.io/about/technical-oversight-committee/)批准了 [Docker Inc .的动议，捐赠**container d**](https://thenewstack.io/docker-donate-container-runtime-containerd-cloud-native-computing-foundation/)——其核心容器运行时的当前化身——作为 CNCF 官方孵化项目。在同一次会议上，TOC 还一致投票通过采用 CoreOS 的容器运行时。

“容器编排者需要社区驱动的容器运行时，”CNCF 执行董事 Dan Kohn 在周三的一份正式声明中写道，“我们很高兴拥有 containerd，今天每个运行 Docker 的人都在使用它。成为 CNCF 的一员将为生态系统内更广泛的合作带来新的机遇。”

到目前为止，很可能支持世界上大多数虚拟工作负载容器的引擎不再属于 Docker，而是由一个成员包括 Docker 的独立机构管理。

Docker Inc .有兴趣向外部组织捐赠 containerd，这已经不是秘密。一个月前，在 Docker 主办的旧金山 containerd 开发者聚会上，该公司承认了此类交易发生的可能性。就在两周前，CNCF TOC 成员兼 Docker 首席技术官 Solomon Hykes 告诉 CNCF，他的公司打算有效地剥离其对该软件的专有权利，但尚未决定如何进行。

Hykes [当时写道:“我们的目的是转移到一个 github 组织，这个组织 1)不是 Docker 品牌的，2)由 Linux 基金会控制。](https://github.com/cncf/toc/pull/32/files)

![](img/d034e8b72232c7b15f156d044bd5b962.png)

Hykes 还宣布了 Docker 捐赠“其他项目”的意向，但没有指名道姓。Hykes 收到的唯一轻微阻力来自 Kohn，他解释说，虽然他的团队很乐意主持 Docker 创建的更多项目，但将所有项目捐赠给同一个基金会可能没有直接好处。

除了那份建议，没有人反对 Docker 的举动，包括 CoreOS 开发者 Jonathan Boulle。在由整个社区贡献的非约束性选民中，也一致支持 Docker。

虽然 Docker 和 CoreOS 之间的捐赠姿态不是联合或组合的——正如 [Docker Inc .本月早些时候通知新堆栈的](https://thenewstack.io/chess-games-cloud-native-world/)——CNCF 成员确实通过相同的邮件列表消息了解了两个投票 docket。

周三发布到 GitHub 的文档采取措施区分 rkt 和 containerd，使项目的新成员更加清楚这两个组件实际上是不可互换的，尽管它们都被称为“容器运行时”。文档指出，rkt 是无守护进程的，因此依赖于 [systemd](https://thenewstack.io/unix-greatest-inspiration-behind-systemd/) 进行引导，[不像 Docker 的 containerd](https://thenewstack.io/why-docker-containers-and-systemd-drive-a-wedge-through-the-concept-of-linux-distributions/) 。

“与该项目的固执己见和限定范围的性质相一致，”CNCF 文档继续说道，“rkt 不包括任何用于构建容器映像的本机工作流，而是期望与构建系统结合使用，如 [Dockerfile](https://docs.docker.com/engine/reference/builder/) 、 [acbuild](https://github.com/containers/build) 或 [box](https://github.com/erikh/box) 项目。”

## CRI-O 向何处去

CNCF 的 CNCF Kubernetes Container orchestrator 开发人员面临的一个问题是——如果不是现在，那么很快——他们打算如何进行他们的容器运行时接口(CRI)项目。正如 Google 工程经理和 Kubernetes 首席开发人员 Tim Hockin 在 Docker 上个月的内部峰会上指出的，它的目的是使各种容器运行时可以插入到 Kubernetes 中。现在，CNCF 掌管着这个品种的大部分。

Hockin 对他的团队在 Docker Engine 上构建 CRI 的决定表示了持续的保留。他说，其中“制作容器的调用链相当惊人”，用图表表示了从 kubelet 到 runc 组件的四次跳跃。他警告说，如果每一跳都出了问题，就很难追踪。当 Docker 对其引擎进行更改时，他补充说，“对我们来说，验证 Docker 的新版本成为一项越来越大的任务，这些新版本以新的有趣的方式出现，或者只是引入新的非常微妙的不兼容，而这些不会给我们带来任何价值。”

这是 CRI-O 项目的灵感来源——努力构建一个基于 runc 的、只运行的容器运行时，使 Kubernetes 能够运行已经构建好的容器。但是对于这次会议，Hockin 建议转而直接支持 containerd。

“这似乎是一个更好的匹配，一个比 Docker 通过 Docker API 给我们的更低级的原语，”Hockin 解释说，“这正是我们需要的。老实说，containerd 的设计再好不过了，完全符合我们对 Kubernetes 的要求。”

因此，周三完成的交易似乎给了霍金和他的同事们一份礼物，这份礼物是 CRI-O 在现状保持不变的情况下(它从来没有这样做过)应该赠送的。就在上周末，[在 GitHub](https://github.com/kubernetes/kubernetes/pull/43655) 上发布了一个将 containerd 直接与 Kubernetes 集成的概念验证包。

Hockin 在推特上发布了 POC 项目的存在，然后很快就跟进了这条消息:“在一个真正开放的开放项目中，没有人能让你变得重要，除了你自己。只有你能让你变得重要。”

[云本地计算基金会](https://www.cncf.io/)和 [CoreOS](https://coreos.com/) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>