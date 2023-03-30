# CodeReady Workspaces 提供 Kubernetes-Native IDE

> 原文：<https://thenewstack.io/codeready-workspaces-delivers-kubernetes-native-ide/>

如果你想坚持到底，自己免费做所有的事情，栈就在那里等着你去做。您可以运行任意数量的 Linux 发行版，从命令行启动 Kubernetes，然后处理确保所有开发人员拥有兼容且安全的开发环境的难题。或者，如果您愿意，您可以选择 Red Hat 路线，它提供了所有这些工具，但是附带了支持、附加功能和中间件。

对于那些走红帽路线的人来说，确保兼容和安全的开发工具可能变得更容易了，因为红帽已经向公众发布了其 [CodeReady Workspaces](https://developers.redhat.com/products/codeready-workspaces/overview/) ，这是一个基于云的集成开发环境(IDE)，可以直接与[红帽企业 Linux](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux) 和 [OpenShift](https://www.openshift.com/) ，红帽基于 Docker 和 Kubernetes 构建的 PaaS 一起工作。就像这个堆栈中的其他工具一样，CodeReady Workspaces 也是基于一个免费的开源对应物— [Eclipse Che](https://thenewstack.io/close-look-eclipse-che/) 。

根据该公司的声明，CodeReady Workspaces 是“一个 Kubernetes 原生的、基于浏览器的开发环境，能够实现开发团队之间更顺畅的协作”，并且“旨在为企业开发团队提供一个可共享的开发环境，包括编码、构建、测试、运行和调试基于容器的应用程序所需的工具和依赖关系。”此外，CodeReady Workspaces 与众不同，因为它是“市场上第一个运行在 Kubernetes 集群中的 IDE，管理开发人员在 OpenShift pods 和容器中的代码、依赖项和工件。”

CodeReady Workspaces，就像它的开源对手一样，帮助团队更安全和有效地运作，Red Hat 开发人员体验和程序的高级主管 Brad Micklea 说，他以前也是 CodeEnvy 的首席运营官，code envy 开发了 Eclipse Che，两年前被 Red Hat 收购。

“Che 中的许多功能在大型组织中都很有价值。当你想到开发人员如何在大组织中工作时，他们不得不关注更多的应用程序，而不是他们的团队，”Micklea 说。“如果出现问题，需要围绕该任务迅速组建一个团队。他们必须构建运行时，获得代码库，并开始进行更改。这些过渡状态正是 Eclipse Che 方法带来巨大收益的地方。”

Micklea 说，CodeReady 工作空间真正大放异彩的地方是在 Kubernetes 优先的环境中。

Micklea 说:“与其他开发者 ide 不同，它们可以用来构建容器并部署到 Kubernetes，它们不是在 Kubernetes 是您所做的一切的本机或默认运行时的情况下设计的。“有了 CodeReady 工作区，从你开始编码的那一刻起，你就置身于 Kubernetes 的容器中。你别无选择，只能呆在库伯内特斯。”

[https://www.youtube.com/embed/S3auoOqwDS8?feature=oembed](https://www.youtube.com/embed/S3auoOqwDS8?feature=oembed)

视频

除了将 Kubernetes 置于 IDE 的中心之外，CodeReady Workspaces 还极大地简化了安全性和开发人员的加入。在传统环境中，少量源代码不断地从开发人员的个人计算机流向中央存储库。这意味着每台计算机都提供了一个攻击面。然而，使用 CodeReady 工作区，没有任何东西被移动到本地机器，而是集中托管，并通过基于 Web 的 IDE 或开发人员通过 SSH 选择的 IDE 进行访问。Onboarding 同样得到了简化，因为开发人员的环境是在 pod 内部复制的，而不是在他们的本地机器上，使用的是一种称为“工厂”的东西，它是“包含源代码位置、运行时和工具配置以及项目所需命令的模板”

Micklea 指出，与开源软件不同，CodeReady Workspaces 将以三个月为一个周期发布，以确保稳定性和支持。目前，[发布说明](https://access.redhat.com/documentation/en-us/red_hat_codeready_workspaces_for_openshift/1.0.0/html/release_notes_and_known_issues/release_notes)提供了一系列支持的语言，包括 Red Hat 支持的 Node.js 和用于 Red Hat Enterprise Linux 的 Java，以及社区支持的 C/C++。Net，Golang，PHP 和 Python。

红帽是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>