# 停止谈论多云和混合云，开始谈论集成

> 原文：<https://thenewstack.io/stop-talking-about-multicloud-and-hybrid-cloud-and-start-talking-about-integration/>

[](https://www.linkedin.com/in/markrhinkle/)

 [马克·辛克尔

Mark 在新兴技术和开源领域有着悠久的历史。在共同创立 TriggerMesh 之前，他是 Node.js 基金会的执行董事，也是 Citrix、Cloud.com 和 Zenoss 的高管，在那里他领导了他们的开源工作。](https://www.linkedin.com/in/markrhinkle/) [](https://www.linkedin.com/in/markrhinkle/)

混合云和 T2 多云这两个术语在云用户中是两极分化的。从历史上看，混合云表明工作负载正在从私有数据中心转移到公共云。如今，它意味着本地应用程序和云中服务之间的集成。多云有着相似的起源——最初表示工作负载将根据价格和性能等情况从一个云迁移到另一个云。然而，这些用例就像骑着独角兽的小妖精一样难以辨认。现在，多云简单的说就是用户在使用多个云平台。如果云计算真的像宣传的那样，那么基础设施在哪里运行并不重要。

在每个企业中，公司都在使用来自多个云的服务。工作负载在哪里运行几乎变得无关紧要，只要有一种方法可以集成服务并(通过明智的选择)在没有过多工具的情况下管理它们。高质量云服务的激增使我们能够消费来自最佳提供商的服务来满足我们的特定需求。可能是亚马逊的对象存储，谷歌的计算，Salesforce 的 CRM，Splunk 和 Datadog 的管理服务。松散耦合的服务创建的应用程序是云服务的融合——通过网络组合——成为云原生应用程序。

这种设计模式非常类似于 20 世纪 90 年代后期倡导的面向服务的架构(SOA)。虽然它们不仅仅是 API 驱动的，而是事件驱动的。当互联网的使用在 20 世纪 90 年代首次出现快速增长时，大多数用户的带宽非常低，人们在电子邮件和网络之外消费的服务数量也很少。快进到 2021 年，今天我们有快速的互联网、无数的云服务、智能设备，以及对最新信息的不懈渴望——无论是脸书的状态更新，还是比特币或 GameStop 的最新价格。

## **API 与事件驱动架构**

云中有两种流行的交互模型。首先是 REST API(或者 RESTful API)。其余部分代表*具象状态转换*，API 代表*应用编程接口*。RESTful APIs 是系统之间进行交互的一种方式，就像对话一样。在 RESTful 架构中，有请求和响应；如此往复，直到信息被确定。这非常繁琐，需要同步通信。相比之下，事件驱动的架构就像是从消防水管中喝水——事件以异步方式流动，用户基于发布/订阅模型(称为发布/订阅)消费主题。

事件驱动架构可以有多种形式，但最常见的两种是 Webhook 和 streaming。在事件驱动的架构中，数据是实时到达的，而不是作为对查询的响应(与 API 方法一样)。例如，在 Webhook 的情况下，我们要求事件的生产者告诉我们一项工作何时完成；当事件发生时，我们会收到通知。那就是异步通信。在流的情况下，当状态改变时，我们接收事件。这可能是对数据库的更改、将文件上传到存储 blob 或完成无服务器功能。

## **事件驱动架构的兴起**

既然我们理解了什么是事件驱动，为什么它很重要？这很重要，因为这些事件被用来触发和传递分离的服务。事件只是系统中状态的变化。它可以携带状态(例如，在数据库中插入了一行)或标识符(例如，数据库脱机)。这些事件可用于触发工作流。云之间的这些工作流打破了孤岛，并提供了数据同步或复杂任务的完成。

这里有一个简单的多云例子:一个摄影师上传一张图片到亚马逊 S3，它创建了一个事件说有一张新图片。这一事件触发了谷歌视觉的机器学习来识别图像。一旦图像被识别，Google Vision 就会生成一个事件，表明该图像被识别为一只黑白狗，并将该图像插入到一个 [MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) Atlas 数据库中。这些信息、图像和其他相关细节随后通过托管在另一个云上的 JAMStack 网站呈现，如 Netlify 的 CDN(内容交付网络)。Netlify 在网络的边缘提供网站，更接近服务的消费者。因为网站与后端是分离的，这使得包含来自各种来源的数据成为可能——这些来源可以是最适合网站需求的云服务。

## **云中的事件驱动架构**

今天，云的结构已经变成了 Kubernetes。它无处不在，允许运行在容器中的应用程序的可移植性。用户通常在容器或无服务器功能中部署全天运行的微服务。这些函数能够使用事件相互通信。有许多事件流技术——一些可以跨越多个云，另一些特定于每个云。

Amazon [Kinesis](https://aws.amazon.com/kinesis/) 提供了一种在 AWS 中管理事件流的方法。 [Eventarc](https://cloud.google.com/blog/topics/developers-practitioners/eventarc-unified-eventing-experience-google-cloud) 是谷歌云的解决方案，用于将事件从谷歌服务发送到可以接收来自发布/订阅主题的消息的目标或服务。微软 Azure 的[事件网格](https://azure.microsoft.com/en-us/services/event-grid/)管理 Azure 云中从源到目的地的事件路由。这些解决方案是单一云事件流解决方案的良好范例。

想做多云怎么办？ [Apache Kafka](https://kafka.apache.org/) 是一个开源的分布式事件流平台。如今，它被广泛用于流式内部事件或来自云基础设施的事件。此外， [Confluent](https://www.confluent.io/) 提供 Apache Kafka 作为服务。

## **从多云/混合云到集成**

你可能会问:你怎么知道它是关于集成的？说实话，当我们在 2018 年成立 [TriggerMesh](https://triggermesh.com/?utm_content=inline-mention) 时，我们专注于多云无服务器管理。我们的论点是，云用户会想要跨所有云一致的工具。这个论点是正确的，尽管事实证明管理无服务器功能的部署相当容易。不容易的是提供云服务之间一致的通信方式。

随着我们继续与云服务用户交谈，我们意识到云架构师正在努力解决的问题不仅是如何在云服务之间进行通信，还包括如何路由事件流，有时甚至将这些事件从一种格式转换为另一种格式。我们看到新兴标准围绕着[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)的[云事件](https://cloudevents.io/)规范。

我们看到大型银行希望从 Azure 到 Splunk 过滤事件，以降低存储成本。通过 Apache Kafka 提供的事件流，我们与其他想要集成 Salesforce 和他们现有 ERP 系统的人进行了交谈。我们看到，像 Oracle 这样的一些云比三大云提供商的工具更少。他们需要将云指标传输到 Datadog。所有这些问题都是整合问题；源和目标位于云中和内部。这时“啊哈时刻”到来了，我们全力以赴进行整合。我们认为用于部署云基础设施的 [HashiCorp](https://www.hashicorp.com/?utm_content=inline-mention) 的[Terraform](https://www.terraform.io/)infra structure-as-code 之流的工具需要存在以进行集成(我们称之为 *integration-as-code)* 。这就是为什么服务在哪里并不重要——它只需要易于集成。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>