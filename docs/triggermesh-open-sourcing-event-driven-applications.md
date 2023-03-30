# TriggerMesh:开源事件驱动应用

> 原文：<https://thenewstack.io/triggermesh-open-sourcing-event-driven-applications/>

[事件驱动的架构](https://thenewstack.io/the-rise-of-event-driven-architecture/)正在重塑产生信息的服务和消费信息的服务之间共享信息的方式。随着软件架构继续从 API 驱动向事件驱动转变，以及实时事件流继续流行，系统空闲和等待数据变得越来越过时。

随着公司、项目和基础设施的增长，对更多多云实时数据流的需求也在增长。企业需要更简单的开发运维工程师工作流程、测试完成时的实时提醒，以及在不同软件即服务(SaaS)应用之间跟踪安全日志。

在今天不断增长的[云原生生态系统](https://thenewstack.io/cloud-native/)中，所有这些都是必要的，如果没有开源工具或供应商锁定的限制，它们很难找到。

[TriggerMesh](https://triggermesh.com/?utm_content=inline-mention) 是一个[无服务器](https://thenewstack.io/serverless/)事件路由器，只有一个简单的主要目标:实时处理事件，并将它们路由到正确的消费者。这是一个多用途的工具，使用案例越来越多。

[TriggerMesh 的开源集成平台](https://thenewstack.io/triggermesh-integration-platform-now-an-open-source-project/)为用户提供了一种配置驱动的解决方案，这种解决方案会让基础设施即代码(IaC)产品的用户感到熟悉，如 [Ansible、](https://thenewstack.io/terraform-vs-ansible-which-is-best-for-you/) [Chef](https://thenewstack.io/chef-extends-security-and-compliance-across-hybrid-cloud/) 和 [Terraform](https://www.terraform.io/) 。它构建于 [Kubernetes 之上，](https://kubernetes.io/)它包括一个声明式 API，可以快速地以编程方式将来自多个来源的数据和服务连接到事件驱动的应用程序中。

消息消费的来源包括[亚马逊网络服务(AWS) SQS、](https://aws.amazon.com/?utm_content=inline-mention)谷歌发布/订阅、Azure 事件中心和 Kafka。TriggerMesh 过滤和转换消息，将处理能力与无服务器功能相结合，并将它们与链接 Elasticsearch、AWS 简单存储服务(S3)和 Apache Kafka 的消息接收器相连接。

TriggerMesh 连接到遗留服务总线，并在应用程序或数据接收器之间创建工作流，以连接到其他系统，如 Azure Data Lakes 或 Snowflake。

TriggerMesh 的产品经理 Jonathan Michaux 告诉新的 Stack 说:“人们通常会用它来触发功能、服务或……微服务。

他补充说，TriggerMesh 也可以在更大的流媒体生态系统中发挥作用，例如提供“处理事件的功能，并将它们推送到另一个系统，如 Kafka，以便稍后进行进一步处理。”

为了快速比较，想想亚马逊的 [EventBridge。](https://thenewstack.io/aws-debuts-an-event-bus-programmable-infrastructure-support/)事件路由器于 2019 年推出，允许开发者编写规则，一旦亚马逊的 S3 桶中发生事件，这些规则就会采取行动。

TriggerMesh 是开源的替代方案，提供类似的功能，而没有供应商锁定的要求。最近，TriggerMesh 推出了其最新的开源产品， [Shaker，](https://www.triggermesh.com/blog/triggermesh-announces-open-source-aws-eventbridge-alternative)，继续推动 TriggerMesh 更广泛的采用。Shaker 去掉了 Kubernetes 的需求，并提供了 TriggerMesh 在 Docker 上运行的能力。

开源不仅仅提供了摆脱供应商束缚的自由。这意味着 TriggerMesh 完全与云无关，允许用户在多个云和本地数据中心之间进行生产和消费。

“想想这是什么，如果我们能以一种简单的方式将任何应用程序通过事件连接起来，它会有多强大，”Michaux 说。“你可以在任何 Kubernetes 集群或任何安装了 Docker on [OpenShift、](https://www.openshift.com/try?utm_content=inline-mention) on Amazon、Azure 或 Google 的机器上部署它。”

[软件治理公司 Fianu Labs 的联合创始人 Michael Edenzon 告诉 New Stack，TriggerMesh 的云不可知论“在让开发人员更容易构建事件驱动的应用程序方面，绝对向前迈进了一大步。”](https://www.linkedin.com/in/medenzon/)

## 案例研究和使用案例

真实的组织如何在他们的事件驱动架构中使用 TriggerMesh？这里有两个例子。

### ManoMano:节省运行微服务的成本

总部位于欧洲的家居装修市场 ManoMano 是一家提供网络和移动体验的电子商务网站。其众多业务需求需要数百个[微服务。对于这么大的代码库，它依赖于不同的性能测试。](https://thenewstack.io/microservices-101/)

通过将 TriggerMesh 添加到其堆栈中，ManoMano 的[站点可靠性工程(SRE)](https://thenewstack.io/devops-institute-checks-the-pulse-of-sre/) 团队现在拥有了正确的软件工具来提供无服务器事件体验，允许测试开发人员在特定 AWS 事件发生时执行代码，方法是让测试开发人员订阅特定事件。

最近，ManoMano 开始涉足其长期运行的微服务。它们需要长时间运行并一直运行吗？它们的使用是否证明持续消耗计算资源和相关成本是合理的？

答案是否定的，这促使该公司开始只在需要的基础上运行服务。调查显示，这些服务中有许多每天只处理几个请求，并且大部分时间都处于闲置状态。

ManoMano 将长期运行的空闲任务替换为按需调度的容器，以运行 EKS 来响应 AWS S3 事件。这要归功于新的事件驱动架构，它从 AWS 服务收集事件，将它们吸收到一个集中的代理中，并允许开发人员订阅特定的事件以供使用。该平台将安全性和基础设施问题抽象化。

### Fianu 实验室:内部自动化软件治理

Fianu Labs 的全自动、事件驱动的软件治理工具在整个 [CI/CD](https://thenewstack.io/a-primer-continuous-integration-and-continuous-delivery-ci-cd/) 流程中提供工具，并在整个软件开发生命周期中捕获事件，并将它们与预定义的策略和自动化合规性文档进行比较。

TriggerMesh 位于[谷歌 Kubernetes 引擎和 Knative](https://thenewstack.io/tutorial-deploying-microservices-to-knative-running-on-google-kubernetes-engine/)之上，是 Fianu 架构的关键部分，贯穿于其工作流程的结构之中。虽然没有大规模运行，但 Fianu 需要冗余和可靠性，同时支持 200，000 个代码库，这大致可以分解为每分钟 500 到 1，000 个事件。

“TriggerMesh 工具和我们使用它的方式使我们能够保持一个健壮的、事件驱动的系统，并保持它非常整洁，”Fianu Labs 的 Edenzon 告诉新堆栈。

Fianu 内部典型的 TriggerMesh 工作流的一个例子是从摄取事件开始的。在接收事件时，Fianu 使用 TriggerMesh 函数(Fianu 使用嵌入式 Python，但 TriggerMesh 也有 Node.js 和 Ruby 选项)对有效负载进行转换和计算。

Edenzon 讨论了将字符串改为浮点数的例子，以确保输入的数据符合策略。虽然可能有一个输入数据源，但是可能需要许多不同的输出，并且 TriggerMesh 函数抽象出创建核心工具的需求。

“不需要创建一个无服务器的函数，我们可以嵌入 TriggerMesh 函数来执行小部分的业务逻辑，”他说。

TriggerMesh 目标是 Endezon 指出的 TriggerMesh 功能的另一个方面。Targets 允许 Fianu 的客户在 Fianu 软件的基础上进行定制，因为它有助于复杂的活动目的地，通过抽象出进入 Kafka 流或 slack 的活动的复杂性。

TriggerMesh 不仅帮助 Fianu 开发者，也帮助该公司的客户。Fianu 为其最终用户提供了许多开箱即用的功能，虽然该公司没有提供具体的 TriggerMesh 工具，但由于 TriggerMesh 的高度抽象，客户可以用任何语言编写自定义插件作为 Knative 函数，并将其放入运行的实例中，因为 TriggerMesh 将它们视为另一个事件处理器。

“作为开发人员，如果我们只需要关注业务功能，我们会非常有效率，”Edenzon 说。“所以这是我们喜欢[TriggerMesh]的原因之一。这使得我们能够非常轻松地隔离和测试业务功能。”

### 嵌入到 SaaS 应用中

TriggerMesh 使 SaaS 应用程序能够从多个云提供商获取事件，转换事件以匹配特定的模式，然后将这些事件发送到任何目的地。

“TriggerMesh 使得将新的事件源摄取到应用程序中变得非常容易，”Michaux 说。他补充说，“B2B SaaS 供应商可以扩展他们的应用生态系统，同时让开发团队专注于核心产品。”

在网络安全领域，这意味着在将不同的云安全事件发送到客户首选的安全解决方案进行分析和威胁检测之前，将它们转换为标准化的模式，例如最近发布的开放式网络安全模式框架。

对安全社区的价值非常高。由于安全威胁是实时发生的，其价值不仅在于收集数据或集成应用程序，还在于在事件发生时进行处理。

“一个典型的例子是有人试图登录系统失败，例如像 T2 甲骨文或 AWS 这样的云提供商，”Michaux 说。“这是威胁检测系统有兴趣分析的事件。TriggerMesh 可以帮助摄取事件，并以正确的格式实时将其传送到安全系统，而不会造成任何麻烦。”

## 结论

TriggerMesh 是一个用例满足需求并允许需求加速与技术交互的例子。它是开源的，现在唯一的要求是 Docker 和新发布的 Shaker，这使得采用变得更加容易。

“当充分利用 TriggerMesh 时，通过正确的应用程序设计，它允许您隔离业务功能，而不必担心数据如何到达哪里的机制，”Edenzon 说。“因此，您可以专注于业务功能”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>