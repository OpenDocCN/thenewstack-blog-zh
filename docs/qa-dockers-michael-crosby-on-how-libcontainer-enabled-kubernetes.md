# 问与答:Docker 的 Michael Crosby 介绍 Libcontainer 如何支持 Kubernetes

> 原文：<https://thenewstack.io/qa-dockers-michael-crosby-on-how-libcontainer-enabled-kubernetes/>

软件工程师 Michael Crosby 于 2014 年开始在 Docker 的核心团队工作。他仍然是 Docker 的一名工程师，负责 libcontainer 内核接口和 [runc](https://github.com/opencontainers/runc) 容器运行时，并监督围绕这些项目的开源社区。2018 年当选为[开放集装箱倡议](https://www.opencontainers.org/) (OCI)技术监督委员会主席。

从. 04 版开始，Crosby 负责管理 [libcontainer](https://github.com/docker/libcontainer) ，这是一个用于 Linux 和 Windows 的守护进程，管理其主机系统的整个容器生命周期。最初编写 libcontainer 是为了防止 Docker 在每次发布升级时崩溃，它在早期是开源的。Crosby 的依赖不可知设计非常适合 Kubernetes 和其他能够在 libcontainer 之上构建的语言。Libcontainer 现在是 runc 的一部分。

在 [DockerCon 2019](https://www.docker.com/dockercon/) 上，我们与 Crosby 坐下来谈论 containerd 的开端以及他在过去五年中最知名的开源项目之一上的工作。

**在导致 libcontainer 开发的那些年里，你开始发现了什么？**

我们没有真正的路线图。当时只有(Docker 创始人)所罗门·海克斯的愿景。我们有很大的自由，我注意到我们在 LXC 的发布上有一个又一个的问题。每次有更新的时候，事情都会变糟，所以我就用 libcontainer 离开了这条路。

**lib container 当时的近期目标是什么？**

那是为了解除对 LXC 的依赖。因此，无论何时部署 Docker，您都可以获得静态 Docker 二进制文件，一切就绪。当时没有其他依赖关系。

**在 1.0 之后，这如何适应真正的横向扩展？**

当时，在 Docker 内部，出现了许多新概念和新功能。按照 libcontainer 的设计方式，您可以在多个容器之间共享一个网络名称空间。

当时我们不知道什么是豆荚或 Kubernetes，但新的架构使它们成为可能，并导致这些类型的事情发生。

新的架构是什么？

关于这个库是如何创建的，LXC 说，“这是一个配置，这样做。”libcontainer 说，“这里有一些如何创建容器的参数，”你可以更容易地将它们缝合在一起，所以你可以更灵活地将一个 pod 中的多个容器缝合在一起，诸如此类。

人们开始思考，“既然我们能做到这一点，我们如何制造豆荚，在哪里制造呢？”所以我让社区里的其他人思考如何处理事情。

那这又是如何回到你的工作中的呢？

我做过一段时间 Docker 的首席维护员。随着规模的扩大，我开始关注长期方面。我得到了 libcontainer，然后是文件系统，一旦我们完成了 OCI，我当时就在做很多标准。

Docker 是一个非常活跃的开源项目，所以我很熟悉我们的拉请求问题和社区支持。对于 OCI，我只是学习了更多关于开放治理的知识，并通过 Linux 基金会获得了一些东西，所以，我和 Docker 的一些其他人帮助建立了治理，然后基金会开始了，最初的贡献是 libcontainer。

对于 libcontainer，有一个关于如何创建容器的规范，它被注入到我们今天拥有的运行时规范中。于是有了两个规范和 runc 代码，它们都是基于 libcontainer 构建的，是 OCI 的两个初始产品。

**当时你是如何和社区里的其他人一起参与的？有 Docker 维护者，但也有许多其他相关方。**

最初的代码来自 Docker，后来社区中的其他公司对我们很感兴趣。由于我们得到了一致的贡献，一些人成为了 OCI 的维护者，并获得了写权限。我们壮大了这个团队，这些年来还包括了不在 Docker 的人。有一个小社区的人都在开发 libcontainer 运行时代码。我们彼此了解，我们一起工作了很长时间，所以这些人中有很多是今天 OCI 的维护者。

**您在内部构建了哪些工具来帮助您获得更高的贡献水平？**

最初，Docker 命令界面运行在我的个人电脑上。我建立了一个云实例，然后我们让团队构建了一个基础架构，对今天有人发布的每一个拉式版本进行所有测试。

**在 OCI，你开始看到哪些有助于 Docker 下一步发展的效率？**

有了 OCI，我们开始从公司那里得到更多的贡献，所以我们需要一个标准，每个人都可以团结起来，在这个基础上开始建设。一旦我们将 OCI 标准锁定在 1.0 运行时规范中，[我们]就开始看到类似[亚马逊网络服务]][鞭炮](https://firecracker-microvm.github.io/)和其他项目。这刺激了运行时层面的创新浪潮。

在我们捐赠了关于注册表如何工作和图像格式的注册表规范之后，我们开始看到各种各样的图像注册表，比如 Google 容器注册表。这些标准刺激了人们可以使用的其他产品。

**你现在对那些时光有什么感想？在容器生态系统中，这是一个更加困难的时期；市场压力很大。**

我认为对所有资源项目说“不”是一个问题。作为维护者，对贡献说“不”是很难的，因为有些人有两种不同的方式。只要你清楚地解释了你拒绝的原因，大多数人都会接受。

然后，你可以让社区中的一些人说，“哦，因为他们是我公司的一部分，所以他们拒绝这样做。”作为一名开源维护者，每次我说不都是因为它写得不好，设计不好，或者它不适合项目的整体架构，我认为大多数维护者在接受或拒绝贡献时都有同样的工作和感受。因此，外部贡献总是平衡的，这取决于贡献者如何处理这些。

**你现在在做什么？**

集装箱。这可能是我在 Kubernetes 退出之前开始的。我记得有一天晚上，我们围坐在一起吃晚饭，我在想“如果我们有一个小的运行时，就像 Swarm 之类的供管弦乐队使用，那不是很酷吗？”

那是在我们谈论 Swarm 的时候，所以我写了 containerd，这个想法是拥有一个非常小的运行时，可以非常快地为 orchestrators 创建容器。

这是因为我们要和 OCI 进行整合工作。因此，我们将 containerd 作为 Docker 中的默认运行时，集成了所有 OCI 规范。Kubernetes 出来后，一天晚上我和 Solomon 聊天，我说，“让我们扩展 containerd 的范围来处理 Kubernetes 和所有这些不同的运行时。”

所以我一直在忙这个。

T.C. Currie 为这个故事整理了文本。

照片由来自 Pixabay 的 Frauke Feind 拍摄

**想要更多？**

[Kubernetes vs dockers warm:有什么区别？](https://thenewstack.io/kubernetes-vs-docker-swarm-whats-the-difference/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>