# API 目录有助于开发运维安全的 3 种方式

> 原文：<https://thenewstack.io/api_catalogs_deliver_security_benefits/>

API 是现代软件的构建模块，然而，当涉及到他们创建和使用的 API 时，许多组织并不知道他们在处理什么。

在 TechStrong 主办的虚拟会议[devo PS Connect:DevSecOps Con](https://www.techstrongevents.com/devopsconnect-devsecops-rsac-2022/2006494)上的演讲“API 目录:保护你的 API 的第一步”中， [Traceable AI](https://www.traceable.ai/) 的产品营销负责人和安全宣传员 [Jessica Marie](https://www.linkedin.com/in/jessicamariemba/) 说，这是个问题。

“您知道您的组织中有多少个[API](https://thenewstack.io/its-not-only-banking-apis-that-must-be-secured/)吗？您知道最近推出了哪些 API 吗？哪些 API 是面向外部的，哪些是面向内部的？”玛丽问。“大多数公司根本不知道他们有多少 API，这些 API 位于何处，以及这些 API 实际上在做什么，这给组织带来了巨大的风险。”

玛丽的逻辑是这样的:软件吃掉了世界。API 吃掉了软件。因为业务是基于 API 的软件，为了保护业务，IT 必须知道流入和流出的 API 发生了什么。这从 API 目录开始。

“为了保护我们的软件业务，我们需要保护访问软件的 API，包括内部和外部，”Marie 说。API 安全性始于能够实时自动编目和跟踪这些 API 的更改及其分布式交互

安全问题需要的不仅仅是发现 APIs[保护 API](https://thenewstack.io/developer-beware-the-3-api-security-risks-you-cant-overlook/)需要一个可操作的 API 目录。

“基本上，你需要一个 API 目录，因为 API 连接一切——实际上是一切，”她说。“您有数千个 API 运行在多个云上，并且它们都在快速增长。”

## API 带来的安全问题

Marie 认为，当涉及到安全问题时，API 值得重新审视有几个原因。

首先，API 正在快速发展，部分原因是开发团队使用多种工具来快速构建和更新 API。她说，像持续集成和持续部署或交付( [CI/CD](https://thenewstack.io/three-ways-ci-cd-adoption-can-benefit-your-devops-team/) )这样的实践会对 API 产生频繁的变化。这意味着组织不能总是看到未知或影子 API 在生产中发布，甚至是在没有通知安全团队的情况下更新的 API。

“API 的频繁更新会导致版本和文档问题，”她提醒道。"除此之外，我们都知道 API 容易出现欺诈和恶意行为."

她补充说，应该对内部 API 进行监控，以防泄露，但组织也应该监控外部 API，并验证这些 API 是否可信。她补充说，已经有一些 API 被用来让攻击者访问关键基础设施的例子。

她认为，API 网关、[边车代理](https://thenewstack.io/operators-and-sidecars-are-the-new-model-for-software-delivery/)和[入口控制器](https://thenewstack.io/ingress-controllers-the-swiss-army-knife-of-kubernetes/)不足以管理集群内 API 架构的蔓延。

第二，API 被用来传输数据，而且通常是敏感数据。Marie 说,[开放网络应用安全项目(OWASP](https://thenewstack.io/owasp-top-10-a-guide-to-the-worst-software-vulnerabilities/) )将数据泄露列为 API 流量的[最大威胁之一。](https://owasp.org/www-project-api-security/)

“API 数量的增加，以及 API 流量的增加，使得这成为安全和 GRC(治理、风险和合规)团队需要解决的一个巨大问题，就像昨天一样，”她说。“因此，了解数据流并了解您的整体安全状况非常重要。”

## API 编目的 3 个步骤

Marie 建议，首先，从一个解决方案开始，这个解决方案可以是跟踪所有 API 的唯一来源，并提供自动发现、正确的版本控制和文档记录。她补充说，这应该有助于您评估 API 到 API 的连接性，并对 API 的可靠性进行统一监控。

她说:“你必须对属于组织的网络资产有一个准确的清单，并相应地保护它们。”。“您需要自动发现您的所有 [API 端点](https://thenewstack.io/slice-up-your-api-with-kubernetes-endpointslices-for-cluster-network-bottlenecks/)，并按照应用服务域对您的 API 进行分组，以便您的安全团队能够分析信息并做出更好的安全决策。”

然而，这个发现过程说起来容易做起来难，因为 API 可能部署在很多地方，从内部部署到混合部署再到云部署。她补充道,[微服务架构](https://thenewstack.io/what-it-requires-to-secure-apis-for-microservices/)也使 API 感知变得复杂，因为它使得应用高度分布式。她说，最后，每周发布多个版本的敏捷发布会使情况变得复杂。

发现 API 后，组织应该将这些 API 分类为外部、内部或第三方。API 目录还应该自动化编目新 API 和现有 API 更新的过程。

其次，他说，原料药目录应该自动生成原料药的风险分值。她补充说，这是 API 目录与 API 发现工具之间的一个区别——API 发现工具通常不会这样做，或者如果它们这样做，它往往是一个更加手动的过程。

“风险评分是一种不容讨价还价的能力，”她说。“能够生成主动识别易受攻击的 API 的风险分值非常重要，这些 API 风险分值使用您的业务逻辑来评估 AP 的漏洞。这也是不可谈判的能力。”

她补充说，通过提升 API 风险，组织也可以优先考虑并减轻这些风险。

她说，API 目录还将使更广泛的 it 组织受益，从安全性到开发运维到合规性，使他们能够应对 API 安全问题。她说，对于 DevOps 来说，这意味着确保他们的 CI/CD 集成允许他们在生产和非生产环境中尽早解决安全问题。

她说，第三，使用 T2 开放 API 规范 T3。她补充说，一个开放的标准让 API 的生产者和消费者可以用同一种语言交流。开放规范允许组织回答一些问题，比如 API 是否如开发人员所希望的那样被安全地使用，以及 API 是否暴露了任何未知的参数？她解释说，开放规范也是安全工具之间可移植性的关键。

她说:“你将立即获得你所需要的唯一的真相来源，这对不同的团队和合作伙伴都有好处。”“您将拥有不同安全工具之间的可移植性，并且更容易识别哪些 API 暴露了敏感数据以及在哪里暴露了敏感数据。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>