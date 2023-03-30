# 轮廓简介:将流量路由到 Kubernetes 中的应用程序

> 原文：<https://thenewstack.io/introducing-contour-routing-traffic-to-applications-in-kubernetes/>

[](https://www.linkedin.com/in/mimichael/)

 [迈克尔迈克尔

迈克尔迈克尔是 VMware 的产品管理总监，也是 Contour 的维护者，负责整个项目的战略和功能，并负责为 Contour 的发展创造一个健康的生态系统。](https://www.linkedin.com/in/mimichael/) [](https://www.linkedin.com/in/mimichael/)

我们很高兴地分享这个消息，Contour 现在[是云本地计算基金会(CNCF)的孵化级托管项目](https://www.cncf.io/blog/2020/07/07/toc-accepts-contour-as-incubating-project/)。这是一个非常自豪的时刻，我们代表其他项目维护者感谢社区为我们走到这一步所做的所有工作。

如果您还不知道的话，Contour 是一个简单且可扩展的开源入口控制器，用于将流量路由到 Kubernetes 中运行的应用程序。在即将到来的 kube con+CloudNativeCon Europe 的[会议上，我们将深入探讨 Contour 的工作原理，并概述我们的开发路线图。我们想在这里提供一个轮廓做什么的预览，接受 CNCF 对这个项目意味着什么，以及我们如何看到它在未来的发展。](https://kccnceu20.sched.com/event/b6H3/bof-introduction-to-contour-a-high-performance-multitenant-ingress-controller-for-kubernetes-michael-michael-nick-young-vmware)

## **激光聚焦入口**

 [尼克·杨

Nick 是 VMware 的一名员工工程师，也是 Contour 的维护者和技术负责人。他负责项目的整体技术一致性和方向。](https://www.linkedin.com/in/nick-young-58088629/) 

首先，一些背景。到目前为止，Kubernetes 社区已经基本确定了如何处理任务，例如运行工作负载和为这些工作负载提供存储访问。但它的网络和连接选项仍然对创新敞开大门。一项基本但必要的网络任务是让流量从集群外部进入集群内部。在 Kubernetes，这被称为入口，而这正是 Contour 所提供的。这是一个工具，您可以轻松地将它放入您的集群，以根据需要引入您的流量，但它的功能可以随着您的 Kubernetes 需求的发展而增长。

更专业地说，Contour 通过部署 [Envoy](https://www.envoyproxy.io/) 作为反向代理和负载平衡器来工作。它支持开箱即用的动态配置更新，可以扩展到多流 Kubernetes 集群，并提供高级负载平衡策略。

在 Kubernetes 中有很多方法可以运行入口控制器，但 Contour 是独一无二的，它只专注于一项任务，并在考虑安全性和多租户的情况下以高水平的性能运行。

虽然您可以部署一个[服务网格](https://blogs.vmware.com/opensource/2019/08/01/explaining-service-mesh/)来完成这项工作，但这将意味着在您的集群中引入额外的复杂性。相比之下，Contour 提供了入口功能，而不必让您的解决方案与它附带的更大的服务网格结构相一致(但如果您需要的话，它也可以与服务网格一起工作)。因此，它提供了一种渐进的入口，很快被证明对广泛的用户具有吸引力。

## **CNCF 支持的力量**

Contour 于 2017 年底由 Heptio 的开发者发起，去年 11 月进入 1.0 阶段，现在拥有 600 多名 Slack 成员的社区，有 300 多名贡献者，90 多名提交者和[五名维护者](https://github.com/projectcontour/community/blob/master/MAINTAINERS.md)。也许最重要的是，它正被包括 Adobe、Kinvolk、Kintone、PhishLabs 在内的企业和组织用于生产，并被复制。看到用户已经在运行 Contour 的生产级实例，并且知道我们已经建立了一个强大的社区，CNCF 觉得可以让我们跳过他们的沙盒级别，将 Contour 作为一个孵化项目引入。

这对我们来说意义重大。我们将 CNCF 的邀请视为对我们已经是一个可持续、开放和友好的社区的肯定，它与 CNCF 的技术目标一致，并与生态系统中的其他项目(如 Kubernetes 和 Envoy)合作良好。最重要的是，它向每个想使用 Contour 的人保证我们有厂商中立的治理——他们可以作为贡献者参与进来，并帮助影响项目的策略、方向和愿景。

随着越来越多的人参与进来，我们希望显著增加新功能添加的多样性和速度。但是我们将继续以每月发布一次的节奏运行；这样，我们就不会让用户等待新的功能、错误修复或安全修复。

## **为 Kubernetes 生态系统做出贡献**

在近期，我们的[计划](https://github.com/projectcontour/community/blob/master/ROADMAP.md)是根据社区的需求构建功能。其中一些请求是针对主要项目的，如外部身份认证支持，这是人们长期以来一直想要的，但我们直到最近才有资源来处理。外部认证支持也是一件你只有从你的社区获得大量反馈才能成功完成的事情；我们终于有足够的空间来进行这样的对话了。

我们希望在不久的将来增加的其他内容包括:

我们也开始考虑 [UDP(用户数据报协议)支持](https://github.com/projectcontour/contour/issues/1248)。Contour 是一个 HTTP 第 7 层入口控制器，但我们的一些用户希望在 Kubernetes 上放置不符合 HTTP 模型的云原生应用程序(例如，VOIP 和电信风格的应用程序)。这些通常使用 UDP，所以我们正在考虑扩展我们的场景来满足他们的需求。

在[更广阔的前景](https://projectcontour.io/resources/philosophy/)中，我们希望将我们从实施 Ingress 控制器中学到的东西反馈给开源社区，帮助改进下一代 Kubernetes [服务 API](https://github.com/kubernetes-sigs/service-apis)中从外部世界到集群的数据路由，特别是对于我们已经成为解决专家的用例。

## **了解更多信息，并加入我们！**

如果您想了解更多关于 Contour 的信息，包括更深入地了解项目如何运作，以及我们加入 CNCF 后团队希望实现的目标，我们希望在中欧夏令时 8 月 20 日下午 1 点的虚拟 [KubeCon 会议](https://kccnceu20.sched.com/event/b6H3/bof-introduction-to-contour-a-high-performance-multitenant-ingress-controller-for-kubernetes-michael-michael-nick-young-vmware)上与您见面。

那些不能来的人被邀请参加项目的任何周二[社区会议](https://projectcontour.io/community/)，这些会议都有记录。你也可以注册 Contour [邮件列表](https://groups.google.com/forum/#!forum/projectcontour-announce)，我们提供固定的[办公时间](https://github.com/projectcontour/community/wiki/Office-Hours)，在那里你可以提出问题，或者与熟悉项目的人一起通过 PR 实时工作。如果您或您的团队想要一个演示，只需在 Slack 上与我们联系或在我们的邮件列表中发布消息。

最后，如果你有兴趣投稿，我们希望你能加入我们。查看我们的[文档](https://github.com/projectcontour/contour)，就 [Slack](https://kubernetes.slack.com/?redir=%2Fmessages%2Fcontour) 与我们聊天，或者从我们的[好的第一期](https://github.com/projectcontour/contour/issues?q=is%3Aopen+is%3Aissue+label%3A%22Good+first+issue%22)开始。我们总是对您想要分享的任何反馈感兴趣:用户故事、部署故事、任何您想看到添加到项目中的东西。

*要了解更多关于 Contour 和其他云原生技术的信息，请考虑参加 8 月 17 日至 20 日在 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 举办的虚拟会议。*

[![](img/75815f6c9d934e86ec6fa33b77909e39.png)](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>