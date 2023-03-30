# 服务网和 Istio 的承诺

> 原文：<https://thenewstack.io/service-mesh-and-the-promise-of-istio/>

[](https://www.raincapital.com/)

[![](img/291025fd273d3107f910f67c65014065.png)](https://www.raincapital.com/) [【王晨曦】

王晨曦博士是早期专注于网络安全的风险投资基金 Rain Capital 的创始人和普通合伙人。王博士也是网络安全咨询公司 Jane Bond Project 的联合创始人。在此之前，晨曦在 Twistlock 担任首席战略官，负责 Twistlock 的早期成长。晨曦是 2016 年& 2017 年格蕾丝·赫柏会议安全&隐私项目的联合主席，并被 SC 杂志评为 2016 年最具影响力女性。Chenxi 在 Forrester Research、Intel Security 和 CipherCloud 建立了辉煌的职业生涯。在 Forrester，Chenxi 写了许多有力的研究论文。在英特尔安全部门，她领导了涵盖硬件和软件平台的无处不在战略。陈曦的职业生涯始于她在卡内基梅隆大学担任计算机工程教员。晨曦是广受欢迎的公众演说家，也是 IT 高管值得信赖的顾问。她曾被《纽约时报》、《华尔街日报》、《Forbes.com》、《福克斯商业新闻》、《彭博》、《黑暗阅读》和许多其他媒体引用。晨曦拥有弗吉尼亚大学计算机科学博士学位。](https://www.raincapital.com/) 

在今年的 [DockerCon 2018](https://2018.dockercon.com/) 上，服务网格的概念是一个热门话题。由软件如 [Istio](https://istio.io/) 体现的服务网格出现在会议、走廊对话中，甚至出现在主题演讲台上。

服务网格背后的论点是，有一组常见的网络相关任务，如路由、重试、负载平衡，甚至可以从应用程序和底层网络中抽象出来的认证。因此，网格只不过是为不同的服务执行这些任务的软件实体的网络。如果没有这种抽象，您要么将这些任务作为网络基础架构的一部分嵌入(例如 L3 或 L4)，要么将其编码到应用层(如在 L7 网络覆盖中)。

在微服务环境中，这两个选项都不理想。应用覆盖方法是应用感知的，并且可以执行复杂的基于内容的路由，但是它将导致每个服务中的大量冗余代码，并且潜在地降低性能。相反，依赖传统的 L3 或 L4 网络意味着 it 既没有服务请求的概念，也没有服务请求的可见性，而这对于做出最佳路由决策至关重要。

这就是为什么服务网格对微服务环境如此有吸引力——它在 L7 级别运行，但与应用程序代码分离，并可以通过应用程序级别的洞察力实施 L3/L4 策略。要理解这一点，首先要深入挖掘服务网格的架构。

## 服务网格架构和抽象的力量

服务网格是一种有意设计的抽象，由控制平面和数据平面组成。

*   **数据平面:**数据平面处理从一个应用到另一个应用的实际流量。关于实际服务请求的任何联网方面，例如路由、转发、负载平衡，甚至认证和授权，都是服务网格数据平面的一部分。数据平面概念并不新鲜。在传统网络中，路由器和交换机是构成数据平面的组件。然而，在服务网格中，数据平面是边车代理的集合——每个服务一个代理。

从服务的角度来看，除了与代理交互的方式之外，它对网络一无所知。在这种情况下，代理充当网络的抽象。这意味着服务的开发者可以专注于服务的内容，而不用担心网络的细微差别。这种 sidecar 代理的一个开源例子是 [特使](https://www.envoyproxy.io/) 。

*   **控制平面:**简单来说，控制平面就是将各种数据平面连接成分布式网络的实体。这是服务网格的策略和管理层，主要负责收集遥测数据，并就配置、谁可以与谁对话以及此类策略的实施做出明智的决策。这种服务网格控制平面的一个开源示例是 [Istio](http://www.istio.io) 。

该架构实现了服务网格设定的目标，即高性能、智能和安全的流量管理。数据平面是一组高性能代理，用于拦截网络流量，并与网络层交互以路由流量。控制平面具有第 7 层洞察力，可以指示数据平面根据策略、安全状况和实时遥测信息做出复杂的路由决策。

服务网格提供的抽象提供了强大的分离功能，有助于开发人员、运营团队和安全性。数据平面将底层网络从应用中抽象出来。控制平面进一步抽象出决策引擎逻辑，这意味着数据平面可以专注于成为高性能的流量拦截器和路由器。总之，服务网格可以自动做出智能、动态的路由决策，而无需对应用程序代码进行任何更改。

服务网格中的另一个基本概念是服务身份。也就是说，每个服务都被分配了一个加密的强身份。在强身份的上下文中管理服务可以实现细粒度的、基于身份的策略，这在以前是不可能实施的。

## 服务网格的关键功能和主要使用案例

如今，服务网格空间越来越受到关注。服务网格的一些关键功能包括:

*   **清单和可见性:**提供对哪些服务正在运行、谁在与谁对话以及服务依赖关系的洞察和可见性。
*   **性能管理:**这里的性能是指响应时间、资源利用率，以及应用性能与业务指标的最终相关性。通过服务网格，组织可以设置特定的性能指标，以确保资源在服务之间以最佳方式分配和使用，并满足特定的操作指标。
*   **安全策略管理:**服务网格提供了基于身份定义和管理策略的能力，例如，谁可以与谁对话。此外，您还可以应用组织策略来管理服务之间的交互。
*   **流量管理:**在网状网络中，使用路由规则管理服务间的流量相当容易。例如，Istio 公开了一组 API，允许您设置细粒度的流量规则。这还包括自动路由策略，当网络面临不利条件时，这些策略可以使服务请求更加可靠。

使用服务网格的最大好处是，您可以动态地更改策略，而无需更改任何应用程序代码。

对于组织而言，服务网格的一些主要使用情形包括:

*   **服务发现:**组织通常不知道哪些服务正在他们的基础设施中运行——这个问题在微服务环境中更加严重。服务网格提供服务级别的可见性和遥测，这有助于组织进行服务清单和依赖性分析。
*   **运行可靠性:**遥测数据服务网格提供的服务可以让您了解服务的执行情况——响应服务请求需要多长时间，使用了多少资源，甚至包括服务的使用频率等。这使您能够在问题出现时发现问题，并在它们影响更大的应用程序环境之前纠正它们。
*   **细粒度流量治理:**组织可能希望阻止特定内容或特定 URL 或子 URL。借助服务网格，您可以配置网格网络来执行这些细粒度的流量管理策略，而无需返回并更改应用程序。这包括特定网格内的服务，以及进出该网格的入站和出站流量。
*   **安全的服务到服务通信:**有了通用服务身份的概念，对服务到服务的通信实施相互 TLS 是可行的。此外，您还可以使用 TLS 或 JSON Web 令牌(JWS)来实施服务级身份验证。
*   **基于信任的访问控制:**不是基于静态属性(如用户身份、IP 地址或访问控制列表)来管理访问。服务网格提取实时主机和网络遥测数据，基于这些数据，您可以做出基于信任的动态访问控制决策。例如，您可以指定一个策略，使服务请求只能根据请求来自的位置来授予，或者证书签名请求(CSR)只能在请求者通过健康检查时才能成功。
*   **混沌工程和测试:**服务网格包括执行故障注入和测试服务弹性的特定功能。例如，Istio 允许您在服务响应中注入特定的延迟，并测试应用程序作为一个整体的行为。注入延迟是一种混沌工程技术，已被证明有助于提高整个系统的弹性。

## 一个网格统治所有网格——面向多云的服务网格的承诺

在今年的 DockerCon 大会上，支持多云的信息清晰而响亮。Docker 不仅推出了灵活的多云支持，还有许多第三方功能旨在支持多云工作负载和不同云基础设施之间的轻松移动。

服务网格非常适合多云，因为它提供了一个单一的抽象层，掩盖了底层云的细节。组织可以使用服务网格设置策略，并在不同的云实例中强制执行这些策略。

Istio 作为一个服务网格，提供了强大的多平台特性。Istio 的 Mixer 适配器将基础设施后端信息抽象为一个统一的 API，该 API 执行日志记录、监控、ACL 检查和其他功能。请注意，这些功能可以在单个集群内，跨不同集群，甚至跨不同云平台。

例如，如果您有五个全局集群，并且在其中三个集群中运行您的应用程序。为了最小化成本和最大化性能，您可能需要实时可见性来确定哪三个集群运行您的应用程序以及如何平均分配负载。这些都是 Istio 可以优雅地、自动地、无需人工干预地完成的任务。

## 服务网格的当前状态

如今，服务网格的开源景观包括 [Linkerd](http://www.linkerd.io) 、 [Istio、](https://istio.io/) 和 Conduit 。有关不同服务网状网络的详细信息，请查看新堆栈上这篇比较不同项目的伟大文章。

Istio 和 Conduit 对 Kubernetes 都有很好的支持。谷歌、Lyft 和 IBM 是 Istio 背后的最初实体。Istio 与 Kubernetes 的强大集成、出色的流量管理功能及其对真正的云无关管理的承诺，有助于为 Istio 在云原生社区中赢得强劲的发展势头。

然而，今天安装和管理 Istio 并不简单。最大的挑战之一是将组织的复杂管理需求转化为 Istio 策略，这不是一个简单的过程。这就是为什么像 Istio 项目负责人创立的 [Tetrate](http://www.tetrate.io) 这样的初创公司越来越受到关注，不仅因为其帮助组织建立和运行 Istio 的专业知识，还因为其承诺提供技术来丰富网格功能，自动化网格操作，并实现跨集群和云的集中管理。

Tetrate 的工程师 Zack Butcher 在今年的 DockerCon 上发表了两场与 Istio 相关的演讲，其中包括一场 Istio 培训。Butcher 指出，该行业渴望像 Istio 这样的工具，它提供“简单而强大的抽象来解决复杂的问题。”

我们期待更多的创新进入服务网格领域。在接下来的 18 个月中，我们应该会看到大量的改进，包括…

*   **数据平面和控制平面进一步整合**。数据平面和控制平面之间更紧密的集成将带来更好的性能和潜在的更丰富的控制。
*   **遥测和控制的更多 API 开发**:我们应该会看到新的 API 出现，提供更深入的遥测、更简单的查询和更复杂的服务控制。像细粒度数据访问这样的控制——哪个服务可以访问哪个数据——是服务网格空间中新出现的功能。
*   **特定云环境的覆盖**:对 Istio 加深对特定云生产环境的支持的需求越来越大，比如 Azure 容器服务、Openshift 环境等。

微服务提供强大的业务优势，但代表了应用部署和运营的西部荒原。当组织采用微服务时，运营和安全团队通常会失去可见性和控制力。借助 service mesh，组织有望继续获得微服务的自动化和效率优势，同时从运营角度获得急需的透明度和管理。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>