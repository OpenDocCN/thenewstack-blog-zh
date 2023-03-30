# Kubernetes 部署安全性的 4 种威胁模型

> 原文：<https://thenewstack.io/4-threat-models-for-kubernetes-deployment-security/>

作为一个编排平台， [Kubernetes](https://kubernetes.io/) 影响了许多运行时安全功能。这些包括身份验证、授权、日志记录和资源隔离，以及更高级的含义，如工作负载放置和网络分段。

由于 orchestrator 在容器运行时环境中的广泛影响力，Kubernetes 安全性是容器基础设施安全性的一个重要方面。在我们新博客系列的第一部分，也是我们即将发布的关于 [Kubernetes 部署和安全模式](https://thenewstack.io/ebooks/kubernetes/kubernetes-deployment-and-security-patterns/)的电子书的一部分，我们将讨论 Kubernetes 部署的威胁模型。

## Kubernetes 威胁模型

![](img/291025fd273d3107f910f67c65014065.png)

王晨曦博士

王晨曦博士是网络安全战略咨询公司简·邦德项目的创始人。网络安全行业知名战略家、演说家、作家。Wang 博士还担任 OWASP 基金会董事会副主席，ClearSky security 和 630 Cyber 的投资顾问，以及各种安全初创公司和 IT Security Planet 的战略顾问。此前，陈曦是 Twistlock 的首席战略官，负责将 Twistlock 的品牌和业务从零发展到细分市场的领导者。陈曦被《SC》杂志评为 2016 年度最具影响力女性，她还担任了 2017 年格蕾丝·赫柏会议的项目主席(安全和隐私)。晨曦在网络安全行业建立了辉煌的职业生涯，包括在 Forrester Research、Intel Security 和 CipherCloud 担任多个高管职位。在 Forrester，Chenxi 研究了移动、云和企业安全，并撰写了许多有影响力的研究论文。在英特尔安全部门，她领导了涵盖硬件和软件平台的无处不在战略。陈曦的职业生涯始于她在卡内基梅隆大学担任计算机工程教员。晨曦是一位广受欢迎的公共演说家，曾被全球顶级媒体和活动报道过。晨曦拥有弗吉尼亚大学计算机科学博士学位。

在 [Kubernetes](/category/kubernetes/) 环境中，无论部署模式如何，通常都存在四种类型的威胁(有一些边缘情况例外):

1.  **旨在破坏 Kubernetes 控制的外部攻击:**这种威胁存在于所有连接的系统中。在 Kubernetes 集群的上下文中，这表示攻击者获得了对系统的访问权，或者破坏了将影响系统安全性的某些控制。
2.  **受损的容器或节点:**如果 Kubernetes 控制的环境中有恶意容器，或者集群中有恶意节点，对其余节点或集群有什么影响？您能否有效地控制节点上和群集内的“爆炸半径”？
3.  **凭证受损:**当 Kubernetes 管理员的凭证受损时会发生什么？这对集群有多大影响？
4.  **滥用合法权限:**当系统配置错误、缺乏控制或运营未受到密切监控时，可能会发生这种情况。

这些不同的威胁可能会导致大量危害和不良情况，包括特权提升、敏感数据泄露、运营受损或违反合规性政策。

[cyclone slider id = " kubernetes-series-book-2-赞助商"]

已经引起相当多关注的攻击场景之一是对“爆炸半径”的担忧，即被破坏的容器会对同一节点上的其他容器造成多大的损害，或者被破坏的节点会对集群的其余部分造成多大的损害？Kubernetes 部署的所有安全考虑都是由这些威胁模型以及最小化“爆炸半径”的需求所驱动的。

## 外部攻击

在 Kubernetes 环境中，外部可访问的组件将暴露于外部攻击。这些组件可以包括应用编程接口(API)服务器、 [kubelet](https://kubernetes.io/docs/reference/generated/kubelet/) 和 [etcd](https://coreos.com/etcd/) 。(请参阅新堆栈的电子书“Kubernetes 生态系统的状态”以查看 Kubernetes 节点中的组件。)

为了减轻外部攻击的威胁，请确保只暴露必要的 Kubernetes 服务，而不是更多。始终对任何公开的服务实施身份验证并配置正确的网络安全策略。

## 受损容器

最终，Kubernetes 管理在容器中运行的工作负载。如果一个容器受到威胁，那么问题是该容器是否可以提升权限来控制其他容器或集群。

Kubernetes 的隔离机制，如名称空间或网络分段，以及一些内置的、操作系统级的控制，可以管理容器可以访问的内容，有助于限制受损容器的影响。用户应该注意的另一个控制是限制可以在特权模式下运行的容器数量的能力——如果特权容器被破坏，它将比普通容器造成更大的危害。

## 泄露的凭据

当合法用户的凭据遭到破坏时，系统中可能有恶意用户。因此，正确管理和限制用户对群集资源的访问并密切监视用户操作至关重要。

为了减少恶意用户的影响，您需要实施最低权限访问、基于角色的访问控制或其他细粒度的访问控制。

## 滥用特权

如果系统配置不正确，可能会导致滥用用户权限。例如，如果网络策略不限制 pod 或命名空间之间的访问，则用户可能能够读取他或她本来不应该访问的其他命名空间的流量。

防止滥用特权的主要手段是适当的强化。确保所有系统组件(如容器、pod、名称空间和 kubelets)都得到加强，以显著降低滥用权限的可能性。

另一个重要的防御是授权控制。Kubernetes 支持插件架构，允许包含复杂的授权逻辑。正确设计和实施授权；这是反对滥用特权的最有效的武器之一。

考虑到威胁模型，下一次我们将沿着四个主要原则探索 Kubernetes 安全性:身份验证和授权；资源隔离；硬化和网络安全；以及日志和审计。

由 [Yannick Pulver](https://unsplash.com/photos/ZwPuquZBnyM?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>