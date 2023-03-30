# Kubernetes Starboard 项目提供来自 Kubectl 的安全扫描

> 原文：<https://thenewstack.io/kubernetes-starboard-project-offers-security-scanning-from-kubectl/>

新的开源 Kubernetes 安全工具包 Starboard 背后的基本思想非常简单，开源工程副总裁 [Liz Rice](https://www.linkedin.com/in/lizrice) 说 [Aqua Security](https://www.aquasec.com/) ，一旦你看到它，它就是有意义的。

“当您在应用程序状态信息旁边看到漏洞信息时，您会认为这是一个好主意，因为它看起来太明显了。当然，您希望在应用程序本身旁边看到漏洞信息，”Rice 说。

本月早些时候[发布的](https://blog.aquasec.com/starboard-kubernetes-tools) [Starboard](https://github.com/aquasecurity/starboard) 是一个 Kubernetes 原生的、可扩展的安全工具包，用于发现 Kubernetes 工作负载和环境中的风险。

该项目在 Apache 2.0 下获得许可，由 Aqua Security 等公司创建，使用[自定义资源定义](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/) (CRDs)来集成安全工具，并通过 Kubernetes API 访问结果。

Rice 解释说:“如果我们考虑安全工具以及它们在 Kubernetes 部署中的使用情况，它们往往会与 Kubernetes 部署一起使用。“如果你愿意，你可以有许多不同的安全工具，每个都有自己的界面，每个都生成自己风格的报告，可能会将信息存储在不同的数据库中，或者以 JSON 或 YAML 或该工具支持的任何形式输出。Starboard 的想法是说，如果我们可以通过 Kubernetes API 访问这些信息，那就太好了。”

Starboard 的这个初始版本包括一个 [kubectl 插件](https://github.com/aquasecurity/starboard#kubectl-plugin)，一组[自定义安全资源定义](https://github.com/aquasecurity/starboard#custom-security-resources-definitions)，一个 [Go 模块](https://github.com/aquasecurity/starboard/tree/master/pkg)，和一个 [Octant 插件](https://github.com/aquasecurity/starboard-octant-plugin)，以及与四个工具的集成，其中三个由 Aqua 构建。其中包括容器漏洞扫描器 [Trivy](https://github.com/aquasecurity/trivy) ，互联网安全中心(CIS)基准测试工具 [kube-bench](https://github.com/aquasecurity/kube-bench) ，以及 [kube-hunter](https://github.com/aquasecurity/kube-hunter) 渗透测试工具。

最后一个工具， [Polaris](https://github.com/FairwindsOps/polaris) ，由 Fairwinds 构建，旨在识别 Kubernetes 的错误配置，确保使用最佳实践配置吊舱和控制器。然后，这些工具的结果将直接与 Kubernetes 的操作信息一起放在 Octant 中，Octant 是“用于 Kubernetes 的以开发人员为中心的开源 web 界面，允许您检查 Kubernetes 集群及其应用程序”，是作为 VMware Tanzu 的一部分而构建的。

虽然这些是最初推出时提供的工具，但 Rice 强调该系统是可扩展的。

“我们的想法是，虽然在这个版本中我们已经设置了可以使用 Trivy 生成漏洞报告，但对于另一个漏洞扫描器来说，它可以很容易地与 Starboard 集成，使用相同的 CRD 定义，并以相同的方式填充漏洞信息。用户也能以同样的方式看到它，”赖斯说。“对于用户来说，他们应该能够使用 Starboard 即插即用不同的安全工具。显然，这些不同的工具都需要集成，但我们已经尝试用一些 Go 库尽可能地简化这一过程。”

赖斯在介绍 Starboard 的博客文章中指出，使用 CRDs 的另一个好处是，它允许管理员利用 Kubernetes RBAC，因此将安全报告的访问权限限制在应该访问它们的人。

赖斯称这是一个“初始”版本，她说他们希望得到反馈，并提出了该项目下一步走向何处的一些可能性。

“我认为下一步我们想要建立的是一个运营商，这样你就可以在新资源部署到 Kubernetes 时自动生成这些资源，比如漏洞报告。或者，另一个例子是操作员监视一个新节点，一旦该节点出现，就自动在该节点上运行 CIS 基准测试，以便立即为 Kubernetes API 提供一份报告，”Rice 说。

目前，Starboard 通过命令行提供安全扫描，但一个“灵活的、可插拔的” [Starboard 安全操作符](https://github.com/aquasecurity/starboard-security-operator)正在工作中，以提供更好的可扩展性，并提供每个名称空间和整个集群中的安全风险信息的“汇总”,以帮助识别最高风险。赖斯说，与 Aqua 商业产品的整合也在进行中。

[https://www.youtube.com/embed/wMUdK5SaSuY?feature=oembed](https://www.youtube.com/embed/wMUdK5SaSuY?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>