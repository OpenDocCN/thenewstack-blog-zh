# 不同的 VMware:API 驱动的虚拟机管理程序和面向 Docker 的 vSphere

> 原文：<https://thenewstack.io/a-different-vmware-an-api-driven-hypervisor-and-a-docker-oriented-vsphere/>

VMware 的云原生应用程序团队继续努力让开发人员成为数据中心的一流用户，今天在 DockerCon 上推出了两项新技术预览版— VMware AppCatalyst 和 Project Bonneville。

VMware 产品管理和架构高级总监 Jared Rosoff 表示:“我们已经花了大量时间来研究开发人员实际上是如何构建这些云原生应用程序的，并寻找我们可以减少开发人员工作流和 IT 数据中心工作流之间摩擦的方法。

*   AppCatalyst 是一种 API 和命令行界面(CLI)驱动的管理程序，旨在为开发人员提供一种在桌面上复制私有云的简单方法。它的特点是[项目光子](https://thenewstack.io/the-role-for-vmwares-project-fargo-in-the-docker-ecosystem/)，一个开源的最小 Linux 容器主机，Docker 机器和一个与流浪者的集成。

这是 Mac OS X 的免费产品[在这里](http://www.vmware.com/go/communities-appcatalyst)(需要注册)。

*   **Project Bonneville** 将 Docker 容器无缝集成到 VMware vSphere 平台中，允许管理员使用他们现有的管理流程和工具。这仅仅是一个预览；罗塞夫说，VMware 尚未决定如何最好地将其包装成一种产品。

Rosoff 说，虽然开发人员使用其 Fusion 和工作站产品，但该公司看到了一个机会，可以通过 AppCatalyst 为他们创造更好的体验。

他说:“我们希望在你的数据中心使用所有的 API、存储、网络抽象和其他类型的服务，并在你的桌面上模拟它们。”虽然它计划最终添加网络和存储抽象，但目前还不可用。

他说，大多数软件开发人员都在分布式系统上工作，但是很难在桌面上运行这些分布式系统。部分原因是虚拟机管理程序旨在运行基于图形用户界面的工作流来创建虚拟机，而不是 API 驱动的工作流。Fusion 不像 ESX 那样基于相同的虚拟机管理程序，它没有虚拟存储和虚拟网络，这些东西可能会在您的应用程序中使用。

AppCatalyst 利用了与 Fusion 或 Workstation 或 ESX 相同的虚拟机管理程序，“但我们已经删除了 GUI，因为它碍事，”他说。这是第一个捆绑了 VMware 在 4 月份推出的 Photon container 主机运行时的虚拟机管理程序。

“关于 AppCatalyst 的事情是，如果你正在运行容器工作负载，你根本不需要担心虚拟机或 Linux 实例，你只需要启动 AppCatalyst，你可以指向 Docker，就好像你的 Mac 有本机容器支持一样，”他说。

与此同时，Bonneville 项目基本上是 Docker 容器引擎和 ESX 系统管理程序的合并。

对于开发人员来说，它使 vSphere 基础架构看起来像一个 Docker 主机。他们可以创建容器，使用 Docker Hub 或任何存储库中的任何映像，但每个容器实际上都通过 vSphere 封装在虚拟机中。

“它融合了两个世界的精华——开发人员可以在他们的桌面上使用真正简单的 Docker 工作流，但对于数据中心管理员和 It 运营人员来说，容器在所有管理系统中都以虚拟机的形式出现。你可以使用数据中心管理工具的整个生态系统，”他说。

虽然开发人员喜欢 Docker，但运营人员一直担心管理和安全问题。Rosoff 说，容器内的应用程序对他们来说是不可见的，并且在他们的日志聚合平台之外运行。

因此，虽然 VMware 希望为开发人员保留 Docker 的用户体验，但它希望提高运营方面的管理能力。

对于开发人员来说，数据中心看起来就像 Docker 主机在笔记本电脑上的样子。

“在后端，Bonneville 将 Docker API 与我们在 vSphere 6 中引入的 VAS VM clone 技术相集成，”他解释道。这是该公司集成分叉技术的地方，以前被称为 [Project Fargo](https://thenewstack.io/the-role-for-vmwares-project-fargo-in-the-docker-ecosystem/) ，这是一种启动速度更快的轻量级虚拟机，看起来和感觉上都像一个容器。

“因此，当你启动一个容器时，正如 Bonneville 所做的那样，它会派生出虚拟机，并在虚拟机中运行你的容器。对于开发人员来说，您可以获得无缝体验。它在其他地方看起来就像一个 Docker 运行时。有了运营团队，您可以从包装这些容器的虚拟机中获得非常强大的安全隔离。它们以虚拟机的形式出现在您的管理工具中，您可以应用与现有数据中心相同的安全模式和治理模式，”Rosoff 说。

十个月前，VMware 宣布计划通过与 Docker 和 Google Kubernetes 的[合作来拥抱容器技术。VMware 副总裁兼云原生应用首席技术官 Kit Colbert 表示，公司将在未来几个月](https://thenewstack.io/vmware-teams-with-docker-and-google-further-boosting-the-container-ecosystem/)发布一系列[公告。](https://thenewstack.io/amid-container-vs-vm-hype-vmware-draws-docker-closer/)

[4 月，它宣布了 Project Lightwave](https://thenewstack.io/vmware-announces-cloud-native-tools/) ，一个容器身份和访问管理解决方案；它的轻量级 Linux 操作系统 Photon 而它的分拆公司 Pivotal 宣布了 Lattice，这是 Cloud Foundry 的集群化容器调度、路由和日志聚合的轻量级包装。

IDC 分析师 Gary Chin 是云和虚拟化系统软件的研究经理，他认为 AppCatalyst 是为了吸引开发人员，开发人员是该公司的新受众。它的传统客户群一直在运营方面。他认为 AppCatalyst 更多的是为了获得 VMware 更大平台的采用。

他指出，通过 Bonneville 项目，VMware 正在优化容器的虚拟机管理程序，而不仅仅是将容器主机插入虚拟机。

“很明显，VMware 在虚拟机管理程序方面有着悠久的历史和投资，你可以看到他们为什么更喜欢这种模式，”他说。

在业界关于裸机与虚拟化容器的讨论中，虚拟化为容器提供了额外的安全性和特性。他说，大多数客户已经有了虚拟化，而且技术非常成熟，所以开始部署容器是合乎逻辑的。

“然而，虚拟化给容器带来了一些开销和低效，这是 VMware 试图消除的异议。我们也看到英特尔用 Clear Containers 展示了类似的东西，微软也暗示了在下一代 Windows 服务器中使用 Windows containers 和 Hyper-V 的类似模型。

“每个人都在试图减少虚拟化容器的启动时间和内存使用，试图实现两全其美，”他说。“在商业企业市场，我们已经看到大多数容器都是虚拟化部署的，这很可能将成为未来的主流模式，裸机容器则留给更多的利基场景。”

“如果这种混合虚拟机管理程序/容器技术确实可行，并且能够提供两者的最佳优势，那么客户就不必非要选择其中一个。”

VMware、Pivotal 和 Docker 是新体系的赞助商。

专题图片: [Thomas Anderson](https://www.flickr.com/photos/senoranderson/) 的[驾驶沃尔沃](https://www.flickr.com/photos/senoranderson/3363262014/in/photolist-68cAC7-qApHxE-kATkk-9w8eWL-3f2msW-4x2VzV-57CQyi-scyJrC-dtNMk2-6qnFNw-39cTno-5yoD2z-nWLzWw-5ysWZE-94DQwV-meZASP-dcr6LN-95ZYQH-sPhey-p29BJ2-6HsUwj-nK5Uuy-ekmC86-qrcSxK-fnu1NJ-dC4vsD-pQoLRf-6YWwXp-jH3uEM-8PEwKj-dGFJ4M-b5nAqK-cfs16N-meZE2e-dHT3Q3-vRLVd-iNmvEe-pLnSeN-dYdqhF-95sjWq-sYsSp-o5UjiH-o1bEXY-5c57BW-qutH67-dum3Ah-wEM4b-aNMMCt-5a5XJH-ss52zb)，2.0 的 [CC 授权。](https://creativecommons.org/licenses/by/2.0/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>