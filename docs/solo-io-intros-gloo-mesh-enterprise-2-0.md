# Solo.io 介绍 Gloo Mesh Enterprise 2.0

> 原文：<https://thenewstack.io/solo-io-intros-gloo-mesh-enterprise-2-0/>

Solo.io 本周推出了 Gloo Mesh Enterprise 2.0，这是其 [Istio](https://thenewstack.io/solo-io-istio-is-winning-the-service-mesh-war/) 服务网格和控制平面的最新版本，简化了分布式应用程序中的服务到服务连接。

新版本中的主要增强功能包括多租户工作区、用于东西和南北流量管理的新统一 API、用于可观察性的新 UI 以及改进的虚拟机支持。

此外，应用网络公司宣布了 Gloo Edge 的 [GraphQL 的测试版，该测试版将](https://www.solo.io/blog/announcing-graphql-for-gloo-edge-in-beta-now/) [GraphQL 服务器原生嵌入 Gloo Edge](https://thenewstack.io/solo-io-adds-graphql-to-gloo-mesh-and-gloo-edge/) — Solo.io 的 API 网关和入口控制器，支持 API 的联邦 GraphQL 查询。

本周，Solo.io 在第二届 SoloCon 数字用户年会上宣布了这些消息。

Solo.io 的创始人兼首席执行官 [Idit Levine](https://www.linkedin.com/in/iditlevine/) 在一份声明中说:“这些增强是我们的 API 的自然演变，继续简化在单集群和多集群环境中对 Istio 的采用、使用和管理。”他指出，Solo.io 的客户正在一些可以想象的最大、最复杂和最多样化的实施环境中使用 Istio，许多环境运行在多个平台上，每天有数千个 API 和数亿个请求。

## 客户驱动的功能

Levine 补充说，Gloo Mesh Enterprise 2.0 中的新功能主要是由客户驱动的，基于 Solo.io 通过 Slack 保持联系的数百名客户的反馈。

“我们所有的客户基本上都在 Slack 上，他们每个人都有自己的渠道，我们与他们有着非常好的关系，对他们非常敏感，”Levine 告诉 New Stack。“不过，他们有几百个。这是和正规公司不一样的模式。这是一个非常非常疯狂的规模。”

Invitae 的云网络主管汤姆·霍华德在一份声明中说:“我们面临的一个关键挑战是，我们在评估服务网络提供商时，依赖于从未实现的支持。“我们通过 Solo.io 和 Gloo Mesh 找到了我们想要的东西。对支持的响应，对与顾客和客户建立合作伙伴关系的关注，我们认为这是一种互动的合作关系，可以推动平台的发展。”

去年推出的 Gloo Mesh Enterprise 是一个基于 Istio 的 Kubernetes-native 解决方案，用于多集群和多网格服务管理。

2.0 中的新功能(如多租户工作区)使用户能够基于共享基础架构的角色设置细粒度的访问控制和编辑权限，从而使团队能够在大型环境中进行协作。用户可以直接在 UI 中管理流量、建立工作区依赖关系、定义集群名称空间和控制目的地。并且可以使用标签重复使用和修改策略。

Gloo Mesh Enterprise 2.0 还具有一个新的 Gloo Mesh API，用于 Istio 管理，使开发人员能够从一个统一的 API 为南北流量和东西流量配置规则和策略。新的 API 还简化了从单个集群扩展到数十或数百个集群的过程。用于观察的新 Gloo Mesh UI 提供服务拓扑图，突出显示网络流量、延迟和速度，同时在移动集群或节点时自动保存新状态。

此外，该公司表示，新改进的虚拟机支持减少了向 Istio 服务网格环境添加虚拟机所需的时间和代码量。

[Waylay](https://www.waylay.io/) 的平台工程师 [Gert-Jan Groeninckx](https://www.linkedin.com/in/gert-jan-groeninckx-440272149/?originalSubdomain=be) 在一份声明中表示:“作为 Gloo 企业产品的用户，我们期待将 Istio 服务网格的复杂性抽象到一个控制平面中，并与我们当前的 Gloo Edge 网关相结合。“将 Gloo Mesh 添加到企业产品中，将使 Istio 的采用及其在多集群路由、可观察性和管理整个系统方面的优势变得非常有趣。”

## Gloo 边缘的 GraphQL

与此同时，Solo.io 还宣布了 Gloo Edge 的 GraphQL 测试版。Solo.io 已经将 GraphQL 服务器原生嵌入到 Gloo Edge 中，这允许使用客户的服务网格和 API 网关对客户的 API 进行联合 GraphQL 查询，而不需要额外的 GraphQL 基础设施。GraphQL，一种用于 API 的开源数据查询语言，用于简化客户端-服务器交互。

“基本上，我们教 Envoy 成为一个 GraphQL 服务器，”Levine 说。

[Ory](https://www.ory.sh/) 的联合创始人 [Thomas Curran](https://www.linkedin.com/in/thomasaidancurran/) 在一份声明中说:“Ory 是一家开源公司，正在建立一个专注于客户零信任的全球网络基础设施。“由于我们的整个许可基础设施，我们对 GraphQL 非常感兴趣，我们很兴奋。io 正在将 GraphQL 添加到 Gloo，以支持开发人员的 API 作为 GraphQL 查询。"

GraphQL 提供声明性数据提取，客户端通过单个端点指定它需要从 API 和底层服务获取什么数据。

GraphQL for Gloo Edge 提供:

*   GraphQL 服务器、解析器、GraphQL 模式生成器和 GraphQL 的模式拼接都是由声明性配置驱动的。
*   将 GraphQL 模式存储为代码、观察使用情况、发布信息以及管理模式和服务器更改的能力，从而节省时间和精力。
*   集成的监控功能，提供对 GraphQL 请求、查询执行和上游解析器的关键指标的访问，以监控性能和调试问题。用户可以用普罗米修斯和 [Grafana](https://thenewstack.io/will-grafana-become-easier-to-use-in-2022/) 导出指标。

“Solo.io 对 Gloo Edge 的 GraphQL 支持用简单的配置取代了繁琐的解析器代码，”[惠誉集团](https://www.fitch.group/)架构高级总监[马特·琼斯](https://www.linkedin.com/in/mattjonestechnology/)说。

## 新 eBPF 加速

与此同时，Solo.io 最近推出了 [BumbleBee](https://thenewstack.io/solo-io-brings-docker-like-experience-to-ebpf-with-bumblebee/) ，这是一个新的 eBPF(extended Berkeley Packet Filter)开源项目，它简化了 eBPF 工具的开发、打包和共享。该公司现在将 eBPF 并入 Gloo Mesh Enterprise，以补充 Istio 并进一步提高性能。

“我们正在利用 eBPF 来获得服务网格更好的延迟和吞吐量，”Levine 说。"基本上我们正在做的是使用 eBPF 来简化 HTTP 堆栈."

该公司表示，eBPF 工具包括容器网络接口(CNI)扩展和用 eBPF 编写的网络策略扩展 CNI 的能力，而不需要用户替换现有的 CNI。

## 新员工

在 SoloCon 活动的其他相关新闻中，Solo.io 宣布聘请[Brian gracey](https://www.linkedin.com/in/briangracely/)担任其新的产品战略副总裁。Gracely 从 Red Hat 来到 Solo.io，他在那里担任产品战略高级总监，负责监管该公司的开放混合云产品，包括 OpenShift。该公司表示，他在开源软件、容器、Kubernetes、云计算、数据中心虚拟化、无服务器等领域拥有 20 多年的行业经验。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>