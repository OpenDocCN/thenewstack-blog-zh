# TriggerMesh 集成平台现在是一个开源项目

> 原文：<https://thenewstack.io/triggermesh-integration-platform-now-an-open-source-project/>

更正:本文的前一个版本错误地将 TriggerMesh 的方法描述为“基础设施即代码”该公司的方法是“代码集成”

云原生集成平台 TriggerMesh ，该公司周二在今年于洛杉机举行的[kube con+CloudNativeCon North America](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)上宣布，已经推出了其作为开源项目的旗舰产品。

该集成平台旨在使跨越多个云和内部数据中心的[数据](https://thenewstack.io/category/data/)和[云原生](https://thenewstack.io/category/cloud-native/)应用程序的连接更加容易和快速，现已在 Apache 软件许可证 2.0 下提供。([下面是 GitHub 回购](https://github.com/triggermesh/triggermesh)。)

TriggerMesh 的平台集成方法与“基础设施即代码”类似，Anisble、Chef、 [Hashicorp](https://www.hashicorp.com/?utm_content=inline-mention) 和 [Puppet](https://puppet.com/?utm_content=inline-mention) 等解决方案有助于将基础设施部署到 [DevOps 团队](https://thenewstack.io/category/devops/)。

该公司称其方法为“代码集成”它建立在 Kubernetes 的基础上，并提供了一个声明式 API 和一个集成语言来将数据和服务快速连接到事件驱动的应用程序中。

该平台允许开发运维人员和云运营商以代码形式部署集成，从而加快价值实现。它基于事件驱动的方法，消费来自各种来源的消息(如 [AWS](https://aws.amazon.com/?utm_content=inline-mention) SQS、谷歌存储、Azure 活动日志)，过滤并转换它们，向无服务器功能添加处理能力，并与消息接收器连接(如 Elasticsearch、AWS S3 和 Apache Kafka)。

TriggerMesh 集成平台旨在与遗留企业服务总线(或 ESB)集成，以创建应用程序之间的工作流，或其他系统的数据汇(如 Azure 数据湖或雪花)。

TriggerMesh 的联合创始人 Sebastien Goasguen 在 2020 年的 Makers 播客中告诉新堆栈的创始人兼发行人 Alex Williams，事件驱动的架构使开发人员可以专注于创建他们的应用程序，而不是管理他们的部署。

## 合并所有回购

对于 TriggerMesh 的联合创始人兼产品负责人 Goasguen 来说，让 TriggerMesh 集成平台开源既是自然的进化，也是合乎逻辑的商业决策。

Goasguen 和他的公司的首席执行官兼联合创始人[马克·辛克尔](https://www.linkedin.com/in/markrhinkle/)都在开源领域有很深的渊源。在他们 2018 年开始 TriggerMesh 之前，Goasguen 为 Kubernetes 创立了 Kubeless serverless 框架，Hinkle 是 Node.js 基金会的执行董事。

“作为企业主，你需要弄清楚什么对实际业务有意义，当你是一家小型创业公司时，这并不总是容易的，”Goasguen 在 9 月份告诉 New Stack。

欣克尔[在 3 月](https://thenewstack.io/stop-talking-about-multicloud-and-hybrid-cloud-and-start-talking-about-integration/)写给新堆栈的一篇文章中写道:公司成立时，专注于多云无服务器管理。然而，一旦它的领导者开始与云服务用户交谈，它就将重心转移到了整合上。

Hinkle 写道:“我们的论点是，云用户希望工具在所有云中保持一致。”“这个论点是正确的，尽管事实证明管理无服务器功能的部署相当容易。不容易的是提供云服务之间一致的通信方式。”

2020 年，TriggerMesh 获得了 300 万美元的种子资金。从那时起，Goasguen 说，“我们正在试验和开发我们的产品市场适合度，并试图真正了解客户在整合方面的需求。”

在过去的一年半时间里，该公司为其产品开发了多种功能，涉及事件管理、无服务器功能、事件源和事件接收器的目录。

“其中一些已经是开源的，”他在周二声明的几周前指出。“但我们还没有真正推动围绕这一点建立一个社区，因为这还为时过早。如果你去我们的 GitHub 回购，你实际上会看到我们平台的大部分都已经开源了——但是是在单独的回购中。”

他说，现在这个项目已经更加成熟了，想法已经改变了。“我们创建了这个整合平台。我们将把这个平台开源为一个内聚的代码库。”

## 更多资源来建立一个社区

7 月，TriggerMesh [获得了来自思科和包括 Crane 和 Index Ventures 在内的现有投资者的额外战略资金](https://www.triggermesh.com/blog/cloud-native-integration-platform-triggermesh-receives-strategic-funding-from-cisco-investments-existing-investors)。Goasguen 说，这笔钱将有助于为 TriggerMesh 提供资源，帮助它围绕其开源项目发展一个社区。

“我们有足够的资源来推动开发者社区的发展，帮助人们参与进来并管理这个社区。现在是真正推进的时候了。”

Goasguen 说，在这个项目中，考虑将 TriggerMesh 集成平台提交给[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)进行孵化还为时过早。

“我们的最终目标是，如果我们成功地利用现有的用户和客户围绕这个平台建立了一个成功的社区，那么向 CNCF 提出这个建议是完全有意义的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>