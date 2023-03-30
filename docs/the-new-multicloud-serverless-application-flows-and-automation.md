# 新的多云:无服务器、应用流和自动化

> 原文：<https://thenewstack.io/the-new-multicloud-serverless-application-flows-and-automation/>

[TriggerMesh](https://triggermesh.com/) 赞助了这篇文章。

 [马克·辛克尔

Mark 在新兴技术和开源领域有着悠久的历史。在共同创立 TriggerMesh 之前，他是 Node.js 基金会的执行董事，也是 Citrix、Cloud.com 和 Zenoss 的高管，在那里他领导了他们的开源工作。](https://www.linkedin.com/in/markrhinkle/) 

当人们听到*无服务器*这个词时，往往会联想到在 Amazon Lambda 上执行的功能即服务的图像。但这只是一个方面。顾名思义，它是提供云原生应用程序所需的所有基础设施的抽象。这包括像[谷歌云存储](https://cloud.google.com/storage)这样的存储，像 [Azure SQL](https://techcommunity.microsoft.com/t5/azure-sql/optimize-price-performance-with-compute-auto-scaling-in-azure/ba-p/966149) 这样的数据库，以及像 Confluent 的[托管版](https://www.confluent.io/confluent-cloud/tryfree/)Apache Kafka 提供的分析。请注意，我的例子跨越了三个不同的云提供商。这是因为随着我们走向一个更加无服务器的世界，我们很可能会采用多云方法，在这种方法中，我们使用来自多个提供商的最佳服务。不要与在多个云提供商的类似基础设施上运行相同的工作负载相混淆，这是一个更过时的定义，也是云专家和 AWS 观察家[、Corey Quinn](https://twitter.com/QuinnyPig) 、[在最近一篇虽然经过深思熟虑但却尖刻讽刺](https://www.lastweekinaws.com/blog/multi-cloud-is-the-worst-practice/)的用例。

我同意多云不是当今的标准，但它是 20 世纪 90 年代用面向服务的架构(SOA)提出的愿景，并且它是我们在 2020 年非常接近的东西。

*面向服务的架构(SOA)是一种软件设计风格，其中应用组件通过网络上的通信协议向其他组件提供服务。SOA 服务是一个独立的功能单元，可以远程访问、独立操作和更新，比如在线检索信用卡对账单。SOA 还旨在独立于供应商、产品和技术。* [*百科*](https://en.wikipedia.org/wiki/Service-oriented_architecture)

其思想是大型软件应用程序可以分解为提供离散功能的服务。这些是“黑盒”服务，底层基础设施是从最终用户那里抽象出来的。服务被组合在一起，作为一个应用程序连贯地运行。

## **微服务和事件驱动架构**

随着微服务作为一种设计模式的发展，我们看到 Google、Red Hat、Datadog、Twilio、Salesforce 等基础设施提供商既提供通用基础设施(如对象存储)，也提供更专业的服务，如机器学习和监控。理想情况下，在云的原生世界中，您应该使用同类最佳的方法来组合所有这些服务，以创建一个应用程序。

那么这些服务交互的框架是什么呢？事件、事件和事件。事件只是从一个系统到另一个系统的消息，其中一个系统中的变化被传递到另一个系统。例如，当数据集被上传到对象存储时，机器学习服务可以提供数据集内容的一些分析。

这些事件在系统之间来回流动，使用一个系统的结果来驱动另一个系统的结果。这是一个事件驱动架构(EDA)。实时流式传输这些事件为应用程序提供了数据管道、流式分析和数据集成。分享活动的流行方式是通过流媒体平台，如 [Apache Kafka](https://kafka.apache.org/) 或消息中介，如[Rabbit MQ](https://www.rabbitmq.com/)(VMware Tanzu 产品组合的一部分)。

EDA 的趋势正被业内一些最大的公司所利用。例如，SAP 正在开发 Kyma，这是一个基于 Knative 的无服务器功能和微服务的应用扩展平台。它提供了一系列云原生项目，简化了扩展的创建和管理。Kyma 项目围绕赛事提出了以下愿景:

*   使客户能够插入最符合其需求的消息传递中间件，并并行运行多个消息传递实现。
*   过滤事件并仅传输那些具有现有订阅(触发器)的事件。
*   支持在单个请求中发送多个事件。

[Cloud Run for Anthos](https://cloud.google.com/anthos/run) ，一个基于谷歌 Kubernetes Engine (GKE)的无服务器开发平台，也由 Knative 提供支持，现在包括一个[事件功能](https://cloud.google.com/blog/products/serverless/cloud-run-for-anthos-adds-events)，允许用户在谷歌云上运行事件驱动的系统。一些例子包括:

*   云存储事件触发数据处理管道。
*   每次数据加载完成时，BigQuery 审计日志事件都会启动一个进程。
*   云调度器事件触发批处理作业，这与 Linux 系统上的 cronjob 没有什么不同，但是基于云。

事实上，这些功能正在进入产品，这表明未来是事件驱动的，并将加速云原生应用的自动化。

## **申请流程**

在这一点上，绝大多数 EDA 似乎都被软件的更技术性的基础所吸引。例如， [GitHub Actions](https://github.com/features/actions) ，自动化 CI/CD、构建、测试和部署的软件工作流。另一个例子是 AWS EventBridge，它从 SaaS(如 Zendesk 和 Auth0)接收事件，并将它们路由到 AWS 服务(如 Lambda)。

然而，从长远来看，将云服务结合在一起的能力不仅仅与我所说的通用基础架构(存储、计算和网络)相关，而是更专业的服务，这将提供更强大的应用程序。例如，在 [TriggerMesh](https://triggermesh.com/) ，我们正在寻找在 Salesforce 和 data lakes 之间共享数据的方法，这些数据可以由 Elastic 进一步分析。或者从 GitHub 到 Twilio/SendGrid，或者从 Azure logs 到 Splunk，或者从 SonarSource static code analysis 到 Kaka 转换和过滤事件——在每种情况下都将它们导出为云事件，可以由 Google、Microsoft 和 Amazon clouds 上的服务使用。

## **总结**

我们正进入一个激动人心的时代。从价格和易用性的角度来看，基础设施从未如此容易获得。微服务是单片中使用的软件库的云本地代理。当您将它们组合在一起时，您可以创建应用程序—不仅仅是客户端-服务器，而是跨越云甚至内部数据中心的独立网络应用程序。由于事件驱动的架构和无处不在的低延迟网络，这些应用程序能够更快地实时移动。这是一个罕见的时代，一个前进时代的愿景已经开始按照预想显现，甚至可能超过原作者的愿景。

Amazon Web Services 和 Confluent 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>