# SoloCon 2021:用于多个 Kubernetes 集群和微服务的一个 API

> 原文：<https://thenewstack.io/solocon-2021-one-api-for-multiple-kubernetes-clusters-and-microservices/>

当将运营转移到微服务架构时，DevOps 团队通常必须在数百种工具和平台中进行选择。考虑到这些挑战，领先的服务网格提供商 solo.io 提供了与[特使](https://envoyproxy.io/)、 [Istio](https://istio.io/) 和其他主要 Kubernetes 管理构建模块集成的工具，以消除将它们整合在一起的过程中涉及的许多巨大复杂性。

Solo.io 最近推出了 [Gloo Cloud](https://thenewstack.io/solo-io-offers-an-enterprise-ready-istio-service-mesh-as-a-cloud-service/) ，面向服务网格的软件即服务。这家初创公司现在还提供了所谓的“单一玻璃视图”，用于通过 Gloo Mesh 进行多集群观察，并通过 Gloo Edge 2.0 API 网关完全集成 Istio 管理。此外，solo.io 宣布完全支持 gRPC 规范，使其 Gloo 门户成为开源通用 RPC 框架唯一可用的用户界面。

Solo.io 及其发布旨在帮助组织向单一 API 模型靠拢，以管理云原生部署的整个范围，这也是本月早些时候举行的 solo.io 虚拟会议 [SoloCon 2021](https://solocon.io/) 的主题。

组织在部署多个 Kubernetes 集群和微服务时面临的主要困境是“如何通过单个 API 管理它们”，创始人兼首席执行官[solo . io](https://www.solo.io/)Idit Levine[告诉新堆栈。他们还需要跨所有微服务、安全流程和控制的可观察性，以及对其整个微服务范围的完全可访问性，同样是通过单个 API。部署、可观察性和安全性，“是我们关注的三件事，”莱文说。](https://www.linkedin.com/in/iditlevine)

solo.io 的全球现场首席技术官 Christian Posta 告诉新堆栈，最终，这些公告以及 solo.io 正在进行的工具和平台开发是 solo . io 努力支持寻求依赖微服务风格架构来更快地交付通常处于现代化计划中的应用程序的组织的一部分。

“所以我们说:‘你正在部署应用程序，它们需要相互通信，而且还有更多的应用程序，’波斯塔说。这是一个难题。有助于最大限度降低运行微服务的运营负担的解决方案是什么？我们的产品重点在那个领域。"

## 服务网格即服务

Levine 说，Gloo Edge 2.0 代表了第一个“原生 Istio”API 网关，而 Gloo Cloud 是 Istio 作为“服务网格即服务”的“第一个也是唯一的”版本。Levine 说，Gloo Cloud 还在一个产品中同时提供 Gloo Edge 和 Gloo Mesh。

Gloo Cloud 是 SoloCon 2021 上的主要公告，“代表了 solo.io 的势头和全面进步，”[solo . io 的首席营销官埃里克·弗里伯格](https://www.linkedin.com/in/efrieberg)告诉新堆栈。“最大的进步是 Gloo Cloud:我们真的看到了市场的发展，人们喜欢[Gloo]的功能，但他们也希望它作为服务在托管环境中交付，”Frieberg 说。

令人鼓舞的是，“看到有人在恢复 Kubernetes 作为一个平台的精神方面向前迈进了一步”，同时提供“跨数据中心、私有和公共云环境的最终一致性水平”， [Torsten Volk](https://www.linkedin.com/in/torstenvolk) ，企业管理协会(EMA)的分析师说。“这可能会给更多的组织带来‘一次编码，随处部署’，这些组织不具备实现这一目标所需的昂贵的员工技能，”Volk 说。

除了 Gloo Cloud 和 Gloo Edge 2.0，solo.io 还发布了 Gloo Mesh 的多集群可观测性功能，该公司表示完全支持其门户产品的 gRPC 规范。

“我们采用了服务网格提供的所有工具，将所有数据聚集在一个地方，”莱文说。“我们说‘插入你最喜欢的观察工具，你在屏幕上一分钟内看到的是一种非常漂亮的方式，可以看到微服务之间的流量中发生的一切，即使是跨集群和多集群，’”Levine 说。

对于 gRPC 对 Gloo Portal 的支持，“我们的许多客户都要求这种支持，而不是其他规格，”Frieberg 说。“我们也是市场上唯一支持… gRPC 的开发者门户。”

Gloo Edge 是一个 Istio 集成的 API 网关，用于服务网格级别的多 Kubernetes 集群，现在可以直接通过 Istio 控制平面获得，作为 Gloo Edge 2.0 版本的一部分。这意味着组织不再需要担心自己添加和配置 Istio，因为 Gloo Edge 现在可以自动完成这一过程。

“虽然一些公司只是在产品上提供服务，但我们将[Istio]作为基础产品，并添加了许多增强功能。我们不分叉，所以我们没有创造一个死胡同，”弗里伯格说。“我们也在增加它，使它更容易运行——很多人想构建扩展……所以现在你可以用 web assembly 来扩展它。你可以把自己的业务规则放进去，突然间，它就变得适应性很强了。”

## 客户联系人

莱文说，今年的 SoloCon 除了作为 solo.io 技术发布的场所，还包括客户的演讲，介绍他们如何实施 Gloo Mesh 和 Gloo Edge 以及其他 solo.io 工具和平台。“我们的客户说，他们希望了解其他客户的想法，了解他们是如何实施[Gloo]产品的，”莱文说。他们说这非常重要。"

[Gert-Jan Groeninckx](https://be.linkedin.com/in/gert-jan-groeninckx-440272149) ，一位为 [Waylay](https://www.waylay.io/) 工作的平台工程师，在他的 SoloCon 2021 演讲[“按需物联网平台:使用 Gloo Edge 的多租户和动态路由”](https://sched.co/iETT)中描述了 Waylay 为其物联网自动化和数据分析平台采用 Gloo Edge 的途径，以及它如何将 Gloo Edge 集成到其运营中。

Waylay 采用 Gloo 进行身份验证、速率限制、度量和基于声明的路由，并有许多具体要求。Groeninckx 表示，这些需求包括需要一个统一的网关，并了解分布在云原生环境中的所有微服务之间“后台发生了什么”，以及单租户和多租户部署的流量管理功能。他说，找到一个“直观的配置”也是一个问题，因为没有人“喜欢一个混乱且不容易阅读的配置”。Groeninckx 表示，“Gloo 最终胜出”,“满足了 Waylay 的所有要求”。

在引擎盖下，Groeninckx 的团队也欣赏 Gloo Edge 如何基于特使。事实上，在 Kubernetes 领域中，Envoy 被“大量维护”并广泛用于多个集群的管理，这是关键的考虑因素。

在大约两个月前采用 Gloo 后，同样是 Waylay 平台工程师的奥利弗·卡马特(Oliver Cammaert)表示，他的组织能够“非常快速地启动和运行 Gloo Edge。”“它达到了我们的所有要求，当我们需要一些支持时，还得到了 Gloo 团队的一点帮助，”Cammaert 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>