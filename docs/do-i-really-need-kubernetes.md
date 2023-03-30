# 我真的需要 Kubernetes 吗？

> 原文：<https://thenewstack.io/do-i-really-need-kubernetes/>

[](https://www.linkedin.com/in/powellronald/)

 [罗恩·鲍威尔

罗恩拥有空间物理学背景，曾作为卡西尼小组成员分析土星磁层中的等离子体。他现在在加州旧金山的 CircleCI 公司工作，作为一名开发人员，倡导开发内容，使开发人员能够更快地构建、测试和部署他们的项目。此前，他是美国三星电子公司的开发人员，专门从事 360 度视频制作和虚拟现实硬件、可穿戴设备和物联网应用的开发。](https://www.linkedin.com/in/powellronald/) [](https://www.linkedin.com/in/powellronald/)

如果你关注科技新闻，你会发现 Kubernetes 似乎无处不在。它变得非常受欢迎。事实上，如果开发人员和 DevOps 团队不使用 Kubernetes，他们可能会觉得他们的应用程序开发管道已经过时。

Kubernetes 是一个用于容器化应用程序的编排工具。从 Docker 容器集合开始，Kubernetes 可以控制云应用和微服务的资源分配和流量管理。

因此，它简化了运行面向服务的应用程序基础设施的许多方面。与现代的[持续集成](https://circleci.com/continuous-integration/?utm_medium=content&utm_source=thenewstack&utm_campaign=content-thenewstack-content-2021q3---blogK8s)和持续部署(CI/CD)工具一起，Kubernetes 为扩展这些应用程序提供了基础，而无需大量的工程工作。

使用 Kubernetes 管理云和混合云环境令人兴奋不已。它*是*一个伟大的工具。但是团队经常追逐炒作，过早地转移到 Kubernetes，有时会花费大量的时间、金钱和开发人员的挫折感。

在这篇文章中，我们将试着超越炒作，帮助你回答这个问题:**我真的需要 Kubernetes 吗？**

## Kubernetes 到底是做什么的？

Kubernetes 是一个用于容器化应用程序的编排工具。它负责:

*   部署图像和容器
*   管理容器和集群的扩展
*   资源平衡容器和集群
*   服务的流量管理

当您的应用程序由运行在不同容器中的多个服务组成时，Kubernetes 确实大放异彩。对于具有静态用户基础的单一应用程序来说，这可能是非常必要的。

构建、测试和交付应用程序到容器注册中心的任务不是 Kubernetes 的一部分。这里，用于构建和测试应用程序的 CI/CD 工具完成了这项工作。Kubernetes 作为 [CI/CD 管道](https://circleci.com/blog/what-is-a-ci-cd-pipeline/?utm_medium=content&utm_source=thenewstack&utm_campaign=content-thenewstack-content-2021q3---blogK8s)的一部分，可以帮助您在不停机的情况下将变更部署到生产中。

## 改善你的独石

大多数应用程序都是从整体开始的，这很棒！将整个应用程序放在一个地方，可以快速轻松地进行和部署更改。但是如果你的应用获得成功并成长，你很快就需要找到扩展它的方法。

这是否意味着是时候做 Kubernetes 了？大概不会。

人们很容易认为只有通过 Kubernetes 编排的微服务才能扩展——你会在互联网上读到很多这样的内容。但是扩展通常更多的是关于应用程序的内部，而不是高级架构和工具。例如，您可以通过部署带有支持亲缘标志的负载平衡器的多个实例来扩展 monolith。

**在扩展应用程序时，要考虑的第一个实际步骤是** [**测试驱动开发**](https://circleci.com/blog/how-to-test-software-part-ii-tdd-and-bdd/?utm_medium=content&utm_source=thenewstack&utm_campaign=content-thenewstack-content-2021q3---blogK8s)**【TDD】**，这可以确保质量，并在应用程序增长时防止缺陷。虽然更小的模块或服务更容易测试，模块化也意味着增加对[模仿](https://circleci.com/blog/how-to-test-software-part-i-mocking-stubbing-and-contract-testing/?utm_medium=content&utm_source=thenewstack&utm_campaign=content-thenewstack-content-2021q3---blogK8s)的需求，以及配置和维护的额外工具。良好的测试使构建和扩展您的应用程序变得更加容易。

当您开始向外扩展 monolith 时，像 Chef 和 Ansible 这样的配置管理工具就派上了用场。您可以使用它们来自动配置新的服务器，以确保它们可以运行您的应用程序。您甚至可以更进一步，使用像 [Terraform](https://www.terraform.io/) 这样的工具来帮助配置新的服务器虚拟机，这样您就不必手动创建它们了。

当应用程序的其他部分成为瓶颈时，例如数据库，你也可以扩展它们。各种模式允许应用程序进行扩展，尽管从设计上来说，它们的可扩展性不是很好。例如，如果您的数据库成为瓶颈，您可以将频繁访问的数据移动到高性能的内存数据存储中，如 Redis，以减少数据库的负载。

无论您使用什么配置管理和供应工具，良好的 CI/CD 管道都是必不可少的。第一次部署应用时，你可能已经通过 FTP 将一个. zip 文件复制到了你的服务器上，但是这种方法不能*扩展。简化的 CI/CD 管道确保您的应用程序自动构建、测试和部署，无需您或您的团队做任何额外的工作。*

总之，如果你*最终需要 Kubernetes，这些做法会让你的生活更轻松。*

您甚至可以使用云服务(如 AWS Elastic Beanstalk、Google App Engine 或 Azure App Service)自动扩展整体应用程序。这些都比 Kubernetes 带来了少得多的管理开销，并且它们都可以很好地与 CI/CD 工具配合使用。

**开发新的应用程序时，专注于开发尽可能好的应用程序。**最终，像 Kubernetes 这样的复杂工具可能是管理应用基础设施的正确解决方案。然而，随着你的成长，我们刚刚讨论的许多实践将更加实用。

## 扩大你的巨石

随着您的应用程序继续增长，您最终会到达一个点，在这个点上继续添加内容似乎是站不住脚的。这通常是因为应用程序接近单个开发团队所能完成的极限。

在这一点上，许多团队选择拆分他们的整体，完全进入微服务。虽然这是一个相当受欢迎的决定，但它既不是必要的，也不是灵丹妙药。**考虑从增加服务开始，扩大你的整体，而不是取代它。**这些支持服务中的一些实际上可能是*微服务，因此您可以从使用小型服务中受益，同时仍然利用您的 monolith 的优势。*

即使在介绍服务和微服务时，你也可能不需要或不想从 Kubernetes 开始。Kubernetes 擅长运行和扩展相关服务和微服务容器。然而，最初采用 Kubernetes 有一些容易被忽视的方面。例如，Kubernetes 不包括用于保护 pod、节点和集群的强大内置工具，并且在多云环境中部署 Kubernetes 集群会增加很多复杂性。

从像 Azure Service Fabric 和 AWS Fargate 这样的单一云平台开始可能会更容易启动和扩展服务，而不会强迫您管理 Kubernetes 集群。

另一个选择是完全避免有维护开销的服务，选择功能即服务 (FaaS)，比如 AWS Lambda 或 Azure 功能。当向应用程序添加服务时，FaaS 是最小化潜在基础设施开销的一个好方法。此外，Kubernetes 编排的集群——如果您最终需要的话——可以通过 FaaS 功能得到增强。从混合服务和功能开始，迁移到 Kubernetes 并没有听起来那么复杂。

## 不再有巨石

现在想象一下，你原来的单片应用程序已经增长到你几乎看不到原来的单片了。

它的需求和它的用户群增长得如此之快，以至于你现在有各种各样的助手服务，其中许多服务需要相互交流。您需要确保相互依赖的服务总是在运行，并且彼此可见。

此外，您的客户对正常运行时间和可靠性的要求使您考虑跨多个可用性区域运行，甚至可能跨多个云供应商。

**在这一点上，你可能需要一个像库伯内特这样的管弦乐手。**它让您可以轻松定义相关服务的模块(pod ),并让您自动扩展它们以及在它们之间实现负载平衡。

要使 Kubernetes 发挥作用，需要满足以下条件:

*   您愿意操作几台虚拟机
*   你可以派人去做 Kubernetes 的配置和维护
*   你有不止一个服务要照顾
*   您需要(尽可能)自动化一个几乎同质的服务部署
*   您需要与云(或托管)提供商无关

此外，Kubernetes 内置了对高可用性(Amazon RDS Multi-AZ)部署的支持，这使得提高应用程序的可靠性和可用性变得更加容易。当然，这确实会增加开销:创建和管理集群、定义 pods 以及创建适合部署到 Kubernetes 的容器化应用程序需要时间和工程资源。但是如果你的应用足够大，可以从 Kubernetes 中受益，那么管理开销是值得的。

## 结论

**Kubernetes 功能强大，但这并不意味着它是每个团队和每个应用的正确选择。**与任何一项技术一样，它是为解决某一系列问题而设计的。如果你没有面对 Kubernetes 旨在解决的问题，那就太麻烦了。

不要只是在你的基础设施工具箱中给 Kubernetes 一个位置。让 Kubernetes 赢得它。尤其是在一个新应用程序的开始。

首先，使用可用的工具来快速发布应用程序。当您的应用程序到达部署和扩展成为一项独立工作的阶段时，开始考虑编排是有意义的——很自然地，Kubernetes 成为您的编排工具。一旦您准备好了，请查看【Kubernetes 入门:如何设置您的第一个集群。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>