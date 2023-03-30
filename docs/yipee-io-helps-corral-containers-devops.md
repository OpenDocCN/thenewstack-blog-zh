# Yipee.io 帮助 DevOps 收集容器

> 原文：<https://thenewstack.io/yipee-io-helps-corral-containers-devops/>

Yipee.io 旨在帮助驯化 devops 和[微服务](/category/microservices/)环境的[容器，这些环境太容易失控了。](https://thenewstack.io/ci-cd-devops-and-containers-a-winning-trio/)

“当我们开始 Yipee 时，Docker 空间就像一个狂野的西部。你可以下载这些容器，但是你并不知道你会得到什么。项目创始人[马克·艾默斯](https://twitter.com/MarkEmeis?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)说:“这就像‘我们正在整理你的容器，给你试图使用的图像带来一些组织性’。

Yipee 是一家通过加速器计划在 [CA Technologies](https://www.broadcom.com/info/aiops/docker-monitoring) 内部运行的初创公司，该计划允许 CA 员工获得支持和资金，以开发他们自己的想法并将新产品推向市场。

加速器的其他项目包括一个用于会议即时议程的移动应用程序和为 Docker 团队提供工具链的 Qubeship。

Yipee 现在大约有 15 个月大，它建立在精益原则的基础上，包括微调想法，然后与该领域的许多人交谈，以了解你提出的解决方案是否有助于解决他们的问题。由此，出现了一组最基本的可行特征。有了这些功能，Yipee 正试图吸引更多的用户提供更多的反馈。

它本质上提供了三样东西:

*   应用程序的可视化建模。
*   能够为不同的编排器转换模型。
*   团队分享。

“在采访人们时，我们发现 Docker 有一些不容易让你理解的概念。不是说它们过于复杂，而是它们是新的。有些东西你必须编织在一起。这就是我们在 Yipee.io 中开发视觉建模器的地方，”Emeis 说。

目前最先进的是定义整个应用程序的 YAML 文件。如果您的应用程序中有这么多不同的服务，可能很难理解到底发生了什么。他说，再加上虚拟化网络、存储、内部基于主机的远程存储——所有这些对应用程序的运行至关重要的东西，将所有这些都捕获到一个 YAML 文件中——可能是多个带有 [Kubernetes](/category/kubernetes/) 编排引擎的 YAML 文件——所有这些都很难理解

Yipee.io 是一个可视化的建模工具，它可以让你布局你的服务，通过网络可视化地连接它们，添加存储，配置所有这些，让你的模型语义正确，这样你的应用程序就可以理解。

“在 Yipee，我们将您与编排环境隔离开来，并在 Docker 本身的 [OpenShift](https://www.openshift.com/) 、Kubernetes 或 Compose/Swarm 环境之间进行转换。我们希望你完全理解你的应用程序的模型，所以我们真的认为‘理解你的应用程序是什么’。了解您的应用程序、网络和卷存储之间的依赖关系。然后让 Yipee.io 去担心创建语义甚至正确的编排环境，在那里运行这个应用程序。

他说，它实际上不会为你在不同的云服务上进行编排——你可能已经有了自动化的流程。

使用 Yipee.io 的结果是一个配置文件或一组文件，比如说，Kubernetes，然后您可以在那个环境中运行。

如果你在桌面上做[作曲](https://docs.docker.com/compose/)。你对五六个服务、网络等进行建模，然后下载特定于你要编排的版本的文件，然后做**docker-dome up**。在您的环境中，它会从您在 Yipee 模型中确定的任何存储库中提取图像，然后启动所有这些服务，配置网络等。

它与 Compose v3、Red Hat 的 OpenShift 和 Kubernetes 一起工作，并将根据客户的反馈添加其他应用程序。

他说，Yipee 团队正在努力与其他 CI/CD 工具集成，例如一个 Jenkins 插件，它可以将模型从 Yipee 中取出，这样您就可以用它进行部署。

Emeis 说，它为团队分享提供了单一的事实来源。你可以注册一个团队账户，让多个作者贡献不同的 orchestrator 或应用模型，然后在整个开发团队中共享。Yipee 团队在内部使用它，这样每个人都可以下载当前的模型。

以 Docker Swarm v3 为例，当你让团队的其他成员使用 v2 时，你可以让一些人下载 v3 并在其上测试你的模型，Yipee 会为你完成转换。

到目前为止，该公司的九人团队正在对客户进行单独培训，以确保他们对 Yipee 有良好的体验。Emeis 说，它正致力于能够提供自我注册，并增加功能以跟上最新的 orchestrator 版本。

CA Technologies 和 Red Hat 是这个新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>