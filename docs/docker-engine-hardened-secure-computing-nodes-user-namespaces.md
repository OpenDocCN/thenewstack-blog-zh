# Docker 引擎通过安全计算节点和用户命名空间得到强化

> 原文：<https://thenewstack.io/docker-engine-hardened-secure-computing-nodes-user-namespaces/>

企业系统需要企业级安全性。考虑到这一点，Docker Inc】用一些潜在的强大安全措施更新了其核心容器引擎。

Docker Inc .将此次发布描述为“集装箱安全的巨大飞跃”该公司还为周四发布的 [Docker 1.10](https://github.com/docker/docker/releases/tag/v1.10.0) 添加了过多的网络增强功能。

也许[两个最显著的与安全相关的新增功能](https://blog.docker.com/2016/02/docker-engine-1-10-security/)是安全计算模式(seccomp)的增加，这是 Linux 内核的一个特性，以及容器识别用户名称空间的能力。

Seccomp 通过允许系统管理员过滤容器使用的系统调用来限制容器内可用的操作。这减少了内核暴露的攻击面。

seccomp [上的工作也应该为 Docker Engine 开发本地安全概要铺平道路](https://github.com/docker/docker/issues/17142#issuecomment-148974642)，这将把管理员从手工写出所有系统调用到 block 的大量工作中解放出来。

对用户名称空间的支持仅仅意味着 Docker 容器可以识别多个用户角色，将它们绑定到适当的安全策略。现在，在容器内部拥有 root 权限的人不会自动享有主机上的 root 权限。

此外，为了帮助限制未经授权的活动，管理员现在可以创建“授权插件”来允许或阻止对主机守护程序的 API 请求。

除了安全性，Docker Inc .做了大量工作来增强 Docker 的网络连接选项，建立在去年年底添加的多主机网络功能上。例如，容器可以获得自定义的 IP 地址。主机名查找现在通过外部 DNS 服务器完成，而不是通过查询/etc/hosts 文件，这种方法可以在 hosts 文件损坏的情况下构建容器。

Docker 1.10 也是第一个支持新更新的组织容器集群格式的版本， [Docker Compose 1.6](https://blog.docker.com/2016/02/compose-1-6/) 。Docker Compose 现在可以用于处理另外两个抽象概念，即网络和卷，为管理员提供了一种指定多个网络层和复杂存储配置的方式。

Docker Inc .警告说，升级到 Docker 1.10 的过程可能会非常漫长。所以[提前计划](https://docs.docker.com/engine/migration/)。该公司还将在 2 月 17 日举办一场网络研讨会，以便[更详细地讨论新功能](https://goto.docker.com/Webinar-HumpDayDemosWhatsNewin1.10_LP.html)。

[https://www.youtube.com/embed/OsOLF3_fotM?feature=oembed](https://www.youtube.com/embed/OsOLF3_fotM?feature=oembed)

视频

该公司还更新了许多相邻的工具，如 [Docker Swarm](https://docs.docker.com/swarm/overview/) 集群工具、 [Docker Machine](https://docs.docker.com/machine/install-machine/) 虚拟主机软件和 [Docker 注册表](https://docs.docker.com/registry/)。

[Docker Swarm 1.1](https://github.com/docker/swarm/releases/tag/v1.1.0) ，是 11 月第一个完整版本的增量更新，具有针对故障节点的自动化容器重新调度功能。 [Docker Machine 0.6](https://github.com/docker/machine/releases/tag/v0.6.0) ， [Docker 工具箱](https://www.docker.com/products/docker-toolbox)的一部分，现在与 VirtualBox 和 Windows 一起使用时稳定多了。

Docker Registry 2.3 支持新的清单格式，使得不同图像之间共享层成为可能。

Docker 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>