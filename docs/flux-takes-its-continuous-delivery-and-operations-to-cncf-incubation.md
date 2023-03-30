# Flux 将其持续交付和运营交给 CNCF 孵化器

> 原文：<https://thenewstack.io/flux-takes-its-continuous-delivery-and-operations-to-cncf-incubation/>

[Flux 项目](https://fluxcd.io/)已经转移到云计算原生计算基金会(CNCF)的孵化层，将其独特的持续交付形式带入该基金会的第二层项目成熟度。自 2019 年 8 月加入 CNCF 以来，Flux 已经增加了 7 个维护者，并在超过 80 个生产组织中增加了采用，同时致力于对应用程序进行完整的重构，以更松散地耦合组成 Flux 的各种工具。

虽然 Flux 将自己标榜为持续交付工具，但它也颠覆了持续交付的传统定义，Flux 的创建者和维护者 [Michael Bridgen](https://github.com/squaremo) 称 Flux 是“产生‘GitOps’的项目”简而言之，GitOps 是一个范例，其中运营和基础设施包含在持续集成和交付(CI/CD)流程中。

传统上，CI/CD 是作为一个线性过程存在的，当一个事件发生时，启动一个管道作为响应，并随着软件向基础设施的交付而终止。对许多人来说，这个事件是开发人员提交代码，然后启动构建过程，以容器部署到 Kubernetes 结束。但是，当部署软件的基础设施发生变化时，会发生什么呢？Flux 解决了这个问题，它不仅在集成过程中响应事件，而且在通常线性过程的另一端，当基础设施发生变化时也协调构建。

[Weaveworks](https://www.weave.works/) 首席技术官 [Cornelia Davis](https://www.linkedin.com/in/corneliadavis) 称赞 Kubernetes 通过其声明式模型真正改变了这一范式，Flux 同样也实践了一种基于协调的持续交付和运营形式。

“Kubernetes 真正普及了“你永远不会结束”的观念。事情不是因为某个事件而完成的，就像有人将某些东西签入 Git 存储库，但是事情一直在变化，您必须不断地对这些变化做出响应。可能是有人将某些内容签入了存储库，也可能是基础架构中的某些内容发生了变化，现在您对运行环境的交付需要进行调整，”Davis 解释道。“对 Flux 来说，有一点改变游戏规则的事情是这种基于协调的持续交付方式的概念。Flux 真正改变了这种围绕连续交付的想法，它是一种协调器。”

最初的 Flux 由一个 monorepo 中的多个工具组成，外加覆盖 Helm gitop 的扩展。最近，这些工具已经被重构为 [GitOps Toolkit](https://toolkit.fluxcd.io/components/ "https://toolkit.fluxcd.io/components/") ，这是一组 API 和控制器，它们在一组可组合的模块中捕获 Flux 的功能。然后，Flux v2 将这些模块组合成一个包，具有与 Flux v1 同等的功能，包括舵功能。此外，Flux 项目现在还包括， [Flagger](https://docs.flagger.app/) ，一个用于 Kubernetes 的渐进式交付工具。戴维斯说，Flux v2 的功能与 v1 相当，只是“少了一些我们不赞成的小东西，因为如果你那样做，最终会伤害到你自己。”

Davis 说，在操作上，Flux v2 的主要变化将是如何将 Flux 安装到 Kubernetes 集群中，Flux 现在由一套控制器组成，而不是单个控制器。服务的这种松散耦合将允许更高级别的配置，尤其是对于那些大规模运行 Flux 的服务。在从 v1 迁移到 v2 的过程中，只需要对由 Flux 管理的 Kubernetes 工作负载配置进行最小的更改，Flux 社区已经制作了详细的指南来提供帮助。

“GitOps 正被用作‘大规模’的一个非常重要的使能因素，我所说的‘大规模’并不一定指数百个集群，我指的是数万个或数十万个集群，”Davis 说。“我们看到电信公司正在将 Kubernetes 放在手机信号塔上，我们在 Weaveworks 与相当多的电信公司合作，这些系统可能会更加频繁地接触 Git 存储库。性能可能会受益于松散耦合。”

Flux 还提供了一个 SDK 来创建额外的 Flux 控制器，Davis 说该项目希望包括许多其他项目，超越 Flagger，向前发展。

戴维斯说:“我们现在正在提升 GitOps 管道的概念，在这里，你现在可以将那些基于协调的做事方法组装到这些 GitOps 管道中，从连续交付到运营。“最终将会发生的是，我们将添加额外的控制器，GitOps 控制器将会生成一个控制器生态系统。Flux 本身正在构建一套控制器，以满足连续交付和连续运营的需求，因此您将开始看到一套控制器，以及允许我们将这些控制器连接到这些连续交付和连续运营管道中的工具，我们称之为 GitOps 管道。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>