# CNCF 加入甲骨文，登上特使和耶格项目

> 原文：<https://thenewstack.io/cncf-adds-oracle-onboards-envoy-jaeger-projects/>

云原生计算基金会(Cloud Native Computing Foundation)继续壮大，与最古老的企业软件公司甲骨文(Oracle)签约成为赞助商，并在其投资组合中增加了两个云原生项目，即 Envoy service mesh 和 Jaeger microservice debugging 软件。

CNCF 在本周于洛杉机举行的北美[开源峰会上宣布了新的内容。](http://events.linuxfoundation.org/events/open-source-summit-north-america)

“过去十年是关于虚拟化，而这十年是关于容器化和云原生的。你可以将应用容器化，这样你就可以将应用分成许多部分——微服务——然后你就可以协调所有这些部分，”CNCF 执行董事[丹·科恩](https://www.dankohn.com/)说。“我们认为这确实是计算领域的最大趋势。”

CNCF 已经签约成为五大云供应商的赞助商，分别是 AWS、微软、谷歌、IBM 和阿里巴巴。

通过加入 CNCF，甲骨文对其庞大的用户群采用云原生架构表现出了兴趣。甲骨文发现其客户已经在使用许多 CNCF 技术，包括 Kubernetes、Prometheus、gRPC 和 OpenTracing。

Oracle 还为其 Oracle 云基础设施服务发布了基于 Terraform 的 Kubernetes 安装程序，以及用于 Kubernetes 的 Oracle Linux 容器服务，这是一个旨在简化 CNCF 开源容器编排引擎的配置和设置的包。

## 新项目

[](https://lyft.github.io/envoy/)

 [特使乘号

*   75 投稿人
*   2123 Github 群星
*   242 叉
*   5 发布
*   1085 提交](https://lyft.github.io/envoy/) [](https://lyft.github.io/envoy/)

特使号和耶格号分别是第 11 和第 12 个项目，[被 CNCF](https://www.cncf.io/projects/) 接受。

出于性能原因，用 C++编写的 Envoy 是一个 API 驱动的[服务网格](/tag/service-mesh/)，一个供多个服务相互查找和通信的平台。软件[最初是在 Lyft](https://thenewstack.io/lyfts-envoy-provides-move-monolith-soa/) 上构建的，并于 9 月作为开源发布。谷歌和 IBM 都对该项目做出了巨大贡献(事实上，谷歌在 Envoy 上的编码人员比 Lyft 本身还多)。

Kubernetes 提供开箱即用的作业编排，而 Envoy 提供和管理跨不同服务的外部连接。Kohn 解释说:“服务网格就是在集群环境的基础上为您提供一整套额外的功能。

[](https://github.com/uber/jaeger)

 [耶格被编号

*   15 投稿人
*   1215 Github 群星
*   126 叉子
*   5 发布
*   263 提交](https://github.com/uber/jaeger) [](https://github.com/uber/jaeger)

CNCF 也接受了优步开发的分布式追踪软件。这个软件受到了谷歌 Dapper 论文的启发，并基于 Zipken 项目，使用 OpenTracing 标准。目前，优步使用 Jaeger 来管理 1200 个单独的微服务，每个微服务在任何给定时间都可能有多个实例在运行。

作为一个微服务调试器，Jaeger 可以用来跟踪不同服务的问题，方便进行根本原因分析、服务依赖性分析和性能优化。

Kohn 指出，具有讽刺意味的是，这两个项目都源于车辆共享服务(这两个应用程序都必须处理某种流量，尽管是网络流量)。然而，与此同时，“它们的共同点是，在过去几年里，这两家公司都必须非常迅速地建立大规模的网络基础设施。”

其他 CNCF 项目包括 Kubernetes、Prometheus、OpenTracing、Fluentd、linkerd、gRPC、CoreDNS、containerd、rkt 和容器网络倡议。

TNS 分析师劳伦斯·赫特对本文有贡献。

[](http://events.linuxfoundation.org/events/open-source-summit-north-america/program/schedule)

[云计算原生计算基金会](https://www.cncf.io/)是新堆栈的赞助商。

专题图片:洛杉矶壁画[克里斯·勒克斯](http://www.chrislux.com/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>