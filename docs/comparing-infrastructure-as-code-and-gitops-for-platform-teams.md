# 为平台团队比较基础设施即代码和 GitOps

> 原文：<https://thenewstack.io/comparing-infrastructure-as-code-and-gitops-for-platform-teams/>

Kubernetes 为寻找加速开发管道的平台团队提供了许多好处。但是，随着 Kubernetes 变得更加动态和复杂，它可能会带来一些挑战，包括代码部署的频率，持续扩展集群以跟上新应用程序和功能的需要，以及跨开发、测试和生产操作多个集群带来的其他复杂性。

 [克里夫·马尔姆堡

Cliff 是 Rafay Systems 的高级产品营销经理，他是一位富有活力的产品营销领导者，拥有超过 15 年的经验。他热衷于讲述故事和将复杂的产品带入生活，并拥有成功颠覆行业的上市历史。](https://www.linkedin.com/in/cliffmalmborg/) 

手动完成这项任务非常困难，如果不是不可能的话，需要大型平台和开发团队投入数百小时的工作。随着 Kubernetes 规模的扩大，人为错误的机会也会增加，网络攻击和其他安全问题的机会也会变得越来越普遍。

尝试手动管理基础架构配置需求可能会导致灾难，需要大量的管理时间，并会引入难以排除的配置错误。更令人担忧的是，错误配置会导致安全漏洞，从而招致网络攻击。

减少这种手动工作量并降低出错风险和安全问题的最佳方法是什么？自动化。自动化是确保 Kubernetes 为平台团队工作的最有效的方法之一，它减少了人工干预过程，使开发更加安全和有效。

在本文中，我们将探讨基础设施即代码(IaC)的概念如何应对 Kubernetes 中的扩展挑战，并讨论 IaC 和 GitOps 之间的差异。

## **基础设施代码 101**

通过 IaC，配置文件被设置为包含基础设施规范，这意味着配置文件自动提供和管理初始基础设施，这是创建稳定和安全的应用程序的关键步骤。

使用 IaC，每次代码运行时，它都会指定确切的基础结构配置，每次都有完全相同的结果。这意味着每个环境的创建——开发、生产和测试——都很容易版本化、测试和重复。

这种方法的流行导致了大量工具和平台的产生，以帮助支持 IaC。厨师，木偶，Ansible 和 Terraform 是一些常用的工具。

那么，当采用 IaC 方法时，平台团队意识到了什么好处呢？第一个是过程的加速。通过自动化创建基础架构，减少了生产时间，同时降低了出错的可能性。实现 IaC 的平台团队还享有更高的可重用性，因为 IaC 配置文件可以作为未来需求的剧本。IaC 还通过稳定和可预测的结果提供了更高的一致性。因此，配置更容易跟踪和审计，这有助于增加机构知识。最后，当意外发生时，实现 IaC 的平台团队准备得更充分。当一个崩溃或失败的环境发生时，IaC 允许团队快速有效地启动并更快更有效地运行。

## **探索 GitOps**

GitOps 和 IaC 不是相互竞争的想法。事实上，GitOps 仅仅是建立在 IaC 的思想之上，通过整合诸如 git 存储库、合并请求和持续集成/持续部署(CI/CD)之类的功能来帮助将开发和基础设施整合到一个内聚的过程中。

通过利用 GitOps 和 IaC，平台团队可以对他们的基础设施配置和软件代码使用相同的方法。结果呢？更有效的全面协作。GitOps 还将 git 定位为基础设施和应用程序的焦点——因为 GitOps 是一个单点，所以它增强了标准化、安全性和生产能力。

## **平台团队如何实施 gitop**

这是一个平台团队如何利用 GitOps 的示例:

首先，编写一个概述基础设施配置的 YAML 文件，并将其存储在正确的 git 存储库中。这样做将有助于跟踪版本以及增强团队协作。

第二，执行一个拉/合并请求，以确保任何必要的协作和/或批准发生。在这个阶段，任何审查和测试都应该在部署到生产环境之前进行。

第三步有两种方法。在此步骤中，通过 CI/CD 管道启动部署。使用推送部署，该部署将使用 CI/CD 管道通过 git 操作或手动触发来触发作业。作为第二种选择，拉部署将利用源基础设施上的代理来监控 git 存储库中的状态，并确保准确地应用了更改。就 GitOps 而言，基于拉的部署通常更受青睐，因为它们更安全、更主动。

## **结论**

GitOps 和 IaC 是两种方法，当它们一起使用时，可以创建一个强大的端到端解决方案来利用开发管道中的自动化，并且在 Kubernetes 中使用时特别有效。随着 Kubernetes 的扩展，平台团队面临着越来越多的复杂性。采用 IaC 和 GitOps 可以减少错误，提高安全性，并有助于交付更好的应用程序。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>