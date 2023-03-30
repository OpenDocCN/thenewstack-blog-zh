# Snyk 的 Gareth Rushgrove 讲述可见性如何推动安全

> 原文：<https://thenewstack.io/snyks-gareth-rushgrove-on-how-visibility-is-driving-security/>

[CloudBees](https://www.cloudbees.com/) 在 11 月 18 日至 21 日于圣地亚哥举行的 [KubeCon + CloudNativeCon 北美 2019](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 之后赞助了本播客。

如果没有人去寻找，就没有人真正去思考。

这是经典的安全问题[，Snyk](https://twitter.com/garethr) 产品管理总监 Gareth Rushgrove ，在 kube con[云原生安全日](https://events19.linuxfoundation.org/events/cloud-native-security-day-2019/)与 New Stack 创始人兼发行人 Alex Williams 的对话中指出。Snyk 是一个软件即服务，致力于帮助组织标记和修复其开源、第三方依赖关系中的漏洞。

Rushgrove 说:“传递性依赖是漏洞的一个常见来源。“不仅仅是你选择包括的东西，而是你选择包括的东西选择包括，潜在地沿着许多依赖关系的树。”

[Snyk 的加雷斯·拉什格罗夫谈能见度如何保障驾驶安全](https://thenewstack.simplecast.com/episodes/snyks-gareth-rushgrove-on-how-visibility-is-driving-security)

这导致软件供应链迅速变得复杂和无序。使用代码的开发人员和编写代码的人之间的距离只会越来越大。

“大多数人都无法回答一个微服务中包含多少组件的问题。将多种微服务结合起来，用我们今天通常使用的工具来回答这些类型的问题变得非常困难，”Rushgrove 说。

它让安全性成为解决问题的第三方内容的便利性的自然折衷。在您的系统中共享任何第三方内容都会给这些系统带来潜在风险。

## Snyk 发布舵图安全报告

Synk 有助于揭示和修复流行工具和语言中的安全漏洞，如 Java、Python、containers 和 Kubernetes。在这次采访时，他们发布了报告[“Helm Chart security 的不为人知的故事”](https://snyk.io/wp-content/uploads/helm-report.pdf)及其新的 [Helm security 插件](/snyk-announced-new-container-product-what-to-know/)。

Helm 是一个非常流行的开源应用包管理器，运行在 Kubernetes 之上，简化了团队安装和管理 Kubernetes 应用的过程。Rushgrove 称舵图是一组模板化的清单或 Kubernetes 配置和一组模板化的值，以便您可以在 Kubernetes 的基础上进行构建。Snyk 插件渲染该模板，提取图像并通过 Snyk 安全检查，然后提供报告。

他们发现了什么？首先，如果以前没有人真正寻找过漏洞，就像 Helm 的情况一样，那么漏洞的数量总是很高。如果贡献者总是快速更新到最新版本的图片，一个简单的解决方案将会产生巨大的影响。

Rushgrove 的团队与 Helm 的维护者讨论了他们如何激励或游戏化他们的开源社区以保持最新。毕竟，在如此多的工具中，被称为安全的工具总是占优势。

最后，Helm 提供了一个更高层次的抽象，使得在 Kubernetes 上构建更加简单。Rushgrove 说这就是 Helm 带来的价值——它的工作不是增加安全性。

这也是更多像 Snyk 这样的工具将继续流行的地方，提高对漏洞的认识，特别是对开发人员。

Rushgrove 说，传统上，开发人员被要求走得快，而安全人员则被要求慢下来。但是现在开发团队越来越多地对他们选择利用的工具栈的安全性负责。在这个开发者驱动开发的新世界中，只有将两者结合起来，我们才能优先考虑安全性。

[https://www.youtube.com/embed/4zkGTBBXJk4?feature=oembed](https://www.youtube.com/embed/4zkGTBBXJk4?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>