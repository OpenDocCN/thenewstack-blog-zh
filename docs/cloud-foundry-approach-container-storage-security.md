# 容器存储和安全性的云铸造方法

> 原文：<https://thenewstack.io/cloud-foundry-approach-container-storage-security/>

最近，New Stack 发表了一篇名为“[容器和存储:为什么我们还没有到达那里](https://thenewstack.io/containers-storage-arent-yet)”的文章，报道了[在三月份 Linux 基金会的 Vault 会议上与 IBM 的](http://sched.co/9WQf) [James Bottomley](http://researcher.ibm.com/researcher/view.php?person=us-jejb) 的一次谈话。演讲和文章都聚焦于我们在 [Cloud Foundry Foundation](https://www.cloudfoundry.org/) 的 Diego Persistence 项目团队中一直致力于解决的一个核心问题，所以我们认为强调我们为缓解这个问题而添加的功能是一个好主意。Cloud Foundry 在容器安全方面做得比这篇文章所建议的要好得多，所以我们也将在这里讨论它。

## UID 到 FSUID 的映射

 [朱利安·霍特肖伊

Julian Hjortshoj 是一名在戴尔 EMC 工作了 12 年的资深员工，目前是云代工厂 Diego Persistence 团队的产品经理。他和妻子住在旧金山，目前正与邻居地鼠进行一场激烈的卡迪沙克式的战斗。](http://www.Dell.com) 

正如文章所说:

*目前，容器有状态存储的一个主要障碍是，在当前的 Linux-y 架构下，无法将外部存储系统使用的文件系统用户 ID (fsuid)与容器内创建的用户 fsuid)进行协调。它们不能以既安全又可维护又不丧失系统或系统管理员的一致性的任何方式进行协调。*

2016 年年中，当我们开始考虑 Cloud Foundry 中网络连接存储的客户使用案例时，我们遇到了这个问题。对于 Cloud Foundry 应用程序，这个问题可能比通常在其他容器编排器中运行的应用程序更严重，因为 Cloud Foundry 坚持应用程序运行的方式，并且它将所有 buildpack 应用程序作为 UID 2000 运行。如果我们想使用常规的 Linux 内核挂载将存储挂载到容器中，这意味着:

*   任何附加的文件系统都需要打开对 UID 2000 的访问。
*   部署到 Cloud Foundry 的任何应用程序创建的文件在文件系统看来都属于 UID 2000，事实上无法区分哪个应用程序做了什么。

我们研究了几种不同的方法来解决这个问题(包括一个短暂的悲叹，即 [ShiftFS](https://lwn.net/Articles/687354/) 在内核中还不可用)。Cloud Foundry 应用程序在用户名称空间中运行，因此 UID 映射是可用的，[就像它在 Docker](https://docs.docker.com/engine/reference/commandline/dockerd/#daemon-user-namespace-options) 中一样。问题是，每个容器运行时我们只能得到一个映射，所以虽然我们可以很容易地将容器上的 UID 2000 重新映射到主机上的其他 UID，但我们最终会让所有应用程序都以那个新 UID 连接。我们需要的是一种实现每个应用程序 UID 映射的方法。

我们最终提出了一个解决方案:使用 fuse mounts 和 NFS 客户端将 UID 映射注入 NFS 挂载本身。由于网络文件系统(NFS)只是一个远程过程调用(RPC)协议，因此在 NFS 接口和 fuse 实现之间注入映射逻辑相对简单。这允许应用程序声明对远程 NFS 服务器有意义的 UID，并使到远程服务器的流量显示为该 UID，同时相同的文件作为我们用来运行容器应用程序的标准 UID 2000 呈现给容器和容器主机。

> 可以说，我们受这些问题的影响较小，因为我们对容器的使用更加专注。

[在我们最新发布的 NFS 插件](http://bosh.io/releases/github.com/cloudfoundry-incubator/nfs-volume-release)中，我们还支持可选的轻量级目录访问协议(LDAP)服务器配置，因此客户可以使用活动目录联合服务(ADFS)将登录凭据解析为 uid，这与他们从非 Cloud Foundry 应用程序使用 NFS 共享时的情况非常相似。

当然，这个解决方案只是部分解决了基于容器的应用程序的 UID 映射这个更广泛的问题。今天，它只适用于 NFS 股票，虽然它允许我们为容器提供持久存储，但它不能为容器提供持久存储。但是在 Cloud Foundry 上下文中，容器状态预计是短暂的，所以容器状态的存储是一种反模式。

## 集装箱安全

本文还强调了在容器中运行应用程序时的一些潜在安全问题，特别是当应用程序希望附加外部存储时，因为挂载操作需要 CAP_SYSADMIN:

Linux 用户名称空间的工作方式是关键。Bottomley 断言，容器安全性依赖于用户名称空间，这是公认的常识，但这只是部分事实。默认情况下，安全系统应该将某人锁在系统之外。名称空间实际上做了相反的事情:它们为用户提供了增强的特权。

在用户命名空间内允许用户进行某些根操作，而在用户命名空间外则不允许。例如，您可以从名称空间中运行 mount 命令，但不能以普通用户的身份运行。

但是在 Cloud Foundry 中，容器应用很少以 root 身份运行。如上所述， [buildpack 应用程序](https://docs.cloudfoundry.org/buildpacks/)(将应用程序部署到 Cloud Foundry 的标准方法)总是作为拥有 UID 2000 的非特权用户运行。可以在 Cloud Foundry 中运行 Docker 应用程序，在这种情况下，默认行为是以 root 用户身份运行，但即使在这种情况下，CAP_SYS_ADMIN 功能也只是由 Garden 运行时预先使用，以将存储和网络绑定到容器中，然后在应用程序进程启动之前撤销。

## 观点的差异

值得注意的是，我们在 Cloud Foundry 中对容器的目标与 [Bottomley 设计 ShiftFS 时的最初用例](https://blog.hansenpartnership.com/unprivileged-build-containers/)大相径庭。Bottomley 在他的演讲中指出的容器技术的局限性是非常真实的，而且在很大程度上，我们还没有解决它们。

但可以说，我们受它们的影响较小，因为我们对容器的使用更加专注。当今容器技术的大部分缺点来自于在容器中运行的进程，这些进程想要做类似根的事情，比如连接网络、安装设备等等。允许类似根的东西出现在容器中，同时保持容器中包含的特权，比简单地使用容器来加强接口的隔离和一致性要困难得多。

由于 Cloud Foundry 在基于容器的应用程序的上下文之外管理和提供卷安装和网络接口，因此它不太容易受到以特权运行容器应用程序所固有的安全缺陷的影响。如前所述，为基于容器的应用程序获得可用的外部存储要比为容器本身提供存储容易得多。

我们是否已经到达那里取决于我们想去哪里。

[云铸造基金会](https://www.cloudfoundry.org/)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>