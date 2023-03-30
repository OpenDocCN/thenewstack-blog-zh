# 提高开发人员对 Kubernetes 的满意度，但首先:谁来做配置？

> 原文：<https://thenewstack.io/improving-developer-happiness-on-kubernetes-but-first-who-does-configuration/>

Kubernetes 拥有独特数量的不同用户角色。与其他基础设施软件一样，平台运营商是关键用户。但是 Kubernetes 用户还包括实际的最终用户和编写代码的人。现在，一个新出现的独特角色是实际执行应用程序配置的人。这个“配置者”或“应用程序操作员”角色可能是传统的 IT 操作员或开发人员。

这些角色的模糊是理解为什么开发人员对 Kubernetes 用户体验不满意的关键。在本期[New Stack Analysts](/podcasts/analysts)播客中，我们将探讨两个 Kubernetes 特别兴趣小组(SIG)如何考虑各种用户角色，以帮助塑造 Kubernetes 上的用户体验。本期节目的嘉宾包括:

[在 Kubernetes 上提升开发者幸福感，但首先:谁做配置？](https://thenewstack.simplecast.com/episodes/improving-developer-happiness-on-kubernetes-but-first-who-does-configuration)

有三种方式来思考如何看待 Kubernetes 中的开发人员体验，这有助于定义与确定如何改进它相关的问题。

*   平台:Kubernetes 本质上是网络上的比特。如果没有一个基于它构建的平台，它就不适合开发人员使用。这就是为什么 Red Hat OpenShift 和其他托管服务如此受欢迎。
*   **操作员**:这些是 Kubernetes SIG 集团正在定义的“配置者”角色。问题变成了，谁来做配置？这是一个有多个角色的角色，取决于许多因素。
*   **策略**:随着越来越多的人在一个组织内使用 Kubernetes 基础设施，策略是如何发展的。

随着 Kubernetes 的成熟，越来越明显的是，在多租户和与安全性和集群隔离相关的挑战方面，需要考虑更多的问题，这与开发人员面临的问题有关。例如，需要平台来隔离可能使用同一个集群的多个团队。

“许多托管服务关注的一件事是帮助公司有效地进行多租户，获得正确的隔离，”Drew 说。“当然，还有配置管理。基本上，服务侧重于提供一种自以为是的方法，这样会更容易一些。”

定义集群越来越成为使用自定义资源定义(CRD)为 Kubernetes API 提供 API 的问题。但是，开发 CRD 对大多数管理员来说还是一项相当新的任务。Kubernetes SIG 所做的工作就是定义角色，这将为运营商带来改进。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>