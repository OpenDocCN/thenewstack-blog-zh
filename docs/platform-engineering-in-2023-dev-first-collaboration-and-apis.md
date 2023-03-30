# 2023 年的平台工程:开发优先、协作和 API

> 原文：<https://thenewstack.io/platform-engineering-in-2023-dev-first-collaboration-and-apis/>

贯穿 2022 年的一个反复出现的话题很可能在 2023 年变得更加响亮，那就是开发者体验的重要性。2022 年出现了大胆的预测，即“DevOps 的终结”即将到来，这主要是因为开发者平台的崛起，但这些预测还为时过早。

2023 年不会是[平台工程的主导地位与 DevOps 和 SREs](https://www.getambassador.io/resources/rise-of-cloud-native-engineering-organizations/) 之间的拔河比赛。相反，这些趋势并不相互矛盾，而是共同预示着云本地开发环境的巨大变化。

对于许多组织来说，[平台工程](https://thenewstack.io/platform-engineering-infrastructure-meets-dev-experience/)的出现已经改变了开发运维、运营和站点可靠性工程(SRE)团队的日常工作。随着他们引入平台以减轻开发人员的辛苦，以[开发人员平台](https://thenewstack.io/building-an-internal-developer-platform-isnt-just-about-tools/)的形式创建类似于“开箱即用的基础设施”的东西将积极塑造[开发人员体验](https://www.getambassador.io/developer-control-plane/dcp-insights-mario-loria-from-cartax/)并通过“平台运营”提供运营支持

开发者平台通过让 99%的开发者专注于编码而不用担心基础设施或如何运行他们的软件来影响开发者体验。但是许多平台在设计上也很灵活，可以让 1%的开发者去探索和实验。由架构、 [DevOps](https://blog.getambassador.io/is-platform-engineering-the-new-devops-or-sre-472ed97a1885) 和 SRE 团队支持的开发人员平台包含了所有这些团队和角色的转型要素，促进了开发人员体验的改善，从而推动了更快、更安全的软件发布。

我认为 2023 年是开发者体验占据中心舞台并成为业务关键需求的一年。业务利益相关方将理解完全集成的开发运维/平台运维团队的重要性。随着企业组织大量采用云优先开发来提高业务生产力，开发人员必须有一条清晰的路径来实现快速反馈循环，从而更快、更频繁地安全交付软件。

一些趋势表明，开发人员体验在 IT 组织和他们所属的更广泛的业务中占据首要地位。以下是我认为将在 2023 年成形的预测，以支持趋势曲线。

## 预测 1:开发者优先的 Kubernetes 的增长

在第一个云原生时代，Kubernetes 的复杂性几乎要求交付软件首先以运营为中心。当发现新的领域时，行业必然会创建以运营为中心的工具来帮助划分新的界限。例如，随着容器和*软件定义的一切*的引入，新的问题出现了，可以理解的是，这些问题需要运营部门使用专业知识来解决。

开发人员面临着相当长的学习曲线，并被要求承担不同寻常的操作责任。虽然许多组织鼓励“左移”心态和 DIY 方法，但近年来在工具方面，特别是开发人员平台方面所做的大量工作已经简化了这一过程，并有助于将 [Kubernetes](https://thenewstack.io/serverless-vs-kubernetes-the-peoples-vote/) 和云原生开发带来的多重挑战融入[可管理的工作流](https://www.getambassador.io/products/telepresence/)。

从运营优先到开发人员优先的 Kubernetes 是一个不完整但必要的正确方向，不仅有助于通过优化的工具和工作流改善开发人员体验，还有助于在更广泛和更大的组织中增加云原生开发的采用。

## 预测 2:开发者平台释放开发者生产力

这些改进的核心是开发人员平台的概念，如果处理得当，它可以简化工作流程并显著降低开发人员的认知负荷。在 2021 年至 2022 年期间，不同的组织认识到开发人员面临的挑战，转而将内部开发人员平台理念作为释放开发人员生产力、加快和简化入职流程的一种方式，并提供一条包含最佳实践的“黄金路径”。

进入 2023 年，随着平台工程方法达到临界质量，我们将看到更多商业开发者平台选项的引入。这真的会推动开发人员优先的 Kubernetes 吗，还是仅仅是为了炒作“产品化”一些精明的组织已经从大量可用的云原生工具中构建出来的东西？毫无疑问，这将取决于平台。

缩短学习曲线并提供生产力途径和工具将简化所有类型开发人员的云原生开发，并丰富他们的整体体验。

## 预测三:开发者与 DevOps 共存；DevOps 没有死

云原生开发空间支持向左转移并承担运营责任的开发人员，包括他们编码的软件的运输和运行。大使实验室[也写了很多关于这个主题的文章](https://www.getambassador.io/kubernetes-expert-interviews/)，因为我们的许多[同时代人与我们分享了关于](https://www.getambassador.io/developer-control-plane/dcp-insights-kasper-nissen-from-lunar/)[开发者拥有他们创造的软件的整个生命周期](https://www.getambassador.io/kubernetes-expert-interviews/self-service/)的成功故事。但是在我们的讨论中，我们也了解到一种尺寸并不适合所有人。

我们收集的更广泛的共识主张[开发人员应该意识到并理解运营问题](https://www.getambassador.io/developer-control-plane/dcp-insights-mario-loria-from-cartax/)，例如，当出现问题时，能够更快更容易地查明发生了什么，但他们的核心焦点不是运营或平台构建。

这种在不压垮开发人员的情况下增强他们能力的需求，为我们采用[开发人员控制平面(DCP)](https://thenewstack.io/from-kubernetes-to-paas-to-developer-control-planes/)或开发人员平台提供了信息，以指导开发人员的工作，而不强迫他们深入运行软件的本质。平台工程是必要的，但还不够。对 2023 年的一个关键预测是，以开发人员为中心的标准和实现的发展，如针对可观察性的 [OpenTelemetry](https://opentelemetry.io/) 和针对软件材料清单的 [SPDX](https://spdx.dev/) ，将变得越来越重要，并减轻开发人员的一些额外责任。

对开发人员“左移”的关注稀释了开发人员的注意力，并使他们不堪跨职能需求的重负，包括可观察性、安全性和可伸缩性。这导致了关于德沃普斯死亡的大胆预言。毕竟，如果开发人员进入了为自己构建平台的以运营为中心的世界，谁还需要开发运维呢？

这个想法是让开发者能够“左移”而不“右移”这是我们回归的地方，不仅是开发人员的生产力和经验，也是随着开发人员平台成为标准，为开发人员提供他们工作所需的抽象和工具，DevOps 团队角色的变化。

## 预测 API 反击——微服务测试

API 优先的应用程序开发是我们每天使用的应用程序的基石，也是我们作为消费者、员工和人们所享受的日益互联的体验的基石。虽然它为最终用户创造了更加无缝和方便的体验，但对于越来越依赖互联网连接和无数工具来支持关键功能同时确保最高级别的安全性和性能的开发人员来说，它仍然是一个复杂而混乱的网络。

API 存在于许多不同的环境中，更改它们可能会产生意想不到的后果，波及到它们所属的连接系统。仅仅理解和全面了解这些互联系统是很难的。但是跟踪系统的发展和维护使得错综复杂的网络更加混乱，更加难以管理。开发人员必须不断地验证他们的假设(并改变它们)，以便一致地交付可靠的、[高性能的基于 API 的应用程序](https://www.oreilly.com/library/view/mastering-api-architecture/9781492090625/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>