# Kubernetes 1.7 带来了可扩展性、安全强化和网络策略 API

> 原文：<https://thenewstack.io/kubernetes-1-7-brings-extensibility-security-hardening-network-policy-api/>

Kubernetes 1.7 已经发布，主要关注可扩展性和安全性以及大量新特性。

该版本包括四个稳定的特性，7 个测试版，19 个测试版。Kubernetes 每三个月发布一次，发布团队包括来自 Google、CoreOS、Mirantis、Red Hat、微软和其他公司的成员。总共有超过 375 人对新版本做出了贡献。

默认情况下不打开 Alpha 功能；用户可以选择使用它们，但是上游社区不认为它们是“生产就绪”的。红帽的 Joe Brockmeier 在[的博客文章](https://www.redhat.com/en/about/blog/whats-new-kubernetes-17-extensibility-rules)中解释说，测试版功能被认为是经过充分测试的，默认情况下是打开的，但它们可能会在以后发生变化。

他说，改进的可扩展性旨在扩展 Kubernetes 的范围和功能，而不膨胀核心项目。

用于限制容器网络流量的网络策略 API、用于负载平衡器的源 IP 处理、StorageOS 卷插件和云存储指标是 1.7 中被视为稳定的四项功能。

“升级到‘稳定’代表已经证明其生产就绪性的特性，并且在许多后续版本中被锁定。CoreOS 的软件工程师 Eric Chiang 是 Kubernetes 授权和认证特别兴趣小组的联合负责人，他说:“虽然这些往往不是最令人兴奋的发布项目，但它们展示了对 Kubernetes 核心的承诺，其他人可以在此基础上进行构建。

这些功能包括:

*   **自定义资源定义:**CRD 处于测试阶段，第三方资源正在转移到 1.7 的新 API 组中，但根据 CoreOS 的 [Eric Chiang](https://github.com/ericchiang) 的[帖子](https://coreos.com/blog/custom-resource-kubernetes-v17)，到了 1.8 版本，自定义资源定义将成为受支持的扩展机制，第三方资源将完全被否决。CRDs 将允许对 Kubernetes API 进行扩展，以提供核心 Kubernetes 中没有的特性，这些特性对用户来说看起来像是一流的 API。
*   **可扩展的外部准入控制:**这个 alpha 特性使管理员和集成商能够定义他们自己的可扩展策略和安全检查，以便将内容准入他们的 Kubernetes 集群。
*   **API 聚合:**在测试版中，它允许社区成员编写自己的 API 服务器。新的 API 可以在单独的聚合服务器上开发和测试，从而消除了等待核心 Kubernetes 团队审查的 API 提议的积压

**1.7 中的安全增强包括**节点授权器插件，用于限制 kubelet 访问和客户端/服务器传输层安全(TLS)证书轮换。此外:

*   **[网络策略 API](https://kubernetes.io/docs/concepts/services-networking/network-policies/)** —通过网络插件实现，它允许用户设置和执行管理哪些 pod 可以相互通信的规则。
*   **加密 etc 中的机密:**这个 alpha 特性允许在数据存储级别加密存储在 etcd 键值存储中的敏感数据。这超出了加密磁盘上的数据，允许 API 服务器在将数据传递给 etcd 之前对称地加密数据。
*   **限制节点对 API 的访问:**这种新的授权模式和准入插件，在测试版中，旨在将节点对敏感信息的访问仅限于在该特定节点上运行的 pods，而不能访问集群中的全局机密。

其他显著特征包括:

*   **DaemonSet 更新:**这个测试版特性增加了自动化 pod 更新的选项。1.7 增加了[回滚和历史](https://kubernetes.io/docs/tasks/manage-daemon/rollback-daemon-set/)功能。
*   **StatefulSet 升级:**同样在 beta 中，StatefulSet 升级可以自动化，使用一系列更新策略，包括滚动更新。
*   **支持带有 stateful set 的“突发模式”:**它允许对 stateful set 进行快速、无序的更改，以便根据需求进行缩放。在阿尔法。
*   **网络策略现在稳定:**提升到稳定状态，此功能允许标记选择 pod 并定义规则来指定允许进出这些 pod 的网络流量，而不是接受来自任何来源的流量。
*   本地持久存储:一个 alpha 特性，允许用户从一个存储类请求在带有本地附加存储的节点上执行他们的 pod。与 *hostPath* 相比，这种方法将是[存储本地持久数据](https://kubernetes.io/docs/concepts/storage/volumes/)的更可靠的模型。

管理 Kubernetes 项目的[云本地计算基金会](https://www.cncf.io/)引用了 Kubernetes 使用的持续增长，指出它是生产中使用最多的[CNCF 项目](https://www.cncf.io/blog/2017/06/28/survey-shows-kubernetes-leading-orchestration-platform/)。

有几个项目正在当地运行 Kubernetes 集群，即使是那些只想修补它的人，如 [minikube](https://kubernetes.io/docs/getting-started-guides/minikube/) 、 [kubeadm](https://kubernetes.io/docs/getting-started-guides/kubeadm/) 或 [kargo](https://www.youtube.com/watch?v=N9q51JgbWu8) 。

在最近一期的[新堆栈分析师](https://thenewstack.io/podcasts/analysts)播客中，话题是“[Kubernetes 现在要去哪里](https://thenewstack.io/podcast-power-panel-kubernetes-going-now/)？”唐尼·伯克霍尔茨是 451 研究[的前分析师，现在是卡尔森·瓦贡利特旅游公司的 It 服务副总裁；](https://451research.com/) [Krishnan Subramanian](https://twitter.com/krishnan) ，rishi dot Research[创始人兼首席研究顾问](http://rishidot.com/)；以及[贾纳基拉姆·MSV](https://thenewstack.io/author/janakiram/)，贾纳基拉姆&联营公司的负责人。看看这个:

[云本地计算基金会](https://www.cncf.io/)、 [CoreOS](https://coreos.com/) 和 [Red Hat](https://www.openstack.org/) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>