# VMware 的 Antrea 为 Kubernetes 带来了可编程网络

> 原文：<https://thenewstack.io/vmwares-antrea-brings-programmable-networks-to-kubernetes/>

[VMware](https://tanzu.vmware.com?utm_content=inline-mention) 的[项目 Antrea](https://github.com/vmware-tanzu/antrea) 最近达到了两个里程碑，发布了 1.0 版本，并成为[云计算原生计算基金会](https://tanzu.vmware.com?utm_content=inline-mention)沙盒项目，CNCF 及其与开源社区的合作不断取得成果。

在 5 月 5 日举行的 kube con+CloudNativeCon Europe 的一天活动之后，VMware 员工工程师[安东宁巴斯](https://www.linkedin.com/in/antonin-bas-8b444a38/?locale=en_US)和[沈建军](https://github.com/jianjuns)讨论了 Kubernetes 网络和安全工具 Antrea 的新功能，并在“Antrea 项目和 KubeCon EU 总结:VMware 项目维护者概览”直播期间展示了它的一些功能。New Stack 创始人兼出版商亚历克斯·威廉姆斯(Alex Williams)和编辑及营销总监利比·克拉克(Libby Clark)主持了直播。

Bas 说，Antrea 的 1.0 版本及其成为沙盒项目是“过去 18 个月里我们所有合作伙伴的见证”。“我认为这确实标志着我们的愿望，表明了我们对该项目的承诺，我们相信该项目现在已经足够稳定，可以用于生产。”

沈说，为了帮助吸引“社区支持和更多的用户和开发者”，与开源社区保持密切的关系也很重要

巴斯说，这个想法也是为了“增加与 CNCF 其他项目的协同作用”。“我认为 CNCF 项目保持这种协同作用很重要，这是用户拥有一个集中位置的好方法，他们可以在这里[更好地导航 Kubernetes 和云原生景观，”Bas 解释道。

该软件于 2019 年 11 月发布，可作为任何 Kubernetes 集群的[容器网络接口(CNI)](https://github.com/containernetworking/cni) 和 [Kubernetes 网络策略](https://kubernetes.io/docs/concepts/services-networking/network-policies/)，无论其来源如何。基于 [Open vSwitch (OVS)](https://www.openvswitch.org/) 构建，最初的项目团队在它发布之前就意识到没有一个 CNI 插件的 CNCF 项目。

“从那时起，事情发生了变化，但当时，我们真的想把 Antrea 作为 CNI 插件推出，成为 CNCF 的沙盒项目。这就是 kick 开始的原因，”Bas 说。

Bas 说，OVS 的可编程性有助于实现联网和其他功能。Bas 说:“它也有助于解决从基本的第 3 层连接到第 4 层负载平衡的所有问题。”。

Antrea 1.0 的主要功能包括“群集范围”的安全策略和策略分层、出口策略控制、改进的可观察性和诊断以及加密。

Bas 表示，对于共享一个集群的多个租户，每个租户都有一个指定的名称空间，同时还可以“防止跨名称空间的流量，以隔离租户——除非这对您的应用程序来说是必要的”。

例如，对于网络延迟，可以观察服务之间的流量并确定带宽分配，以便“找出是否有人占用了您集群中的带宽，”Bas 说。

用于审计连接的日志记录功能可以揭示例如被拒绝和被授权的连接以及其他数据。日志也存档在一个集中的位置，这样更容易观察和阻止可能违反网络策略的连接。

点击查看完整讨论[。](https://www.youtube.com/watch?v=uoATkCIFRVM&ab_channel=TheNewStack)

[https://www.youtube.com/embed/uoATkCIFRVM?feature=oembed](https://www.youtube.com/embed/uoATkCIFRVM?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>