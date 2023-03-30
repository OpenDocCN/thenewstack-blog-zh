# Kubernetes 1.17 带来了卷快照、更简单的插件管理

> 原文：<https://thenewstack.io/kubernetes-1-17-brings-volume-snapshots-easier-plugin-management/>

Kubernetes 是市场上最广泛使用的开源容器编排工具之一，用于部署、扩展和管理容器。这个工具最初由 Google 创建，现在由 Cloud Native Computing Foundation 维护，今天标志着 1.17 版本的发布。

1.17 版是 2019 年的第四个也是最后一个版本，由 22 项增强功能组成。在这些增强功能中:

*   14 人已经毕业，情况稳定。
*   4 个正在进行测试。
*   4 人进入阿尔法。

让我们来看看 Kubernetes 最新版本中的一些新增强。

首先，让我们检查一个更重要的特性。

## 卷快照

尽管卷快照还没有被迁移到 Stable，但它是许多 Kubernetes 管理员非常喜欢的一个特性。此功能创建永久卷的时间点副本。这些快照可用于调配新卷或将现有卷恢复到以前的状态。

但是，考虑到 Kubernetes 已经包含了一个卷插件(一个为块和文件存储的自动化和供应、附加和装载提供强大工具的插件)，为什么还要向它添加卷快照呢？为了回答这个问题，Kubernetes [官方文档注释](https://kubernetes.io/blog/2019/12/09/kubernetes-1-17-feature-cis-volume-snapshot-beta/):

*支撑所有这些特性的是 Kubernetes 的工作负载可移植性目标:Kubernetes 的目标是在分布式系统应用程序和底层集群之间创建一个抽象层，这样应用程序可以不知道它们运行的集群的细节，应用程序部署不需要“特定于集群”的知识。*

快照操作被视为有状态工作负载的关键功能。通过提供在 Kubernetes API 中触发快照操作的方法，管理员现在可以处理用例，而不必绕过 Kubernetes API。

要阅读更多关于 Kubernetes 卷快照功能的信息，请访问官方文档[。](https://kubernetes.io/blog/2019/12/09/kubernetes-1-17-feature-cis-volume-snapshot-beta/)

## 树内插件迁移

从 1.17 开始，Kubernetes 将把树内插件迁移到容器存储接口(CSI)。为什么会这样？在 1.17 之前，Kubernetes 卷插件是核心 Kubernetes 代码的一部分，与核心 Kubernetes 二进制文件一起提供。因此，向 Kubernetes 添加新的批量插件总是具有挑战性。如果一个供应商想要将他们的存储系统添加到核心中，他们被迫与 Kubernetes 发布过程保持一致。这并非总是可行的。

最重要的是，第三方存储代码可能会导致核心 Kubernetes 二进制文件中的可靠性和安全性问题。

这导致了树内插件向 CSI 的迁移。对于这种迁移，Kubernetes 开发人员说，“当 Kubernetes 集群管理员更新集群以支持 CSI 迁移时，现有的有状态部署和工作负载将继续像以前一样工作；然而，在幕后，Kubernetes 将所有存储管理操作(以前针对树内驱动程序)的控制权交给了 CSI 驱动程序。”

## 其他功能

Kubernetes 1.17 中的特性列表包括:

*   按条件污染节点:表示使用污染阻止调度的节点条件。
*   可配置的 pod 进程名称空间:用户可以通过设置 PodSpec 中的选项来配置 Pod 中的容器，以共享一个公共 PID 名称空间。
*   动态最大卷计数:增加了对每个节点最大卷的动态和通用机制的支持。
*   在子路径挂载中提供环境变量扩展。
*   支持默认的自定义资源。
*   将频繁的 Kubelet 心跳移动到租约 Api: Kubelet 在节点上创建并定期更新租约，节点生命周期控制器将此租约视为健康信号。
*   支持手表书签，以减少 kube-apiserver 上的负载。
*   行为驱动的一致性测试:一致性的行为是预先定义的，与验证这些行为的测试是分开的。
*   服务的终结器保护:添加终结器保护以确保服务资源不会被完全删除，直到相关的 LB 也被删除。
*   避免为每个观察器独立序列化相同的对象。
*   [IPv4/IPv6 双栈支持](https://thenewstack.io/it-takes-a-community-kubernetes-long-road-to-dual-ipv4-ipv6-support/)。
*   拓扑感知的服务路由。
*   为 Windows 运行一个用户名。

要下载 1.17 版本的 Kubernetes，请访问[官方 GitHub 页面查看版本](https://github.com/kubernetes/kubernetes/releases/tag/v1.17.0)。要了解更多新内容，请点击此处阅读完整的变更日志。

云计算原生计算基金会是新堆栈的赞助商。

来自 Pixabay 的 SplitShire 特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>