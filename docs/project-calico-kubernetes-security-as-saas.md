# 卡利科项目:SaaS 的库伯内特安全

> 原文：<https://thenewstack.io/project-calico-kubernetes-security-as-saas/>

保护我们最喜欢的容器编排程序并不容易。但是，一些公司和项目，比如 T2 的 jet stack T3 和 T4 的 cert-manager T5，正试图让它更易于管理。承担这一艰巨工作的最新企业是 [Tigera](https://www.tigera.io/) ，Calico 项目的创建者和维护者，为 Kubernetes 的安全性和可观察性提供软件即服务(SaaS)，Calico Cloud 。

很可能你已经知道了印花布。最初为 [OpenStack](https://www.openstack.org/) ， [Calico 使用互联网协议(IP)路由，而不是交换、虚拟网络、覆盖网络或其他更复杂的方法，简化了在云网络上移动数据包](https://thenewstack.io/project-calico-and-the-challenge-of-cloud-native-networking/)。由于 IP 只能提供粗粒度的跨节点隔离，Calico 添加了一个实时分布式过滤引擎来控制节点如何与每个节点通信。这实际上使您能够使用 Calico 作为网络策略执行工具。

从早期开始， [Calico 就已经采用了扩展的 Berkeley 包过滤器(eBPF](https://thenewstack.io/beyond-kube-proxy-tigera-calico-harnesses-ebpf-for-a-faster-data-plane/) )。这个最近添加到 Linux 内核的[作为一个内核虚拟机(VM ),它提供了更快的可扩展网络包过滤。](https://thenewstack.io/linux-technology-for-the-new-year-ebpf/)

以这种新的、更快、更灵活的数据平面模型为例，除了使用 Calico 作为第 3 层网络在 pod 之间路由数据包之外，Calico 还可以轻松用于网络安全。

为了获得更高层次的数据，Calico 监听来自 Kubernetes API 服务器的事件，从容器网络接口(CNI)和 Kubernetes 策略 API 获取元数据更改和策略添加。让它更有用的是，Calico 实际上不需要 Kubernetes 或任何其他管弦乐队。这意味着您还可以使用它来支持、保护和跟踪遗留应用程序和云服务。非常方便，对吧？

综上所述，Calico 还可以很好地与[谷歌零信任安全模型](https://cloud.google.com/blog/topics/developers-practitioners/what-zero-trust-identity-security)配合使用。这假设网络和主机将被攻破，并自动限制攻击的范围。正如[Tigera 的创始人兼首席技术官 Christopher Liljenstolpe](https://www.linkedin.com/in/liljenstolpe/) 所说，“我们不仅保护其他工作负载免受其他工作负载的影响，我们还保护世界其他地方免受工作负载的影响。”虽然这可能会让你担心，就像 [SELinux](https://www.hpe.com/us/en/insights/articles/how-to-set-up-selinux-right-the-first-time-1901.html) 一样，这意味着它非常复杂，Liljenstolpe 向用户保证“[我们试图让它非常容易理解](https://thenewstack.io/project-calico-and-the-challenge-of-cloud-native-networking/)”

Calico Cloud 带来的是一个单一的玻璃界面。您可以在多集群和多云 Kubernetes 环境中使用它来部署一组标准的出口访问控制，强制实施遵从性安全策略，以及观察和排除应用程序故障。

具体来说，Calico Cloud 解决了五个不同的 Kubernetes 集群网络安全问题。

首先，它提供了南北控制，因为微服务经常需要与运行在 Kubernetes 集群之外的服务或 API 端点进行通信。实现从 Kubernetes pods 到外部端点的访问控制是困难的。大多数传统或云提供商的防火墙不理解 Kubernetes 上下文，这迫使运营团队允许来自整个集群或一组工作节点的流量。

Calico Cloud 通过 DNS 策略解决了这些问题，该策略支持在 Calico 安全策略中使用域名来控制对集群外资源的访问。它还提供了一个出口网关来路由来自特定命名空间的流量，以确保在群集外保持一致的网络身份。对于亚马逊 Web 服务(AWS)用户，它还将组成员资格扩展到集群中的 pod，以便对亚马逊虚拟私有云(VPC)中的资源进行细粒度访问控制。

接下来是处理东西方安全问题。当攻击者发现具有过于强大的安全权限的易受攻击的 pod/服务帐户时，就会出现这种情况。为了解决这一问题，Calico Cloud 在您的多云、虚拟机和 Kubernetes 环境中使用微分段和单一安全策略框架，并辅以[一种“深度防御”](https://www.tigera.io/tigera-products/zero-trust/)方法。

为了保护您的容器网络中的数据，由于大多数传统的安全性和合规性方法不适用于高度动态和短暂的 Kubernetes 工作负载，Calico Cloud 部署了新的 [Linux Wireguard VPN](https://www.zdnet.com/article/linuxs-wireguard-vpn-is-here-and-ready-to-protect-you/) 。它还使用入侵检测系统(IDS)以及报告和警报，使您能够防范任何潜在的外部攻击者。

因为是 SaaS，所以没有前期成本。您可以在两种不同的服务产品中尝试 Calico Cloud:初级订阅，价格为每节点小时 0.05 美元或每节点每年 350 美元；专业版订阅价格为每节点小时 0.08 美元或每节点年 561 美元。你可以[比较选项，精确计算每月支出](https://www.tigera.io/tigera-products/calico-cloud-pricing)。还有一款 [Calico Cloud 14 天免费试用](https://www.tigera.io/tigera-products/cloud-trial)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>