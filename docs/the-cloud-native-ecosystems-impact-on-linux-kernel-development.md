# 云原生生态系统对 Linux 内核开发的影响

> 原文：<https://thenewstack.io/the-cloud-native-ecosystems-impact-on-linux-kernel-development/>

很长一段时间以来，Linux 内核开发都集中在改善桌面和服务器体验上。从扩展的硬件支持，到安全性，再到性能，一切看起来都是高度集中的，就像一台润滑良好的机器一样在前进。

但后来，IT 领域发生了一些变化。容器和云似乎突然变得对企业至关重要。这意味着内核开发人员必须考虑这种发展趋势。从表面上看，这种变化似乎是新工具和新的服务部署思维方式的无缝集成。

当然，事情并不总是像它们看起来那样…至少在表面上是这样。本来应该是微小的变化，当然变成了影响深远的事情。

## 考虑 Docker Hub

典型的例子。最近，Docker [披露了一个未知方获得了对 Docker Hub 数据库的未授权访问](https://thenewstack.io/a-week-later-docker-offers-scant-details-on-hub-attack/)。通过这种未经授权的输入，攻击者获得了近 190，000 个帐户的敏感数据。这本身就是个坏消息。用户信息存在风险。密码、电子邮件地址、姓名——我们更愿意保密的信息。

但是考虑一下:这些信息也可能让攻击者获得用户上传的图片。只需几个快捷的命令，恶意软件、特洛伊木马和其他具有恶意目的的应用程序和/或服务就可以轻松重建这些图像。如果正确的图像被修改并上传，数以千计(如果不是数百万的话)不知情的 Docker 用户可能会删除图像并部署为窃取而构建的容器。

现在我们有一个问题…一个内核社区必须考虑的问题。对于那些关注安全性的内核开发人员来说尤其如此。

[约翰·莫瑞罗](https://www.twistlock.com/about-us/team/john-morello/)，集装箱安全公司[扭锁](https://www.twistlock.com/)的首席技术官，在 Docker Hub 问题上这样说道:

*Docker Hub 是攻击一些下游目标的渠道，他们知道这些目标正在使用 Docker Hub 的图像，因为你所说的基本上是在毒害上游，至少是上游非常远的部分，软件供应链的一部分。举例来说，如果你知道组织 x 正在使用 Docker Hub 上的特定存储库，而你想渗透到组织 x 中，那么一种机制就是破坏他们在 Docker Hub 上使用的存储库，将你的植入物放在那里，然后哪个组织从 Hub 运行这些图像，他们也会运行你的植入物。*

“在上游下毒”应该会让任何与集装箱打交道的人感到不寒而栗。正因为如此，解决一个表面上无法解决的难题就落在了内核开发人员的肩上。Linux 内核如何防止这种对上游的毒害？还是可以？

一篇来自[的](https://www.redhat.com/en/blog/authors/joe-fernandes)[博客帖子](https://www.redhat.com/en/blog/containers-are-linux)，Joe Fernandes ，OpenShift 的红帽产品管理高级主管，完美地总结了容器化过程(以及它与 Linux 内核的关系):

*首先，每个容器化的进程都使用内核名称空间与运行在同一台 Linux 主机上的其他进程隔离开来。内核名称空间为容器进程的运行提供了一个虚拟化的世界。例如，“PID”名称空间导致容器化的进程只能看到该容器内的其他进程，而看不到共享主机上其他容器中的进程。额外的安全隔离由内核特性提供，如丢弃功能、只读挂载和 seccomp。SELinux 在 Red Hat Enterprise Linux 等发行版中提供了额外的文件系统安全隔离。这种隔离有助于确保一个容器无法利用其他容器或关闭底层主机。*

这种类型的利用可以成功或失败一个容器部署。想象一下，您刚刚部署了一个 Docker Swarm 或 Kubernetes 集群来提供您公司的标志性应用或服务，却发现所使用的映像能够利用主机内核并使您公司的网络瘫痪，甚至窃取敏感数据。

## 规模和一致性

Linux 内核作为一项独立的技术，几乎可以在任何类型的设备上运行。从台式机到服务器，从智能手机到物联网和其他嵌入式设备，内核无处不在。

“随着现代开发越来越多地意味着云原生开发，内核贡献者正在为这些用例添加增强 Linux 的功能，”Morello 说。“虚拟化和云推动了 KVM 等技术的创新，容器也推动了 seccomp 和 namespaces 等内核技术的发展。”

但是有了容器和云技术，超越这种隔离变得至关重要。莫雷罗:

你不会真的看到人们在一个典型的基础上，至少，说“我要用 C++建立一个应用程序，并直接在操作系统上作为一个包运行”。这不是大多数人构建现代应用程序的方式，对吗？您正在构建容器化的东西，您将在容器中运行它，您将通过 Kubernetes 之类的东西来部署它，内核提供了抽象部分或所有底层硬件的基础层，所有的复杂性都随之跨越不同的 CPU 类型等等，这允许您以真正一致的方式运行这些应用程序，而不管它的外形是什么，也不管它的规模是什么。”

这种(相对)新技术要求 Linux 内核能够跨大量不同的硬件类型、配置和大规模容器部署提供一致的体验。这不是一件容易的事。

说到缩放…

云巩固了它在技术生态圈中的地位。每天都有数亿用户依赖云。我们的数据存储在那里。我们的照片，我们的视频，我们的文档…所有我们做的和使用的东西，让我们的日常生活更有效率和/或更愉快。

什么在运行云？Linux。

我们现在看到如此多的公司从事基础设施即服务(IaaS)、软件即服务(SaaS)和平台即服务(PaaS)的工作。这是 Linux 大放异彩的另一个舞台。然而，由于这些类型的服务对服务器和网络提出了很高的要求，Linux 内核(以及安装的应用程序)需要进行优化，以便在这样的环境中运行。

来自以色列理工学院和以色列开放大学的一组研究人员在他们的论文“非内核:为云设计的内核”中说:

“在传统服务器中，操作系统管理整个资源:所有 CPU、所有 RAM 和所有可用设备。在云中，内核以越来越精细的粒度获取和释放资源，目标是获取和释放几毫秒的 CPU 周期、单页 RAM、几 Mb/s 的网络带宽。”

显然，为云设计的 Linux 内核必须采用与传统用例完全不同的方式。

本文继续介绍:

*“第一个要求是允许应用程序针对成本进行优化。在传统服务器上，成本是固定的，应用程序只针对“有用的工作”进行优化。有用的工作可以用运行时性能来衡量，例如，用每秒的高速缓存命中来衡量。在云中，执行任何工作都需要租用资源，并且每个资源都有一个与之相关的瞬时价格标签，应用程序仍然希望针对“有用的工作”进行优化，有用的工作越多越好，但现在他们也希望针对成本进行优化。如果你可以为同样数量的有用工作支付更少的费用，为什么还要支付给云提供商更多的费用呢？因此，云内核应该支持应用程序对有用的工作和成本进行双目标优化。”*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>