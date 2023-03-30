# 轮廓入口控制器加入 CNCF 在孵化水平

> 原文：<https://thenewstack.io/contour-ingress-controller-join-cncf-at-incubation-level/>

开源的 [Contour](https://projectcontour.io/) ，Kubernetes 的高性能入口控制器，为[特使](https://www.envoyproxy.io/)代理提供控制平面，作为孵化级项目加入了云计算原生计算基金会(CNCF)，跳过了传统的沙盒级入口点。该项目最初于 2017 年在 Heptio [开发，后来被 VMware](https://thenewstack.io/with-heptio-and-pivotal-vmware-doubles-down-on-kubernetes/) 收购，VMware 产品管理总监 [Michael Michael](https://www.linkedin.com/in/mimichael/) 表示，该项目展示了该领域的使用水平、社区的支持以及生态系统中的活动，足以跳过沙箱。

Michael 指出，Contour 还有一个额外的好处，就是与 CNCF 大学毕业的其他项目——Kuberenetes 和 Envoy——紧密集成，而且该项目是面向未来的。

“我们的目标是成为 CNCF 的一部分，我们希望成为 Kubernetes 最好的入口控制器，”Michael 说。“我们希望与 CNCF 的一些其他项目进行对接，如 Envoy 和 Kubernetes，以构建一个入口控制器来满足客户的需求，这些客户的愿景是未来服务 API 和社区中正在发生的工作，以彻底改变网络连接到您在云原生环境中运行的不同应用的方式。”

Contour 通过执行两个不同的任务来帮助将外部流量路由到 pod。首先，Contour 会监听 Kubernetes API 以了解 pod 规范的变化，从而在发生扩展时确定流量路由，然后它还会关注有关 pod 规范的 YAML 规范。然后，Contour 获取这些信息并配置 Envoy，以确定流量将采用的路由，在这种情况下，Envoy 充当 L7 到 L4 代理。

[https://www.youtube.com/embed/xUJbTnN3Dmw?feature=oembed](https://www.youtube.com/embed/xUJbTnN3Dmw?feature=oembed)

视频

除此之外，该项目还拥有一组基本的功能，包括作为 Kubernetes 部署或 daemonset 进行部署的能力，支持多团队 Kubernetes 集群中的入口，以及支持 TLS 证书委托。

Contour 1.0 于去年 11 月在 KubeCon San Diego 期间发布，Michael 称该发布是“向社区发出的信号，表明我们已经准备好迎接黄金时代了。”

“从那以后，我们就一直在踢屁股。在过去的六七个月里，我们几乎每个月都会发布一次。我们看到这个巨大的社区在贡献、我们的路线图、我们的功能方面都在增长，所以我们很喜欢它的每一步。过去几个月的 Contour 令人惊叹——自从我们发布 1.0 版本以来，你可以看到参与度和使用量都有了巨大的增长，”Michael 说。

展望 Contour 的下一步，该项目计划为跨 Kubernetes 集群的路由服务添加对 [Kubernetes 服务 API](https://github.com/kubernetes-sigs/service-apis)的支持。Michael 解释说，目前，Kubernetes ingress 有一些缺点，例如缺乏对多租户环境、TCP 和 UDP 以及负载平衡的支持。他说，服务 API 将有助于确定一个每个人都可以用于 Kubernetes 应用程序入口的规范。

"迈克尔说，可以把服务 API 看作是下一代的 Kubernetes 入口. "服务 API 是社区中正在进行的工作，许多网络人员——包括 Contour 团队——试图构建下一代 ingress。它将彻底改变 Kubernetes 集群中的入侵方式，就像 CSI 彻底改变存储一样。"

云计算原生计算基金会和 VMware 是新体系的赞助商。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论故事的读者通过[推特](https://twitter.com/thenewstack)或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>