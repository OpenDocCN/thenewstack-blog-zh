# 容器和微服务引发了对更好的文件系统的探索

> 原文：<https://thenewstack.io/better-file-system-containers/>

无论是在操作系统层面还是在技术讨论中，文件系统通常都很低调。Red Hat 最近从其平台上对 [Btrfs](https://btrfs.wiki.kernel.org/index.php/Main_Page) 文件系统的[弃用](http://www.linux-magazine.com/Online/News/Red-Hat-to-Drop-Support-for-Btrfs)激起了人们对文件系统在容器化环境中的作用的兴趣。

作为 Linux 发行的基于容器的操作微服务，它们遇到了与文件系统相关的新挑战。Linux 供应商，包括 Red Hat、SUSE 和 Canonical，是容器领域的主要参与者。除了传统的操作系统，这些公司还构建了容器即服务平台来处理容器化的工作负载和微服务。紧随 [CoreOS](https://coreos.com/) 的 [Container Linux](https://coreos.com/os/docs/latest/) ，[红帽](https://www.openshift.com/)打造了[Project Atomic](https://www.projectatomic.io/)；Canonical 出了 [Ubuntu 核心](https://www.ubuntu.com/core)SUSE 发布了 [SUSE CaaS 平台](https://thenewstack.io/micro-os-suses-answer-container-os/)和 [Kubic](https://insights.hpe.com/articles/introducing-kubic-a-community-driven-container-as-a-service-platform-1708.html) 。

## 命名空间、重复数据删除、计划

“容器生态系统面临的最大挑战之一是文件系统目前不知道名称空间，”Red Hat Linux 容器高级技术产品经理 Ben Breard 说。尽管有几个概念可以用现有的文件系统创建各种名称空间，但是当前的限制带来了挑战，特别是在安全性和可用性方面，比如用户名称空间。

SUSE 全球产品和解决方案营销经理 Raj Meel 认为“重复数据删除”是现代挑战之一。

由于 SUSE 支持多个文件系统，重复数据删除问题可以通过现有的文件系统来解决，如 XFS 和 Btrfs。但这带来了新的挑战。Meel 说，你可以有“完美的”重复数据删除，这样就不会在重复数据上“浪费”空间，但它会带来相当大的性能损失，这种损失必须一直发生，不管数据的相关性如何。

CoreOS DocOps 的 Josh Wood 指出了集装箱化环境中的另一个问题:“永久存储已经倾向于本地化，”他说。为了实现现代基础架构的可扩展性和可靠性目标，它必须具备足够的动态性，以支持应用程序的自动调度和扩展，以及位实际存储在磁盘上的底层计算资源的自动重新调配

另一个更重要的挑战是在容器之间分割有限的 io 资源:“Blkio 节流和 IO 调度器平衡 IO 的能力都有所改善，但仍有很长的路要走，”Wood 说。

## 有什么解决办法？

我们仅仅触及了表面。我们可以继续前进，挖掘传统文件系统的问题。有什么解决办法？我们是否需要新的文件系统来解决这些问题？实际上，他们能做到吗？

“我们的重点不是编写新的文件系统，主要是因为它们需要数年时间来证明自己值得在其上存储关键的客户数据，”Red Hat 首席技术产品经理 [Mark Thacker](https://www.linkedin.com/in/markthacker/) 说。"一些新的文件系统从来没有做到这一点."

然而，有一些“相对”较新的文件系统，比如 [OverlayFS](https://www.kernel.org/doc/Documentation/filesystems/overlayfs.txt) ，确实有效地解决了其中的一些问题。但是 OverlayFS 并不新鲜。然而，这是一个很好的例子，说明了社区如何变得创新，用现有的解决方案来解决新的问题。

## 需要是所有发明之母。

“容器化给本地文件系统带来了几个挑战。也许最明显的例子是在共享的较低层；OverlayFS 的快速发展在很大程度上是由于容器运行时的需求。

Docker 的工程师 Anil Madhavapeddy 说:“在某些情况下，overlay2 是容器根文件系统的最佳选择。

但是对于文件系统，没有灵丹妙药。Meel 说:“每个文件系统都有其优点和缺点，而“最好的”通用文件系统实际上差别不大，但在任何方面都不突出。

大多数现有的文件系统确实具有处理现代工作负载的能力；各公司不断为这些文件系统添加新功能。

例如，[持久性存储设备](https://thenewstack.io/speed-kills-microsoft-prepared-windows-server-2016-persistent-storage/)(如 NVDIMMs)的即将到来挑战了许多关于容量、延迟甚至是内存与存储的假设。为了应对这些挑战，XFS 和 ext4 都进行了修改，以利用这些设备。

但是，萨克警告说，这些都是短期解决方案。从长远来看，围绕这些设备可能会构建更优化的工作负载，这将需要更多的工作和创新。“现代微服务架构，具有快速启动和关闭的要求，以及极端的图像内容重用，可能非常适合这些新的架构，”Thacker 说。

在 SUSE 方面，Meel 坚信 btrfs 是现代工作负载的最佳选择。SUSE 在它的 [SUSE CaaS 平台](https://thenewstack.io/micro-os-suses-answer-container-os/)和它的开源兄弟 [Kubic](https://insights.hpe.com/articles/introducing-kubic-a-community-driven-container-as-a-service-platform-1708.html) 中使用 Btrfs。Btrfs 创建者 Chris Mason 告诉我，他们在脸书的集装箱上使用 Btrfs。

红帽公司支持 XFS，后者正在 RHEL 和红帽企业 Linux 原子主机，其容器即服务平台上使用。“事实上，XFS 是我们唯一支持 OverlayFS 的文件系统，这是现代容器的一个要求，”Breard 说。

当 Red Hat 在 XFS 投资的时候，它也在进行一个新的项目来解决与文件系统相关的问题。它叫做【Stratis 项目。该项目是红帽在 2017 Linux Vault 大会上介绍的。

Project Stratis 是一个以更简单和可扩展的方式管理本地文件系统和设备的提议。Stratis 使用成熟的现有技术，如 XFS 和设备映射器，但将它们与卷管理、文件系统资源调配、数据保护集成在一起，就像卷管理文件系统一样，但不需要新文件系统所需的多年稳定性测试。

“虽然 Stratis 处于社区项目的早期阶段，但它确实有雄心勃勃的目标，包括:客户定义的数据保护 SLA、SSD / NVDIMM 缓存、利用不同容量的驱动器、易于使用的客户 CLI、易于集成的 API 以及主动监控和管理，”Thacker 说。

现在预测 Stratis 是否会被整个行业采用还为时过早，即使是像 SUSE、Canonical 或 Core OS 这样的竞争对手。但是它以前工作过:Systemd 是红帽技术在整个行业使用的一个很好的例子。

Stratis 可能是也可能不是最终的解决方案。不同的公司可能会继续围绕他们最了解的文件系统构建特性。公司也将继续使用混合技术来迎合他们的客户。

“我们致力于促进用户选择，这一理念也适用于文件系统。虽然 BTRFS 是一个受支持的选项，但我们也将继续通过我们的卷插件支持各种文件系统，”Madhavapeddy 说。“最终，有许多选择，每种选择对于特定类型的工作负载都有优势，我们希望鼓励并为用户提供这种灵活性。”

## 结论

Linux 内核维护者 Ted Ts'o 曾经说过，大多数文件系统都是在你需要一个通用文件系统的时代编写的。如今，你不需要很多功能，例如，日志，谷歌等公司正在移除或禁用此类功能。许多公司针对不同的工作负载混合使用文件系统，并针对这些特定的工作负载进行了优化。

但是，随着这些公司和社区围绕文件系统创建、即兴创作和创新新技术，他们面临一个非技术性的问题；这是文化。

“文件系统和容器社区倾向于以非常不同的速度发展，”Breard 说。“鼓励这些社区相互参与，而不是避免和解决彼此之间的问题，从长远来看，这将有助于每个人，并限制导致安全性和可用性问题的变通办法的类型，这些问题需要各方付出额外的努力，”Breard 说。

[科洛斯](https://coreos.com/)和[红帽](https://www.openshift.com/)是新堆栈的赞助商。

史蒂文·拉蒙[通过](https://unsplash.com/photos/ODbOdeQVF2Q) Unsplash 拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>