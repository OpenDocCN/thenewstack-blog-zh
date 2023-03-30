# Knative 申请加入 CNCF 的 Kubernetes 社区

> 原文：<https://thenewstack.io/knative-applies-to-join-kubernetes-community-at-cncf/>

Google 已经向云本地计算基金会(CNCF)提交了 Knative，作为一个孵化项目进行考虑，该项目开始向行业领导的组织捐赠 Knative 商标、知识产权和代码。

这一举措是将 Kubernetes 最有价值的附加软件之一与支持 Kubernetes 的社区联系起来的一大进步。搬到 CNCF 可能会引发更多的参与，因为它从谷歌主导的项目过渡到行业主导的项目。即便如此，已经有很多[对 Knative 做出了贡献](https://knative.teststats.cncf.io/d/5/companies-table?orgId=1&var-period_name=Last%202%20years&var-metric=contributions)，包括 Red Hat、IBM、VMware、SAP 和 TriggerMesh。

## **Kubernetes + Knative = 3**

 [马克·辛克尔

Mark 在新兴技术和开源领域有着悠久的历史。在共同创立 TriggerMesh 之前，他是 Node.js 基金会的执行董事，也是 Citrix、Cloud.com 和 Zenoss 的高管，在那里他领导了开源项目。](https://www.linkedin.com/in/markrhinkle/) 

Knative 是在 Kubernetes 上提供开发环境的最佳方式之一，它使云原生开发人员更加高效。与单独使用 Kubernetes 相比，开发人员可以获得更快的部署。它为构建开发、测试和部署的无服务器体验提供了一个框架。

云原生开发人员可以使用 Knative 更快地部署代码，而不必担心扩展或花费时间设置 Kubernetes 网络路由。此外，组织可以创建他们的无服务器环境以及容器化的应用程序，为企业最大限度地利用他们自己的环境提供了一种方法，然后决定何时以及是否迁移到云。

Knative 以可重用组件的形式为 Kubernetes 带来了很多东西，旨在自动化日常操作。Knative 可以将应用从源代码部署到容器中，使用现代入口网关在服务之间路由流量，在需求增加或减少时扩展资源，并将事件流转发给任意数量的云提供商。此外，对开发人员的限制很少，他们可以使用他们最喜欢的编程语言或框架。

批评者指出，Kubernetes 有一个陡峭的学习曲线，尤其是对开发人员来说。但是 Knative 提供了一种无服务器的方法，大大降低了开发和部署代码的人成为 Kubernetes 专家的需求。运营商可以获得一致的容器管理，并在必要时灵活部署任何映像。

谷歌云平台的著名云倡导者凯尔西·海塔尔说:“如果 Kubernetes 是一个电网，那么 Knative 就是它的电灯开关。”Knative 通过提供一种构建松散耦合的微服务的方式，提供了对复杂系统的更好控制，这些微服务被部署为无服务器功能，而不是单片应用程序。此外，这些微服务可以由云或私有数据中心中几乎任何系统中的活动驱动。

## **Knative 在私有数据中心的优势**

使用 Knative，公共云功能即服务提供商(如 Amazon Lambda 和 Google Cloud Run)的常见优势也可以转化为私有数据中心的用户。公共云中的无服务器平台基于触发器处理负载和执行功能。对函数实例数量的唯一硬性限制是云的容量。

理论上，无服务器部署是无限的，但其成本也是无限的。如果发生太多功能触发事件，成本会急剧增加。拥有现有基础设施投资的企业想要可预测的成本或以极端规模运营，[如 DropBox](https://a16z.com/2021/05/27/cost-of-cloud-paradox-market-cap-cloud-lifecycle-scale-growth-repatriation-optimization/) ，可以使用 Kubernetes 和 Knative 运行他们的云原生基础设施。

在 Kubernetes 中，服务为运行时的应用程序部署提供了一个抽象。开发人员部署他们的代码，而不必担心他们是在亚马逊 EC2 实例、谷歌计算引擎还是在私有数据中心的裸机 Kubernetes 中运行。不使用时，它们可以缩小到零。Knative 简化了管理容器化应用程序所需的 Kubernetes 组件，并提供了简单的方法来扩展和缩减应用程序实例，而无需管理任何底层基础设施。

Knative Eventing 是 Knative 中一个不太为人所知的组件，用于构建事件驱动的架构。通过松散耦合的关系，应用程序可以对整个企业中的事件采取行动。Knative 符合 CNCF [CloudEvents 规范](https://cloudevents.io/)，该规范允许任何语言创建、发送事件并与之交互。因此，您可以快速开发应用程序来响应其他系统中的事件。

Knative 不知道 Kubernetes 的分布，只要它是一致的。它也不知道是部署在云中还是内部数据中心。在最近的一篇[文章中，](https://www.lastweekinaws.com/blog/the-unfulfilled-promise-of-serverless/)提到了 AWS 云经济学家[科里·奎因](https://twitter.com/QuinnyPig)断言“无服务器的未实现承诺”，指出无服务器，特别是 AWS Lambda 的部分问题是缺乏可移植性。通过让你的目标成为 Kubernetes 而不是单一的云提供商，你可以解决这个问题。

Knative 是可组合基础设施新时代中堆栈中有价值部分的一个理想例子。您可以选择在私有数据中心和云提供商的各种组合中运行的开源和企业软件的组合，而不是购买完整的堆栈。您可以免费或通过企业订阅(Rancher、VMware 或 Red Hat OpenShift)或通过云提供商使用 Kubernetes。你也可以为 Knative 选择一个供应商，例如 [VMware](https://tanzu.vmware.com/tanzu) 或 [TriggerMesh](https://www.triggermesh.com/compare-triggermesh-editions) 。不过，如果您决定在使用商业产品的同时使用开源软件，您可以在云中或内部维护您的基础设施。

## **开源**

Knative 一直是开放的，但它搬到 CNCF，凭借其以公司中立的方式运行开源项目的经验，将使 Knative 成为无服务器项目真正的行业主导选择。

开源是一种无处不在的方式来交付今天的云原生和基础设施软件，从 Linux 和 Kubernetes 到软件栈几乎每个级别的解决方案。然而，你不应该仅仅因为开源是免费的就选择它；许可费用，或者没有许可费用，是一个转移注意力的话题。真正的机会是以你选择的方式自由地使用软件，如果你愿意，可以修改它。

许多基础设施企业软件供应商提供商业和开源产品，让企业选择最符合其需求的解决方案。在云中尤其如此，因为 Confluent (Apache Kafka)、Elastic、Kong、MongoDB 和除 Knative 之外的其他软件都是作为开源或企业订阅提供的。

开源软件提供了许多优势，包括使开发人员能够审查代码和添加重要功能，而无需依赖第三方公司来修改软件以满足您部门的需求。此外，它提供了一种在透明、开放的论坛中进行大规模协作的方式，这种方式通常比传统的商业现成软件进行得更快；在云中，事情通常进展得更快。

## **Knative 的未来，企业拥有的事件驱动架构**

虚拟化已经成为共享基础架构的基础，从存储虚拟化到使用 Xen、KVM 和 VMware 的服务器的硬件虚拟化。基础架构即服务(IaaS)很常见，并通过虚拟化实现。有一段时间，像 CloudFoundry 和 AWS Elastic Beanstalk 这样的平台即服务(PaaS)风靡一时。甚至流行的容器技术 Docker 也是从一家 PaaS 公司 DotCloud 产生的，后来更名为 Docker Inc .然而，容器似乎是应用层的正确抽象级别，并将持续相当长的一段时间。

容器(持久和短暂的无服务器部署)确实为解耦服务提供了构建块，以构建云原生应用程序。此外，容器可以是事件驱动架构的一部分，事件驱动架构由提供实时数据流的事件组成，以创建系统间的集成。

在 TriggerMesh，我们是 Knative 开发社区的用户和成员。因此，我们看到了 Knative Serving 提供 FaaS 和 Knative Eventing 构建事件驱动应用程序的强大功能。我们使用 Knative eventing 的方式与 AWS Event Bridge 用作无服务器事件总线来触发 AWS Lambdas 和其他 AWS 目标的方式非常相似。我们还倡导开源，并于 10 月在 KubeCon 发布了 [TriggerMesh 云原生集成平台](https://github.com/triggermesh/triggermesh)，为 Kubernetes 提供我们希望成为事实上的事件驱动集成平台。

当您评估您的基础架构选项时，Knative 和 Kubernetes 是一个强大的组合，有助于构建事件驱动的开放源代码、灵活的基础架构，并为您的云原生计划提供坚实的基础。因此，运营商可以从可靠、易于维护的云原生平台中受益，而开发人员可以为他们的无服务器应用提供快速部署环境。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>