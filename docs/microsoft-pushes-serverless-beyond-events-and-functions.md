# 微软推动无服务器超越事件和功能

> 原文：<https://thenewstack.io/microsoft-pushes-serverless-beyond-events-and-functions/>

微软继续向其无服务器产品添加新功能， [Azure Functions，](https://azure.microsoft.com/en-us/services/functions/)但在最近的 Build conference 上，该公司表示，它也在开发一系列工具和服务，这些工具和服务使用相同的理念，即不必关心从工作负载编排到 Python 机器学习的一切基础设施。

这是无服务器技术快速成熟的标志，其中一些新功能与开发无关，而是用于维护生产应用程序的监控和诊断。Application Insights 现在是 Azure 函数的默认监控体验，默认情况下为每个使用关联 id 的新函数应用程序(可用于现有函数)创建一个 Application Insights 实例，使执行计数器更快、更准确。

> Event Grid 是首批支持云计算原生计算基金会(Cloud Native Computing Foundation)新 CloudEvents 标准的公共云服务之一。

Functions 现在还使用 Azure App Service Diagnostics，它带有一个交互式机器人 Genie，可以建议诊断工具以及错误和性能问题的可能原因。这包括分析 CPU 和内存使用情况的功能健康检查。

超越功能， [Azure Event Grid](https://thenewstack.io/microsoft-azure-event-grid-goes-live/) 将无服务器操作的理念超越功能，应用于 Azure 上越来越多的服务。在构建时，微软宣布了多个新的事件源( [Azure Media Services](https://azure.microsoft.com/en-us/services/media-services/) 和 [Azure Container Registry](https://azure.microsoft.com/en-ca/services/container-registry/) )和目标( [Azure Storage Queues](https://azure.microsoft.com/en-ca/services/storage/queues/) 和[Azure Relay Hybrid Connections](https://docs.microsoft.com/en-us/azure/service-bus-relay/relay-what-is-it))以及输入映射，允许开发人员将他们自己模式中的字段映射到事件网格事件。为了支持像 IFTTT 这样不允许修改 HTTP 响应 POST 以进行安全验证的外部源，验证事件现在将包括一个针对 webhooks 的验证事件，其中向 URL 发出 GET 请求也会验证端点。

## 一连串的事件

微软计划使用无服务器合成模型从所有可以由事件网格管理的 Azure 服务中公开事件，混合连接允许在您自己的硬件上运行的 WebSockets 和服务器应用程序消费事件。这意味着 WebSocket 连接可以将事件中继到应用程序，该应用程序不能公开公共 HTTP 端点，因为它位于防火墙之后，甚至位于桌面 PC 上，因此它仍然可以获得实时通知。用于事件网格的新 Java 管理和客户端 SDK(以及。NET、Node、Python、Go 和 Ruby SDKs)简化了这种企业集成。

但是事件驱动的编程可以在多个公共云和框架上使用，Event Grid 现在也超越了 Azure，成为首批支持来自[Cloud Native Computing Foundation](https://www.cncf.io/)的新 CloudEvents 标准的公共云服务之一。最初的云事件规范非常类似于事件网格消息，事件网格可以将 Azure 存储事件发送到其他无服务器平台，或者消费来自其他 Cloud Events 服务的事件，并在 Azure 功能或连接到事件网格的逻辑应用中处理它们。CloudEvents 意味着同一个触发器，比如正在拍摄的照片，可以创建一个由 Azure 函数和 AWS Lambda 及其他服务消费的事件。

Azure Functions 高级项目经理[杰夫·霍兰](https://github.com/jeffhollan)告诉新的堆栈，随着 Azure Functions 可构建的范围增加，CloudEvent 支持也将开始扩展。取方式[耐用功能](https://thenewstack.io/durable-functions-making-serverless-last/)简化操控状态。这已经超出了预览版，给了 Azure 函数一种编排长时间运行的有状态工作负载的方式，这样开发人员可以将复杂的场景链接在一起，使用扇入和扇出模式进行扩展，或者处理长时间的回调而不保持函数运行。

这意味着函数支持设计模式，如 Map-Reduce、异步 HTTP APIs 和编排来自人类以及其他系统的输入，这几乎总是异步的。现在通过 node.js 支持用 JavaScript 编写 orchestrator 函数，尽管它还在预览版中，因为它需要 Azure Functions v2 运行时。

除了 Azure 功能之外，状态是无服务器开发人员需要处理的事情，问题是抽象服务可以提供多少来简化任务，因为即使是 CloudEvents 在这里也没有帮助。霍兰指出:“目前对 CloudEvents 进行范围界定的方式，仅仅是关于被发送的消息的形状，而对于消息如何到达那里等问题，它是非常独立的。”

“CloudEvents 只是表示你的状态发生了某种变化的信号；它不包含状态。我们才刚刚开始。开发人员的梦想总是我不关心我的状态存储在哪里或如何存储，我只想以一种超级解耦的方式编写代码，”Hollan 说。“我们正在考虑这样一个世界，我构建应用程序，我想要一些东西来响应事件，也许很多决定是为你做的，因为我不在乎这些。如果状态在 S3 桶或 Azure blob 中，或者在 Cosmos DB 或 MongoDB 中，当我不关心状态在哪里时，我们可能需要一个抽象层，无服务器函数应该只知道我有一个新文档，并使用存储状态的任何服务。”

目前，Azure Functions 有一个选项，开发者可以选择新功能是在 Linux 还是 Windows Server 上运行。对于无服务器服务来说，这似乎很奇怪，但它是存在的，因为 Linux 支持在预览版中，而 Windows 支持没有。从长远来看，该配置将转移到 Azure DevOps 项目。最初，这提供了一种非常简单的方法来获取虚拟机或 Azure 应用服务上运行的应用程序，并使用 Visual Studio Team Services 为它们提供 CI/CD 管道。截至构建，它还包括 Azure Kubernetes 服务。NET、Java 和 Node.js web 应用程序管道，以及对. NET 的 Azure 服务结构支持。

这个想法是用智能默认值来指导开发人员运行语言和开发人员正在开发的应用程序类型的推荐路径，Hollan 建议 CloudEvents 将有助于实现这一点。“我们希望它足够简单，一个对云感到恐惧但知道 node.js 和网站是什么的全新开发人员可以选择无服务器。不要让我在他们抛给他们的这么多新概念中做出选择，我只会坚持内部部署，因为分布式计算世界让我害怕。如果我想以一种不管理任何基础设施的方式来托管它，也许我不必知道更改设置是否意味着某些东西将作为功能或 pod 存在于 Kubernetes 群集中，因为事件将是相同的。”

如果 CloudEvents 起飞并获得整个行业的支持，Hollan 希望看到我们如何管理和监控这些解耦流程的更多创新。“构建第一个甚至第十个函数时，你可能会很兴奋，但当你构建到 30 或 40 个函数时，现在你已经有了所有这些独立运行的小程序。您如何确保对它们都有所了解，以便能够管理解决方案和部署解决方案的更新？我知道有来自 Salesforce 的事件，但是每当我添加一个客户时，会有多少功能在运转？如果我更改我的 Salesforce 数据库中的内容，我知道会有多少功能被锁定吗？”

## 更多地使用 Azure 无服务器

其他 Azure 服务中也出现了无服务器模式。新的 Azure Machine Learning SDK for Python 可与所有 Python 兼容的机器学习框架(如 TensorFlow 和 CNTK)配合使用，涵盖了从模型训练到部署到评分的关键机器学习工作流，并在无服务器结构上调度和管理这些工作流的各个阶段，混合了 CPU 和 GPU 配置以适应不同的工作。

新的 [Azure Service Fabric Mesh](https://azure.microsoft.com/en-us/blog/azure-service-fabric-at-microsoft-build-2018/) 预览版意味着您不再需要设置 Service Fabric orchestrator、配置虚拟机、将它们添加到集群以及逐步完成一系列管理任务来运行容器化的应用程序。在 Visual Studio 中创建一个服务网格应用程序项目，该服务现在处理创建 Azure 资源组、设置容器和创建自动放置规则，以遵守为应用程序指定的放置约束，使用 Windows、Linux、Java 和。NET，包括有状态服务和可靠集合。

这将 Service Fabric 转变为一个全面管理、可扩展的“按使用付费”的无服务器微服务平台，该平台可以在 Azure 或本地编排工作负载，可以通过模拟的 Service Fabric 集群或在您自己的服务器上的独立集群上进行本地调试，也可以在另一个公共云甚至是物联网设备上进行调试，所有这些都通过 Azure 门户进行管理。

“Azure Functions 是一个编程模型，但无服务器更多的是一个计费模型，”Hollan 指出。“我们有带 ACI 的无服务器容器，我们有带服务结构的无服务器网状网络。它们是不同的编程模型。功能是说“把我和一个事件联系起来。”有了 ACI,“给我一个完整容器映像并按需计算，但我对计算不是很有意见”,而且您仍然可以获得无服务器的经济性。如果你有一个需要八个小时处理的机器学习工作，你永远不会用 Azure 函数来做，但你可以启动 ACI 来处理视频，压缩视频并给视频加字幕。这是一个重量级的过程，但仍然可以是无服务器的。"

这表明更多的 Azure 服务将提供无服务器的方法，以及连接到事件网格和通过 CloudEvents 输出。

“我只在使用时才付费的按需计算的概念将会广泛传播，”Hollan 说。“它比单个功能大得多。我们将进入一个所有必要的计算都应随需应变的世界。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>