# 厨师和库伯内特斯:一起更好？

> 原文：<https://thenewstack.io/chef-and-kubernetes-better-together/>

如果你使用 Docker 容器和 Kubernetes，你就不再需要 Chef 了，对吗？

[Joshua Timberman](https://twitter.com/jtimberman) 在他的 [ChefConf 2019](https://chefconf.chef.io/) 关于在 Kubernetes 上运行[传统应用的演讲中提出了这个共同的问题。](https://speakerdeck.com/jtimberman/running-legacy-apps-on-k8s/)

原来这家成立 10 年的公司与 Kubernetes 一起运行着它所谓的“遗产”应用程序。其主要原因是平台的一致性。

“对于所有这些旧的应用程序，我们想要一个可以运行它们的地方…我们有各种不同的工作流…当我们[转向不同的产品]时，我们没有以同样的方式做同样的事情。因此，我们想把它带进来，并与我们的工作流程保持一致，”Chef 的首席运营工程师 Timbermann 解释道。

它还提供了成本效益。它运行 15 个不同的应用程序，每个程序有 4 到 8 个实例。有了 Kubernetes，它只在 9 个节点上运行它们。

与此同时，它仍在运行其基础设施自动化工具 Infra 其应用构建工具 Habitat 和遵从性工具 Inspec。

[https://www.youtube.com/embed/dRYRllo-rBw?feature=oembed](https://www.youtube.com/embed/dRYRllo-rBw?feature=oembed)

视频

根据加拿大 IT 服务公司 Indellientdevo PS 的合伙人兼副总裁 Damith Karunaratne[的说法，问题不是 Chef 在 Kubernetes 的世界中适合什么，而是](https://www.linkedin.com/in/damithkarunaratne/?originalSubdomain=ca)[配置管理](/chefs-adam-jacob-configuration-management-versus-human-element/)的角色是什么。

“如果您正在使用[配置管理工具](https://thenewstack.io/kubernetes-federation-post-configuration-management-universe/)，您将构建大量的编排和 K 语句…并且必须弄清楚如何编排这一切。Habitat 提供了能够做到这一点的结构……集群中所有这些不同的节点以及它们如何相互作用。这真的简化了事情，”他说。

他说，有了配置管理工具，在这些复杂的系统中需要几个月才能管理的东西，用 Habitat 只需要几周。

他说，DevOps 面临的挑战是准备好技术，以便它可以应用到任何地方——本地、任何云或多个云。

“如果你为(不同的部署地点)建造所有这些管道，你会到达一个非常难以管理的地步，”他说。“在那里，厨师正在用‘栖息地’做一些真正好吃的东西。这些决定不需要等到最后才做出。这样您就可以有一条或尽可能少的路径来到达[部署]。”

他说，有了配置管理工具，在这些复杂的系统中需要几个月才能管理的东西，用 Habitat 只需要几周。

您可以从您的云提供商那里获得 Kubernetes，但是云提供商仍然需要这些配置管理工具来配置您的系统，以便为您提供 Kubernetes 无服务器体验。

> Chef 首席执行官 Barry Crist 说:“我认为市场现在正在认识到，拥有 Kubernetes 战略并不等同于拥有 IT 战略。

或者您将拥有自己的数据中心。Kubernetes 仍然需要在虚拟机上运行，并且仍然需要那个级别的配置管理工具。他说，这就是栖息地或配置管理仍将发挥作用的地方。

“有了 Habitat，你可以打包应用程序，然后如果你愿意，你可以将应用程序导出到容器中。…所以我不应该用 Kubernetes 来代替 Chef Habitat，而是我可以一起使用它们来获得最佳[体验]，”他说。

Chef 首席执行官 [Barry Crist](https://www.youtube.com/watch?v=CmLUxCzxq3c) 在一次采访中指出，Kubernetes 不是应用软件，而是基础设施软件。

“我认为市场现在正在认识到的一点是，拥有 Kubernetes 战略并不等同于拥有 IT 战略，”他说。

“我们追求的游戏可能是一个更大的游戏。我们正在研究整个堆栈与整个 IT 问题有什么关系。这些问题有些是遗留问题，有些是基础设施问题，有些是应用程序问题，有些是安全问题。我们希望启用其中的一些元素，并且我们希望与容器和 Kubernetes 很好地合作。…我们在与 Kubernetes 的良好合作中进行了大量投资，尤其是在 Habitat 方面。”

克里斯特说，你应该自下而上构建系统的想法已经过时，应用优先的考虑将是未来。

Chef 产品和工程高级副总裁 [Corey Scobey](https://twitter.com/cscobie_chef?lang=en) 补充道:“当你决定使用 Kubernetes 或 Docker 时，你会意识到拥有一个技术战略或基础设施技术战略……你说的是，“我将以不同的方式对我的计算资源进行微分区”，这很好，会给你带来很多好处。

“但这不会改变您需要解决的宏观 it 问题。最大的 IT 问题之一是“无论生产环境是什么样的，我如何对称地从我的开发环境一直到我的生产环境。”

Scobey 说:“Habitat 对你用什么来构建软件以及在哪里部署软件没有偏见。”。

他说，在一个完美的世界里，你将有一个单一的映像部署到一个容器环境中，然后在其上的所有东西都将是特定于应用程序的。

“你构建的系统越多，用这种构建模式服务的应用程序越多，中间的膨胀就越大。你需要越来越多的东西来服务越来越多的主人，”他说。

“沿着他们的 Kubernetes 道路前进的客户正在发现这一点:他们认为他们将从另一端得到好的精益容器，并且，由于它的多样性和应用程序的多样性，他们得到的容器看起来很像他们以前拥有的服务器。他们又大又胖，而且没有好好打扮。它有很多膨胀，”他说。

Scobey 说:“使用 Kubernetes 和 Habitat 的最大价值之一是，Habitat 打包应用程序的方式迫使你忽略所有那些中间事物，只带来你需要的东西。“你从‘栖息地’得到的是你能想象到的最精简、最简陋的容器。”

他说，Kubernetes 正在显著缩小基础设施的足迹，但“不管你在哪里部署，应用程序打包仍然是你需要解决的问题。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>