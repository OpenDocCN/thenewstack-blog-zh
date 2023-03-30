# 右舷:把所有的库本内特安全部件放在一个地方

> 原文：<https://thenewstack.io/starboard-putting-all-the-kubernetes-security-pieces-into-one-place/>

[Honeycomb](https://www.honeycomb.io/) 正在赞助新 Stack 对 Kubecon+CloudNativeCon 北美 2020 的报道。

跟我重复:“ [Kubernetes 默认不安全。](https://thenewstack.io/kubernetes-security-best-practices-to-keep-you-out-of-the-news/)“明白了吗？很好，承认这一点是走向 [Kubernetes](https://kubernetes.io/) 安全智慧的第一步。但是， [Aqua Security](https://www.aquasec.com/) 的开源 Kubernetes 安全 CLI 和操作器 [Starboard](https://github.com/aquasecurity/starboard) 可以帮助您了解 Kubernetes 集群中的安全情况。

在 KubeCon 的演示中，Aqua Security 开源工程副总裁 Liz Rice 和 Aqua Security 开源工程师 Daniel Pacak 解释了 Starboard 的情况。

基本上，Starboard 将来自各种 Kubernetes 安全工具的安全数据收集到 Kubernetes [自定义资源定义(CRD)](https://kubernetes.io/docs/tasks/extend-kubernetes/custom-resources/custom-resource-definitions/) 中。这些扩展了 Kubernetes APIs，因此用户可以通过 Kubernetes 接口管理和访问安全报告，如 [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) 或 [Octant Kubernetes web 接口](https://octant.dev/)，您已经每天都在使用这些接口。它还带有一个 Go 模块，可以更容易地使用现有的安全工具。

除了作为源代码，你还可以作为一个二进制文件运行 Starboard。您可以在两种不同的模式下运行它:

*   作为一个[命令行工具](https://github.com/aquasecurity/starboard#starboard-cli) (CLI)，您可以触发扫描并以一种 kubectl 兼容的方式或作为您的 CI/CD 管道的一部分来查看风险。
*   或者，作为[操作员](https://github.com/aquasecurity/starboard#starboard-operator)自动更新安全报告资源，以响应 Kubernetes 集群上的工作负载和其他变化——例如，在启动新的 pod 时启动漏洞扫描。

使用 Starboard 最简单的方法是简单地运行 [Starboard CLI](https://github.com/aquasecurity/starboard#starboard-cli) ，让它扫描您部署的 Kubernetes 工作负载。在幕后，默认情况下，Starboard 使用 Aqua Security 的 [Trivy](https://github.com/aquasecurity/trivy) 漏洞扫描器来发现集装箱图像中的问题。作为操作员使用时，它会创建存储在集群中的安全报告，作为您每个工作负载的定制资源。

无论是哪种情况，正如赖斯指出的，Starboard 不只是与 Aqua 的工具一起工作。它可以启用漏洞扫描器、工作负载审计器和配置基准测试的结果也就是说，Pacak 承认，“这还不像是即插即用的体验，但总的来说，我们相信我们可以解决其他工具的问题。

这没什么好惊讶的。右舷是一个年轻的项目。它于 2020 年 6 月首次问世。既然已经有这么多 Kubernetes 安全工具，你可能会想为什么 Aqua 要这么麻烦。

原因是 Starboard 的竞争对手都使用非常相似的方法:

1.  通过 Kubernetes API 或解析描述符 YAML 文件来发现 Kubernetes 对象
2.  针对这些对象调用某种风险评估(例如，运行一个 Trivy 二进制可执行文件来查找容器映像漏洞，调用一个 Go 函数来检查给定 Pod 的 SecurityContext，或者使用一些[减压阀](https://www.openpolicyagent.org/docs/latest/policy-language/)规则来评估 Pod 规范)
3.  输出风险评估报告，通常输出到标准输出或文件，通常是 JSON 或 YAML 格式的自由格式模式。

然而，它们没有以统一数据格式生成结果。如果你使用两个或更多的工具，你就不得不尝试理解多种格式。Starboard 的答案是使用本地 Kubernetes 方法处理这些不同的输出:

*   将结果存储在 Kubernetes CRDs 中，可以使用 Kubernetes API 对其进行查询
*   使用 Kubernetes 操作员高效管理集群内不同资源的安全评估
*   利用 Kubernetes 基于角色的访问控制(RBAC)来更容易地控制谁可以访问不同的安全报告
*   使用 Kubernetes 操作符通过灵活的策略将结果聚集到 Kubernetes 本地 CRDs 中

那么，我们该何去何从？Starboard 的团队计划开发完全可插拔的安全报告。

但是，除此之外，Rice 说，我们希望您帮助解决“您的集群中最重要的安全问题是什么，或者您所关心的特定命名空间中最重要的安全问题是什么”。我们希望能够总结这些不同类型的安全报告中最重要的问题。然后，我们可以让工程师更容易发现他真正需要担心的安全问题。”

而且，当你仔细想想，这难道不是我们都能达成一致的目标吗？

云原生计算基金会和 KubeCon+CloudNativeCon 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>