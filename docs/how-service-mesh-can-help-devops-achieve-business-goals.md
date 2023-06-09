# 服务网格如何帮助开发人员实现业务目标

> 原文：<https://thenewstack.io/how-service-mesh-can-help-devops-achieve-business-goals/>

[](https://www.linkedin.com/in/rosesawvel/)

[Rose saw vel](https://www.linkedin.com/in/rosesawvel/)

[Rose 是一位创意和教育领域的技术传播者，专注于开源和云原生生态系统。作为 Aspen Mesh 的内容营销主管，她热衷于识别想法并将其转化为可访问、相关和及时的内容，以帮助人们更好地理解技术。当她不钻研如何谈论服务网格或微服务时，她可以在世界各地的歌剧中专业演唱。](https://www.linkedin.com/in/rosesawvel/)

[](https://www.linkedin.com/in/rosesawvel/)[](https://www.linkedin.com/in/rosesawvel/)

几年前，我们开始看到一些公司从单一架构转向微服务和 Kubernetes 环境。但随着技术的任何转变，微服务的变化为许多人带来了额外的好处，但也带来了新的挑战。没有人知道，例如，他们需要一些东西来帮助管理服务到服务的通信，这样他们的服务就可以有效地相互通信。虽然这种需求帮助推动了服务网格的最初发展，但技术仍在继续发展。现在，随着复杂性和需求的增加，加上资源捉襟见肘或团队缺乏服务网格专业知识，受支持的服务网格(由您组织外部的专家团队测试、强化和备份的服务网格)正成为许多人的良好解决方案，尤其是开发运维团队。

“DevOps”是一个用来描述开发和 IT 运营之间的业务关系的术语。大多数情况下，该术语用于指改善两个团队之间的沟通和协作。但是，虽然开发团队主要负责创建新的功能来推动业务，但运营团队通常是幕后的无名英雄，但也是极其重要的英雄。

在 IT Ops 中，您负责战略开发、系统设计和性能、质量控制、团队指导和协调，同时与开发团队和其他内部利益相关方合作，以实现您的业务目标并提高盈利能力。最终，开发和运营团队将负责帮助确保团队有效沟通，系统得到正确监控，实现高客户满意度，项目和问题解决按时完成。

在本帖中，我们描述了[服务网格不仅可以帮助组织支持已经转移到微服务和 Kubernetes 环境的 DevOps](https://aspenmesh.io/how-service-mesh-enables-devops/) 团队，还可以最终帮助组织实现其业务目标。

## 集成服务网格:与业务目标保持一致

当你考虑采用服务网格时，就像我们在 [Aspen Mesh](https://aspenmesh.io/?utm_content=inline-mention) 所做的那样，请记住，随着时间的推移，你的成功在很大程度上取决于与你公司的业务目标保持一致。与您的服务网格团队分享业务目标将有助于确保您在需要时获得并保持真正需要的特性和功能，并且它们保持相关性。

你公司的商业目标是什么？下面是我们认为服务网格有助于简化的三个方面:

1.  自动化更多流程(例如，消除辛劳)

自动化流程将您的团队从平凡的任务中解放出来，这样他们就可以专注于更重要的项目。自动化可以节省您的时间和金钱，服务网络可以提供帮助。

2.  提高基础设施性能

构建和维护一个久经考验的环境是为最终用户创造愉快体验的关键。确保他们有良好的体验会直接影响客户保持率，并最终影响您公司的底线。

此外，您在 DevOps 的大部分时间都花在了开发监控系统的策略和尽快解决问题上，无论问题是在工作日还是在半夜突然出现。幸运的是，因为服务网格具有[可观察性](https://aspenmesh.io/what-service-mesh-provides/)、[安全性](https://aspenmesh.io/microservices-security-compliance/)和弹性特性，它可以帮助减轻这些责任，减少 MTTD 和 MTTR。

3.  维持对客户的交付

如今，减少用户体验中的摩擦是游戏的名称，因此用户体验设计(UX)和可靠性是让最终用户满意的关键。如果你正在考虑采用服务网格，你肯定已经在使用微服务架构，而且你可能会使用 [Kubernetes](https://kubernetes.io/) 集群。但是，一旦这些在生产中变得过于复杂，或者没有您需要的所有功能，就该在组合中添加服务网格了。这就是服务网格的可观察性特性发挥作用的地方，例如集群健康监控、服务流量监控、简单调试和使用[分布式跟踪](https://aspenmesh.io/distributed-tracing/)的根本原因识别。此外，直观的 UI 是以易于理解和操作的方式呈现这些特性的关键，因此请确保您看到的是易于开发团队使用的服务网格。这将有助于为您的最终用户提供更加无缝(和安全)的体验。

## 进化；不是革命

那么，您实际上如何着手处理集成服务网格的过程呢？首先，确保您的开发和运营团队保持一致。但是特别能推动你成功的是确保你同时拥有[的灵活性和稳定性](https://thenewstack.io/agility-with-stability-why-you-need-a-service-mesh/)。这可能是一个很高的要求，因此将集成服务网格视为进化而不是革命是有帮助的。评估服务网格时需要考虑的三个关键领域包括:

*   降低风险。
*   生产准备就绪。
*   政策框架。

### 降低风险

让我们面对它，风险可能是可怕的，所以必须采取措施确保尽可能降低风险。你的公司唯一应该成为头条新闻的时候是你有好消息要宣布的时候。确保安全性、合规性和数据完整性是必由之路。对于许多人来说，安全性和合规性是头等大事，因此正面解决安全性问题非常重要。

有了一个设计良好的企业服务网，您可以期待大量的安全性、合规性和策略特性，因此您的公司可以轻松地[获得一个零信任网络](https://thenewstack.io/zero-trust-security-with-service-mesh/)。功能可以包括从确保最小特权原则和安全默认设置到诸如细粒度基于角色的访问控制(RBAC)和增量相互传输层安全性(mTLS)等技术功能。

### 生产准备就绪

您的应用程序已经准备好供最终用户使用，您的技术体系也需要准备好。这里真正有影响的是可靠性。动态请求路由、快速重试、配置审查、断路和负载平衡等服务网格特性极大地提高了微服务架构的弹性。

[支持](https://aspenmesh.io/istio-support/)也是一些企业根据服务网格专业知识是否是企业内部核心技能来考虑的一个特性。获得专家支持团队的帮助可以极大地改善您的生产准备情况和最终用户体验。

### 政策框架

虽然配置对于设置系统如何运行很有用，但是[策略](https://aspenmesh.io/managing-service-mesh-policy/)对于规定系统在发生某些事情时如何响应很有用。借助服务网格，策略和配置的力量相结合，提供了能够驱动应用程序基于结果的行为的功能。策略目录可以加速这种行为，而分析会检查策略违规情况，并了解要采取的最佳措施。这通过 canary、授权和服务可用性策略提高了开发人员的工作效率。

## 一起更好

DevOps 团队和服务网络可以共同努力，确保为您的最终用户提供最佳体验，并为您的业务带来最佳成果。微服务非常适合开发运维，但是这些架构所依赖的服务对服务的通信在生产规模上运行和管理起来非常复杂。有了 service mesh 来帮助扩展、保护和监控应用，开发和运营团队可以自由地做他们最擅长的事情。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>