# GRPC 实现了无代理服务网格的承诺

> 原文：<https://thenewstack.io/grpc-delivers-on-the-promise-of-a-proxyless-service-mesh/>

本月早些时候，谷歌 gRPC 产品经理 Megan Yahya 在 [KubeCon+CloudNativeCon EU](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 的演讲中指出，有了最新版本的 gRPC 协议，基于微服务的系统将不再需要单独的独立服务 mesh sidecars。

相反，对于那些已经使用 gRPC 的人来说，他们可以将服务直接扩展到控制平面，并让它接管以前通过代理服务完成的工作，例如今天使用的最流行的 sidecar 代理之一[云本地计算基金会的](https://cncf.io/?utm_content=inline-mention) s [Envoy](https://www.envoyproxy.io/) 。

由谷歌创建并于 2016 年发布的 [gRPC](https://grpc.io/docs/what-is-grpc/introduction/) 是一个基于 http/2 的超低延迟远程调用过程(RPC)，它允许服务或应用程序通过网络调用资源，就像它是一个本地实体一样。这对于通过相互传递消息(数据中心术语中的“东西向流量”)而产生大量网络聊天的微服务来说非常有用。通过支持十几种编程语言，gRPC 允许用不同语言编写的服务相互通信，而不需要一次性的粘合代码。

在典型的服务网格部署中，每个应用程序都有一个 sidecar 代理，它会拦截所有流向应用程序的流量，并使用从控制平面获得的策略对其进行过滤。然而，这种独立的边车方法有其局限性:额外的开销将来自任何附加软件，如代理服务器，以及额外的维护和保养。另一个问题是:没有端到端的安全性，因为在大多数情况下，流量在边车被终止，并以明文形式转发回应用程序本身。

Yahya 指出，gRPC 的最新版本具有直接从控制平面处理请求的能力，消除了对 sidecar 代理的需要。它可以支持一系列服务网格任务，包括负载平衡和服务发现。这要归功于它使用了由 Envoy 团队首先开发的 [XDS 数据平面 API](https://blog.envoyproxy.io/the-universal-data-plane-api-d15cec7a)。

XDS 支持允许应用程序本身直接与控制平面对话，而不是使用 sidecar 作为中间人。应用程序开发人员只需添加一个带有“xds”解析器方案的 gRPC 通道，而不用安装 Envoy。还需要一个引导文件来将应用指向控制平面。伊兹·佩兹。

在她的演讲中，Yahya 承认 gRPC 在覆盖 Envoy 目前提供的所有特性方面还有很长的路要走。围绕 Envoy 的工具，尤其是围绕第三方过滤器的工具，更加成熟。

支持该功能的第一个 gRPC 版本是 2020 年 6 月的 1.30.0 版。当前版本 1.35.00 支持服务发现、负载均衡、流量分流和路由匹配。未来的功能将包括超时、断路、对控制平面的 TLS 和 MLS 支持，以及可观察性功能。

开箱即用，它可以与谷歌云的[流量管理器](https://cloud.google.com/traffic-director)服务网格很好地工作，并对谷歌自己的开源控制平面软件 [Istio](https://istio.io/) 提供实验性(无文档)支持。

点击查看整个介绍[:](https://youtu.be/cGJXkZ7jiDk)

[https://www.youtube.com/embed/cGJXkZ7jiDk?feature=oembed](https://www.youtube.com/embed/cGJXkZ7jiDk?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>