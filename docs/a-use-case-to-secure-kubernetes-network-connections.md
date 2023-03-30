# 保护 Kubernetes 网络连接的用例

> 原文：<https://thenewstack.io/a-use-case-to-secure-kubernetes-network-connections/>

组织在转向 Kubernetes 和微服务基础设施时通常会遇到的一个绊脚石是动态共享和保护数据。

在传统的整体式基础架构中，单个防火墙结构以前基本上足以限制和监控数据，并管理单个边界内的安全层。然而，Kubernetes 集群之间和内部共享的应用程序和数据通常在不同的云和内部环境之间扩展。

正如 [HashiCorp](https://www.hashicorp.com/?TheNewStack) 的开发者支持者 Nicole Hubbard 所观察到的，当客户试图保护他们在 Kubernetes 集群中运行的服务之间的通信时，他们经常面临困难。Hubbard 说，这种困境通常涉及到试图找出如何锁定集群内外的应用程序之间或集群之间的应用程序之间的通信。

[https://www.youtube.com/embed/honVx93d9aM?feature=oembed](https://www.youtube.com/embed/honVx93d9aM?feature=oembed)

视频

在本期[节目中，Hubbard 在加州圣克拉拉的 Palo Alto Networks 工作室现场录制了新的 Stack Makers](https://thenewstack.io/podcasts/makers) 播客，展示了 [Consul Connect](https://www.consul.io/docs/connect/index.html) 和 [Envoy](https://www.envoyproxy.io/) 如何帮助安全地维护不同 Kubernetes 和微服务环境之间的数据通信。

Hubbard 说，Consul 负责定义角色，定义和跟踪可用的服务，并向数据平面提供这些信息，以便数据平面知道如何移动流量。数据平面基本上是一个可插拔的代理，它从控制平面接收这些信息，并使用这些信息将数据正确地路由到正确的位置。

[妮可·哈伯德——保护 Kubernetes 网络](https://thenewstack.simplecast.com/episodes/nicole-hubbard-securing-kubernetes-networking)

“如果你看看你可以运行应用程序的不同方式，你可以在大型机之间的任何地方运行它们，在你自己的数据中心、虚拟机中的你自己的硬件，甚至是无服务器的容器和功能。但是所有这些之间的一个共同点是网络。你必须保护所有不同服务之间的通信，不管它们在哪里运行，”哈伯德说。“但随着您的成长，您开始将这些服务分解为微服务，您会遇到这样的问题:‘a’如何与‘b’对话，以及我如何找到‘b’的位置。”

哈伯德描述了一些银行合作伙伴如何能够拥有多达 4000 项服务，“在没有极高运营开销的情况下，这些服务不会随 VLANs 或防火墙规则而扩展。”Hubbard 描述了在一个服务网格中，有一个控制平面和数据平面，而“我们的控制平面是 Consul。”Hubbard 说:“Consul 负责定义角色，定义和跟踪可用的服务，并将这些信息提供给数据平面，以便数据平面知道如何移动流量。”。“数据平面基本上是一个可插拔的代理，它从控制平面接收这些信息，并使用这些信息将数据正确地路由到正确的位置。”

*欲了解安全思想领袖的更多见解， [Cloud Native Security Live，2020 虚拟峰会](https://vshow.on24.com/vshow/Palo_Alto_Networks/registration/16700)为您提供了一个向开发人员、DevOps 专业人员和 it 领袖学习经验和专业知识的机会，他们在容器技术和 DevSecOps 方面都有很大的利益。由 Palo Alto Networks 的 Prisma 主办，与 New Stack 合作，您仍然可以虚拟地参加 2020 年 2 月 11 日举行的活动，参加一整天关于云原生安全性的讨论，无论您身在何处，都可以在线参加。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>