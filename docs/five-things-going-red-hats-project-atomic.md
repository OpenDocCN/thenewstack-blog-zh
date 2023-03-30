# 红帽的原子项目正在进行的五件事

> 原文：<https://thenewstack.io/five-things-going-red-hats-project-atomic/>

红帽的 [Project Atomic](http://www.projectatomic.io/) ，以其轻量级容器化操作系统 [Atomic Host](https://thenewstack.io/project-atomic-creates-infrastructure-for-linux-containers/) 而闻名，实际上本身并不是一个“项目”，而是无数容器项目的整体品牌。

Project Atomic 铭牌下有超过 [30 个 GitHub 库](https://github.com/projectatomic/)。有些主要是 Red Hat 开源项目，其他的是基于 Linux、Docker、Kubernetes 栈的更广泛的社区。

这些项目包括原子命令行界面、Docker 补丁、公共 Ansible 剧本、[原子构建器包](https://github.com/projectatomic/adb-atomic-developer-bundle)等等。例如，OS 升级 [OSTree 项目](https://github.com/ostreedev/ostree)从 [Gnome](https://www.gnome.org/) 发展而来，并拥有一个不断增长的社区。

Red Hat 软件工程师 [Colin Walters](https://github.com/cgwalters) 和项目原子社区负责人 [Josh Berkus](https://github.com/jberkus) 最近讨论了开源工作的方向，强调这些项目与 Red Hat 的商业产品是分开的。

“对我们来说，真正的挑战是维护大量不同的数据流。在这些社区中，我们仍然保持着 [RPM 模型](http://www.ibm.com/support/knowledgecenter/SSUS84_7.5.1/com.ibm.ram.doc/topics/c_rpm_library.html),而通过 Project Atomic，我们正努力向容器化发展。我发现我们更大的挑战之一是保持两种做事方式。这很棘手，”沃尔特斯说。

“我们试图在现有的基础上继续发展。在 Fedora 和 CentOS 社区中，有人维护基础设施，如内核和用户空间。我们正在提供交付和管理 it 的新方法。这只是两种方式的挑战。”

在项目原子焦点中:

**寻求不可变的基础设施**:该项目试图在操作系统层面实现[不可变的基础设施](https://thenewstack.io/a-brief-look-at-immutable-infrastructure-and-why-it-is-such-a-quest/)。应用程序容器化的好处之一是，与传统的部署和配置方式不同，在应用程序级别，您可以使用容器先配置，然后部署。

Berkus 解释说:“配置系统在你的部署速度和你管理大型基础设施和分布你的团队的能力方面成为一个大的瓶颈。”

“因此，不可变基础设施的理念是你可以…设计容器映像和编排系统，以便在部署容器时，它会以正确的配置和它需要的所有位启动。

“运营人员会说，他们不想只为用户应用程序这样做，他们想为整个基础架构这样做。那么，我们是否也可以配置，然后部署基本操作系统呢？原子主机思想的一个关键部分是，通过这种基于 OSTree 的分发，即操作系统的部署后，您不需要进行配置，或者只需要进行少量的配置。部署是一种单一的开关操作。”

OpenSUSE 项目的成员和其他人正在推进系统容器的概念。

其思想是，您需要特殊的容器，这些容器可能需要主机系统上的许多特权，这些特权不会由通用容器管理器管理，因为它需要在系统启动时启动。Berkus 说，例如，如果你有软件定义的网络，那么这个容器必须是系统的基础。

“我们有可用的系统容器，但我们仍在努力发展，因为我们仍在努力为系统容器开发一个规范，它将被许多 Linux 发行版接受，而不仅仅是 Red Hat 发行版，”他说。

**Atomic Workstation:**Atomic Host 实际上有 Fedora 和 CentOS 两个版本，Fedora 社区中的一些早期采用者正在使用它作为他们的桌面。这些开发人员想要运行 [Fedora Rawhide](https://fedoraproject.org/wiki/Releases/Rawhide) ，这是日常构建。过去，在笔记本电脑上运行它可能会导致无数问题，包括让 wi-fi 完全停止工作。

“有了 Atomic Host 进行二进制原子更新和回滚的能力，你可以把你的笔记本电脑放在 Fedora 上，在当前版本上工作，因为你可以随时回滚到以前的版本，”Berkus 说。

**包分层:** [包分层](https://blog.verbum.org/2016/04/)是 8 月红帽企业版 Linux 原子主机 7.2.6 版本中实现的[特性](http://news.softpedia.com/news/red-hat-announces-the-release-of-red-hat-enterprise-linux-atomic-host-7-2-6-507232.shtml#ixzz4IzMreFnb)。

“如果你看看生态系统，就会发现 yum 等基于包的系统与 Chromebooks 和 ChromeOS 等产品中使用的图像类型系统之间存在这种差异。我们的目标是从一开始就是一个混合的形象和包装系统，”沃尔特斯说。

“和 CoreOS、Chromebooks 做的不一样。人们将在他们的 Chromebook 中运行 Debian 或 Fedora 的 roots。我们一直在研究一种模型，在这种模型中，你可以复制一个基础，在基础上添加包，并且容器中仍然有大多数东西。在我们最近的版本中，我们已经增强了分层包的工作。

“我真的很高兴，因为不是所有东西都可以轻松装箱。例如， [PAM](http://tldp.org/HOWTO/User-Authentication-HOWTO/x115.html) (可插拔认证)模块或在较低级别(内核模块)挂钩到操作系统的东西，我认为包分层工作得非常好。”

**CentOS 原子主机的持续集成版本:**这个最近公开的[版本](http://www.projectatomic.io/blog/2016/07/new-centos-atomic-host-releases-available-for-download/)可以让你相当容易地恢复到稳定版本。

“当我们谈论系统容器和我们的一些新开发工作时，我们有一个公共的连续交付轨道，我认为这对开发人员非常有用。我们正在努力将其扩展到使用容器——容器化 Kubernetes 本身以及我们的一些其他功能。沃尔特斯说:“我们真的也想做一个持续交付型的模型。

物联网:他们没有预料到物联网供应商对 Atomic OS 的需求。

“如果您是一家供应商，并且您正在向一台远程设备推送安全更新，但您的渠道有限，没有控制台，也没有对该设备的物理访问，您需要该更新要么有效，要么无效。你不能让它部分部署，因为没有办法排除故障，”Berkus 解释说。

“我们还没有为 Atomic Host 提供官方的 ARM 端口，但是有人会自己创建一个，因为他们需要它。…这是一个没有得到很好服务的使用案例。如果这种子社区起飞，我们可能会进行另一轮原子主机，精简需求，因为例如，这些用户不一定需要内置于现有原子主机中的 Kubernetes，因为他们不是在做集群，而是在做单个设备。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>