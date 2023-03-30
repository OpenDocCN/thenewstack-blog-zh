# 微软保护 Windows Docker 容器

> 原文：<https://thenewstack.io/microsoft-secures-the-windows-docker-container/>

微软继续致力于在 Windows 上为 Docker 创建一个主页。周四发布的 Windows Server 2016 release candidate 4(RC 4)引入了一种新的 Docker Windows 容器，该容器安全地位于该公司的虚拟化机器 Hyper-VM 中。

Hyper-V 容器使用与 Windows 上运行的 Docker 容器相同的图像格式，该公司在今年早些时候以预览形式推出了 Docker 容器，但是它们提供了虚拟机所提供的更大的隔离。

虽然微软在一年前首次宣布了 Hyper-V 容器的想法，但“这是世界第一次开始使用它们，”微软首席编程管理主管泰勒·布朗说。

Hyper-V 容器可以使用许多用于常规 Windows 容器的相同命令来控制。您使用相同的 Docker 命令来启动 Hyper-V 容器，就像您对常规的 Microsoft Docker 容器所做的那样，只添加了一个隔离标志。

Docker 技术人员 Patrick Chanezon 指出，目前，所有 Docker Compose 命令在两个平台上都可以正常工作，Windows Swarm 的原型也正在测试中。

性能呢？毕竟，容器相对于传统虚拟机的一个很大的优势是，它们可以更快地创建，因为它们共享服务器的内核，而不是启动自己的内核。

布朗承认，事实上，Hyper-V 容器确实需要多花几秒钟来创建。他补充说，与未虚拟化的容器相比，Hyper-V 容器占用了更多的内存空间，因此可以打包到单个服务器上的容器更少。

但这是为了更高的安全性而付出的代价。根据设计，Hyper-V 容器提供的攻击面要小得多。例如，如果在 Windows 内核中发现漏洞，恶意用户就无法从 Hyper-V 容器中挣脱出来，从而利用主机服务器上的故障。

“最糟糕的情况是让虚拟机崩溃。他们无法走出集装箱的界限，”布朗说。

## 没有用于 Windows 的 libc

布朗说，将基于 Linux 的用 Go 编写的 Docker 交叉编译到 Windows 上是一项合作努力，涉及微软、Docker 和第三方贡献者。

事实上，在过去的一年里，微软实际上已经成为 Docker 最大的贡献者之一。根据 Docker 的数据，在过去一年的 319 个拉取请求中，就代码行数而言，微软是第五大贡献者。

请记住，Windows Docker 容器提供 Windows 系统调用，而不是 Linux 系统调用。像 Linux Docker 容器一样，Windows 容器共享主机 OS 内核，只是内核是 Windows，而不是 Linux。

“当你在一个 Windows 容器中时，感觉就像一个 Windows 环境。Docker 工程师 Arnaud Porterie 在本周于巴塞罗那举行的 Dockercon 欧盟会议上谈论 Windows 容器时说道。

微软工程师约翰·斯塔克斯指出，尽管 Docker 代码库是共享的，但基于 Windows 的 Docker 和基于 Linux 的 Docker 容器在体系结构上有许多不同，他也出席了 Dockercon 欧盟 Windows 容器会议。

首先，基于 Linux 的 Docker 容器在主机系统上只能产生一个进程，而 Microsoft 容器会产生多个进程。

然而，对于 Hyper-V 容器来说，情况并非如此，因为它们在 hypervisor 中有自己的轻量级内核，而不是共享主机的内核。因此，“从 Docker 的角度来看，它看起来像一个容器，但你不会在主机上看到它的进程，”Starks 说。

此外，Linux 调用依赖于一些共享库，如 **libc** 。相比之下，Windows 依赖于一组更广泛的**dll**(动态链接库)，其中许多 dll 交织在一起提供服务。因此，每个 Windows 容器实际上都在主机操作系统上运行几个进程，而不是一个。

## 为了胜利的敌意多重租赁

所以基于 Linux 的 Docker 容器将不能在 Windows 机器上本地运行，反之亦然。布朗说，但两者都将能够由相同的 Docker 管理软件控制，允许开发人员将 Windows 和 Linux 的最佳组件混合到一个应用程序中。

完全隔离的容器可能会吸引许多出于各种安全和行业合规性考虑而不愿使用该技术的企业用户。

微软 Azure 本身将使用安全容器来更有效地提供多租户托管服务，如 Azure 机器学习(ML)服务。

“我们可以以更高的密度将客户的脚本彼此完全隔离，这比我们为每个客户建立完整的虚拟机要高得多，”Brown 说。

完全生产就绪的 Hyper-V 容器技术将随着 Windows Server 2016 的完全商业发布而到来，预计将于明年某个时候推出。完整的 Windows Server 2016 和精简的 Nano 版本都将运行这些容器。

一旦微软更新其管理程序，Hyper-V 容器也将在微软的 Azure 容器服务上得到支持。

Docker 是新堆栈的赞助商。

特征图片:Docker 技术人员 Patrick Chanezon 在 Dockercon EU 2015 上，两侧是微软 Azure 架构师 John Gossman(左)和微软首席编程经理 Taylor Brown。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>