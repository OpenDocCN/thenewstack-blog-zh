# Kubernetes 1.16 带来了自定义资源定义、双 IPv4/IPv6 支持

> 原文：<https://thenewstack.io/kubernetes-1-6-has-arrived-with-custom-resource-definitions/>

Kubernetes 最新发布的 1.16 版本已经正式登陆。

“对于这个版本，总的主题是简化 Kubernetes 内部托管的 API 的创建和长期管理，”Red Hat 工程师 [David Eads](https://www.linkedin.com/in/david-eads-64b67212a/) 和 [Stefan Schimanski](https://www.redhat.com/en/blog/authors/stefan-schimanski "See more by Stefan Schimanski") 在宣布发布的博客帖子中写道。任何依赖 Kubernetes 的人，尤其是企业用户，都会发现这个主题对于长期使用和大规模部署至关重要。

尽管 Kubernetes 1.16 中有许多令人兴奋的特性，但人们普遍认为，现在正式发布的 CRDs(自定义资源定义)将为应用程序和服务的开发和部署提供最大的改进。

## 什么是 CRD？

CRD 被引入到 Kubernetes 的上游版本(版本 1.7)中，作为最初作为**第三方资源**开始的面向未来的实现。这个特性很快成为 Kubernetes API 扩展的核心，因为它为平台带来了前所未有的数据一致性。在 CRDs 的帮助下，数据:

*   遵循众所周知的模式。
*   是严格类型化的。
*   只包含开发人员想要的值。

根据 Red Hat 工程师的说法，“CRD 已经在 Red Hat OpenShift 的几个版本中得到完全支持，但将 OpenShift 4 开发为基于操作符的自动化平台让我们有机会直接找到剩余的差距。”因此，Red Hat 借用了一点对 OpenShit 的发展至关重要的技术，将 CRDs 移植到了 Kubernetes。随着运营商 API 的发展，Red Hat 能够将他们的注意力转向当前状态中缺失的功能，并将 CRDs 作为任何 API 的坚实基础提供给公众。“我们一直专注于允许 API 随着时间的推移而发展，提供修剪和结构模式等功能，并将它们添加回上游项目中。”

但是因为 API 从来都不是完美的，红帽让 CRD 的作者通过一个可执行的 OpenAPI 规范来表达意图成为可能。有了这个规范，集群可以自我记录任何给定的 API 如何为开发人员或管理员工作。

据 Kubernetes 的负责人 Lachlan Evenson 称，“随着我们过渡到 GA，重点是 API 客户端的数据一致性。这些结合起来，再加上 CRD 转换机制，就足以构建稳定的 API，随着时间的推移不断发展，就像本地 Kubernetes 资源在不破坏向后兼容性的情况下发生变化一样。”

CRDs 的另一个非常聪明的特性是默认。实际上，缺省意味着清单中未指定的字段总是会被 **kube-apiserver** 自动设置为缺省值。例如，如果管理员忘记设置 **pod.spec.restartPolicy** ，API 服务器会知道将其设置为默认值“总是”当创建清单时，如果没有设置必要的值，这可能会造成很大的不同。有了默认值，您知道那些必填字段将总是自动定义的。

## Kubernetes 1.16 中的其他增强

CRD 并不是 Kubernetes 唯一能让企业感到兴奋的增强功能。根据 Lachlan 的说法，1.16 有四个特性。这些功能仍在开发中，但为大型企业提供了一些令人兴奋的可能性。

*   **Windows 容器工作负载身份:**对活动目录组托管服务帐户(GMSA)的支持现已升级到测试版。GSMA 是一种 AD 帐户，允许 Windows 容器通过网络与其他资源通信。
*   **RunAsUserName:** 这个已经到了 alpha，是一个指定 windows 标识(在 Windows 中)的字符串，用来运行容器的入口点。这是新引入的 windowsOptions 组件的一部分。
*   **对 kubeadm 的设置和节点加入的改进:**现在有了对 kubeadm 的 alpha 支持，使 Kubernetes 用户能够轻松地将 Windows worker 节点加入到现有集群中(与 Linux 中的方式相同)。
*   **容器存储接口(CSI)现已获得 alpha 支持:**这引入了对树外提供者的 CSI 插件支持，这将使 Kubernetes 集群中的 Windows 节点能够为基于 Windows 的工作负载利用持久存储。

Kubernetes 1.16 将引入两个新的增强来提高可伸缩性。这些功能是:

*   端点切片将在网络路由中发挥重要作用。每个网络端点在端点切片中被跟踪，以帮助 **kube-proxy** 生成代理规则，从而允许 pods 更好地与 Kubernetes 通信。
*   IPv4/IPv6 双栈支持将 IPv4 和 IPv6 地址分配给 pod 和服务。这意味着群集将能够访问更大的 IP 地址块。

## 库贝特尔

一段时间以来，将 kubectl 从 Kubernetes 主存储库中分离出来的想法一直被讨论。为什么？根据 Eads 和 Shimanski 的说法， **kubectl** 独立将允许更快的迭代和更短的发布周期。这并非易事。事实上，几个红帽工程师参与了这项工作，许多障碍出现了。然而，随着 Kubernetes 1.16 的发布， **kubectl** 现在被发布到它自己的[库](https://github.com/kubernetes/kubectl/)中。

## 其他改进

Kubernetes 还引入了许多其他新功能和改进。该列表包括以下内容:

*   容器存储接口(CSI)和树内驱动程序之间的功能奇偶校验。
*   改进了 CSI sidecars 的稳定性(一组标准容器，旨在简化 Kubernetes 上 CSI 驱动程序的开发和部署)。
*   卷克隆将允许用户从现有源创建卷。
*   CSI 卷扩展现在设置为默认值。
*   原始块支持改进。
*   etcdv3 现在是默认控制器。
*   消除了对单个容器运行时的直接依赖，因此用户现在可以使用 Docker 之外的运行时(如 rkt 或 CRI-O)。
*   基于角色的访问控制(RBAC)现在处于测试阶段。
*   StorageClass 对象的自动配置意味着自动卷配置现在由 Kubernetes 创建。
*   DaemonSet(允许您指定运行一组特定容器的节点)现在允许您执行滚动更新。
*   一个新的 beta 特性允许你拥有多个调度器，每个调度器控制一组不同的 pod。
*   您现在可以设置 stubDomains，它定义了用于特定域的名称服务器。

如你所见，Kubernetes 1.16 提供了很多功能。为了享受这些新功能，请确保在公司允许的情况下尽快升级到最新版本。关于新增强的更多细节，请务必阅读官方的变更日志。

红帽是新堆栈的赞助商。

照片由来自 Pixabay 的 Youssef Jheir 拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>