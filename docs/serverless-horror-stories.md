# 无服务器恐怖故事

> 原文：<https://thenewstack.io/serverless-horror-stories/>

[](https://www.linkedin.com/in/emrahsamdan/)

 [艾姆拉·萨姆丹

艾姆拉是桑德拉公司的产品副总裁。他热衷于无服务器、可观测性和混沌工程。](https://www.linkedin.com/in/emrahsamdan/) [](https://www.linkedin.com/in/emrahsamdan/)

无服务器是一个强大的范例，它让应用程序开发人员专注于业务逻辑，而不是可伸缩性或服务器维护。但是，了解可能对性能和/或预算产生毁灭性影响的基本无服务器特性非常重要。

在本文中，我们总结了一些现实生活中的恐怖故事，说明了无服务器在生产中的潜在问题，以及如何避免它们。有关这些案例研究的更详细描述，请[下载我们的白皮书](https://www.thundra.io/whitepaper/serverless-horror-stories?utm_source=newstack&utm_medium=paid&utm_campaign=WP-Serverless%20Horror%20Stories&utm_content=lp_slsHorrorStories)。

## 代价高昂的错误

当您为每个服务器实例付费时，成本是不变的——无论服务器是过载还是空闲。如果超载，它可能会崩溃，但不会增加账单。

另一方面，Amazon Web Services 的 Lambda 函数会自动伸缩以适应工作负载。这通常有利于应用程序的弹性和持续的突发峰值，但必须小心监控，正如我们在 Kevin Vandenborne 的文章“[无服务器:吸取的教训”中了解到的那样。敬酒不吃吃罚酒](https://sourcebox.be/serverless-a-lesson-learned-the-hard-way/)

一天早上，Kevin 收到一个 AWS 通知，说发现基础架构成本超支，从预算的 5.00 美元到预测的 83.28 美元。当他登录 AWS 控制台时，实际余额已经是 206.14 美元。一个简短的调查揭示了他的 S3 存储桶配置中的一个简单错误，这个错误导致了一个无限调用循环和一个比预期更大的 AWS 账单。

这个故事告诉我们，仔细监控 Lambda 函数工作负载对于意外流量的重要性，意外流量会推高成本，并使您的云账单高度不可预测。为此，桑德拉具备[主动异常检测功能，支持 insights](https://docs.thundra.io/thundra-web-console/dashboard-page#charts-with-anomalies) 修改，以便在出现意外流量时向您发出警告。

## 选择正确的使用案例

当用于具有变化的工作负载或不可预测的使用峰值的应用程序时，无服务器非常出色，因为无服务器服务可以根据工作负载的大小按需扩展和缩减。因此，您花费了更多的钱来覆盖峰值，但是在不使用 API 时节省了资金。

然而，Einar Egilsson 发现，对于持续繁重的工作负载，无服务器架构实际上比配置服务器或服务器集群来处理负载更慢、更昂贵。在一篇题为“[无服务器:速度慢 15%，成本高 8 倍](https://einaregilsson.com/serverless-15-percent-slower-and-eight-times-more-expensive/)”的帖子中，他描述了他的公司的 API 层从基于 Linux 的服务器到 AWS Lambda/API 网关架构的 POC 迁移如何导致性能慢 15%，成本高 8 倍。

因为 Lambdas 在高抽象层上工作，所以它们总是比手工制作的优化实现要慢一些。成本上的巨大差异与该公司的 API 服务器每天处理约 1000 万个请求的繁重且持续的工作负载是一致的。对于繁重的工作负载，API Gateway 甚至比 Lambdas 本身更昂贵。

## 百万美元的工程问题

事件驱动的无服务器架构的一个众所周知的挑战是难以端到端地跟踪请求，以便调查性能问题。

一个恰当的例子是，[分部的公司](https://segment.com/blog/the-million-dollar-eng-problem/)遇到了一个流行的无服务器服务 DynamoDB 的问题。细分市场的 DynamoDB 实例遇到了严重的性能问题，降低了整个系统的速度。为了缓解这一问题，该公司不得不增加数据库实例的调配吞吐量，但这反过来大大增加了他们的 AWS 账单。

当部门自己的故障排除工作未能发现问题时，他们向 AWS 支持寻求帮助。使用内部工具，AWS 生成了 DynamoDB 实例的分区热图。尽管热图可读性不强，但他们能够发现有性能问题的单个数据库分区，这清楚地表明他们的工作负载没有在分区之间均匀分布。

然而，仍然不清楚哪些记录或密钥有问题。因此，Segment 继续调查这个问题，并发现了一个相对较小的 bug，这个 bug 很难发现，但在修复后，他们的 DynamoDB 容量减少了四分之一，每年为他们节省了 30 万美元。

如果他们查看针对某些请求的单个邮件，调查可能会花费更少的时间。[桑德拉的跟踪地图](https://blog.thundra.io/enhancing-distributed-tracing-with-business-context)展示了请求的完整冒险，让你点击几次就能注意到这样的问题。

## 死亡的队列

一个非常相似的故事发生在 Solita 身上，它发现了 SQS 和 Lambda 设置的问题。在详细的测试之后，Solita 注意到来自 SQS 队列的一些消息没有被 Lambda 函数处理，并且[在死信队列](https://data.solita.fi/lessons-learned-from-combining-sqs-and-lambda-in-a-data-project/)中结束。

Solita 对这种情况感到困惑:消息是有效的，应用程序日志中没有错误，而且这个问题显然只在高负载下出现。最后，他们注意到无效行为只发生在 Lambda 节流同时发生的时候。

在深入研究 AWS 文档后，他们发现根本原因是 SQS 和 Lambda 配置设置的组合，由于 Lambda 限制，这些设置导致消息被多次拒绝。结果，它们无法被处理，最终被放在死信队列中。

## 避免无服务器生产的恐惧

Solita 和 Segment 故事都强调了测试无服务器应用程序和捕捉潜在问题(其中一些可能非常微妙)的重要性，以免它们成为生产环境中的恐怖故事。

确保顺利进行无服务器部署的其他方法包括:

*   **了解你的服务**:虽然无服务器简化了基础设施管理，但它不是即插即用的。您需要了解您所使用的无服务器服务的配置细节，以及它们是如何工作的。此外，您必须了解按使用付费模式的影响，以便控制基础架构成本。
*   **监控和警报**:无服务器是一个相对较新的范例，有许多异步事件和并行执行，加上一个阻碍可见性的高抽象层。您必须确保知道如何跟踪服务的状态，如何识别性能问题，以及如何发现执行问题—通过警报来帮助防止意外的基础架构成本超支。
*   **下一代工具**:专业的人工智能驱动平台，如桑德拉，提供实时可视化和跟踪，这对监控、调试、故障排除和保护无服务器应用至关重要。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>