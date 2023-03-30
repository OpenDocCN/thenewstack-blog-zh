# WebAssembly 应该获得 PaaS 吗？

> 原文：<https://thenewstack.io/should-webassembly-get-a-paas/>

今天的问题是 Wasm 仍然是一项新兴技术，到目前为止，很多(如果不是大部分)精力都花在解释它的作用和宣传上。

出于本文的目的，我们从较高的层次来解释 Wasm 是什么，以及为什么 PaaS 选项是必不可少的。Wasm 提供商 Cosmonic [的](https://cosmonic.com/blog/wasmcloud-orleans-kindred-spirits)首席技术官 Kevin Hoffman 最近写道，对 WebAssembly 的最基本描述与微软 [Orleans](https://learn.microsoft.com/en-us/dotnet/orleans/) 的目的或“使命声明”相符:“Orleans 是一个跨平台框架，用于构建健壮的、可伸缩的分布式应用程序。”我认为，wasmCloud、Wasm 和 Orleans 都是为了改进和简化开发人员构建应用程序的方式，减少运营和与运营团队互动的麻烦。然而，正如霍夫曼所写的，wasmCloud 和 Orleans 在实现上有所不同。

事实上，Wasm 旨在使开发人员的过程更加简单和直接，至少减轻了一些满足运营需求的压力，因为其实现提供了一种更直接的部署途径，这主要归功于其二进制计算结构。这样，它提供了跨多个目标的单一二进制可执行文件，而不必为每个目标重新配置。

“WebAssembly 的前提之一是有机会因为执行模型而回归简单性。Fermyon Technologies 公司首席执行官和联合创始人马特·布彻告诉新堆栈。" WebAssembly 只是比其他一些核心技术更容易操作."

PaaS 的替代方案——至少在理论上——使得这个过程对开发者来说更加容易。显然，它并不代表无服务器解决方案，这主要是由于 Wasm 为用户提供了跨分布式环境实现和应用的自由和灵活性(由于 Wasm 的计算和二进制执行直接写入 CPU)。

这种灵活性使 Wasm 不同于固执己见的平台，如[Cloud Foundry](https://thenewstack.io/when-to-choose-cloud-foundry-over-kubernetes/),[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉新堆栈。“Wasm 为开发人员提供了很多自由和简单的可扩展性，当涉及到滚动他们自己的应用程序堆栈时，”Volk 说。“当然，与流行的数据库、消息平台、可观察性工具和其他运行时组件的更多交钥匙集成将加快采用速度 GitHub 上提供这些集成的事实告诉我，这是可以做到的。”

## 厄运将至

PaaS 需要为开发人员提供自助服务的解决方案。早在 Kubernetes 出现之前，甚至早在几年前 DigitalOcean 的令人惊叹和有趣的选项(只需点击几下就可以通过 API 设置自己的服务器)出现之前，这种需求就已经存在了。

Butcher 告诉 the New Stack，PaaS 的核心思想是，开发人员能够使用自己的工作流，然后将其发布到最不适合开发阶段(如果不是生产阶段)的环境中。“我认为 PaaS 最引人注目的部分是，它意味着基础设施管理团队和平台工程师或开发人员之间的关系通过 PaaS 平台正式化，”他说。

需要考虑的一个关键的新的细微差别是，并非所有的 PaaS 选项都是为 WebAssembly 设计的。它们已经并且应该继续为构建在 WebAssembly 之上的工具和层而设计。在底特律举行的 KubeCon+CloudNativeCon 大会上，Wasm 推出了几个 PaaS 选项，包括 [Cosmonic platform 的](https://www.prnewswire.com/news-releases/cosmonics-webassembly-paas-removes-complexity-from-large-scale-cloud-and-edge-deployments-preview-now-open-to-developers-everywhere-301655208.html)免费开发者层。该公司表示，它提供:

*   wasmCloud 中的轻量级和“低样板”开发环境标准。
*   通过“超级星座”功能，开发人员可以携带自己的笔记本电脑、云资源或整个数据中心，并通过 Cosmonic 管理的资源组合和扩展它们，同时从单一界面管理它们。
*   能够在任何云、边缘或其他环境上运行，因此无需针对新环境重构应用。
*   改进，使开发人员更少关注会议操作，因为许多与操作相关的任务和约束都被删除了，否则开发人员将不得不承担这些任务和约束。

Fermyon 表示，其平台通过提供一个完整的基于 WebAssembly 的执行环境和一个易于使用的 Web 界面，消除了“构建云应用程序的 90%的麻烦、复杂性和成本”。“Fermyon 传达的能力包括:

*   微服务在毫秒而不是秒内启动，可以“几乎立即”扩大或缩小，并在安全的沙盒环境中执行，无需重新编译或重写即可在 Windows、macOS 和 Linux 上运行。
*   开发者可以编写微服务、web 应用、预定的批处理作业或由 HTTP、Redis pubsub 或基于时间的事件触发的机器学习。

Fermyon 也建立在一套现有的开源项目之上，这些项目共同组成了一个 WebAssembly PaaS。该公司表示，Hippo 提供了一个网络界面，Bindle 管理包， [HashiCorp 的 Nomad](https://thenewstack.io/conductor-why-we-migrated-from-kubernetes-to-nomad/) 协调部署，Spin 为其执行环境添加了模板、监控、日志和缓存。

## 赫罗库不仅仅是一个辉煌的失败

PaaS 由于与 Heroku 联系在一起而有一些负面的含义。但是这种假设是误导性的，因为 Heroku 实际上通过为 Kubernetes 提供有效的构建功能实现了它应该做的事情。Butcher 在一篇非常全面的博文中描述了这种细微差别，这篇博文讲述了 Heroku 和 PaaS 之间的历史联系，以及 Heroku 的功能如何与 GitHub Actions 的功能相似。

冒着过于简单化的风险，Heroku 的消亡通常仍然与 PaaS 联系在一起，因为 Heroku 的功能没有跟上开发人员不断发展的需求。就像 Wasm 中不可避免出现的无服务器甚至低代码的替代方案一样，PaaS 也面临着被视为对开发人员缺乏选择的风险，特别是对于复杂的用例。

“说 Paas 是‘正确的道路’实际上只是意味着这是我们今天想要的方式，因为我认为 Heroku 在正确的时间以正确的方式为他们做了这件事，并受到了一点点不好的指责，Butcher 说。”它们非常成功，我用了好几年，它们棒极了，但是在某个时候，我有了不同的兴趣，Heroku 没有随着我的兴趣而改变。“所以，这就是技术的工作方式。WebAssembly 确实是一个机会，可以用有趣的方式让旧的东西变新，以解决新的问题。”

我们总是很容易找到这样的人——比如一些运营和安全人员——他们认为让开发人员能够更多、更容易地使用 PaaS 替代方案来创建和部署应用程序不是一个好主意。事实上，反对 PaaS 不可避免地不可行的观点已经存在，我期待着在未来了解这一点。与此同时，PaaS 似乎不会获得通过，但应该很容易被采用。

沃尔克说:“放任开发人员发展和给他们足够的自由以最有效的方式充分表达他们的创造力之间有一条细微的界限。”“但我相信，Cosmonic 和 Fermyon 都可以集成到企业软件供应链中，为 DevOps 提供行使适当治理级别所需的控制。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>