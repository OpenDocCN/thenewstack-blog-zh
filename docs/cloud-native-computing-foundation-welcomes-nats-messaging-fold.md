# 云本地计算基金会欢迎 NATS 消息协议加入

> 原文：<https://thenewstack.io/cloud-native-computing-foundation-welcomes-nats-messaging-fold/>

继续充实其云友好基础设施软件组合，[云本地计算基金会](https://www.cncf.io/) (CNCF)已经接受了 [NATS](https://nats.io) 消息软件作为孵化级托管项目。

“从第一天起，NATS 就证明了自己是构建分布式系统的工具，”CNCF 技术监督委员会成员和该项目的发起人[亚历克西斯·理查森](https://www.linkedin.com/in/richardsonalexis/)说。

Richardson 的公司 [Weaveworks](https://www.weave.works/) ，使用 NATS 作为自己的容器管理平台的一部分，以及 CNCF 的 Kubernetes 容器编排管理器。“就像我们可以在任何地方运行 Kubernetes 并拥有云原生模式一样，我们也可以在任何地方运行 NATS 并拥有云原生模式，”Richardson 说。

“本质上，NATS 非常容易使用和适应，这就是为什么我认为它非常适合 CNCF，”NATS 创作者德里克[科利森](https://github.com/derekcollison)说。科利森现在是 Synadia Communications 的首席执行官，该公司维护开源 NATS 服务器和客户端软件以及相关库的代码库。

七年前，消息传递技术资深人士科利森在 VMware 创建 NATS 时，他是云计算平台即服务软件的控制平台。科利森说，在企业服务总线(ESB)等繁重的消息传递技术十年之后，NATS 被设计成“回归简单”。

“这对开发者来说很容易学会，”理查森同意道。“协议相当简单。它非常容易理解和调试。”

NATS 的另一个关键设计决策是让技术保持每个终端节点的连接性，即使一些终端节点离线。对于基于云的系统，“云消息需要支持很多模式，”理查森说。这些模式中有许多是“在空间和时间上分离的”，这意味着需要相互通信的所有节点并不总是同时在线。

NATS 通过基于日志的流来解决这一问题，它提供了一种简单的方法来存储和重放消息，以便在丢失的端点恢复在线时可以接收这些消息。NATS 为分布式系统实现了流行的消息队列模式，如发布/订阅和请求/回复。

 [NATS 里程碑

*   44 名贡献者
*   3820 颗 GitHub 星星
*   20 个版本
*   1356 次提交
*   415 叉](https://nats.io/) 

作为一项成熟的技术，NATS 已经部署在许多云原生和物联网系统中，包括由 Apcera、Apporeto、百度、Capital One、Cloud Foundry、Comcast、爱立信、通用电气(GE)、Netlify、Pivotal、三星和 VMware 运行的系统。

NATS 加入了 CNCF 管理的其他 16 项云原生技术:Kubernetes、Prometheus、OpenTracing、Fluentd、Linkerd、gRPC、CoreDNS、containerd、rkt、CNI、Envoy、Jaeger、公证人、TUF、Rook 和 Vitess。NATS 也在这些项目中大量使用，特别是 Kubernetes、Prometheus、gRPC、Fluentd、Linkerd 和 containerd。

[https://www.youtube.com/embed/t_USxxOGzcw?feature=oembed](https://www.youtube.com/embed/t_USxxOGzcw?feature=oembed)

视频

[云本地计算基金会](https://www.cncf.io/)是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>