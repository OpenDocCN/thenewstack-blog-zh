# 构建、部署、运行时:Kubernetes 安全性的三个阶段

> 原文：<https://thenewstack.io/build-deploy-runtime-the-3-stages-of-kubernetes-security/>

[](https://twitter.com/DMBisson)

 [大卫·比森

大卫·比森是一名信息安全作家和安全迷。他是 IBM 安全情报、Tripwire 安全博客的特约编辑，也是 Bora 的特约撰稿人。他还定期为 Zix 和数字安全领域的许多其他公司撰写书面内容。](https://twitter.com/DMBisson) [](https://twitter.com/DMBisson)

Kubernetes 安全性是许多组织面临的一个问题。在一份由 [TechRepublic](https://www.techrepublic.com/article/security-concerns-hampering-adoption-of-containers-and-kubernetes/) 报道的 2020 年报告中，94%的受访者透露，他们的组织在过去 12 个月中经历了一次涉及 Kubernetes 和 container 环境的安全事件。近一半(44%)的组织对这些事件的反应是推迟其应用程序的生产部署。

这些发现表明，对于寻求将容器和 Kubernetes 应用程序部署到生产环境中的组织来说，安全性是并且需要继续是一个优先考虑的问题。为了尽可能顺利地进行部署，组织必须了解整个应用程序开发生命周期的安全性和法规遵从性要求。这意味着将安全性集成到容器生命周期的三个阶段:构建、部署和运行时。

## 阶段 1:构建

应用程序开发生命周期的构建阶段中存在的漏洞在运行时可能变得更加难以修复，修复成本也更高。这就是组织在构建阶段关注容器安全的重要性。他们可以通过遵循几个安全最佳实践来做到这一点:

*   **构建安全映像**:这里要记住的重要一点是让容器尽可能简单。组织应该避免使用具有操作系统包管理器或外壳的容器映像。这些类型的资源可能包含漏洞，从而为攻击者提供了可能的进入途径。他们还应该努力从容器中移除调试工具和其他不必要的组件；这些程序中的缺陷也可能为恶意行为者打开大门。
*   **最小化您的攻击面**:组织需要仔细查看其容器的必要元素。为此，他们应该确保运行最新版本的容器。这样做将有助于最大限度地减少漏洞的存在。此外，他们应该利用图像扫描仪扫描他们的集装箱，寻找潜在的安全漏洞。该工具应该能够扫描操作系统包和第三方运行时库中的 bug，以查找容器化应用程序所使用的语言类型。如果该工具检测到缺陷，组织应该使用他们的漏洞管理工具来确定适当修复的优先级。如果他们认为某个漏洞不值得(立即)修复，他们还可以选择使用白名单规则来确保漏洞不会扰乱他们的安全团队。

## 阶段 2:部署

组织需要在部署 Kubernetes 基础设施之前确保其安全。这项工作应该从确保组织对其网络有足够的可见性开始。[帮助网络安全](https://www.helpnetsecurity.com/2019/06/17/runtime-container-security/)阐明可见性对于确保集装箱安全的重要性:

通过深入的可见性和保护来保护网络至关重要，因为网络是阻止恶意行为者攻击工作负载的第一道防线。同时，网络是最后一道防线，保护数据不被暴露。在第一道和最后一道防线之间，网络可见性和适当的网络控制可以防止内部东西向流量中的攻击升级。

就可见性而言，组织需要明确了解每种资源的部署内容、位置和方式，以及它可以访问的内容。然后，他们可以利用网络策略来调整 pod 和集群之间的流量。正如 [Kubernetes](https://kubernetes.io/docs/concepts/services-networking/network-policies/) 在其网站上指出的，pods 在默认情况下是非隔离的，因此可以接受来自任何来源的流量。幸运的是，组织可以通过创建网络策略来限制这些通信流。

组织也不应该忘记在部署阶段扫描映像。一旦他们有了这些扫描的结果，他们必须采取行动。例如，如果容器映像缺少扫描结果或者存在已知的漏洞，他们可以使用这些扫描结果和[准入控制器](https://kubernetes.io/docs/reference/access-authn-authz/admission-controllers/)来拒绝部署应用程序。

## 阶段 3:运行时

最后但同样重要的是，组织需要在运行时阶段投资于容器安全性。可见度和图像扫描在这个阶段仍然很重要。但是组织需要记住一些重要的区别。 [StackRox](https://www.stackrox.com/post/2020/04/container-image-security-beyond-vulnerability-scanning/) 确定构建和运行阶段的流程映像扫描有何不同:

在生产系统上运行时，可以利用您用来生成和编译应用程序的构建工具。请记住，容器应该被视为临时的、短暂的实体。永远不要计划“修补”或改变正在运行的容器。构建新的映像并替换过时的容器部署。使用多级 docker 文件将软件编译排除在运行时映像之外。

同样，组织确保其运行时容器安全性的唯一方法是确保网络上的异常行为无法隐藏。Help Net Security 解释说，因此，组织需要能够在第 7 层检查网络数据包。这样，组织还将能够利用深度数据包检测(DPI)和其他类型的技术来帮助检测更复杂的攻击。

## 其他提示比比皆是

组织可以使用上面提供的技巧，在应用程序开发生命周期的构建、部署和运行时阶段开始保护它们的容器。然而，这篇文章的建议并不详尽。更多安全提示可以在[这里](https://kubernetes.io/docs/concepts/security/)找到。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过[推特](https://twitter.com/thenewstack)或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>