# Eclipse Che 7 成为 Kubernetes-Native，将 Eclipse IDE 留在后面

> 原文：<https://thenewstack.io/eclipse-che-7-goes-kubernetes-native-leaves-eclipse-ide-behind/>

本周在三藩市举行的 Oracle Code One 大会见证了由 [Eclipse 基金会](https://www.eclipse.org/org/foundation/)创建的集成开发环境 [Eclipse Che 7](https://www.eclipse.org/che/) 的发布。Eclipse Che 起源于[桌面 Eclipse IDE](https://www.eclipse.org/ide/) ，但现在随着 Che 7 的发布，它独立成为该基金会在一份声明中所称的“第一个 Kubernetes-原生 IDE”。根据 Eclipse 基金会执行董事 Mike Milinkovich 的说法，Eclipse Che 7 不仅在 Kubernetes 原生操作上，而且在代码库上都不同于以前的版本。

“这是全新一代的工具平台。几乎没有来自桌面 IDE 的代码作为 Eclipse Che 的一部分。这是一个全新的代码库，”Milinkovich 告诉新堆栈。“这是一个全新的平台，从一开始就被设计为云原生和网络优先。我们所说的 Kubernetes-native 是指您认为的开发人员工作区被容器化，将在 Kubernetes 集群中运行，提供大量基础设施，使开发人员更容易采用 Kubernetes。”

Eclipse Che 7 现在提供了一个基于 web 的 IDE，该 IDE 基于扩展版本的 [Eclipse 忒伊亚](https://www.theia-ide.org/)，它提供了浏览器内的 Visual Studio 代码体验，并在公共 Kubernetes 集群或内部数据中心中运行。Milinkovich 解释说，Che 7 提供的关键价值是，通过在 Kubernetes 上托管开发人员工作区和代码本身，许多过程从开发人员那里移除，使他们能够解决代码中的问题，而不是配置或编排中的问题。

“如今，开发人员面临的难题是设置 Kubernetes、在 Kubernetes 上启动和运行应用程序以及再现应用程序环境的学习曲线。Che 处理这些开箱即用的东西，这样开发人员就不必花太多时间担心如何建立 Kubernetes。“从一个项目到另一个项目的转换可能需要大量的工作来重新配置您的桌面 IDE。Che 的概念是开发人员工作区是 Docker 容器，它能够创建运行时堆栈，这意味着开发人员不必再担心这种配置问题。您可以比以前更容易地向整个团队推广新的配置。我们认为 Che 是一个全新的平台，专门针对 Kubernetes 开发人员的需求而构建。”

如果这些听起来很熟悉，那可能是因为 Red Hat 抢先了 Eclipse Che 一步，去年 2 月发布了基于 Eclipse Che 的 Red Hat CodeReady Workspaces ,具有在 Kubernetes 上托管整个开发人员工作区的能力。 [Brad Micklea](https://www.linkedin.com/in/bradmicklea) ，Red Hat 开发体验高级主管，负责 CodeReady Workspaces，提供了 Eclipse Che 的价值主张总结。

Micklea 在一份声明中说:“有了 Che 7，云原生开发人员需要的一切——包括 IDE、其插件及其依赖关系——都可以作为 Kubernetes 应用程序运行，因此一切都变得可重复和可再现，而在此之前，开发团队必须花费大量时间来构建和维护开发人员环境。”“现在，开发人员可以更快地在 Kubernetes 中建立一个镜像生产应用程序的开发环境，Che 将负责添加他们所需的开发、构建和调试工具。”

虽然 Red Hat 可能已经先行一步，Milinkovich 说，通过加快 Eclipse Che 的速度，它也使其他项目能够提供这种级别的功能——而不仅仅是一个供应商的一个项目。

“如果回到 90 年代早期，每个供应商都有自己的 IDE，而 Eclipse 桌面 IDE 围绕着一个单一的平台联合了整个行业。Milinkovich 说:“我们看到历史在很大程度上重演，因为有太多的单一用途 web IDEs，我们看到了 Che 真正帮助业界围绕一个厂商中立的开源平台建立这些工具的机会。“这是云原生的新工具平台。你可能已经注意到了，问题是什么已经不重要了，答案是 Kubernetes。因此，在某种程度上，Kubernetes 正在定义新的混合云、多云和本地世界，开发人员和他们的经理希望能够在它们之间灵活移动，Eclipse Che 将成为帮助实现这一目标的首选工具集。”

Oracle 和 Red Hat 是新体系的赞助商。

来自 Pixabay 的 Olya Lolé拍摄的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>