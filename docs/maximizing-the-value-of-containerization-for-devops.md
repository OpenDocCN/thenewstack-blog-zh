# 为 DevOps 实现集装箱化价值最大化

> 原文：<https://thenewstack.io/maximizing-the-value-of-containerization-for-devops/>

[](https://twitter.com/siruslan)

 [鲁斯兰·Synytsky

鲁斯兰·Synytsky 是 Jelastic PaaS 和 Java Champion 的 CEO 和联合创始人。Jelastic 是一家位于加利福尼亚州帕洛阿尔托的公司，为全球的 ISV、MSP 和云托管提供商提供交钥匙的多云平台。Jelastic 平台即服务的核心技术旨在通过全球独立数据中心提供商的分散网络运行和管理数百万个容器。在创建 Jelastic 之前，Ruslan 是乌克兰国家航天局的主要工程领导之一。目前，Ruslan 专注于开发尖端的云解决方案和相关的商业技术。](https://twitter.com/siruslan) [](https://twitter.com/siruslan)

集装箱化越来越受欢迎，这是有原因的。这是一种很好的应用程序打包方式，为自动化 It 供应流程提供了有效的解决方案。容器化可以使 DevOps 团队专注于他们最重要的目标——管理人员准备具有所需依赖和配置的容器；和开发人员进行高效编码，以便快速轻松地部署应用程序。

基于容器的平台即服务解决方案或纯容器即服务实现了自动化以及其他好处，如消除人为错误、加快上市时间和提高资源利用效率。

集装箱化的主要好处包括:

*   与虚拟机相比，应用程序密度高，服务器资源利用率最高。
*   低 TCO 作为系统容器的高级隔离，允许在同一硬件节点上运行不同类型的应用程序。
*   为同一主机上的其他容器重用未消耗的资源。
*   基于当前负载优化内存和 CPU 使用，自动垂直扩展，在更改资源限制时无需重启。

充分利用 DevOps 的容器化需要对几个关键障碍给予深思熟虑的关注，尤其是对于初学者。下面我们将讨论在构建和实施集装箱化策略时应该考虑的一些要点。

## 评估当前项目需求

一开始，DevOps 团队需要仔细评估他们项目的状态，确定迁移到容器的必要条件，并实现这一迁移的长期、持续的好处。

人们经常有这样的误解，认为容器只适合绿地应用(微服务和云原生)。但是单一的和遗留的应用程序也可以通过使用容器来改变和开始新的生活。选择合适的容器类型至关重要。

一个应用程序容器(比如 Docker)可以只运行一个进程。它们通常是新项目的更好选择，因为考虑到微服务模式和现代基础设施设计要求，使用公开可用的 Docker 模板创建所需的映像相当简单。

一个系统容器(如 LXC、OpenVZ 或 Virtuozzo)作为一个完整的操作系统运行，可以运行全功能的单元系统，并在其中生成其他进程。这种类型更适合于单片和遗留应用程序，因为它允许重用在最初的基于 VM 的设计中实现的架构和配置，因此结构将保持大致相同。

## 预测未来的项目需求

在分析程序定义之后，技术人员必须预测未来的需求。随着项目的增长，复杂性将会增加，因此很可能需要一个主要流程的编排和自动化平台。

集装箱化环境的管理既复杂又密集。因此，PaaS 解决方案是支持开发人员并让他们专注于编码的一种有价值的方法。谈到容器编排平台和服务，有无数的选择。决定哪一个最适合特定的组织和应用程序可能是困难的，尤其是当需求快速发展的时候。在选择集装箱化平台时，需要注意以下几点:

*   **灵活性**:该平台应该提供一套多样化的内置工具，以及集成第三方技术的可能性，这样开发者的创新就不会受到阻碍。此外，拥有一个可以根据不断变化的需求进行调整的自动化平台也很重要。
*   **锁定:**许多 PaaS 解决方案都是专有的，因此他们可以将您锁定在一家供应商或基础设施提供商。
*   **云选项:**在云中使用容器化时，您的方法支持公共、私有、混合和[多云](https://jelastic.com/blog/multi-cloud-interoperability/)部署至关重要，因为需求总是在不断扩大。
*   **定价:**选择一个平台，往往是一个长期的承诺。因此，你需要考虑定价结构，不要让[面临一个规模合适的问题](https://jelastic.com/blog/right-sizing-problem-cloud-computing/)。许多公共云平台提供基于虚拟机的许可，如果您已经迁移到容器，这可能并不理想，容器可以按实际使用量收费，而不是按保留的限制收费。

您选择的平台会对您的业务成功产生重大影响，因此该过程应该经过深思熟虑和充分讨论。

## 构建专业知识

从虚拟机过渡到容器化并非没有复杂性。您的运营团队需要熟悉这两种截然不同的方法之间的主要区别，以实现集装箱化所能带来的效率、灵活性和成功。

谈到云中的高效容器化，传统的运营知识已经过时。云提供商现在通常提供基础设施硬件和网络的管理，而 [DevOps 团队需要通过编写脚本和使用面向容器的工具来管理软件部署自动化战略](https://thenewstack.io/deployment-strategies/)。

系统集成商和咨询公司可以提供他们的知识，帮助您实现容器的好处。但是如果你想在内部管理整个过程，最好的方法是培养内部专业知识——雇佣有经验的 DevOps 专业人员，研究最佳实践，并开发新的知识库。

此外，对于大型组织来说，选择一个在单一平台内使用虚拟机和容器来处理异构类型工作负载的解决方案至关重要，因为企业范围的容器采用可能是一个渐进的过程。

## 确保安全

容器化的环境非常动态，能够比虚拟机中的环境变化得更快。这种敏捷性是容器的一个宝贵优势，但在确保适当的安全性级别的同时，为开发人员提供所需的快速和简化的访问可能是一个挑战。

当您开始实施容器化策略时，您需要评估您组织的独特安全风险，以确保您的专有信息和数据得到保护。您必须记住，在调用微服务应用程序内部的内部组件时，基本容器技术不容易处理服务间身份验证、网络配置、分区和其他有关网络安全的问题。

此外，使用未知第三方提供的公开可用的容器模板可能充满风险。这种类型的容器中可能会有意或无意地包含漏洞。

传统的安全方法应该通过定期的安全评估来支持，以跟上当今快速变化的技术形势。市场上有无数的工具和流程编排平台，它们都有经过认证和验证的模板，因此您可以保护容器并加快配置过程。

容器编排有各种各样的技术选项，使采用变得更简单。然而，在充分利用 DevOps 的容器化方面，最重要的一块拼图是一个知识丰富的团队，他们了解特定于容器的最佳实践，以最大化这种方法的价值，并确保您的组织获得持久的 DevOps 成功。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>