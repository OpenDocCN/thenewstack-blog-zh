# Pivotal 应用程序服务解决了 Kubernetes 的复杂性

> 原文：<https://thenewstack.io/the-pivotal-application-service-addresses-kubernetes-complexity/>

仅仅提到 Kubernetes 可能会带来自动化和可伸缩性的想法，但是对于那些密切使用容器编排工具的人来说，配置和部署的复杂性也可能跃居首位。对于 Pivotal 来说，管理和抽象出这些复杂性是游戏的名称，该公司已经发布了几个新的工具，为其客户带来 Kubernetes 的好处，而无需处理固有的复杂性。

本周，Pivotal 在 Kubernetes 上发布了 Pivotal 应用服务(PAS)的 alpha 版本。PAS 基于开源云应用平台 Cloud Foundry，并提供了云、开发人员框架和应用服务的选择，使构建、测试、部署和扩展应用变得更快、更容易。

此外，Pivotal 还为 Kubernetes 发布了 Pivotal Build 服务的 alpha 版本和 RabbitMQ 开源消息代理软件的 alpha 版本，根据一份声明，“自动化了 RabbitMQ 的部署和持续运营，为开发人员提供了自助服务和可配置的体验”。这些新特性与 PAS 旗下的 [Pivotal Spring Runtime](https://content.pivotal.io/blog/introducing-pivotal-spring-runtime-full-support-for-openjdk-spring-framework-and-apache-tomcat) 和 [Pivotal Service Mesh](https://content.pivotal.io/blog/simplified-platform-networking-with-pivotal-service-mesh-powered-by-istio-and-envoy) 的 alpha 版本一起加入。

在接受新堆栈采访时，Pivotal 云研发高级副总裁 [Onsi Fakhouri](https://pivotal.io/team/fakhouri) 解释了这些功能如何共同帮助 Pivotal 客户。

“在过去的几年里，我们从客户那里听到的最大需求之一是企业级 Kubernetes，因此我们一直在扩展在 PAS 上运行的应用程序的类型，”Fakhouri 说。“传递 Kubernetes 将为 Kubernetes 带来强大的成熟的 Cloud Foundry 推送体验，我们的许多客户和他们的开发人员已经爱上了这种体验，这使得开发人员只需专注于他们的代码，并让我们管理运行代码和操作代码的所有复杂性，变得非常容易和简单。”

在一份声明中，Pivotal 将 Pivotal Build Service 描述为“为开发人员轻松创建容器映像提供自动化，同时为企业提供必要的审计和安全控制，以便放心地大规模运行。”Fakhouri 详细阐述了这一想法，指出它意味着从头到尾处理所有事情。

“许多组织都试图让他们的开发人员能够在 Kubernetes 上运行他们的工作负载，而我们的许多客户向我们询问的一个基本问题是‘我们如何大规模管理这个问题？’整个软件供应链问题正在成为一件非常令人生畏和复杂的事情。“Pivotal Build 服务就是为了解决这一问题而构建的，它利用了我们已经拥有的大量技术，这些技术以云原生构建包的形式出现在今天的 PAS 中，”Fakhouri 说。Pivotal Build Service 采用了 PAS 真正强大的关键组件之一——获取源代码并将其转换为运行中的工件的能力，该工件具有所有的依赖项、操作系统，一切都捆绑在一起，易于更新、审计等——并将其作为独立产品提供给 Kubernetes。"

目前，除了 Pivotal Spring 运行时之外，所有这些特性都可以在 alpha 中获得，这意味着它可以提供给精选的客户，尽管也对那些希望尝试它们的人开放。

Fakhouri 说，最后，所有这些特性都归结为一个统一的理念:管理复杂性。

“整个生态系统的发展速度非常快，对于我们的客户来说，要知道他们应该在何时、何地以及如何使用哪一部分，确实是一项挑战，令人望而生畏。我们想做的是真正帮助策划最好的，同时管理复杂性，这样我们的客户就不必这样做了。”

Pivotal 是新堆栈的赞助商。

图片由来自 Pixabay 的 Erich Westendarp 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>