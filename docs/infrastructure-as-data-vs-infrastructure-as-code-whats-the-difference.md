# 作为数据的基础架构与作为代码的基础架构:有什么区别？

> 原文：<https://thenewstack.io/infrastructure-as-data-vs-infrastructure-as-code-whats-the-difference/>

Kubernetes 带来的最大挑战之一是在不同的云和内部环境中部署[微服务](https://thenewstack.io/category/microservices/)和应用。

正如后端开发人员和运营团队第一手了解的那样，配置和管理不同的环境仍然主要是一个手动过程，不仅对于主要的应用程序部署，而且对于任何代码、应用程序、微服务、安全或任何其他更新都是如此。

因此，为了减轻运营和后端开发人员的负担，简化和自动化这一过程是重中之重。

最终，团队应该能够通过单一界面在多云环境、Kubernetes 集群和内部环境中无缝、轻松地部署应用、微服务或更新。对于运营工程师来说，这将是多云和云原生计算的圣杯。

最近，VMware 工程师推出了由 SaltStack 创始人兼首席技术官 Tom Hatch 领导的开源[基础设施即数据项目](https://learnidem.github.io/)，以帮助实现这一目标。

由此产生的开源工具旨在减少与将每个云部署和 API 的大量代码库编排成一种由数据组成的格式相关的巨大复杂性，项目创建者表示，这种数据可以容易地理解和管理。

它的创造者说，Idem 代表云配置的基础设施即数据(IaD ),因为它将云配置简化为数据。它旨在使云配置变得更易于配置和管理应用程序部署。

但在许多方面，Idem 的创造者希望达到的最终结果与 Red Hat 的 Ansible 据称为 IaD 提供的结果非常相似。Ansible 的创造者[Michael de Haan 在 2013 年](http://radar.oreilly.com/2013/08/the-rise-of-infrastructure-as-data.html)为 [O'Reilly 的 Radar](https://www.oreilly.com/radar/) 写道，IaD 不是将基础设施建模为代码(IaC)或 GUI，而是基于“基于文本、中间地带和数据驱动的策略”。

“我称之为‘基础设施即数据’——用简单的机器可读数据格式描述你的系统是什么样子，”德哈恩写道。“让程序执行这些数据格式，并确保您的基础架构与之匹配。结果是，配置可以是灵活的，并且易于原型化、易于审计和易于维护。”

此外，还有基础架构作为多云和多环境供应的代码。凭借 HashiCorp 的开源[terra form](https://www.terraform.io/)——目前已有数百万个使用案例，是领先的 IaC 平台——以及 Idem 与之直接竞争的相关 HashiCorp 产品，许多用户已经依赖 IaC 在多云和内部数据中心环境中供应和管理应用。

从高层次来看，VMware 的 Idem 和 Ansible 以及 Terraform 主导的 Infrastructure-as-Code 等基础架构即数据工具旨在帮助 DevOps 团队实现简化和自动化跨多云和不同环境的应用部署的目标，同时帮助减少手动配置和流程。

在这里，我们将探讨 IaD 和 IaC 的比较，以及它们在某些情况下如何互补。

## 数据解决的基础设施挑战

[DevOps](https://thenewstack.io/category/devops/) 团队继续面临降低供应多个云环境的复杂性的挑战。

“特定于代码库的 [CI/CD](https://thenewstack.io/category/ci-cd/) 管道的特征与[云原生](https://thenewstack.io/category/cloud-native/)应用开发的不变原则相冲突。DevOps 工具链的每个组件都构成了一个潜在的集成点，需要设置、初始配置和管理，”[Enterprise Management Associates 的分析师 Torsten Volk](https://www.linkedin.com/in/torstenvolk/) 告诉新堆栈。

“这就是为什么我们需要特定于云的基础设施工程师团队来找出如何在 AWS、Azure、GCP 等平台上创建最佳的特定于应用的环境。”

哈奇说，就采用率而言，Terraform“目前拥有市场”。“当然，与 Terraform 竞争是一座需要攀登的大山，”他补充道，但将基础设施用作代码与将基础设施用作数据之间存在巨大差异。

他说，当云架构需要用代码来表达时，“你只是在编写越来越多、越来越多的 Terraform”。“Idem 与您通常将基础架构视为代码的方式不同，一切都可以归结为这些可预测的数据集。”

“不要坐下来说，‘我要用 Terraform 写出一个云’，你可以将 Idem 指向你的云，它会自动生成所有数据、所有代码和运行时，以强制它保持当前状态。”

同时，Idem 以及 [Ansible](https://thenewstack.io/how-to-deploy-a-container-using-ansible/) 在一定程度上被设计成使云供应更加自动化和易于管理。

“虽然这听起来像魔术，但 Idem 确实解决了许多 Terraform 用户，开源和商业用户所表达的问题，”Volk 说。

“将传统基础架构编写为任何类型的代码都会不自觉地导致基础架构代码层层叠加，需要不断调整才能跟上云 API 的变化、不断变化的应用程序要求以及整体业务环境的变化。”

## 改进基础设施即代码工具

与此同时， [HashiCorp](https://www.hashicorp.com/?utm_content=inline-mention) 通过 Terraform 的每个后续版本及其提供的相关工具，继续完善和改进基础设施即代码。Terraform 的关键特征是 HashiCorp 声称的任何 IT 基础设施的可扩展性。

根据 HashiCorp 的定义，IaC 也是 Terraform 中“基础设施自动化”的一个组成部分，目的是:

1.  采用基础设施作为代码。
2.  为 IaC 的组合、协作和重用构建工作流。
3.  根据安全性、合规性和管理要求标准化工作流。
4.  通过自助服务基础架构选项为最终用户应用程序开发人员和交付团队提供创新。

“Terraform 在基础设施层工作，基础设施即代码是提供自动化的最佳方式，可以从任何云平台、私有数据中心等提供任何基础设施。“[hashi corp 产品营销高级总监 Meghan Liese](https://www.linkedin.com/in/meghanliese) 告诉 New Stack。

“Terraform 实际上是指运营商能够定义需要供应的基础设施，以便开发人员能够以自助服务模式使用这些基础设施。因此，在另一层，像 [Waypoint](https://www.waypointproject.io/) 这样的工具说，“嘿，开发者，你编写你的应用需求，然后通过 Waypoint 运行，Waypoint 将自助服务平台，”

IaC 和 IaD 的使用方式可能会有重叠。Liese 没有具体评论 Idem，但表示，在使用基础设施即数据在多个环境中提供基础设施时，使用 Ansible 可以补充 Terraform。

“Ansible 和 Terraform 的创建者看到组织有很多相同的问题，但我们也合作得很好。Liese 说:“我们与使用 Terraform 铺设基础设施的组织合作，Ansible 多次配置机器。“因此，随着市场的不断成熟，这些工具可能会提供一些重叠的功能，这就是其中之一。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>