# 为什么您应该关注 Istio 网关

> 原文：<https://thenewstack.io/why-you-should-care-about-istio-gateways/>

[](https://aspenmesh.io/)

 [尼拉杰·波德达尔，阿斯彭网格平台主管

尼拉杰·波德达尔是阿斯彭网格平台主管。在他的职业生涯中，他研究过操作系统、网络和分布式系统的各个方面。他热衷于开发高效和高性能的分布式应用程序。他喜欢打壁球，并通过尝试新餐馆来收回打球消耗的卡路里。](https://aspenmesh.io/) [](https://aspenmesh.io/)

如果您正在拆分 monolith，使用 Istio 管理您的微服务的一个巨大优势是，它支持利用类似于传统负载平衡器和应用交付控制器的入口模型的配置。在负载平衡器领域，虚拟 IP 和虚拟服务器长期以来一直被用作使运营商能够以灵活和可扩展的方式配置入口流量的概念( [Lori Macvittie 对此有一些相关的想法](https://devcentral.f5.com/s/articles/wils-virtual-server-versus-virtual-ip-address) )。

在 Istio 中，网关控制网格边缘的服务公开。网关允许运营商指定 L4-L6 设置，如端口和 TLS 设置。对于入口流量的 L7 设置，Istio 允许您将网关绑定到虚拟服务。这种分离使得管理进入网格的流量变得很容易，就像在传统负载平衡器中将虚拟 IP 绑定到虚拟服务器一样。这使得遗留技术的用户能够以无缝的方式迁移到微服务。对于习惯于单片和边缘负载平衡器的团队来说，这是一种自然的发展，而不是一种全新的方式来考虑网络配置。

需要注意的一件重要事情是，在服务网格内路由流量和将外部流量引入网格有点不同。在网格中，您可以指定正常流量的例外情况，因为缺省情况下，Istio(与 Kubernetes 兼容)允许网格中的所有内容进行一次对话。如果您不希望某些服务进行通信，则有必要添加一个策略。让流量进入网状网络是一种反向代理情况(类似于传统的负载平衡器)，在这种情况下，您必须确切地指定您希望允许什么流量进入。

Istio 的早期版本利用了 Kubernetes 的 Ingress 资源，但最近发布的 Istio v1 alpha3 APIs 利用网关实现了更丰富的功能，因为 Kubernetes Ingress 已被证明不足以满足 Istio 应用。Kubernetes Ingress API 合并了 L4-6 和 L7 的规范，这使得具有独立信任域(如 SecOps 和 NetOps)的组织中的不同团队很难拥有 Ingress 流量管理。

此外，入口 API 的表达能力不如 Istio 通过 Envoy 提供的路由功能。在 Kubernetes Ingress API 中进行高级路由的唯一方法是为不同的入口控制器添加注释。组织内不同的关注点和信任域保证了需要一种更有能力的方法来管理入口，这种方法由 Istio Gateways 和 VirtualServices 提供。

一旦流量进入网格，最好能够为虚拟服务提供一个关注点分离，这样不同的团队就可以为他们的服务管理流量路由。L4-L6 规范通常是 SecOps 或 NetOps 可能关心的东西。L7 规范是集群操作员或应用程序所有者最关心的问题。因此，正确分离关注点至关重要。由于我们相信团队责任的力量，我们认为这是一项重要的能力。由于我们相信 Istio 的力量，我们在 Istio 社区提交了一个 [RFE](https://docs.google.com/document/d/17K0Tbp2Hv1RAkpFxVTIYPLQRuceyUnABtt0amd9ZVow/edit#heading=h.m6yvqjh71gxi) ，我们希望这将有助于在网格内实现流量管理的所有权语义。

我们很高兴 [Istio 已经达到 1.0](https://thenewstack.io/istio-1-0-come-for-traffic-routing-stay-for-distributed-tracing/) ，并且很高兴能够随着它的继续发展继续为项目和社区做出贡献。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>