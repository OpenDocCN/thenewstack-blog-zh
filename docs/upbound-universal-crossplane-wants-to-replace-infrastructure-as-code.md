# 上行通用交叉板希望取代代码形式的基础设施

> 原文：<https://thenewstack.io/upbound-universal-crossplane-wants-to-replace-infrastructure-as-code/>

创造了[交叉平面](https://crossplane.io/)的 Upbound 公司，已经创造了它所说的第一个交叉平面的企业分布，叫做 [Upbound 通用交叉平面(UXP)](https://www.upbound.io/uxp/) 。

Crossplane 目前是[Cloud Native Computing Foundation](https://cncf.io/?utm_content=inline-mention)(CNCF)的一个沙盒级项目，是一个开源的 Kubernetes 插件，它使团队能够使用 Kubernetes API 供应和管理来自不同云供应商的云基础设施。

Upbound 创始人兼首席执行官 Bassam Tabbara 在一次采访中说:“我们的想法是将 Kubernetes 所做的和做得很好的东西带到容器之外的整个场景。Crossplane”成为您可以使用的通用控制平面，使用 Kubernetes 社区开创的相同风格，从单个控制平面管理企业接触的所有基础设施。

因此，UXP 是一个开源的、供应商支持的、企业级的交叉平面分布，它还增加了一个 24/7 支持层、优先错误修复和订阅咨询。个人用户可以免费获得 UXP，大型部署可以通过订阅获得，它是用一个命令安装的交叉板的替代产品。

Tabbara 指出，UXP 是“供应商支持的，而不是社区支持的”，因为 Upbound 将“帮助企业部署它，支持它，并为他们提供许多功能，使他们更容易在其环境中部署和管理它。”作为一个长期支持的项目，UXP 也落后于 Crossplane upstream，以确保可靠性，Upbound 在一份新闻声明中描述 UXP“旨在帮助企业采用通用控制平面，超越基础设施作为代码”。

在 UXP 的情况下，Crossplane 进一步扩展了它与 Upbound Cloud 和 Upbound Registry 的集成，这两者在 UXP 发布的同时变得普遍可用。上行云为团队提供了对其 UXP 实例和正在管理的基础架构的可见性，使他们能够了解什么在哪里运行，以及由谁进行了资源调配。Upbound Registry 提供了一个公开和私下共享交叉板配置的地方，也为提供商提供了一个共享管理资源的地方。

“有了 UXP，有了上行云和上行注册，我们相信我们现在有一系列产品可以真正采用这种在企业中使用控制平面的方法，并将其转变为管理基础设施的一种新方式，”Tabbara 说。“我们在现有客户身上看到了这一点，他们甚至可能会用 Terraform 和基础设施即代码方法等工具来取代他们现在所做的事情，并更倾向于控制平面方法，甚至是控制平面之上的 gitOps。”

Tabbara 认为所有这些的最大区别是，通过采用 API 驱动的方法而不是依赖模板，就像将基础设施作为代码一样，Crossplane 和 UXP 可以提供更可扩展的体验来管理大型和多样化环境中的基础设施。他解释说，Crossplane 的部分吸引力在于这样一个事实，即团队可以使用他们已经在使用的相同的基于 Kubernetes 的工具和方法来部署软件以供应和管理基础设施。

“如果你正在使用 Helm 或 kustomize，或者如果你正在使用 Kubernetes 上人们正在部署、喜爱和使用的任何工具，作为一个容器编排器，这些工具的工作方式完全相同，”Tabbara 说。“当您使用 Kubernetes plus Crossplane 来管理云基础架构的其余部分以及跨云和混合云的部署时，这些工具的工作方式完全相同。他们使用的交叉平面 API 是 Kubernetes 控制平面的 Kubernetes 扩展的扩展。

在最近的 [KubeCon+CloudNativeCon](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 之后，有一些关于 Kubernetes 作为通用控制平面的可行性的 [Twitter 辩论](https://twitter.com/adamhjk/status/1389945779641409541)，显然，Tabbara 支持这个想法，指出行业已经“用脚投票”

“Kubernetes 所做的事情的美妙之处在于，它给了你一个声明性的 API，不是模板，不是配置，而是一个实际的 API，你可以在那里设置你的配置——你希望发生什么，一个期望的状态——然后这就是人类工作流程的终点，”塔巴拉说。“从这一点开始，机器人会捡起它，并实际部署和管理它。事实证明，这种方法实际上与已经在云提供商中运行并导致超大规模云提供商的方法完全相同。如果你看看亚马逊的幕后，你会发现他们实际上使用这样的控制平面方法来运行他们的大规模服务。”

Tabbara 补充说，“Kubernetes 不仅正在成为通用控制平面，单看供应商的采用情况，单看今天市场上的 CRD 和控制器的数量，就可以清楚地看到，没有其他控制平面达到了这种采用程度。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>