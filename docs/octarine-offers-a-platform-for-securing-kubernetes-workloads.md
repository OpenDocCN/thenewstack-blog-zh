# Octarine 提供了一个保护 Kubernetes 工作负载的平台

> 原文：<https://thenewstack.io/octarine-offers-a-platform-for-securing-kubernetes-workloads/>

Portworx 赞助了 New Stack 在圣地亚哥的 KubeCon + CloudNativeCon 的报道。

集装箱安全公司 [Octarine](https://www.octarinesec.com) 已经推出了 [Guardrails](https://www.octarinesec.com/streamline-kubernetes-app-security-with-octarineguardrail/) 和 Runtime，这两项技术旨在确保 [Kubernetes 工作负载在开发、测试和部署阶段以及运行时的安全](https://thenewstack.io/primer-what-is-container-security/)。

Octarine 的首席技术官和联合创始人 Haim Helman 解释说，许多在生产中运行 Kubernetes 的公司依靠[集装箱图像扫描](/how-to-scan-docker-images-for-vulnerabilities-with-harbor/)来检测威胁。“这为 Kubernetes 中部署的工作负载配置以及运行时行为中的风险留下了盲点。”

Octarine Guardrails 和 Octarine Runtime 解决了这两个安全盲点。

Octarine 的一个客户让一名开发人员从一个工作负载中删除了所有身份验证，该工作负载不应该暴露在互联网上以便进行测试。然后工作量不小心被推到生产中暴露了。这就是护栏可以预防的那种安全问题。Helman 说，如果工作负载受到损害，运行时会检测到任何异常行为，但容器扫描不会。

Helman 解释说:“安全团队缺乏云原生知识。“DevOps 团队缺乏安全知识和技能。固执己见、具有预先制定的策略、自动化友好的工具有助于弥合差距。”

### 竖起护栏

Kubernetes 不仅仅是编排容器。开发人员使用它来提供存储、配置网络、管理机密和定义权限。这是直接使用 YAML 完成的。除非有一种方法可以确保最佳实践在整个组织范围内得到一致的遵循，否则就有可能——也许是不可避免的——出现错误。

Octarine Guardrails 提供了一个准入控制器，它在集群中运行并执行策略。最佳实践策略是预先加载的，但用户也可以扩展或更改 Octarine 默认提供的模板。违反策略的部署会被自动拒绝。

此外，有一个 API 可以集成到持续集成工具中，该工具提供对 YAML 文件的策略违规分析。

Helman 说，最接近护栏的是 Kubernetes Pod 安全策略，它包含在核心 Kubernetes 中。但是 pod 安全策略只查看 pod 的属性，而不查看 pod 如何暴露给外部世界，比如 Pod 可以访问哪些秘密。来自 Pod 安全策略的数据也隐藏在日志中，难以可视化，并且没有自动执行。

## 运行时的安全性

“扫描图像有两个主要问题，”赫尔曼解释道。"一是它只寻找已经被发现和理解的漏洞."这通常不会发生，直到漏洞已经存在数周或数月。在图像扫描器检测到它之前，必须将其添加到漏洞数据库中。

“第二个问题是，容器扫描只查看已知的库，”Helman 说。它不会寻找自定义代码，也不会检测自定义代码中的策略违规，因为这不是该工具所寻找的。

Octarine Runtime 使用一个[服务网格](https://thenewstack.io/how-zero-trust-service-meshes-and-role-based-access-control-can-prevent-a-cloud-based-security-mess/)，要么与客户的 Istio 部署集成，要么使用自己的基于 Envoy 的服务网格，来捕获和分析流量，并寻找任何行为异常。服务网格还可以用于在运行时定义和实施与分段、访问控制和出口流量相关的策略。

Octarine 将于本周在圣地亚哥的 [KubeCon+CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 展示这些新技术。

[KubeCon+CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 是新堆栈的赞助商。

来自 Pixabay 的 Jill Wellington 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>