# 何时选择 Cloud Foundry 而非 Kubernetes

> 原文：<https://thenewstack.io/when-to-choose-cloud-foundry-over-kubernetes/>

Kubernetes (K8s)是一项令人着迷的技术。它可以运行各种不同的工作负载。然而，Kubernetes 并不是唯一的选择。

仔细观察 Cloud Foundry (CF)会发现，对于几个用例，Cloud Foundry 环境可能比 Kubernetes 更受欢迎。本文重点介绍了用于 VMs 的 Cloud Foundry(BOSH)，与 CF-4-K8s 形成对比，后者值得专门进行比较。

## 云铸造厂

 [朱利安·菲舍尔

Julian 是 anynines 的首席执行官，致力于软件操作的自动化。在平台自动化领域，Julian 非常关注大规模数据服务自动化。](https://www.linkedin.com/in/julianfischer/) 

虽然 Kubernetes 的想法是成为一个构建平台的平台，但 Cloud Foundry 的概念是提供一个交钥匙应用程序开发平台解决方案。

借助 Cloud Foundry，可以在任何主要基础设施上建立平台环境，无论是公共基础设施还是内部基础设施。特别是当使用 BOSH 管理其生命周期时，Cloud Foundry 显示了它的优势:在一个大型环境中为数百个租户运行数千个应用程序。

在这样的云铸造环境中，操作系统的更新，就像在 [Shellshock 漏洞利用](https://en.wikipedia.org/wiki/Shellshock_(software_bug))之后所必须的那样，就像修改几行 YAML 代码一样简单。当使用基于 [BOSH 的数据服务自动化](https://www.anynines.com/data-services)时，更新将作为跨环境重建虚拟机的浪潮而被执行。这些环境通常包含数千个虚拟机，托管来自不同租户的应用。Cloud Foundry 租户，也称为“组织”，通常用于表示组织单位，如内部业务单位。由于 Cloud Foundry 能够隔离租户，因此在维护集中式平台的同时，大型环境也是可能的，从而展现出显著的规模经济效应。

Cloud Foundry 平台环境最初会占用相对较大的基础设施。一般来说，云铸造环境的开销取决于冗余级别，因此也取决于最终平台的预期可用性。

一旦建立了 Cloud Foundry 环境，它将提供任何应用程序开发平台所需的几项关键服务，包括用户管理和身份验证服务，包括创建组织和“空间”的能力、跨集群调度工作负载的容器编制器、使用构建包或容器映像部署代码的能力以及中央服务市场。

Cloud Foundry 中的中心市场允许集成兼容服务代理的开放服务代理 API。该市场提供了一个可用的[服务](https://12factor.net/backing-services)列表，并将使用户能够以按需自助服务的方式管理数据服务实例。

假设有一个可用的服务代理列表，应用程序开发人员可以立即从本地代码部署应用程序，创建数据库实例，如 [PostgreSQL 流集群](https://www.anynines.com/data-services)，并将应用程序绑定到数据库。开发人员的用户体验基于定义良好的 API，工作负载可以使用 CLI 或通过应用 YAML 规范来描述。

简单地说，Cloud Foundry 提供了企业级托管，实现了高度自动化和强制执行组织策略的能力。

构建包的使用是一个很好的例子，说明了组织如何决定是允许工程团队中的本地决策，还是通过允许任意构建包或将选择限制在经过良好测试、安全检查的构建包列表中，来强制使用质量保证的配置自动化。

CF 市场是中央治理的另一个例子。为数据服务自动化和提供其他服务而选择的服务代理提供了对如何处理数据的细粒度控制。工程师不需要选择、安装和生命周期管理运营商。他们所要做的就是选择一个数据服务，选择一个服务计划并创建一个服务实例。service broker 的工作是允许全面的生命周期管理，包括配置更改、版本升级、可伸缩性、日志和指标的处理等等。

## **Kubernetes**

Vanilla Kubernetes 提供了名称空间，这是一个用于在 Kubernetes 集群中分隔工作负载的概念。然而，名称空间不能像 Cloud Foundry 组织那样隔离，Kubernetes 也不能提供现成的用户管理和认证服务。

如果用作应用程序开发平台，Kubernetes 环境往往与 Cloud Foundry 环境具有不同的结构。特别是 Kubernetes 集群的数量远远高于 Cloud Foundry 实例的数量**。**虽然 Cloud Foundry 环境(暂存或生产环境，通常包含单个 Cloud Foundry 安装)，但 Kubernetes 环境通常由多个 Kubernetes 集群组成。虽然单个 Kubernetes 集群可能比单个云代工厂更容易操作，但管理 100 个 Kubernetes 集群比管理单个云代工厂要困难几个数量级。这个场景可能看起来很极端，但是它显示了潜在的问题。

管理大量的 Kubernetes 集群会带来复杂性，而 Cloud Foundry 则不需要这样。诚然，有辩证讨论的余地。工作负载必须与 Cloud Foundry 兼容，Cloud Foundry 比 Kubernetes 对 [12 因素合规性](https://12factor.net/)要求更高。Kubernetes 比 Cloud Foundry 更容易定制，因此可以接受 Cloud Foundry 无法接受的工作负载。虽然这一论点也为 Cloud Foundry 提出了一个论点，这是一个需要指出的关键陈述:如果一个组织运行大量与 Cloud Foundry 兼容的工作负载，Cloud Foundry 可能代表更好的运营经济性。

如果工作负载更加异构，Kubernetes 会胜出，而增加的操作复杂性是可以容忍的。

## Cloud Foundry vs. Kubernetes

虽然 Kubernetes 可以进行配置、扩展和调整，以接近 Cloud Foundry 的行为，但 Cloud Foundry 在管理大型全球工作负载的能力方面仍然是独一无二的。大规模云铸造环境的经济性非常好。对于主要运行 12 因素兼容应用程序的组织来说，它仍然是一个有效的选择，旨在为其开发人员提供最大程度的自动化。

作为一种固执己见的技术，Cloud Foundry 最适合构建集中式应用程序开发平台。在其经典变体中，使用 BOSH 和虚拟机自动化，这是创建具有数百个租户和数千个应用程序的大型平台环境的可靠选择。CF 推送体验及其中心市场是 Cloud Foundry 如何帮助大型组织定义统一开发人员体验的两个例子。当规模经济效应开始发挥时，其最初的基础设施足迹将被遗忘，允许一个小型运营团队处理跨多个公共和内部基础设施的巨大平台环境。

特别是如果大型组织需要跨基础设施开发和运行许多具有同质用户体验的应用程序，Cloud Foundry 是一项应该考虑的技术。

另一方面，Kubernetes 已经成为容器化工作负载的事实上的标准。每当需要高度的灵活性时，Kubernetes 就是最佳选择。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>