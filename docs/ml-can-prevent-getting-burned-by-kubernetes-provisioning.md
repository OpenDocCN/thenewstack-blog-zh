# ML 可以简化 Kubernetes 供应

> 原文：<https://thenewstack.io/ml-can-prevent-getting-burned-by-kubernetes-provisioning/>

底特律——在创建、供应和管理 [Kubernetes、](https://thenewstack.io/docker-versus-kubernetes-start-here/)的热潮中，适当的资源供应经常被忽略。根据 [StormForge，](https://www.stormforge.io/?utm_content=inline-mention)的说法，例如，一家公司每月支付 100 万美元的云计算资源，可能每年会浪费 600 万美元的云资源用于未使用的 Kubernetes 集群。

造成这种情况的原因是多方面的，并且可能有所不同。它们包括 [DevOps](https://thenewstack.io/platform-engineering-is-devops-evolved-new-report-shows/) 团队如何倾向于在资源供应上过于保守或激进或超支。在这一集的 New Stack Makers 播客中，StormForge 的 [Yasmin Rajabi、](https://www.linkedin.com/in/yasminrajabi) 产品管理副总裁和 [首席技术官帕特里克·博格斯特伦](https://www.linkedin.com/in/bergstrompatrick) 、讨论了如何正确调配 Kubernetes 资源，并探讨了相关挑战。

这一集《创客在路上》是在[kube con+CloudNativeCon 北美 2022 期间在底特律现场录制的。对话由 TNS 的长期撰稿人](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention)b . Cameron Gain 主持。

[ML 可以预防烫伤](https://thenewstack.simplecast.com/episodes/ml-canprevent-getting-burned-for-kubernetes-provisioning)

## 黑暗中的开发者

具有讽刺意味的是，最常用的 Kubernetes 资源甚至会使优化应用程序资源的能力变得复杂。这些流程通常涉及 Kubernetes 资源请求和限制，以及预测资源可能如何影响 pods 的服务质量。

在 Kubernetes 上部署应用程序的开发人员通常需要设置 CPU 请求、内存请求和其他资源限制。“他们通常会说‘我不知道——不管之前是什么，不管默认是什么，’”Raja bi 说。“他们被蒙在鼓里。”

[https://www.youtube.com/embed/k9cUk8kBXKM](https://www.youtube.com/embed/k9cUk8kBXKM)

视频

Rajabi 说，有时候，开发人员可能会使用他们最喜欢的可观察性工具，然后说，“我们看看最大值在哪里，然后猜一猜。”。

“挑战在于，如果你从那里开始横向扩展，特别是对于使用 Kubernetes 进行横向扩展的组织来说，那么你就会遇到这个问题，而且你会在任何地方扩大这个问题。所以，当你在大规模上遇到这种复杂性时，花一秒钟回顾一下，然后问‘我们如何解决这个问题？’，你不希望只是随意减少资源，因为你必须考虑如何影响你的可靠性的权衡。”

这个过程变得非常随意。Rajabi 说:“当所有这些环境、所有这些名称空间中有如此多的设置时，这就变得非常复杂了。”“这几乎是一个只有机器学习才能解决的问题，这让它变得非常有趣。”

但是，在组织学会如何不自动优化、部署和管理 Kubernetes 之前，许多资源和成本都被浪费了。

博格斯特伦说:“作为一个组织，你发展得越快，挑战就越大。

许多 StormForge 客户正在部署成千上万的名称空间和工作负载，他说:“你突然试图单独管理每个工作负载，以确保它拥有所需的资源和内存。”

当 ML 被正确实施时，该过程实际上应该是没有痛苦的。随着 StormForge 与 Datadog 的合作，应用 ML 收集历史数据成为可能，博格斯特伦说。

“然后，在我们将我们的算法部署到您的环境中的几个小时内，我们就有了机器学习，它使用了两到三周的数据进行训练，然后可以自动为您的应用程序设置正确的资源。这是因为我们知道应用程序实际使用的是什么，”博格斯特伦说。“我们可以预测模式，也知道成功需要什么。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>