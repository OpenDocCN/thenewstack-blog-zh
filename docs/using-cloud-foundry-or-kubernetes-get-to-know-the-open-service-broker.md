# 使用 Cloud Foundry 还是 Kubernetes？了解开放服务代理

> 原文：<https://thenewstack.io/using-cloud-foundry-or-kubernetes-get-to-know-the-open-service-broker/>

[](https://tanzu.vmware.com/)

[Matt McNeeney](https://tanzu.vmware.com/)

[Matt 是 Cloud Foundry Services API 项目的项目负责人，该项目旨在增强开发人员提供和管理服务的体验。Matt 还是 Open Service Broker API 的联合主席，该项目由 Pivotal、Google、IBM、Red Hat 和其他公司开发，允许开发人员向运行在多个平台上的应用程序提供服务，包括 Cloud Foundry 和 Kubernetes。在过去的一年中，Matt 在各种会议上发表了关于服务和服务代理的演讲，包括 CF Summit EU、VMworld 和 SpringOne Platform。](https://tanzu.vmware.com/)

[](https://tanzu.vmware.com/)[](https://tanzu.vmware.com/)

[Pivotal](https://tanzu.vmware.com/) 赞助了这篇文章。

为了改善他们的数字财富，企业正在拥抱[云铸造](https://www.cloudfoundry.org/)和 [Kubernetes](https://kubernetes.io/) 。这些项目分别为应用程序和容器提供了坚如磐石的抽象。最近，第三种抽象也成为了行业标准:开放服务代理 API (OSBAPI)。

OSBAPI 诞生于一个简单的事实:定制应用程序需要后台服务来做任何有趣的事情。随着 Cloud Foundry 的崛起，社区开始考虑平台作者和服务提供商应该如何互动。Cloud Foundry Service Broker API 项目始于 2014 年，旨在为这些方提供一个简单而稳定的合同。几年后，当 Kubernetes 到来时，K8s 社区立即看到了该合同为生态系统提供的价值，这导致了相同模式的采用。为了更好地与 OSBAPI 项目将开发人员连接到全球服务生态系统的目标保持一致，该项目被重命名为 Open Service Broker API，并被赋予新的治理模型以更好地反映其意图。

这种跨项目的共享工具是一件大事。这使得独立软件供应商(ISV)更容易以最小的开销向两个社区提供他们的技术。IT 从业者也会受益，因为他们只需要掌握一个工作流和 API。

IT 行业采用 OSBAPI 标准有三个关键:

1.  **OS papi 是多云的。**应用及其相关服务必须能够在数据中心之间轻松迁移，包括从内部迁移到公共云。OSBAPI 规范是一个可靠的抽象，负责底层资源。它提供了一致的开发体验——在这个多云世界中，这是一个非常重要的属性。
2.  **奥斯巴皮连接一切。**您选择的平台将运行数百乃至数千种应用。这意味着需要支持多种多样的附加服务。从 DB2 和 Oracle 等企业系统到 Spring Cloud Services (SCS)等流行的微服务管理工具。OSBAPI 规范是一个一致的接口，允许 ISV 专注于构建强大、可扩展和安全的服务，并为开发人员提供一致的自助服务体验，以获得他们的应用程序所需的任何服务。这为 ISV 提供了一个由数千名使用云原生平台的开发者组成的新的可寻址市场。
3.  **OSBAPI 可以满足常见的信息安全要求。**当您使用 OSBAPI 规范绑定(和解除绑定)到服务实例时，您的应用程序或容器会收到可用于访问服务的唯一凭证。这意味着您可以随时撤销对一个应用程序的访问权限。OSBAPI 项目还将独特的凭证管理挂钩到 Cloud Foundry 和 Kubernetes 中。像 [CredHub](https://docs.cloudfoundry.org/credhub/) 这样的开源项目使得平台到服务的集成更加安全。

有鉴于此，企业如何将 OSBAPI 与现代平台结合使用呢？让我们来看看常见的用例。

## OSBAPI 用例及最佳实践

### 为现代应用程序与传统系统交互

许多公司都有大量遗留系统。这些系统可能在定制硬件上本地运行。难题就在这里:现代的云原生应用和服务需要与存储在这些系统中的有价值的数据进行交互。然而，授予开发人员访问这些系统的权限通常很慢，需要通过支持票据进行手动干预。

谢天谢地，OSBAPI 提供了一个解决方案。当您构建一个服务代理来处理您的现代云平台和遗留服务之间的交互时，管理负担就会大大减轻。您的开发团队现在能够更快地创新。

这种方法也有长期的好处。一旦代理就位，这个一致的接口允许其他开发团队开始计划将遗留系统迁移到云。对现有应用程序或团队的影响微乎其微。

### 轻松访问公共云服务

超大规模云提供商拥有丰富的 API 来与其服务进行交互。这些公司已经使用开放服务代理 API 在他们的服务组合和平台之间创建了一个简单的接口。(更多信息见[亚马逊网络服务](https://pivotal.io/platform/services-marketplace/data-management/aws)、[谷歌云平台](https://pivotal.io/platform/services-marketplace/data-management/google-cloud-platform)和[微软 Azure)。](https://pivotal.io/platform/services-marketplace/data-management/microsoft-azure)因此，无论您在哪里托管应用，开发人员都可以轻松利用任何特定公共云服务的能力。

### 企业安全性和合规性

当平台和服务代理相互通信时，需要[基本访问认证](https://en.wikipedia.org/wiki/Basic_access_authentication)。这对许多服务提供商来说都很有效。他们可以使用身份验证头中的凭证来了解哪些客户正在与他们的经纪人交谈。从那里，他们可以实施审计和计费工作流。

最近，Open Service Broker API 规范进行了更新，以允许更安全的认证流，如 [OAuth](https://github.com/openservicebrokerapi/servicebroker/blob/master/spec.md#platform-to-service-broker-authentication) 。当然，这可能涉及平台和服务代理之间的一些带外通信。但是作为交换，它可以提供更高级别的安全性和可审计性。我们已经看到许多“托管”或“托管”服务代理选择这种模式(参见灵活部署选项)，尤其是已经提供托管服务套件的基于云的提供商。

如上所述，每当应用程序或容器试图通过服务绑定访问服务实例时，服务代理应该生成唯一的凭证。这提供了两个关键的好处。首先，您获得了一个严格控制的安全/访问模型。其次，这允许立即撤销访问，而无需重新部署任何代码。

这种快速可控的安全模式对于许多行业来说至关重要。如今，许多服务代理都提供这种现成的服务。

对于拥有专门团队为应用程序团队提供服务的大型企业来说，service broker 模型是一项巨大的资产。该模型允许团队配置特定代理提供的服务和计划。在此基础上，出于性能、合规性或成本原因，他们可以根据不同应用的需求定制服务。您的应用程序团队可以放心地进行构建，因为他们知道自己使用的是安全、合规和可维护的服务。

### 灵活的部署选项

有许多不同的部署方法可用于构建 service broker。正确的选择取决于您的 service broker 将部署在哪里以及如何访问它。

许多服务代理被包装成可下载的包，例如 [Pivotal Network](https://network.pivotal.io/) 的 [tiles](https://docs.pivotal.io/tiledev/tile-structure.html) 或 Kubernetes 的 [Helm Charts](https://github.com/kubernetes/charts) ，允许平台运营商轻松地在他们的平台上安装服务。从那里，他们授予他们的开发团队访问所述服务的许可。这种模式通常适用于注重安全性的企业。它还允许他们在入口和出口网络策略被严格锁定的无互联网环境中使用服务代理。

其他服务提供商，如那些提供托管 API 或基于云的服务的提供商，通常更喜欢选择“托管”或“托管”service broker 模型。在这种部署方法中，服务提供者负责部署、维护和升级自己的服务代理。提供商还必须向客户分发访问详细信息。这种模式允许服务提供商不断创新他们的服务，并随时更新。(请注意，通常需要互联网连接。)

还有一类服务代理可能希望以某种方式偏离开放服务代理 API 规范。例如，Google 云平台服务代理需要一个特殊的 OAuth 安全流，而 Cloud Foundry 不支持“开箱即用”。为了减轻这一点，可以使用服务代理(例如 [Google 云平台代理服务代理](https://github.com/cloudfoundry-incubator/gcp-broker-proxy))。

通过简单的“cf”推送，代理应用程序被部署到平台上，平台就像其他服务代理一样与之交互。然而，在幕后，该应用程序将请求代理到托管的 service broker，同时处理任何自定义的身份验证流。这是一个类似于我们之前讨论的模型，其中一个小垫片(托管 API 端点)可以放在遗留系统的前面。这样，您仍然可以启用自助服务来使用现有服务。

## OSBAPI:将任何服务连接到您选择的平台的一致、安全的方式

分布式系统变化频繁，底层技术也在不断发展。在这种背景下，Cloud Foundry 和 Kubernetes 是企业 IT 的基础技术。是时候把 OSBAPI 看作一个类似的基础构件了。

有关 OSBAPI 的更多信息，请从 pivotal.io 下载[最近发布的白皮书。](https://content.pivotal.io/white-papers/an-inside-look-at-the-open-service-broker-api)

Cloud Foundry Foundation、微软和谷歌是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>