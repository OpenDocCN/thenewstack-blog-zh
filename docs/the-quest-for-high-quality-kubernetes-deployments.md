# 寻求高质量的 Kubernetes 部署

> 原文：<https://thenewstack.io/the-quest-for-high-quality-kubernetes-deployments/>

无论您是刚开始使用 Kubernetes，还是管理复杂 GitOps 周期的经验丰富的平台工程师，您都会遇到处理部署工件、清单、Kustomize、舵图及其 YAML 语法的挑战，以便理解所有这些。

环境越复杂，找出它的指数复杂性就越大。用于检查和理解 Kubernetes 集群的工具很多，但是用于与创建、编辑、验证和调试 Kubernetes 配置相关的部署前任务的集成可视化工具很少。一个通用的 IDE 将会有一些本地或通过插件的支持，但是那些是钝的瑞士军刀，没有集成的和一致的 Kubernetes 意识。

在 Kubeshop，我们采访了许多人——平台工程师、站点可靠性工程师(SREs)、开发人员、开发人员和他们的领导。以下是我们从他们那里听到的一些常见挑战:

**开发者**

*   我正在看所有这些 Kubernetes YAML 文件，Kustomize 覆盖和舵图，试图了解他们如何相互联系。
*   当我对其中任何一项进行更改时，我希望确保不会破坏任何依赖关系或运行时策略。

**平台工程师**

*   我所关心的是我们团队快速一致地定义他们的应用程序的期望状态的能力。我能安装的模板和护栏越多，我就越开心。
*   我希望我们采用 GitOps 方法，但我需要确保随着 Kubernetes 部署速度的提高，我们能够保持应用程序的质量。
*   我们很想实现策略管理，但是定义兼容的配置比我们预期的要困难和缓慢。

**SREs**

*   我需要快速检查我的集群配置并对其进行故障排除，当出现问题时，我需要了解问题的方式和原因。比较集群、名称空间、分支和提交之间的配置是这个过程的关键。

**副总裁或首席技术官**

*   我们做了什么来帮助我们的团队专注于驱动我们业务的应用程序的交付，而不是被错综复杂的 Kubernetes 配置管理和工作流所拖累？

**结论:**无论我们称之为 Kubernetes“左移”还是其他什么，在开发和部署的生命周期中，您对 Kubernetes 配置的了解越多，它们就越容易管理。Kubernetes 非常复杂，学习曲线很陡。为什么不通过允许开发人员高效地使用专门构建的工具，帮助可视化事物以便于导航，并集成其他同类最佳的开源项目(如 Helm、Kustomize 和 Open Policy Agent (OPA ))来使其变得更容易呢？

这些以及其他许多核心挑战为 Monokle 作为一个统一的可视化工具来创作、分析和部署 Kubernetes 清单奠定了基础。

Monokle Desktop 获得了越来越多的关注，因为任何成功的软件开发的关键之一就是协作。

## **你好，斑云！**

最近 Monokle 团队宣布了 Monokle Cloud 的初始版本，这是现有的流行 Monokle 桌面的一个基于浏览器的版本。

正如其桌面版一样，Monokle Cloud 通过在任何现代浏览器中免费提供 Monokle Desktop 的强大功能，帮助开发人员、开发人员和平台工程师提高其 Kubernetes 部署的质量。它与 GitHub 紧密集成，通过共享功能促进更快、更容易的同行预览、比较和验证，提高生产力和跨职能协作。

以下是 Monokle Cloud 的总结:

### 这是什么？

Monokle Cloud 是一款基于浏览器的免费工具，用于探索和分析 Kubernetes 配置以及优化 GitOps 工作流。

### 是给谁的？

Monokle Cloud 适用于任何使用存储在 GitHub 上的 Kubernetes 配置的工程师，无论是简单的 YAML 部署还是完整的 GitOps 存储库。

### 它如何让您的 Kubernetes/GitOps 生活更轻松？

Monokle Cloud 提供的功能可帮助团队提高其 Kubernetes 配置的质量，并简化预部署工作流程:

*   浏览并理解您的 Kubernetes 资源及其依赖关系。
*   根据 OPA 策略、JSON 模式和资源约束验证您的 Kubernetes 配置。
*   预览并验证 Helm 和 Kustomize 的输出。
*   跨分支、提交和预览比较完整的 Kubernetes 配置集。
*   通过与 GitHub 集成并共享您的任何发现的直接链接，与利益相关者进行协作。

### Monokle Cloud 如何与 GitHub 集成？

Monokle Cloud 以几种方式与 GitHub 集成:

*   上面提到的所有特性对于任何公共的 GitHub 库都是可用的。
*   打开 GitHub 编辑器或为验证错误创建 GitHub 问题的操作被集成到 Monokle Cloud 接口中。
*   作为 GitHub 工作流的一部分，GitHub 可以在 GitHub:【https://github.com/kubeshop/monokle-action上验证你的 Kubernetes 资源的所有方面。
*   将 Monokle 云操作注入 GitHub 用户界面的 Chrome 扩展可以在 GitHub 上获得(很快将在 Chrome 商店中获得):[https://github.com/kubeshop/monokle-chrome-extension](https://github.com/kubeshop/monokle-chrome-extension)

### 好奇吗？

观看我们的首席工程师 Wito Delnat 制作的这个[四分钟的视频](https://www.youtube.com/watch?v=ds4OLjlI620)，了解 Monokle Cloud 如何让 Kubernetes 配置管理变得简单快捷。

或者尝试下面的一个直接链接，看看 Monokle Cloud 的运行情况。(您至少需要登录 Monokle Cloud 一次。)

### 哪里可以得到 Monokle Cloud？

1.  使用现代浏览器(Chrome、Safari、Edge、Firefox)前往 app.monokle.com。
2.  使用您的 GitHub 帐户登录(我们只要求最低权限)。
3.  选择或复制包含 Kubernetes 配置的任何公共 GitHub 存储库的 URL 并粘贴到 Monokle Cloud 中。

就是这样！

有问题吗？建议？取得联系！

前往我们的 [Discord 服务器](https://discord.com/channels/884464549347074049/885184562026647622)上的#monokle-cloud 频道联系，报告问题，询问功能，谈论天气等。我们希望收到您的来信！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>