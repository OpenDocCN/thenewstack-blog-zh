# Kubernetes 为容器原生存储奠定了基础

> 原文：<https://thenewstack.io/kubernetes-brings-new-persistent-storage-options-containers/>

随着上个月 Kubernetes 1.6 的发布，出现了许多可以简化容器存储的生产就绪特性。Red Hat、CoreOS 和 Quantum Storage 已经在努力利用这些功能，使从 Kubernetes 内部管理大规模容器原生存储系统变得更加容易。

根据设计，容器是无状态的实体。它们应该被旋转和关闭，不会留下任何痕迹。但是它们包含的应用程序需要持久的(“有状态的”)存储来存储数据，例如配置数据和数据库。

一种方法是使用网络文件系统(NFS)为所有存储建立单个命名空间，但这在管理存储资源方面缺乏灵活性。另一种流行的方法是使用分布式文件系统，比如 Gluster 或 Ceph。但是这些可能很难自己管理。

容器和 Kubernetes 使得开发者部署分布式容器化应用程序变得非常容易；分布式文件系统本质上是分布式应用程序。某处的控制器需要进行资源管理、资源分配和再平衡。那么，为什么不让 Kubernetes 来做管理分布式文件系统的工作，尽管这有其固有的困难？ [Quantum](https://www.quantum.com/) 的首席技术官[巴萨姆·塔巴拉](https://twitter.com/bassamtabbara)认为:“当人们在云原生环境中运行任何应用程序时，都会面临同样的问题。

“在 Kubernetes 上运行存储集群是一种天然的选择。将它纳入范围并保持统一的管理界面，让一切都像一堆豆荚一样，难道不是很有意义吗？”巴萨姆说。“我认为有了像 Kubernetes 这样的协调器，存储集群变得更有弹性。”

事实上，Kubernetes 在配置分布式存储方面非常方便，就像它在配置其他分布式应用程序方面一样，这一批新的 Kubernetes 配置工具不仅可以简化(或破坏)容器存储，还可以简化过于复杂的[软件定义的存储](http://www.computerweekly.com/guides/A-guide-to-software-defined-storage)。

## 即时存储

这一新功能的关键是 Kubernetes 1.4 中首次引入的许多新特性，这些特性现在已经可以用于 Kubernetes 1.6 的生产。

一个是[动态存储供应](https://kubernetes.io/docs/user-guide/persistent-volumes/) 模块，它可能“对存储的生命周期和管理自动化非常有用，”在 Kubecon Europe 2017 大会上发言的[谷歌 Kubernetes 产品管理团队负责人](https://youtu.be/OIsCwc7qfTU?t=1358)[阿帕娜·辛哈](https://twitter.com/apbhatnagar)说。

Kubernetes 供应依赖于另一个新的生产就绪特性，[存储类](http://blog.kubernetes.io/2016/10/dynamic-provisioning-and-storage-in-kubernetes.html)，它提供了一种描述存储属性的格式，因此它们可以在不同的功能之间共享，以帮助实现自动化。

Kubernetes 使用“持久卷”的概念来封装后端存储。Sinha 解释说，Kubernetes 可以通过两种方式提供存储卷，动态或静态。在静态配置中，卷的创建必须事先完成，因此它们可以在以后与永久卷声明联系起来。

一种更快速、更高效的存储分配方式是通过新推出的动态预配置。在这种方法中，Kubernetes 将收到一个来自新启动的应用程序的请求，为自己创建一个存储卷，Kubernetes 可以使用插件为不同的存储类型提供存储卷。

借助动态存储供应，开发人员甚至不必提前向集群管理员发送存储分配请求。整个系统可以自动化。

为了帮助应用程序开发人员了解可用的存储选项，集群管理员使用存储类来描述现有的不同存储选项。在永久卷声明(PVC)中，应用程序仅使用适当的存储类指定所需的确切存储设置。

Kubernetes 随后调配一个新卷，然后将其绑定回 PVC。然后，应用程序可以使用 PVC 来装载新配置的卷。称之为即时供应。

“Kubernetes 将把卷安装到 pod 上，”Sinha 说。“pod 可能会死亡并移动到不同的节点，Kubernetes 会自动将存储重新装载到新节点。数据将仍然存在，因为 PVC 仍然存在。PVC 是不变的，并拥有对存储的所有权。”一旦声明被删除，卷也会被删除。

## 赫克提

但是 Kubernetes 仍然需要与分布式文件系统更紧密地集成，以使整个过程无缝。

正在进行的一项工作是 Heketi，这是一个基于 RESTful 的服务，可以使用 Kubernetes、 [OpenStack Manila](https://wiki.openstack.org/wiki/Manila) 或 Red Hat 的 [OpenShift](https://www.openshift.com/) 来动态提供和管理 [Gluster](https://www.gluster.org/) 分布式文件系统的整个生命周期。

实际上，Heketi 是一个位于 Gluster 之上的高级服务接口，可以简化卷的创建。通过 RESTful 接口，Heketi 可以接受来自 Kubernetes 的请求。Kubernetes Gluster provisioner 将“与 Heketi 交谈，后者将与 Gluster 交谈以创建卷，”Red Hat architect 的 Michael Adam 解释道，他在本月早些时候在波士顿举行的 Linux Foundation 的 Vault storage conference 上发表了关于 Heketi 的演讲。

Heketi 可以管理多个 Gluster 部署，并可以跟踪每个集群上还有多少空间。您可以向 API 请求所需的存储量，以及存储的类型或速度(即 SSD)。开发人员不应该知道使用了哪些磁盘，或者使用了哪个集群，所以所有这些都被抽象掉了。

一旦创建了新卷，Heketi 就将卷信息返回给 provisioner，provisioner 将该信息转发给调用者。

当存储管理员提出创建 Gluster 卷的请求时，Heketi 将在分布在服务器集群上的 Gluster 卷中分配所需的存储量，甚至跨多个故障域分配副本。软件格式化、安装并启动新创建的 Gluster 卷([试试这里的演示](https://github.com/heketi/vagrant-heketi))。

Gluster 处理复制和分发，因此这些职责不需要存储管理员或开发人员来承担。Gluster 卷由砖块组成(最简单的形式是节点中的本地目录)。可以通过各种调用访问 Gluster，包括来自 OpenStack 社区的标准 [POSIX 文件系统调用](http://pubs.opengroup.org/onlinepubs/9699919799/)、 [NFS](https://help.ubuntu.com/lts/serverguide/network-file-system.html) 、[中小企业](https://www.samba.org/cifs/docs/what-is-smb.html)、 [iSCSI](https://www.thomas-krenn.com/en/wiki/ISCSI_Basics) ，以及针对[对象存储](https://thenewstack.io/forget-file-system-future-scalable-cloud-storage-will-objects/)的亚马逊 Web 服务的 S3 兼容 [Swift](https://github.com/openstack/swift3) 。

因此，虽然可以使用外部 Gluster 集群进行 Kubernetes 供应，但为什么不直接进行下一步，将 Gluster 本身容器化呢？Red Hat 和存储领域的其他公司将这种方法称为“超融合基础架构”

Gluster 有自己的基于 FUSE 的 mount 命令，作为安装在每个存储节点和服务器上的 Gluster 客户端的一部分。与将笨重的 Gluster 胖客户机捆绑到每个容器中不同，容器所需的卷被装载到 Kubernetes 主机上，然后绑定装载到容器中。在容器内部，用户只能看到挂载的文件系统的目录。

Heketi 通过数据库跟踪集群的状态(这就是为什么一旦通过 Heketi 设置了 Gluster 卷，没有 Heketi 就不能更改其信息，以免跟踪信息变得不同步)。

Adams 指出，Gluster 容器在许多方面都不是典型的容器。它们是特权容器，因为它们通过主机网络而不是虚拟网络相互使用和通信。它们还被绑定到特定的节点，亚当承认这是一个决定，但不是每个人都喜欢。

为了简化通过 Kubernetes 部署 Gluster 集群的过程，Red Hat 团队领导了一个名为 [Gluster-Kubernetes](https://github.com/gluster/gluster-kubernetes) 的项目。这个软件包可以通过使用描述物理节点的拓扑文件来创建一个容器化的 Gluster 集群。它设置了 Heketi，并将拓扑文件传递给新创建的数据库(也是容器化的)，这样 Heketi 就可以配置集群。

## 车

一周后，在柏林的 KubeCon 会议上，Quantum 的 Tabbara 展示了另一种基于 Kubernetes 的存储控制平面，这种平面基于 Ceph 分布式文件系统，称为 Rook。“我们希望创建一个软件定义的存储集群，它可以在现代云原生环境中运行良好，”Tabbara 说。

[Kubernetes 为集装箱原生存储奠定基础](https://thenewstack.simplecast.com/episodes/kubernetes-sets-the-stage-for-container-native-storage)

Tabbara 指出了 Kubernetes 的清晰的关注点分离，这有助于澄清应用程序开发人员和存储管理员的工作角色。集群管理员处理不同的硬件资源，应该能够独立于应用程序开发人员来设置如何使用这些资源的策略。应用程序管理员应该能够按照存储管理员的策略轻松创建卷和使用存储。

在演示中，Tabbara 采用了一个没有外部存储的裸 Kubernetes 集群，并且仅仅通过使用 kubectl，就部署了一个 Ceph 集群。然后，他创建了存储类，然后部署了 MySQL 和 WordPress pod，通过 Rook 提供了卷(一位与会者呼吁 Tabbara 终止 WordPress pod，他最终这样做了，在 Kubernetes 中启动了一个进程，用一个新的副本自动恢复它)。

Rook 可以独立于 Kubernetes 工作，尽管该软件确实有一个独立版本。它与 Ceph 有很大关系。“我们认为 Ceph 是存储的 Linux，”Tabbara 说。

Rook 的作用在于“它从 Ceph 中抽象出一些复杂性。从 Rook 中暴露出来的概念是群集管理员会理解的概念，即存储节点、设备、SSD。这种抽象需要大量的工作。”

Rook 依靠 Kubernetes 来计算 Ceph 的哪些部分在哪里运行，并处理资源管理。Ceph 本身在保持数据安全和复制方面很聪明。

## 舵手

Kubernetes 非常像数据中心的操作系统。多亏了操作系统，就像你不用担心哪个 CPU 内核在你的计算机上运行应用程序一样，你也不应该担心哪个节点在运行你的分布式计算作业，这是 Kubernetes 的角色，CoreOS 工程师 Luis Pabón 在 Vault 会议上给了 T10 一个关于容器存储技术的演讲。

“这是一种新的思维方式，Kubernetes 负责整个集群，”Pabón 承认。“当容器从一个节点移动到另一个节点时，Kubernetes 确保连接(到存储)跟随容器，”他说。

Pabón 说，尽管有这么多好处，但是将一个文件系统塞进一个容器，让它可以被 Kubernetes 运行，仍然需要大量的调整和调节，即使是使用像 Heketi 这样的工具。带着这种想法，Pabón 创建了[军需官](https://github.com/coreos/quartermaster)，一个将存储系统部署到 Kubernetes 的框架。

军需官由 CoreOS 帮助贡献给 Kubernetes 的一个新功能驱动，叫做[操作员](https://coreos.com/blog/introducing-operators.html)。操作员是运行在系统上的容器，它知道如何部署和管理应用程序。CoreOS 已经创造了一个[普罗米修斯操作员](https://coreos.com/blog/the-prometheus-operator.html)和一个 [etcd 操作员](https://coreos.com/blog/introducing-the-etcd-operator.html)。现在，公司想用军需官来规范在 Kubernetes 部署存储的模式。

军需官是一个容器，它监听 Kubernetes 对用户定义的 Kubernetes 存储对象的调用。实际上，管理员创建了一个存储集群，定义了他们想要的集群属性，军需官执行所有要求来实现它。

由于属性是在 YAML/JSON 中定义的，它们不仅可以由管理员提供，还可以通过 API 以编程方式提供。

GitHub 页面上写道:“通过简化存储系统的部署，军需官使得在 Kubernetes 集群中轻松可靠地部署、升级和获得所需存储系统的状态成为可能。”“一旦部署，军需管理储存系统可以用来满足持续的数量索赔要求。军需官也可以用来帮助设置和测试由部署在库伯内特的集装箱存储系统提供的持久容量。

虽然 Heketi 和 Rook 都有自己的部署模式，但军需官的设计是为了在不同的文件系统中实现统一的部署。最初，军需官支持格鲁斯特，但随着时间的推移，帕邦希望扩展到 Ceph，NFS-甘尼萨，鲁克和其他人。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>