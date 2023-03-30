# 事件驱动架构如何推动业务敏捷性

> 原文：<https://thenewstack.io/how-an-event-driven-architecture-drives-business-agility/>

[Triggermesh](https://triggermesh.com/) 赞助了这篇文章。

事件驱动架构(EDA)允许开发人员创建动态应用程序，为业务流程注入速度和响应能力，帮助公司更高效地运营。

通过这种方式，EDAs 激发了组织的兴趣，这些组织通过使用现代的、以云为中心的应用程序开发流程(如 DevOps)和技术(如容器化的 Kubernetes 应用程序)来寻求数字化转型的好处。

顾名思义，EDA 围绕着应用程序事件的生成、传输和处理，这些事件反过来会异步触发组织基础架构中其他应用程序和系统的操作。

标准普尔全球市场情报部(S&Global Market Intelligence)下属的 [451 Research](https://451research.com/) 的研究主管[威廉·费罗斯(William Fellows)表示:“如果客户进行了购买，该‘事件’就会被发布和/或以流媒体形式传输，以便对了解此类事件感兴趣的服务能够消费。”。](https://www.linkedin.com/)

## 消息总线的现代选择

EDA 已经成为一种分布式的、可扩展的、更有弹性的替代方案，替代了汞合金洞察公司的研究员 Tom Petrocelli 所说的“单一消息总线”。“我们正在重新设计已经存在了 30 年的信息传递方法，”他说。

EDA 特别适合于高吞吐量的交易应用程序，例如用于电子商务的应用程序。“你可以称它们为事件、交易或消息:这都是一回事，”Petrocelli 说。“这是一些必须从一个地方转移到另一个地方的数据，你不能冒丢失任何数据的风险。事件网格就是为那种环境设计的。”

Fellows 说，因为 EDAs 中的服务是松散耦合的，所以它们特别适合云原生微服务架构，在这种架构中，组件可以独立开发，仅在需要时部署。

对业务的影响可能是巨大的。“EDA 帮助组织提高了效率，改善了敏捷性和响应时间，从而支持了更好的客户体验，无论是内部还是外部的，”Fellows 说。EDA 的理想用例包括支付处理、网站监控、物联网、实时营销和欺诈检测。

他说，对于 DevOps 团队来说，EDA 允许开发人员更加敏捷，特别是在创建或更新需要及时消费数据以更新或触发其他事件的应用程序时。

“事件驱动的应用程序由微服务组成，这些微服务可以在需要时独立扩展和缩减，而业务逻辑由处理事件调度和消费的事件总线处理，”Fellows 说。

Petrocelli 称，EDAs 还有助于控制云计算成本。“在这个云原生世界中，我为事物运行的时间付费，”他说。“如果某些东西可以不运行，只在需要时唤醒，特别是那些不经常被调用的服务，那么我可以节省一些钱。”

## 展望未来

展望未来，Petrocelli 预见到 EDA 在理想路径由于某种原因中断的情况下，寻找替代路径的方法会有所改进。“替代路径优化是一个我们将看到大量增长的领域，”他说。

Petrocelli 还预测了 EDA 性能优化方面的改进，因为加快速度是他们价值主张的一大部分。“我认为，你将开始看到它们变得更加精简，比它们开始的地方更加优化，”他说。

Fellows 说，虽然 EDA 被认为相对容易开发，因为它们可以使用最适合工作的任何语言和技术，但随着某件事情触发的事件数量增加，它们会变得更难控制。

此外，在特定系统或应用程序中创建的事件通常只能在该系统中被检测、消费和操作。目前有大量的创新集中在创建集成和转换服务，提供不同系统之间的桥梁，”他说。

## 业务敏捷性

据支持 EDA 的云原生集成平台提供商 [TriggerMesh](https://www.triggermesh.com/) 的首席执行官 [Mark Hinkle](https://www.linkedin.com/in/markrhinkle/) 称，EDA 之旅是从批处理驱动的世界(例如，每天报告一次应用更改)到实时、事件驱动的应用。

例如，Zendesk 票据可以被转发到 AWS 理解自然语言处理服务，以便理解情绪，并根据客户是生气、高兴还是无动于衷采取不同的行动。Hinkle 说，或者如果有一个数据集上传到你的云存储，博客对象存储的变化可以启动 Kubernetes 上的 Hadoop MapReduce 工作流来处理数据集。

TriggerMesh 充当 EDAs 中的代理，允许开发人员在云服务和/或内部应用程序之间创建自动化工作流。它消费、路由和转换事件，例如通过实时库存调整和更新，帮助其客户减少其业务中正在发生的事情与他们知道此事之间的延迟。

Hinkle 说:“因为它与云和基础设施无关，所以 TriggerMesh 可以消费运行在数据中心和来自企业服务总线的事件，并将它们转发到云以触发一个动作，就像 Kubernetes 工作负载一样。”

另一个例子:根据 Hinkle 的说法，如果你有许多来自微软 Azure 的安全事件，你可以使用 TriggerMesh 仅将关键事件转发到 Splunk，从而降低存储成本并使数据分析更容易。

TriggerMesh 合作伙伴 Confluent 的技术合作伙伴和项目总监 Sid Rabindran 表示:“cloud native 的承诺是能够将云服务、SaaS 和内部应用集成到强大的定制流程中，以满足您不断变化的业务需求。

Confluent 和 TriggerMesh 合作伙伴关系允许客户将来自任何流行来源的事件直接集成到他们的集群中，包括 Slack、AWS、GitLab、GitHub 和 Azure。

Rabindran 表示，它还使他们能够使用任何服务构建智能应用流，运行在云中或内部，使对混合云、多云和云原生应用流感兴趣的企业和云开发人员、架构师和技术策略师受益。

GitLab 源代码产品经理 Daniel Gruesso 表示，GitLab 与 TriggerMesh 合作，为其用户提供了一种使用 Knative 从 GitLab 将无服务器工作负载部署到 Kubernetes 集群的简单方法。此外，TriggerMesh 还为 Knative 创建并维护了官方的 GitLab 事件源。

“TriggerMesh 提供的工具和知识使我们能够快速完成 GitLab Serverless 的第一次迭代。我们已经从开源社区和有经验的项目维护者那里得到了非常积极的回应，”格鲁索说。

TriggerMesh 团队对无服务器架构有深入的了解，并且是少数几个在 Knative 方面有经验的团队之一。此外，他们有很好的专业素养，并分享 GitLab 的开源基因，他说。

“他们开发了一些工具，可以轻松地与不同的无服务器技术进行交互。他们的团队总是站在不同供应商的各种无服务器解决方案的最前沿，”Gruesso 说。

## TriggerMesh 云本机集成

本月，TriggerMesh 发布了其集成和自动化平台的[生产就绪版本](https://thenewstack.io/triggermesh-1-0-platform-promises-event-driven-production-workflows-across-the-clouds/)。该产品名为 trigger mesh Cloud Native Integration Platform 1.0，由 500 多名用户进行了 beta 测试，可以支持最苛刻的企业工作负载。

它旨在允许用户集成服务、自动化工作流并加速信息在整个组织中的移动。通过帮助组织在任何内部应用程序或云服务的基础上构建事件驱动的应用程序，TriggerMesh 推动了数字化转型工作。

例如，一家测试 TriggerMesh 平台的银行希望实现治理自动化。如今，他们有多个系统监视异常活动，例如一天内从一个帐户进行三次以上的电汇。

Hinkle 说:“他们采用这些治理策略，查看系统，如果发生了什么，他们会标记这些策略，并在其合规性数据库中开一张罚单。”。

该银行运行一组无服务器的功能来实施治理，这些功能是基于来自其系统的事件计数来触发的。输出在数据库中标记它们，要么锁定帐户，要么标记它们以供审查。

“在这种情况下，孤立且未集成的系统现在正由无服务器功能进行集成和管理。我们正在为这些功能的触发提供渠道，”欣克尔说。

关键特性包括声明式 API 事件转换，将事件从一种格式转发到另一种格式；以及自动化基础架构和在 Salesforce、OracleDB、Zendesk、Datadog、Oracle Cloud Security Logs、Splunk 等之间桥接工作流的新桥梁。

其使用案例包括 EDA 自动化，其中使用 TriggerFlow 技术，用户可以使用基于规则的逻辑连接系统事件和触发工作负载。TriggerMesh 还可以补充机器人过程自动化(RPA)技术，并帮助记录数据流。

TriggerMesh Cloud Native Integration Platform 1.0 以两种 SaaS 部署选项提供，在 Kubernetes 上自我管理或作为 trigger mesh Cloud 上的完全托管服务。

展望未来，Hinkle 表示，TriggerMesh 计划增加对开源项目的贡献，特别是通过为事件的消费者和生产者添加连接器，他称之为一种“插件架构”。他还设想为事件驱动的工作流创建更多的管理功能。

“我们也有机会使用机器学习和人工智能来自动化工作流程，”他说。“这是一个长期愿景，但我们有潜力做到这一点。”

Gerd Altmann de Pixabay 的特写图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>