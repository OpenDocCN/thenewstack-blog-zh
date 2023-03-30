# SPIFFE/SPIRE 为分布式架构带来了联合身份

> 原文：<https://thenewstack.io/spiffe-spire-brings-federated-identity-to-distributed-architectures/>

Portworx 赞助了 New Stack 在圣地亚哥的 KubeCon + CloudNativeCon 的报道。

在本周举行的 kube con+CloudNativeCon North America 2019 上， [SPIFFE 和 SPIRE](https://spiffe.io/) 项目将展示其扩展的功能，以提供 [OpenID Connect (OIDC)](https://openid.net/connect/) 联合身份，使微服务不仅可以在单个 SPIRE 实例上的自身之间使用这种安全性，还可以在数据库、服务网格和公共云提供商等共享服务之间使用这种安全性，而不必使用秘密和/或网络安全控制。

随着向分布式应用架构(由在多个位置运行的短暂微服务组成)的迁移，外围安全不再适用。相反，微服务可以采用一种称为零信任安全的安全形式，其中每个组件都与它必须与之交互的任何其他组件进行身份验证。

2018 年初，这两个项目加入了[云原生计算基金会](https://www.cncf.io/) (CNCF)，以帮助开发者更轻松地在其云原生应用中采用这种形式的安全。

[SPIFFE](https://spiffe.io/) ，代表面向所有人的安全生产身份框架，是一套开源标准，SPIFFE 运行时环境 [SPIRE](https://spiffe.io/spire/) 是实际实现该规范的软件。这两个[都在 2018 年初](https://blog.scytale.io/spiffe-joins-the-cncf-a2f0f36e4071)在沙盒级别加入了 CNCF，从那时起， [Scytale](https://www.scytale.io/) ，一个专门为 SPIFFE 创立的初创公司，也[推出了 Scytale Enterprise](https://thenewstack.io/scytale-launches-spiffe-based-service-identity-management/) ，这是一个基于 SPIFFE/SPIRE 的基于云的订阅，旨在跨云、容器和内部基础设施标准化服务认证。自创建以来，SPIFFE 标准还被谷歌的 Istio 服务网和 Hashicorp 的领事 T21、特使和 gRPC 等项目采用。

Scytale 的联合创始人兼产品负责人 Andrew Jessup 在接受新堆栈采访时解释说，到目前为止，SPIFFE 兼容软件只能使用同一身份服务器与其他组件进行安全通信。他解释说，现在有了联合身份，不同的系统和服务能够安全地相互通信，这是客户一直以来的要求。

“我有所有这些不同的服务网格在运行，也许我还在使用其他实现，我如何才能真正开始将这些东西连接在一起，这些小孤岛？即使我有两个不同类型的业务部门运行不同的基础架构，都运行 SPIFFE 兼容的系统，我如何在它们之间建立连续的信任？”杰赛普说。“如果我在一个数据中心运行 SPIRE，在另一个数据中心运行 Istio，即使这是 SPIFFE 的两种不同实现，这些东西也可以联合起来并学会相互信任，这样，在一个数据中心的 Istio 集群上运行的软件和在另一个数据中心的数据中心上运行的软件也可以相互信任。”

Scytale 的工程师 Evan Gilman 在公司声明中进一步解释了这些新功能的重要性。

吉尔曼说:“OIDC 联邦是分布式系统安全交互的一个很好的方式，而不需要分发共享的秘密。“例如，在 SPIRE 管理的内部数据中心内运行的系统现在可以直接通过 AWS 等云平台进行身份验证，而无需共享机密或私钥。”

杰瑟普说，这种共享秘密或私钥的缺乏有助于防止密码泄露或最近的 Capitol One 漏洞(有人获得了共享的 AWS 密钥和秘密)导致的漏洞。

Jessup 说:“我们已经看到了许多早期的兴趣，不仅是将 SPIFFE 用于连接数据中心内的单个工作负载或连接跨数据中心的内容，现在还用于连接现有的传统软件系统。“这似乎是一个微妙的问题，但对于 SPIFFE 项目来说，这是一个非常重要的转变，因为它极大地拓宽了 SPIFFE 实际能够做的事情的范围和用途。”

对于那些参加 kube con+CloudNativeCon North America 2019 并有兴趣了解更多信息的人来说，Scytale 将在展位#S21 展示 SPIRE 和 Scytale Enterprise，并在 SPIFFE/SPIRE 上举办几次闪电讲座。

Kubecon+CloudNativeCon 和 HashiCorp 是新堆栈的赞助商。

来自 Pixabay 的 David Mark 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>