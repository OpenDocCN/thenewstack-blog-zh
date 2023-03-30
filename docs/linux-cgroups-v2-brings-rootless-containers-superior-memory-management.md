# Linux cgroups v2 带来了无根容器、卓越的内存管理

> 原文：<https://thenewstack.io/linux-cgroups-v2-brings-rootless-containers-superior-memory-management/>

容器和容器管理工具有很多活动部件。尽管您可以毫不费力地快速部署一个 Docker 容器，但是容器的规模越大，添加的服务越多，它就变得越复杂。事实上，Kubernetes 的部署会变得非常复杂。他们还会对资源要求很高。

集装箱运动画面的一部分是 [cgroups](https://www.kernel.org/doc/Documentation/cgroup-v1/) 。cgroup 最初由 Google 创建，并被纳入 Linux 内核 2.6.24，它代表“控制组”，是一种管理一组进程(即容器)使用多少计算资源的方法。通过 cgroups，您可以将核心工作负载与后台任务隔离开来，防止一个工作负载压倒其他工作负载，等等。

直到最近，容器开发人员一直在使用 cgroups v1。然而，从内核的 4.5 版本开始可用的 [cgroups v2](https://www.kernel.org/doc/Documentation/cgroup-v2.txt) ，现在可以被大多数容器部署系统使用和支持。这个新版本包含了许多容器开发者想要了解的[重要变化](https://www.kernel.org/doc/html/latest/admin-guide/cgroup-v2.html)。

## 简单

v2 中对 cgroups 的最大改变是关注层次结构的简单性。v1 为每个控制器使用了独立的树(如**/sys/fs/cgroup/CPU/group name**和**/sys/fs/cgroup/memory/group name】**，v2 将统一**/sys/fs/cgroup/group name**中的树。同样，如果进程 X 加入了 **/sys/fs/cgroup/test** ，那么每个为 test 启用的控制器都将控制进程 X。

例如，在 cgroups v2 中，内存保护在四个文件中配置:

*   **memory.min** :这个内存永远不会被回收。
*   **memory.low** :如果其他 cgroups 中没有其他可回收的内存，则低于此阈值的内存将被回收。
*   **memory.high** :内核将试图保持内存使用低于这个配置。
*   如果内存达到这个水平，就会在 cgroup 上调用 OOM killer(一个系统，用来牺牲一个或多个进程来为系统释放内存)。

## 无根容器

无根容器已经成为防止容器运行时漏洞的一种非常流行的方法。为什么[无根容器](https://thenewstack.io/containers-microservices-two-peas-devops-pod/)？有了这个附加的安全层，如果容器受到危害，攻击者将无法获得主机上的根权限。无根容器也允许嵌套容器之间的隔离。目前的问题是 cgroups v1 不支持对无根容器施加资源限制。cgroups v2 的所有变化，作为无根容器，现在将包括资源限制特性。

## 其他变化

cgroups v2 中的其他变化包括:

*   现在，群控制器可以在问题实际发生之前与子系统进行协商。这些子系统也能够采取行动来补救问题。
*   全球 inotify 支持。
*   单一统一层次结构意味着不需要同步。
*   更多的前期设计。
*   通用阈值。

## 运行时支持

重要的是要知道大多数高级容器运行时(Containerd、Docker、Podman 和 Kubernetes)现在都能够完全支持 cgroups v2。这种支持大部分是在 2019 年 11 月出现的，但随着 cgroups v1 被弃用，是时候开始从 v1 到 v2 的挑战性迁移了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>