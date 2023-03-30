# 云铸造峰会:Kubernetes 必须由开发者做得更好

> 原文：<https://thenewstack.io/cloud-foundry-summit-kubernetes-must-do-better-by-developers/>

对于开发人员来说，Kubernetes 仍然是一个令人担忧和烦恼的问题，因为他们必须投入大量的时间和资源来确保他们的代码能够在 Kubernetes 集群上正确运行。在最坏的情况下，开发人员还必须重新配置他们的代码，以满足不同集群环境的需求。根据最近 Cloud Foundry 峰会上的发言人的说法，最终的想法是让开发人员发挥他们的软件工程魔力，而 Kubernetes 作为一个基础设施层，例如虚拟机，在未来不是开发人员必须努力解决的问题。

“开发人员蜂拥进入 Kubernetes 有点……我想说……转移视线。Kubernetes 是一种基础设施抽象，在许多方面类似于虚拟机:它非常强大，绝对是下一代基础设施，将在所有云和内部基础设施环境中通用， [Cloud Foundry Foundation](https://www.cloudfoundry.org/?utm_content=inline-mention) 执行董事 [Chip Childers](https://www.linkedin.com/in/chipchilders) 在 [Cloud Foundry Summit 2021](https://www.cloudfoundry.org/events/summit/cfsummit2021/) 之前的 Q & A 会议上表示。“它有很大的潜力，随着它在整个市场上被采用，我们看到这种潜力正在实现，但它是基础设施。”

在 Cloud Foundry Foundation 的虚拟峰会期间，Childers 的评论和主题演讲以及许多讲座的主题都是关于 Cloud Foundry 的使命，即帮助降低进入门槛并改善在云原生环境中工作的开发人员的流程。Cloud Foundry 对云原生计划的支持主要包括其开放平台即服务(PaaS)产品，但它也寻求促进合作伙伴关系和协作，以及在 DevOps 中灌输价值观和文化，包括促进多样性。

然而，尽管取得了进展，但选择直接与 Kubernetes 互动的开发人员“发现，从他们的代码到[部署]软件，他们必须做大量的工作，”Childers 说。“该软件的操作不是应用感知的，如果您直接使用 Kubernetes，它更多的是关于基础设施抽象组件的离散类型。”

换句话说，Kubernetes 需要做更多的工作，才能更好地为开发者服务，与此同时，工具制造商正在加快步伐。“你需要根据基础设施需求来描述这项服务，”Childers 说。“因此，让开发人员的生活变得更容易的新方法几乎出现了寒武纪大爆发。"

作为帮助改善 Kubernetes 开发人员体验的一种方式，Cloud Foundry 在 Cloud Foundry 峰会期间发布了 [cf-for-k8s v5](https://github.com/cloudfoundry/cf-for-k8s/releases) ，它将 Cloud Foundry 的开发人员 API 与 Kubernetes、Istio 和其他开源工具和平台相结合。cf-for-k8s 的第五个版本虽然适用于大型企业，但它是专门针对小型组织和开发团队以及个人开发人员的需求而设计的，为用户添加了新的操作功能。根据 Cloud Foundry 的文档，该版本有助于改善底层 [Istio](https://istio.io/) 服务网状网络组件的升级过程，以及最新一代 Paketo buildpacks 的升级过程。

第五版 [cf-for-k8s](https://github.com/cloudfoundry/cf-for-k8s) 的功能“升级”包括对核心 API、认证和访问控制服务器的改进，“这带来了一系列新功能，是在 Kubernetes 环境中运行所独有的，”Childers 说。更具体地说，正如文档中所述，对 Kubernetes 集群的支持涵盖了 1.18-1.21 的 K8s 版本范围。Istio 1.10.2 bump 包含集群版本范围，增加了 Kubernetes 1.21。

正如 Childers 所指出的，Istio service mesh 在升级和安装方面肯定是“出了名的困难”,而 cf-for-k8s 的改进主要是为了支持运营团队和开发人员。

“Cloud Foundry 的目标一直是简化开发人员和运营商的底层技术，因为开发人员和运营商角色已经在一个较小的环境中走到了一起，开发人员实际上正在安装 Cloud Foundry，”Childers 说。“让这些升级周期变得非常简单非常重要。因此，我们做了大量工作来确保升级到基础 Istio 服务网格的过程非常顺利。”

另一个关键升级包括对 Kpack v0.3.1 的改进和对新 buildpack 的支持，而 Childers 将 Kpack 描述为“Cloud Foundry buildpack 过程或从源代码构建容器的过程背后的魔法。基于 [Heroku](https://www.heroku.com/) 云平台，对 buildpacks 的改进因此成为 Cloud Foundry 支持云原生开发者的关键组成部分。

“Buildpacks 是一个概念，是从源代码到容器映像的神奇调料，”Childers 说。

因为构建包是以可重新创建容器的方式以编程方式构建的，所以它们还提供了平台内的操作优势。Childers 说，这些包括能够取代传统的操作系统库，以便作为操作者修补整个应用程序群，而不是必须回到开发人员那里，要求他们重新编译。

Childers 说:“构建包真的很强大，它们现在被大多数现有的 CI/CD 工具所采用。“他们现在是一等公民，正在许多超大规模云提供商服务中使用。因此，Cloud Foundry 已经使用了很长时间的这种模式现在正成为开发人员与工具交互的更有吸引力的方式之一，然后该工具与 Kubernetes 交互以部署他们自己。我认为，我们将继续看到开发人员不再考虑谁拥有对他们直接工作有意义的环境，他们将考虑 Kubernetes 作为基础设施的呈现方式，但他们正在寻找工具，这些工具要么位于成品容器之上，要么位于成品容器旁边，并将成品容器推入 Kubernetes。”

## Cloud Native 中的 Wasm 方程

虚拟机语言 [WebAssembly (Wasm)](https://webassembly.org/) 最初是为了帮助提高 web 应用程序的代码效率而创建的。它的使用和应用已经扩展到了云本地计算的范围，这包括通过作为特使配置和管理的 API 网关，它越来越多地集成到 Kubernetes 环境中。通过将 JavaScript [(JS)](https://developer.mozilla.org/fr/docs/Web/JavaScript) 、[、C++](https://fr.wikipedia.org/wiki/C%2B%2B) 和 [Rust](https://www.rust-lang.org/fr) 组合成一个单一的运行时平台，Wasm 的创造者正在继续扩大其用于云原生部署的范围，包括 edge Kubernetes 以及服务网格支持。

对于 Cloud Foundry 用户来说，这意味着 Wasm 提供了“一种多语言的计算性质，在这里你可以使用不同的语言，然后它们可以被编译到 WebAssembly 运行时中，”SAP 的首席架构师 Shashank Mohan Jain 在他的演讲[“web assembly 简介”中说道。](https://www.youtube.com/watch?v=pUkRAtzudmY&list=PLhuMOCWn4P9iNtNmzrKzMgic8RbJyMKB8&index=23&ab_channel=CloudFoundry)

例如，对于服务网格，Jain 说 WebAssembly 可以允许“将所有类型的过滤器和其他逻辑构建到 Istio 世界中。”Jain 还在一个演示中展示了一个基于浏览器的场景，其中基于 Rust 的代码被编译到 WebAssembly 中，并在浏览器中执行之前定义和导出函数。

## 文化很重要

以尽可能好的方式使用来自 Cloud Foundry 和其他来源的最佳工具和实践，显然不足以实现 cloud native 和 DevOps 的总体目标。开发人员的创造力和对其才能的最佳利用也取决于工作的文化方面，包括促进多样性、防止倦怠和实施其他重要因素。营销和通信服务提供商 [OneMagnify](https://onemagnify.com/) 的信息技术高级总监和[妇女安全联盟](https://www.womsa.org/)的董事会成员[在她的演讲【15 分钟与 OneMagnify 的 Kerry Schaffer】中说，简单地消除 DevOps 团队必须应对的工作传票只是促进更健康的工作环境的一个例子](https://www.youtube.com/watch?v=8pUZuDTMaw8&list=PLhuMOCWn4P9iNtNmzrKzMgic8RbJyMKB8&index=29&ab_channel=CloudFoundry)

“由于容器的工作方式，消除了对我们票证的需求减少了运营工作量，并提高了[DevOps 团队成员]在工作时间进行部署的能力，这实际上意味着我们可以更快地为客户提供结果，”谢弗说对于开发人员来说，这意味着更少的下班时间。"

谢弗还表示，通过她在 OneMagnify 的工作和作为女性安全联盟董事会成员，她对试图增加女性在 IT 行业的人数充满热情。“当我发现进入 IT 行业的女性人数自 1985 年以来逐年下降时，我感到震惊，这似乎很疯狂，因为 It 行业有很好的工作，对女性来说有很好的职业机会，”谢弗说。“当你看看 2020 年 COVID 19 疫情发生了什么，我们实际上看到更多的女性退出了劳动力市场。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>