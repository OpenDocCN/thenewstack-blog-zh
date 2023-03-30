# 微软首次将开放服务网格引入一个拥挤的、有争议的生态系统

> 原文：<https://thenewstack.io/microsoft-debuts-open-service-mesh-into-a-crowded-contentious-ecosystem/>

虽然 Istio 一直是头条新闻，但微软已经将其新的[开放服务网格项目](https://techcrunch.com/2020/08/05/microsoft-launches-open-service-mesh/)发布到日益拥挤的[和](https://layer5.io/landscape)[经常令人困惑的生态系统](https://servicemesh.io/)。

已经有 Linkerd(创造了这个术语的项目)，加上(排名不分先后)库马、Maesh、Mesher、SOFAMesh、Cilium、Consul Connect、AWS App Mesh、Citrix Service Mesh、F5 的 Aspen Mesh 和 VMware 的 Tanzu(三个带有企业管理的商业 Istio 发行版)，以及支持服务网格功能的 NGINX 等负载平衡器。甚至有像网络服务网格这样的项目使用这个术语，尽管它不是服务网格。Meshery、Service Mesh Hub 和 Weave Flagger 等工具允许您在多个服务网格上进行管理或部署，以防您采用的一个项目与您选择用于其他应用程序的服务网格具有不同的亲缘关系。那么，为什么还要建立另一个服务网呢？

微软已经与 Linkerd、Hashicorp、Red Hat、Rancher、Docker、Aspen Mesh、VMware 和其他公司在云本地计算基金会托管的[服务网格接口(SMI)规范](https://github.com/servicemeshinterface)中就公共服务网格功能的 API 进行了合作，类似于 Linkerd，但不同于 Istio，开放服务网格可以由该 SMI 进行配置，甚至可以作为参考实现。

GitHub 上的开放服务网格活动于 2019 年底开始。这意味着它已经进行了太长时间，不能立即对谷歌的决定作出反应，谷歌决定建立一个新的组织来保护 Istio 商标，而不是像 IBM 坚持的那样将项目捐赠给 CNCF。

相反，这似乎更有可能是对微软客户(和其他人)的回应，他们希望在 Envoy 上实现标准化——这是一个代理，而不是服务网格，因此 OSM 使用 Envoy 时遵循了一种常见的模式，即在应用程序的每个实例旁边注入一个 Envoy 代理作为辅助容器，以处理访问控制规则、路由和收集可观察性指标。

使用 SMI 规范有望更容易地迁移到另一个配置了 SMI 的服务网格(这在微软内部可能很有用，因为那里使用了几个不同的服务网格项目)。然而，OSM 配置分为使用 SMI 进行更简单的选项和使用 OSM 内部的 Envoy xDS APIs 进行更高级的集成，如果您选择像 Linkerd 这样不使用 Envoy 的服务网格，后者可能更难移动。

微软承诺将 OSM 带到 CNCF，[在宣布后不久提交了一份提案](https://github.com/cncf/toc/pull/507)将其添加为沙盒 CNCF 项目；下一轮沙盒项目的投票将于 9 月举行。

该项目在更广泛的 Kubernetes 社区中引起了一些兴趣:Knative 的联合创始人马特·摩尔谈到了[构建 Knative 集成](https://twitter.com/mattomata/status/1291078362471915520)和街机 Kubernetes CLI [很快增加了 OSM 支持](https://github.com/alexellis/arkade/releases/tag/0.6.0)。关于增加 SMI 流量指标的讨论[已经在 Kiali 项目中展开](https://twitter.com/michellenoorali/status/1291103647259144196)(一个使用 Istio 实现可观测性和配置的管理控制台),这样 Kiali 就可以为 OSM 提供可观测性。

Kubernetes 的联合创始人 Joe Beda [提出了“服务网格(以及类似服务网格的东西)如何能够安全和高保真地相互对话”的问题](https://twitter.com/jbeda/status/1291144994850447360)，因为 OSM 和 Dapr 运行时都使用 Envoy sidecars 和 mTLS(尽管在不同的层)来组装平台无关的应用程序。

正如特使创建者马特·克莱恩之前告诉新堆栈的那样，“特使正在成为一个构建模块；人们正在构建不同的东西，我们很高兴有特使成为无处不在的构建模块。我们的目标不是成为一个控制平面或人们做事的一种方式；我们希望成为人们可以用来构建系统的工具包。”

但是，当 Linkerd 产品负责人 Oliver Gould [指出](https://twitter.com/olix0r/status/1291408257982947328)OSM 回购包括“健康检查”代码似乎是从 Linkerd 复制而来时，也引起了一些争议。微软对缺乏归属表示道歉，完全删除了代码，并承诺改善[项目的审查过程。](https://github.com/openservicemesh/osm/issues/1432)

剩下的问题是开放服务网格如何在拥挤且仍在发展的服务网格空间中脱颖而出。

云计算原生计算基金会、HashiCorp、Aspen Mesh、Red Hat 和 VMware 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>