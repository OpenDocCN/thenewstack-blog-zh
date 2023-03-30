# Kubernetes 头盔包管理器的更新可以简化应用程序的部署

> 原文：<https://thenewstack.io/update-kubernetes-helm-package-manager-simplify-app-deployment/>

用于 [Kubernetes](/category/kubernetes/) 编排引擎的 Helm package manager 已经更新，简化了命令并减少了外部依赖性，从而使在 K8s 集群上部署应用程序比以往任何时候都更容易。

Helm 是 Deis 去年开始的[项目，其主要架构师——](https://thenewstack.io/deis-aims-extend-kubernetes-platform/)[马特·布彻](https://github.com/technosophos)和[杰森·汉森](https://github.com/slack?tab=repositories)——设想了一种众包模式，用于在各种情况下配置不同工作负载的部署。

Helm 使用称为“图表”的包，其中包含模板化的 Kubernetes 资源，用于将应用程序部署到 Kubernetes 集群上。Helm 还会在部署后管理这些版本。

在去年 6 月发布的一个 Kubernetes 社区视频中，Butcher 介绍了 Helm 2.0 的第一个发布候选版本的 alpha 版本。“基本上，我们现在做的是，我们有三大部分，”布彻说。“我们有命令行 Helm 实用程序，它通过 gRPC[与服务器通信；我们有服务器端组件，它的工作基本上是获取包，将它们部署到 Kubernetes 中，并管理它们；然后我们有了第三个概念，即存储库。”](https://thenewstack.io/grpc-lean-mean-communication-protocol-microservices/)

他解释了 Helm 如何充当一种配置客户端，它的对应部分(自然称为 Tiller)管理来自服务器端 pod 的交互。当 Helm 向 Tiller 展示要启动的应用程序清单时，Tiller 会有效地绘制路线，评估清单*图表*(如前所述)并将其应用于当前系统配置。该产品是一套最新的部署说明，然后可以上传给 Kubernetes。

Butcher 告诉社区:“图表就像一捆预先编制好的 Kubernetes 资源文件和清单，有模板支持之类的东西。”“我们想做一些东西，让在 Kubernetes 上安装新东西像说的那样容易，比如 **apt-get install nginx** 或 **yum install wordpress** 或类似的东西。”

软件包管理器的第一个版本，现在被复古地称为“Helm Classic”，强烈模仿了为 MacOS 开发的软件包管理器 [Homebrew(是的，Mac 用户确实使用终端提示符)。正如 Butcher 所演示的，Helm 2.0 的命令在某种程度上是对“经典”的简化，允许使用一个命令从现有文件创建图表，使用一个命令围绕该图表构建一个 tarball 包以供分发。](http://brew.sh/)

新的包管理器消除了其前身对 GitHub 作为共享图表的存储库的一些依赖，转而更普遍地接受任何可通过 HTTP 导航的文件系统。Butcher 说，Helm 的新存储系统使图表的共享有了范围，因此一些图表可以被指定为适用于整个组织，而另一些图表则只能由指定的个人使用。

据[其公司博客](https://deis.com/blog/2016/helm-is-now-stable/)称，Deis 管理着两个官方的 Helm 库: **stable** ，其中包含针对 Jenkins 和 MariaDB 等广泛使用的应用程序的久经考验的配置；以及**孵化器**，其特点是掌舵团队想要推广的图表，但其结果不能在所有情况下都得到保证。

在五个月前的演示中，Butcher 注意到还有一个主要的特性需要实现——回滚 pod 删除的方法。按照计划，Tiller 将保留从集群中移除的 pod 的状态信息。通过这种方式，一个逃生舱有一个很窄的时间窗可以复活，尤其是在意外移除的情况下。但是要指定哪个 pod 需要被取消删除，必须存在其状态的一些记录，如果 pod 被删除，就不一定是这种情况——这导致了 Butcher 和他的同事当时面临的相反的鸡和蛋的难题。周四发布的消息表明，他们已经找到了解决方案。

在周四的一篇博客文章中，Butcher 称赞谷歌、应用部署平台 Bitnami 和面向 Kubernetes 的咨询公司 skip box 在 Helm 2.0 项目上的合作。“其结果，”他写道，“是一种工具，它不仅使团队合作成为一种核心价值，而且也是一种旨在满足 Kubernetes 用户不断增长的社区需求的工具，这些用户正在安装复杂的应用程序。”

[英特尔的乔纳森·唐纳森讨论 Kubernetes](https://thenewstack.simplecast.com/episodes/intels-jonathan-donaldson-discusses-kubernetes)

Bitnami 是新堆栈的赞助商。

专题图片:电影海报来自《谋杀之路》系列电影之一[马特·赫尔姆](http://www.matthelmbooks.com/)的冒险故事。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>