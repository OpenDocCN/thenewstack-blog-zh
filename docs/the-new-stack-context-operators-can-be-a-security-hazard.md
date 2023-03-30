# 新的堆栈上下文:操作符可能是一个安全隐患

> 原文：<https://thenewstack.io/the-new-stack-context-operators-can-be-a-security-hazard/>

几年前，Kubernetes 处于全面开发阶段，它的许多基本概念仍在发展中，因此安全性并不是一个重要的优先事项。但是随着 K8s 部署进入生产阶段，更多的注意力集中在保护 Kubernetes 及其工作负载上。 [Gadi Naor](https://www.linkedin.com/in/gadinaor/?originalSubdomain=il) 从一开始就跟随 Kubernetes security。 [Alcide](https://www.alcide.io/company/) ，Naor 创立的公司，现在担任 CTO，提供端到端的 Kubernetes 安全平台。

在本周的[新堆栈环境](/podcasts/context)播客中，我们将与 Naor 讨论各种与 Kubernetes 安全相关的话题。上周，Naor 为 Cloud Native Computing Foundation 举办了一场 Kubernetes 安全网络研讨会，除了提供许多有用的提示，还详细讨论了最近在 Kubernetes 中发现的大量漏洞。而对于*新栈*，他[在 Kubernetes 里写过配置漂移](/ci-checks-are-not-enough-combat-configuration-drift-in-kubernetes-resources/)的问题，以及为什么不能简单的通过持续集成工具来解决。

TNS 编辑和营销总监 [Libby Clark](/author/libby/) 主持这一集，旁边还有 TNS 高级编辑 [Richard MacManus](/author/richard/) 和 TNS 执行主编 [Joab Jackson](/author/joab/) 。

[第 128 集:操作人员可能成为安全隐患](https://thenewstack.simplecast.com/episodes/episode-128-operators-can-be-a-security-hazard)

对话中最令人惊讶的部分之一是 Naor 解释了他对[操作符](/this-week-in-programming-clearing-up-any-confusion-around-kubernetes-operators/)的担忧，这是一个越来越多地用于管理 Kubernetes 上复杂应用的框架:

如果有人构建一个操作符来部署一个应用程序的单个实例，这是对操作符的错误使用。你可以更好地使用掌舵图或定制资源，并把东西推到一个集群。从审计的角度来看，操作符通常作为特权组件运行，这意味着它们成为集群内部的薄弱环节。我试图在[持续集成]中扫描它，但它对所有工具都没有意义，因为它是非常特定于供应商的，不负责任地特定于供应商。您最终会带着实际上削弱了您的 Kubernetes 安全姿态的东西运行。因此，在一天结束时，为[普罗米修斯]创造一个操作员是非常有意义的，因为它自动化了你的监控系统的许多布线。它做得非常优雅。但是你有安全供应商，我不会指名道姓，他们使用操作者来部署单个实例，并且正在滥用(操作者的)这个概念。

讨论的其他主题包括:

*   披露新漏洞所需的时间越来越长。
*   控制平面上的漏洞与节点上的漏洞。
*   自我管理的 Kubernetes 与管理的 Kubernetes 中的漏洞管理。
*   为什么 Kubernetes 运营商是一个安全风险。
*   Kubernetes 中的配置漂移。
*   持续交付对 Kubernetes 安全性的重要性。
*   为什么托管平台可能会捕捉到大多数自主发行版可能会忽略的安全错误。
*   启动埃尔希德的动机。

然后，在稍后的节目中，我们来看看*新栈*本周的一些热门帖子:

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过[推特](https://twitter.com/thenewstack)或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>