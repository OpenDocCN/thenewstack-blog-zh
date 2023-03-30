# SaltStack 在 Google Kubernetes 中的“大”角色，以及为什么不可变的基础设施使云成为一台巨型计算机

> 原文：<https://thenewstack.io/saltstacks-big-role-in-google-kubernetes-and-why-immutable-infrastructure-makes-the-cloud-a-giant-computer/>

自从去年我在 OSCON 采访这个团队以来，SaltStack 已经取得了很大的进步。上周，我在 VMworld 上与他们进行了一次简短的采访，内容是关于 SaltStack 如何在 [Google Kubernetes](https://googlecloudplatform.blogspot.com/2014/08/containers-vms-kubernetes-and-vmware.html) 中发挥重要作用，该项目于两个月前宣布，将谷歌在数千台机器上操作应用程序的专业知识带入其中。

[Google Kubernetes 如何使用 SaltStack](https://thenewstack.simplecast.com/episodes/how-google-kubernetes-uses-saltstack)

在采访中，SaltStack 的 Matt Merservy 简要讨论了管理平台如何在安全的环境中快速加速 Google Kubernetes 和测试应用程序中的计算资源，并在必要时将其缩减。这是 Kubernetes 的一个重要方面，但是应该注意的是，SaltStack 并不用于调度容器。SaltStack 的营销副总裁瑞德·格劳泽说，集装箱调度是谷歌代码。然而，在 Kubernetes 之外， SaltStack 是首批提供大规模 Docker 和容器环境部署和管理的公司之一

[https://www.youtube.com/embed/EVq6hn25lYM?feature=oembed](https://www.youtube.com/embed/EVq6hn25lYM?feature=oembed)

视频

Microsoft Azure 还将 SaltStack 用作 Kubernetes 中的核心编排管理引擎，使其在这个新的编排技术生态系统中发挥更大的作用。但是 SaltStack 在 Kubernetes 中的作用有多大取决于你和谁交谈。将来会有其他方式来提供 Kubernetes。例如，[运行 Kubernetes](https://coreos.com/blog/running-kubernetes-example-on-CoreOS-part-2/) 的 CoreOS 指令使用了一种叫做[云配置](https://coreos.com/docs/cluster-management/setup/cloudinit-cloud-config/)的类似方法，首席执行官 Alex Polvi 在一封电子邮件中将其描述为更像是“运行程序的参数，而不是将服务器塑造成其他东西的脚本”

CoreOs 方法指出了一个更重要的故事，它与管理平台不断变化的环境以及与现有配置管理环境的决裂有关。SaltStack 反映了这种转变，Ansible 等其他新兴服务也是如此。Docker 和 Kubernetes 等平台是这一转变的催化剂，改变了将云服务整合成《连线》的 Cade Metz 所说的一台巨型计算机的要求。Pivotal 首席执行官保罗·马里茨(Paul Maritz)也是这样描述的。在将 Pivotal 从 EMC 剥离出来之前，Maritz 领导了 VMware 多年。现在，Pivotal 和 VMware 与 Google Kubernetes 和许多其他公司合作，使这台巨型计算机成为现实。它正在发生，但不一定是以我们期望的方式。客户机/服务器系统需要配置管理。这种需求给了木偶和厨师以及诸如 SaltStack 等新服务以信任。

但随着分布式系统的兴起，需要重新思考这些方法，并寻找能够更有效地管理这些大型计算机的替代方法。看看 Google，他们有 Borg，但那是 Google 规模的系统，很明显它需要更好的集群管理。因此，他们创建了 Kubernetes 作为一个开源项目，从静态管理转向动态管理，这样就可以在他们所谓的“pods”中管理集群这些豆荚就像一簇簇容器，充当着它们自己的网络。

现在，随着这种管理“大型计算机”的新方式的出现，管理应用程序的方式也有了不同。完成这个配置代码使其工作的过程并不容易。更简单的做法是把它想象成一个可以被删除并替换为新数据的数据结构。这就出现了各种各样的关于安全的问题([想一想认证](https://thenewstack.io/dont-be-a-saas-hypochondriac/))、联网(想一想开放虚拟交换机等等。)和存储(想想软件定义的)以及构建松耦合系统的新方法(想想微服务)。

现在的问题是，随着转移到更缥缈的环境变得流行，这些新服务会变成什么样。例如，[不可变基础设施](http://blog.codeship.io/2014/07/22/immutable-infrastructure.html)的概念将导致更多关于配置的心理构造。从一些对话和阅读像 Chad Fowler 这样的聪明人的帖子来看，很明显，管理一个实例的所有不同部分所带来的大量问题花费了太多的时间。软件升级不应该是一个问题。东西会被替换。如果数据结构可以被替换，就像他在 [InfoQ](http://www.infoq.com/articles/virtual-panel-immutable-infrastructure) 上所说的那样，那么许多配置调整就变得没有必要了。福勒写道，这与函数式编程语言的兴起相关，函数式编程语言提供了用单赋值变量创建不变程序的方法。

那么，为什么不在基础设施中采用这种方法呢？如果你完全知道一个系统是通过自动化创建的，并且从创建的那一刻起就没有改变过，那么我上面描述的大多数问题都会消失。需要升级吗？没问题。建立一个新的升级系统，扔掉旧的。新的应用程序版本？同样的事情。用新的版本构建一个服务器(或映像),并丢弃旧的版本。

对更加自动化、不可变的基础设施的需求将改变开发人员构建和部署应用的方式。目前，SaltStack 作为启动和配置分布式系统的一种选择方式正在受到关注。但是未来可能会更加自动化，更像博格人，可以与自动化、可编程的机器人集群相媲美。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>