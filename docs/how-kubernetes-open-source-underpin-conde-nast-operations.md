# 开源软件 Kubernetes 如何支撑康泰纳仕的运营

> 原文：<https://thenewstack.io/how-kubernetes-open-source-underpin-conde-nast-operations/>

KubeCon+CloudNativeCon 赞助了这个播客，作为对 Kubernetes 终端用户的一系列采访的一部分。听听来自[维基媒体](/what-wikipedias-infrastructure-is-like-behind-the-firewall/)的下一个终端用户的故事。

康泰纳仕是世界上最知名的媒体品牌之一，拥有一系列突出的头衔，包括《连线》、《纽约客》和《名利场》这家出版巨头也代表了一个案例研究，即一家大型跨国公司如何能够将其整个国际网络和数据运营转移到一个同质的 Kubernetes 基础架构，该基础架构由它构建，现在使用开源工具进行管理。

在过去的五年里，[康泰纳仕](https://www.condenast.com/)建立了一个单一的基础平台，由分布在世界各地的几十个网站组成，包括俄国、中国、美国和欧洲。它的网站现在每月拥有超过 3 亿的独立用户，每秒钟有 570 篇文章被浏览。

在[的最后一集中，新堆栈分析师](https://thenewstack.io/podcasts/analysts)播客[condéNast](https://medium.com/@jenniferstrej)的站点可靠性工程师 Jennifer Strejevitch 讲述了她在出版公司基础设施相关挑战和成功的第一线的经历和观察。这场秀由 New Stack 创始人兼主编 Alex Williams 和我们的嘉宾[云原生工程副总裁](https://www.linkedin.com/in/kenowens12/)Ken Owens[master card](https://www.mastercard.us/en-us.html)主持。

[Kubernetes 如何开源支撑康泰纳仕的运营](https://thenewstack.simplecast.com/episodes/how-kubernetes-open-source-underpin-conde-nast-operations)

如上所述，康泰纳仕的网络基础设施之前是高度分散的。正如 Strejevitch 所描述的，康泰纳仕的运营状况意味着，例如，世界上的每个国家都有独立的书库。Strejevitch 说，它们将在 WordPress、复杂的[亚马逊网络服务(AWS)](https://aws.amazon.com/) 基础设施和内部运营上运行。

“市场技术之间几乎没有同步性。当一个时尚品牌决定与我们合作做广告时，他们需要与每个国家打交道，并根据每个市场分别提供不同格式的材料，”斯特列耶维奇说。“我们认为，通过合作和统一我们的技术堆栈，我们将受益匪浅。”

Strejevitch 说，统一不同市场中所有不同基础设施的解决方案是一个包罗万象的多租户基础设施，“服务于来自多个品牌和国家的内容”。“在这种情况下，这将允许更快的增长。这样，每个人都可以从新功能中受益，并鼓励更多的合作。”

Kubernetes 的采用被视为在这一转变中发挥了关键作用，同时也依赖于开源工具。Strejevitch 说，康泰纳仕决定的背后是其计划应对与在有许多限制的国家扩展其数据和网络基础设施相关的挑战，例如，使用第三方工具。

这是这家跨国公司管理自己的 Kubernetes 集群并为此使用开源工具的原因之一，包括使用[基础设施作为代码(IaC)](https://en.wikipedia.org/wiki/Infrastructure_as_code) 为其集群提供[构造](https://tectonic.com/blog/announcing-tectonic/)。Strejevitch 说，采用和使用 [Terraform](https://www.terraform.io/) 来提供和管理 IaC 也是康泰纳仕采用 IaC“用于一切并能够复制它，使它在全球范围内可移植”的战略的核心。

Strejevitch 说，Condé Nast 向 Kubernetes 的转变严重依赖于开源工具，同时使用[云本地计算基金会(CNCF)](https://www.cncf.io/) 作为不同项目可信度的过滤器和指南。

“我们首先看需求，然后看不同的选项和供应商，并优先考虑开源，以确保[特定工具]符合安全要求，”Strejevitch 说。

最终，测试是为了确保用户体验——无论是通过单一界面在 20 个不同国家购买媒体空间，还是仅仅在香港阅读《纽约客》的一篇文章——是成功的。如果用户体验没有受到积极影响，改善网络基础设施的工具选择过程就没有多大意义。

例如，Strejevitch 说，依靠可观察性“首先关注客户价值，然后利用你的工具来实现它。”

*加入 KubeCon + CloudNativeCon Virtual，我们将与技术专家探讨自动化时代的 DevOps 运动。[现在注册](https://www.cvent.com/events/kubecon-cloudnativecon-europe-2020/registration-f83a2bca694e4e389f002e61aafcea6f.aspx?r=f0efde22-0652-4eab-b320-afbb48b7ad83&refid=Media&tystub=7hq9h4&fqp=true)！*

[![](img/1126c24a27cdc3f9a5d8d73ed7213aec.png)](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)

[亚马逊网络服务(AWS)](https://aws.amazon.com/) 、云计算原生计算基金会和哈希公司是新堆栈的赞助商。

Dan LeFebvre 在 Unsplash 上拍摄的照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>