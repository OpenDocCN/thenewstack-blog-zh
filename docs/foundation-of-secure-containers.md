# 反思基础设施，采访 Docker 的安全总监

> 原文：<https://thenewstack.io/foundation-of-secure-containers/>

Docker 对客户体验的重视是其创造大规模创新工具这一既定使命的标志。这一理念与 Docker 1.12 直接相关，后者[将集群和编排](https://thenewstack.io/docker-engine-1-12-will-come-built-orchestration-capabilities/)集成到 Docker 引擎本身。

[内森·麦考利](https://www.linkedin.com/in/nathanmccauley)是[码头工人](https://www.mirantis.com/software/docker/kubernetes/)的安全主管。今年夏天早些时候，麦考利采访了 Lee Calcote，他是我们最新的电子书《Docker 和 Containers 的网络、安全和存储》的作者之一。

Docker 提出了一个有趣的观点，即重新思考基础设施以及这意味着什么。Docker 开源工具，它自己用来管理容器。它通过使用自己的工具，为 Docker 的[微服务](/category/microservices/)方法提供了一个窗口，以及这如何反映了 McCauley 的必然结果，即他在 Docker 的目标是提高运行其基础设施的每个人的安全性。

Docker 专注于保护资源并在其平台中构建自动化。部分为了实现这个用户目标，Docker 1.12 有一个使用[传输层安全](https://hpbn.co/transport-layer-security-tls/) (TLS)的过程来加密网络上的每个节点，这是 Docker Swarm 的特定部署的一部分。群集和编排 Docker 容器的是 Swarm。

[#114:构建安全容器的基础](https://thenewstack.simplecast.com/episodes/114-building-the-foundation-of-secure-containers)

这段对话还可以在 YouTube 上听到。

Docker 1.12 引入了加密节点身份。容器中的命名约定在过去导致了开发人员的沮丧，当大规模运行应用程序时，由于缺乏明确标识的容器或组件，他们经常不能快速定位和解决问题容器。Docker 的加密节点通过引入公钥基础设施(PKI)以及每个节点的 TLS 身份来解决这些问题。

“一旦每个节点都有了 TLS 身份，您就可以构建真正有趣的东西，例如自动加密节点和群集之间的所有通信。基于此，您可以决定哪些工作负载将[或]不会在哪些主机上运行，”McCauley 指出。这允许 DevOps 团队通过基于单个节点身份创建新策略来进一步加密他们的系统。

虽然许多开发团队正在转向采用基于容器的基础设施，但他们也必须了解 Docker 本身是如何处理容器安全性的。

“许多组织看到的是向开发运维心态的根本转变。有了这种 DevOps 心态，他们意识到他们需要一种杠杆来实施安全控制，”McCauley 说，并补充说，“许多组织都将安全视为新流程的一部分，而在 DevOps 之前，它更像是一个以人为导向的流程。他们现在意识到 Docker 和 containers 附带的工具允许他们拥有许多他们想要和需要的同类控件。”

这些现成的安全特性引发了关于开发人员是否应该选择加入这些特性的各种讨论。在与苹果公司在其设备上标配的强制安全功能进行对比时，麦考利解释说，“在有可能只做正确的事情的情况下，我们有点觉得没有理由在那里拥有配置能力。只需内置即可，默认内置。”

[cyclone slider id = " ebook-4-赞助商"]

最终，虽然许多大型企业可以选择招聘大量专注于安全的开发人员和运营员工，但 McCauley 恳求 Docker 也专注于帮助较小的团队实现他们的目标。“当我们尽可能多地考虑我们如何制造产品时，我们不希望我们的产品有任何锋利的边缘，因为不正确的操作会导致割伤。我们希望帮助人们解决这个问题。”

[![barcelona](img/19403431e61caee7d8e0ebecb3ae0718.png)](https://www.eventbrite.com/e/openstack-summit-pancake-breakfast-tickets-27692501016)

Docker 是新书库的赞助商。

马西莫·曼奇尼通过 Unsplash 拍摄的特写图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>