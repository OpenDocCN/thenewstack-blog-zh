# CNCF 采用大使 API 网关，使者入口

> 原文：<https://thenewstack.io/cncf-adopts-ambassadors-api-gateway-emissary-ingress/>

用于 Kubernetes 的[使者入口](https://github.com/emissary-ingress/community)开源入口控制器和 API 网关本周加入了[云本地计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)的孵化阶段。

如果你想知道为什么这个你可能还没有听说过的第 7 层负载平衡器跳过了 CNCF 的沙盒级别，这可能是因为使者入口实际上是另一个有新名字的流行项目。使者入口原名为[大使](https://github.com/datawire/ambassador)，由 Datawire 创建，是[大使边缘栈](https://www.getambassador.io/)背后的开源核心，并有了新的身份，[大使实验室](https://blog.getambassador.io/)创始人兼首席执行官 [Richard Li](https://www.linkedin.com/in/richardli/) 解释道。

凭借其对 CNCF 的贡献，该项目移交了包括商标在内的知识产权。但是“我们不能把我们公司名称的所有权利都给 CNCF，”李说，“所以我们一致认为最简单的办法就是重新命名，而‘使者’是另一种‘大使’"

根据一份新闻声明，messenger Ingress 正在被 Ticketmaster、 [Chick-Fil-A](https://www.chick-fil-a.com/) 和 [AppDirect](https://www.appdirect.com/products/overview) 等公司使用，用例报告“每秒钟高达 50 万次请求，在不到 10 分钟内用户数从 500 万跃升至 1500 万。”自 2014 年以来，使者入口实际上已经以某种形式存在。李解释说，这发生在特使创建者 Matt Klein 在早期的微服务实践者峰会上谈到构建特使代理后不久，特使代理也是 CNCF 的一个项目。

“我们在他演讲后的三四个月推出了基于特使的大使，因为我们看到了特使是云原生生态系统代理的未来，”李说，“我们也看到了 Kubernetes 是未来，我们知道，从逻辑上讲，人们需要在 Kubernetes 上部署特使。”

使者入口现在是继 [VMWare](https://tanzu.vmware.com?utm_content=inline-mention) 的 [Contour](https://projectcontour.io/) 之后加入 CNCF 的第二个入口控制器，尽管李说使者入口在 API 网关领域比 Contour 具有更多功能，Contour 刚刚开始采用这些功能。李说，作为一个入口控制器，使者入口具有“非常技术性的结构”，实现了由 Kubernetes 网络工作组定义的[入口规范](https://kubernetes.io/docs/concepts/services-networking/ingress/)，而 API 网关更多的是该功能的超集，接受相同的南北流量，并执行诸如认证和速率限制等功能，以及其他潜在功能。

事实上，除了 ingress 的基本功能，使者-ingress 还提供了[数量的功能](https://github.com/datawire/ambassador)，例如与 Grafana、Prometheus 和 Datadog 的集成，与[开发人员门户](https://www.getambassador.io/docs/latest/topics/using/dev-portal/)的开发人员入职， [Knative 无服务器集成](https://www.getambassador.io/docs/latest/howtos/knative/)，与[consult](https://www.getambassador.io/docs/latest/howtos/consul/)、 [Linkerd](https://www.getambassador.io/docs/latest/howtos/linkerd2/) 和 [Istio](https://www.getambassador.io/docs/latest/howtos/istio/) 的服务网格连接，以及与 [canary releases](https://www.getambassador.io/docs/latest/topics/using/canary/) 的渐进式交付。使者入口也依赖于 Kubernetes 的持久性，这消除了对单独数据库的需要，并允许 Kubernetes 在出现问题时重新启动使者入口。

李解释说，加入有几个原因，包括收养、社区建设和基金会提供的中立治理。

“在 Kubernetes 的入口控制器和 API 网关领域，我们看到的世界是，你想建立在特使代理上，你可能想选择一个基于的项目，因为中立的治理和知道进入需要一定的牵引力，”李说。“我们希望扩大从事这项工作的人员队伍。这可能是最大的事情，只是增加用户以及贡献者和维护者的社区。我们与其他组织合作，为 Ambassador 贡献功能，取得了很多成功，他们非常出色，我们认为，只要成为 CNCF 的一部分，其他组织就会意识到这不仅仅是一个大使实验室项目。”

使者入口路线图包括添加对 Web 组装(WASM)和缓存 API 的支持，但李似乎最感兴趣的是他们与 [Argo](https://argoproj.github.io/argo-cd/) 在金丝雀版本上的[合作](https://www.getambassador.io/docs/argo/)，渐进式交付，以及将对使者入口的原生支持合并到 Argo 推出中。

除此之外，李还表示，他们正在努力支持网关 API T5，这是 Ingress 规范的后继者，他认为社区对此很感兴趣。Gateway API 是“在 Kubernetes 中建模服务网络的资源集合”，它“旨在通过由许多供应商实现的、具有表现力的、可扩展的、面向角色的接口来发展 Kubernetes 服务网络，并得到广泛的行业支持。”

“网关 API 中有许多东西使其比当前的入口规范更加灵活，”李说。“我们也很高兴能在这方面开展工作。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>