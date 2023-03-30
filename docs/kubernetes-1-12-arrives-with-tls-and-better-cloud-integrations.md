# Kubernetes 1.12 带来了 TLS 和更好的云集成

> 原文：<https://thenewstack.io/kubernetes-1-12-arrives-with-tls-and-better-cloud-integrations/>

Kubernetes 项目正以极快的速度走向令人厌烦的境地。随着流行的开源容器编排平台的成熟，那些乏味的特性已经成为了焦点，其中很多都关注稳定性和可靠性。对于周四发布的[Kubernetes 1.12](https://www.coreos.com/blog/kubernetes-112-released)，那些致力于这个项目和各个[特殊利益集团](https://github.com/kubernetes/community/blob/master/sig-list.md) (SIGs)的人最初列出了 60 多个提议的特性。其中一半多一点的版本最终发布，更多的版本像往常一样被推迟或延迟。

此版本中的变化包括 TLS 引导的普遍可用性、使用 Kubernetes API 从卷快照数据源恢复卷的能力、新的测试版 KubeletPluginsWatcher，以及一些为解决大型集群面临的调度挑战而做的基础工作。

[Stephen Augustus](https://www.linkedin.com/in/stephenaugustus) ，Red Hat[open shift](https://www.redhat.com)Tiger 团队的专业解决方案架构师和 Kubernetes 产品管理主席说，如今 Kubernetes 的游戏名称是无聊，避免突破性的改变。

“我们真的已经超越了必须在核心 Kubernetes 中的概念。Augustus 说:“无论是着眼于 [CoreDNS](https://coredns.io/) 还是 [Kube-DNS](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/dns/kube-dns) ，还是其他一些组件，我们都正在进入选择自己的冒险 Kubernetes 的阶段。“我们开始进入跨运行时、网络、存储和 DNS 提供商的不同组合；这是新的故事。我们一直在说，现在的共同主题是 Kubernetes 是稳定的。也就是说，每一个向前发展的版本都应该是一个“无聊”的版本。

“在 1.3 到 1.12 的发布周期中，我们已经成功地确定了 Kubernetes 的核心功能。我们已经提供了所有的核心功能。下一步是确保它的稳定性，不断改进测试套件以确保稳定性，并继续检查我们在新增强中看到的可伸缩性问题。我认为 CoreDNS 目前是一个典范，它突出了新的挑战:试图定义一个生态系统中的稳定性是什么样的，现在允许你挑选和选择它的基本组件，”Augustus 指出。

## TLS 达到 GA，增加刺激

事实上，要在这个 Kubernetes 版本中找到刺激，人们必须关注其中仍然在发展的项目，并从 alpha 到 GA 进行推广。围绕 TLS 的新特性就是 1.12 中的一个例子。在 Kubernetes 1.4 中，TLS 引导首次作为 alpha 特性加入。从那时起，用户就一直要求这种以第一天为中心的功能达到成熟。从版本 1.12 开始，这个特性现在已经普遍可用，应该可以更容易地启动和运行集群。

但是，还有一些 TLS 管理功能在不断成熟。TLS 证书轮换就是其中的一个特性，在 Kubernetes 1.12 中它已经达到了 beta。

在最后一刻被推迟的这个版本的一个推动因素是从 [Kube-DNS](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/dns/kube-dns) 到 [CoreDNS](https://coredns.io/) 作为默认 DNS 服务的转变。CoreDNS 的引入是为了解决在其他 DNS 插件中发现的安全性和可扩展性问题，但最近，在[谷歌云引擎](https://cloud.google.com/compute/)中运行的更大规模(1000 多个节点)集群中的 CoreDNS 出现了问题。虽然大多数用户不会在他们的日志中注意到这个问题，但是, [VMware](https://www.vmware.com/) 的高级工程师兼 Kubernetes 1.12 版本的负责人 [Tim Pepper](https://www.linkedin.com/in/tim-pepper-b0017a4/) 说，这足以推迟将 CoreDNS 作为该版本的默认提供商的转变。

这个版本的另一个主题是更好的云提供商集成。例如，这个版本尤其包含了许多旨在帮助 Kubernetes 在微软 Azure 上运行的改变。为了跟踪各种变化并确保云提供商之间的代码和流程一致性，Kubernetes 团队建立了一个新的 SIG，称为 [SIG 云提供商](https://github.com/kubernetes/community/blob/master/sig-cloud-provider/README.md)。

Pepper 表示，SIG 正在进行的工作旨在找到跨云实现的解决方案，而不是简单地修补 Azure、亚马逊或谷歌等的漏洞。他说，参与的团队已经越来越善于在 Kubernetes 代码库中找到超出其特定云的解决方案。

## 供应商一致性仍然是一个问题

随着 Kubernetes 市场上所有这些云提供商和发行商的出现，CNCF 内部正在努力建立一种衡量一致性的方法。Pepper 说，“现在有一个非常大的一致性努力在问这个问题，Kubernetes 集群应该是什么样子，它需要遵守什么规则才能合规？’从性能文档和功能的角度来看，我可以看到，人们的态度很明显是“让我们来解决存储问题”。让我们计算一下。我们不仅要为我们的云提供商解决这些问题，还要以一致的方式来解决，这样才能在所有云提供商中实施。"

虽然一致性仍在进行中，但人们可以想象云提供商和 Kubernetes 分发提供商可以展示 CNCF 认证贴纸，证明他们的实现符合该项目提出的要求。这类工作已经由 Cloud Foundry PaaS 完成，主要由该项目的非营利管理基金会推动。

*作者亚历克斯·汉迪为红帽工作；这篇文章是独立完成的。*

云计算原生计算基金会、Red Hat 和 VMware 是新体系的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>