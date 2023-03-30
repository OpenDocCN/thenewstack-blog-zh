# StarlingX 6.0，边缘计算云堆栈到来

> 原文：<https://thenewstack.io/starlingx-6-0-the-edge-computing-cloud-stack-arrives/>

[OpenInfra Foundation](https://openinfra.dev/) 的开源、边缘计算云栈 [StarlingX](https://www.starlingx.io/) 的最新版本 [StarlingX 6.0](https://docs.starlingx.io/specs/specs/stx-6.0/index.html) 已经发布并准备运行。它针对低延迟和高性能应用进行了优化。换句话说，这意味着边缘和物联网(IoT)平台。它通过结合 Ceph、OpenStack、Kubernetes 和其他开源包来实现这一点。

StarlingX 的主要市场是电信运营商，如 T-Systems、威瑞森和沃达丰。但是，需要在几台到数百台服务器上部署边缘云的企业也在接受它。

## 升级的 Linux 操作系统

其最根本的新特性是 StarlingX 将其核心 Linux 操作系统升级至 [Linux 内核 5.10](https://www.fosslinux.com/44881/features-of-linux-kernel-5-10.htm) 。这样做主要是因为这个内核支持[虚拟路由和转发(VRF)](https://www.techtarget.com/searchnetworking/definition/virtual-routing-and-forwarding-VRF) 。借助 VRF，您可以在网络堆栈中创建虚拟路由和转发域。一个用例是多租户问题，其中每个租户都有自己独特的路由表，或者至少需要不同的默认网关。Linux 内核 5.10 也有用户空间工具来配置 VRF 的路由和转发接口。

新的 StarlingX 还配备了安全增强功能。其中包括自动证书管理和警报。这是通过[证书管理器](https://cert-manager.io/docs/)完成的。现在，平台服务可以使用 cert-manager 来简化以下平台证书的管理(例如自动续订): RESTAPI /GUI 证书；注册表. local 证书；以及 [OIDC/DEX 证书](https://dexidp.io/docs/oidc-certification-setup/)。

这个新的证书功能还使您能够使用上传的证书或自动生成的证书来更新正在运行的系统上的 Kubernetes 根 CA 证书。还为云和分布式云部署提供了证书编排。

有了这个，你也可以避免令人头痛的过期证书， [StarlingX 现在会向你发送一个过期或已经过期的证书](https://docs.starlingx.io/security/kubernetes/alarm-expiring-soon-and-expired-certificates-baf5b8f73009.html#alarm-expiring-soon-and-expired-certificates-baf5b8f73009)的警报。你也可以为 Kubernetes 和 [etcd](https://etcd.io/) 做一个单独的认证中心(CA)。这是用 etcd 根 CA 证书完成的[。它签署 etcd 服务器和客户端证书，以及 kube-apiserver etcd 客户端证书。这也是用于验证由 etcd 根 CA 证书签名的各种服务器和客户端证书的 CA 证书。这样，您现在可以为 Kubernetes 和 etcd 提供一个单独的根 CA。](https://docs.starlingx.io/security/kubernetes/etcd-certificates-c1fc943e4a9c.html#etcd-certificates-c1fc943e4a9c)

另一个安全性增强是它对 Linux 审计系统 auditd 的支持。这样，您可以根据预配置的审计规则跟踪安全违规事件。这些事件由`auditd`守护进程记录在一个日志文件中，您可以使用它来检测误用或未授权的活动。有了这些信息，你就可以采取适当的行动。

## 双工配置

自 StarlingX 于 2018 年问世以来，你可以在一体化设置中安装它，过渡到不同的配置则是另一回事。现在，您可以将部署迁移到包含两个控制器节点的双工配置。这样，您可以从一个子云部署转移到另一个子云部署，而无需全新安装。

这也意味着 StarlingX 很快就可以用于灾难恢复。作为这项工作的一部分，您现在可以在恢复系统控制器的同时，在分布式云系统之间移动子云。您还可以使用这种技术来整合部署并关闭一些未使用的边缘站点。

听起来很有趣？今天就可以[下载 StarlingX 6.0 代码](https://opendev.org/starlingx)，看看是否符合你的需求。我个人从第一天就喜欢 StarlingX，推荐尝试。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>