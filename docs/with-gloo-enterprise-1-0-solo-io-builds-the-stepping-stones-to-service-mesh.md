# 有了 Gloo Enterprise 1.0，Solo.io 为服务网格构建了垫脚石

> 原文：<https://thenewstack.io/with-gloo-enterprise-1-0-solo-io-builds-the-stepping-stones-to-service-mesh/>

Portworx 赞助了 New Stack 对 KubeCon+CloudNativeCon 北美 2019 的报道。

Solo.io 发布了 Gloo 的第一个生产就绪版本，即其企业级服务网格和 API 网关。顾名思义， [Gloo Enterprise 1.0](https://medium.com/solo-io/announcing-gloo-1-0-a-production-ready-envoy-based-api-gateway-90edde077145) 充当传统和现代分布式架构之间的粘性链接。

T2 solo . io 的理念是帮助客户实现基础设施的现代化。首席执行官兼创始人 [Idit Levine](https://twitter.com/idit_levine) 告诉 New Stack，他们的大多数客户都是大型金融企业，在过去两年中，他们一直在使用 Solo.io，从单片架构转向微服务架构。该公司在本周在圣地亚哥举行的 KubeCon+CloudNativeCon 北美 2019 年会议上首次亮相这项技术。

Levine 说她的客户将 Gloo 1.0 称为迈向服务网格的第一步。它的创建是为了解决大多数大型企业面临的一个简单问题，这些企业的服务分布在不同的环境、云和区域中。微服务通过 API 通信，她说这需要一个 API 网关。Levine 认为，它需要是一个简单的服务，在遗留的、无服务器的和基于 Kubernetes 的服务中是一样的，因为从一个单一的服务到许多服务的过渡不是快速的，所有这些部分必须一起通信。

由于 Solo.io 目前的大多数客户都是金融领域的大玩家，Levine 称这是“严肃的业务，因为基本上我们正在接管所有的网络。”

“如果我们做错了什么，所有的基础设施都瘫痪了，”她继续谈论她感到有多大的责任。

“不管你在做什么，Gloo 都会确保你在网络上，”Levine 说。

一个长期客户是互联网巨头 Vonage。Vonage 的首席技术官 Sagi Dudai 在一份声明中说:

“Gloo Enterprise 的强大技术，加上协作的 Solo.io 团队，使我们能够跨地区和云提供商部署这些功能，同时与我们的身份验证机制相集成，以满足高级使用计划的业务需求，并与我们的 CICD 管道相集成，以支持 Vonage 的自治团队。”

Gloo 允许组织以相同的方式构建，而不管云提供商、环境或服务类型，所有这些都在生产中运行。

Gloo 因抢先酷炫而获得加分，因为它是在 Envoy 之上两年构建的，Envoy 是目前非常受欢迎的进出服务网格的高性能代理。

Levine 表示，Solo.io 是迄今为止唯一一家为 Envoy 编写扩展的公司，该扩展包括一个 web 应用防火墙、一个 web 组装引擎、数据丢失保护和一种授权域的方式。这些都是受监管的金融客户转向这些更分散的架构的最低要求。

Solo.io 也无缝地运行在 Kubernetes 之上，包括存储自定义资源定义或 CRD。

Solo.io 与微软一起开发了[服务网格接口(SMI)](https://www.solo.io/solutions/service-mesh/) 作为不同网格之间的翻译器，允许它们在生产中看起来相似，跨多个服务网格交流相同的“语言”，并共享相同的根证书。它允许您管理和操作服务网格，并允许您在集群上安装服务网格或重新发现已经安装的服务网格。

Levine 说，他们开发这个是因为你永远不会只运行一个网格实例，而是跨不同的集群和云服务运行多个实例。

她称之为“扁平化网络——每个服务网格都可以与同一个集群中的另一个服务网格相互作用。”

最后，本周早些时候，该公司还发布了一个[开源自动驾驶操作员框架](https://medium.com/solo-io/introducing-autopilot-an-open-source-project-for-adaptive-service-mesh-3195accc9670)。它的创建是为了解决服务网格操作的问题。

"如果你给服务网格错误的配置，严重的是，你的数据中心关闭."莱文说。“确保人们不犯错的最好方法是确保人们不必做任何事情。”

开发人员通常会在[渐进交付](/the-rise-of-progressive-delivery-for-systems-resilience/)期间对他们的服务网格进行更改，这可能会导致大规模崩溃。

莱文说，有了自动驾驶仪，你就创造了一个门槛。Autopilot 监控你的网格，你的环境，指标和服务，包括 Github 和 Webhooks。如果有东西越过了这个门槛，Autopilot 就会自动停止那个服务，回滚到之前的版本。

Levine 这样描述了公司的目标和加工过程:

“首先，我们正在帮助客户利用下一代 API 网关管理他们的微服务和 API。然后，我们帮助他们采用服务网格—无论是哪种类型、在哪里、无论是哪种云或工作流。然后，我们让他们在这个服务网格上扩展，以确保他们的网格是自适应的，我们正在使用自动驾驶仪来做到这一点。”

您可以在 2019 年 12 月 5 日参加 Gloo Enterprise 上的演示。

KubeCon+CloudNativeCon 是新堆栈的赞助商。

来自 Pixabay 的 enriquelopezgarre 的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>