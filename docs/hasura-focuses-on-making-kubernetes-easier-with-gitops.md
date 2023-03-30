# Hasura 专注于通过 GitOps 简化 Kubernetes

> 原文：<https://thenewstack.io/hasura-focuses-on-making-kubernetes-easier-with-gitops/>

Kunjan Chauhan 着手减少印度食品供应链中的浪费，并帮助确保街头水果和蔬菜摊贩在购买农产品时获得公平交易。他的公司 [Bompod Solutions](http://www.bompod.com/) ，开发了一种手持[销售点系统](http://www.bompod.io/)，即使是文盲也可以使用。小型物联网设备可以测量蔬菜的重量和账单条目。

但是他的开发者越来越生他的气。

“在开发我的技术之前，我喜欢实地学习。非常迭代。我从来不确定我在建造什么，我一直在改变它。所以我和开发人员的关系变得非常紧张。变革的成本非常高。每次我做出改变，他们都会很不高兴，”他说。

大约一年半前，其中一名开发人员建议使用 [Hasura](https://hasura.io/) 微服务堆栈，旨在帮助对 Docker 和 Kubernetes 缺乏经验的 IT 团队入门。

“我不是搞技术的人；我是个商人。设计对我来说很容易。[设置服务器]，维护服务器，我不需要为此雇佣任何人。因为用 Hasura 维护集群非常非常容易，”他说。

## 使开发更容易

Hasura 的联合创始人 Rajoshi Ghosh 和 Tanmai Gopal 最初打算建立一个食品配送市场。为了节省反复构建相同组件的时间，Gopal 组装了一个名为“Procrust.es”的后端和 DevOps 工具包。这是一个数据库平台，结合了 NoSQL API 的易用性和处理事务的能力。

随着两人在印度 Bengaluru 成立了一个开发机构，该工具包不断发展，最终成为 2017 年 2 月首次亮相的 Hasura 平台。

“我们一开始并不知道最终结果会是什么样。Ghosh 说:“我们最初的想法是让开发变得更容易。

Gopal 说，他们在 GraphQL 问世之前创建了自己的 GraphQL 版本，并最终在 Postgres 之上建立了一个 GraphQL 层，该层自动化了在数据库之上提供 API 的过程，以部署任何类型的代码，而不必为每个应用程序构建底层代码。

Hasura 平台为开发者提供了高性能的数据层(GraphQL 和 JSON)、带有认证中间件的 API 网关和 GitOps automation。

它具有访问控制、高性能和可扩展性。

“我们开发的其他东西有助于加快部署，”Gopal 说。“我们的想法是，你想要那种 Heroku 式的体验，因为它令人惊叹，但你想要那种在企业或大范围内你可以控制的环境中的体验。所以它最终成为了一个 Docker，基于 Kubernetes 的工具。”

这是一个名为 [Gitkube](https://github.com/hasura/gitkube) 的开源项目。

“[它]说，‘嘿，你可以拿一个 Docker 文件，你可以拿一个 Kubernetes YAML 规范，你可以做 git 推送，并获得相同的体验’……我们已经让开发人员更容易、更快地使用它们。这是捆绑在一起的。那就是 Hasura 平台，”Gopal 说。

它计划在接下来的几个月里将所有的 Kubernetes 原生组件开源。

## PaaS+BaaS

他们将 Hasura 描述为 PaaS(平台即服务)加 BaaS(后端即服务),可以让您快速构建和部署。

你[通过创建 Hasura 项目开始](https://blog.hasura.io/how-hasura-works-in-doodles-ba03d6ce6044)，该项目采用微服务来自动化后端任务。几乎没有现成的微服务，如 data、auth 和 filestore，它们可以提供即时后端 API，可以直接在应用程序中使用。用户还可以创建自己的微服务，如 API 服务或 web 应用程序。

Hasura 还提供了特定于语言和用例的初学者工具包，如 Python、data science 或 chatbots，它们消除了编写大量样板代码的需要。

第二步是在云中创建一个 Hasura 集群来托管 Hasura 项目。目前，它支持 DigitalOcean、谷歌云平台、AWS 和微软 Azure，并与部署到其他平台的客户合作。该公司表示，该平台实现了它们之间的自动迁移。

然后，开源工具 Gitkube 使用 git 将您的代码作为容器部署在您的 Hasura 集群上。配置、数据库模式和您的微服务都将通过运行 **git push hasura master** 来部署。

他们称这种方法为 GitOps。Gopal 最近在 KubeCon + CloudNativeCon 2018 欧洲大会上谈到了 git push。

[https://www.youtube.com/embed/gDGT4Gf_4JM?feature=oembed](https://www.youtube.com/embed/gDGT4Gf_4JM?feature=oembed)

视频

“只要一切(基础设施配置、应用程序依赖性、环境配置、有状态迁移、测试)都是声明性的，git 就是开发人员驱动他们的 DevOps 任务所需的唯一工具，”Gopal 在一篇博客文章[中说。](http://vmblog.com/archive/2018/04/19/can-gitops-solve-the-developer-ops-boundary-once-and-for-all.aspx#.Wuw7c9Mvz9A)

他解释说，只使用 git 减少了所需的工具集，并提供了完全的可扩展性:git-hooks 和 webhooks 允许操作员实现无限的定制和工具，而不会影响开发人员的工作流程。

他说，一个学习如何编写 docker 文件和 Kubernetes 基础知识的全栈开发者可以完全控制他们的栈。他们完全可以自己为数百万用户构建、部署、操作和扩展他们的微服务应用。

“这是前所未有的力量。一旦企业内部的人可以使用它，这将改变应用程序构建的动态，”他说。

## CNCF 认证

今年 4 月，这家总部位于旧金山和印度的公司宣布了由 Nexus Venture Partners 和 GREE Ventures 牵头的 160 万美元的种子轮投资。

[Nexus Venture Partners](https://nexusvp.com/) 的董事总经理萨梅尔·布里杰·维尔马当时说:“使用 Hasura 的平台，开发者现在可以在几分钟内创建云原生的、可移植的和‘弹性’的应用程序，而不需要一开始对 Kubernetes 有任何了解。”。

[云本地计算基金会](https://www.cncf.io/)最近在 22 家新的[认证的 Kubernetes 供应商](https://www.cncf.io/certification/software-conformance/)中提名 Hasura。据 Gopal 称，该公司约有 4 万名开发人员。

“通常是开发人员和系统管理员在关注 Kubernetes。但最终，应用程序开发人员将在 Kubernetes 基础上构建应用程序。Ghosh 说:“我们正在加速将 Kubernetes 带给应用开发者的过程。”

“从一家公司的角度来看，从第一天开始，您就有了一个 Kubernetes 集群，它具备了编写应用程序所需的所有自动化功能，并且您可以访问底层。…您可以慢慢获得使用 Kubernetes 的经验，尝试一下，因为您拥有这些层，并且可以使用这些 Kubernetes 命令。”

Chauhan 说，Hasura 与他合作定制功能，例如启用 [Realm](https://realm.io/products/realm-database/) ，这可以帮助你在多个设备之间同步。

他过去不得不审视整个项目，而不是其中的一小部分，因为开发人员不喜欢构建小部分——而且他还不知道自己希望整个项目是什么样的。

“现在我只是向他们展示，‘这就是采购订单格式的样子’，这就是 API 端点。从这里取出数据，放入这个表格。现在是一个非常简单的 API 调用。我可以将一组非常有用的 API 中的每个特性可视化。因此，这有助于我更详细地了解情况，我现在可以在更小的范围内工作。我可以构建很小很小的功能并进行测试，然后将它们集成到项目中。”

云本地计算基金会和 T2 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>