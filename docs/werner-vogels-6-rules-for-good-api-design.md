# 沃纳·沃格尔良好 API 设计的 6 条规则

> 原文：<https://thenewstack.io/werner-vogels-6-rules-for-good-api-design/>

如果有一家公司应该知道如何构建应用编程接口(API)，那应该是[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)。这个云巨人处理[5 亿 API 调用*第二个*](https://twitter.com/Joab_Jackson/status/1466458112190124033) 仅仅是为了它的身份和访问管理服务——将用户和机器登录到 AWS 云资源。

不过，正如 AWS 首席技术官[沃纳·威格尔](https://twitter.com/Werner)在本周于拉斯韦加斯举行的 AWS re:Invent 用户大会的主题演讲中指出的那样，该公司仍在学习如何最好地创建和管理 API。

他描述了该公司在 API 设计方面的早期失误。沃格尔斯告诉观众，每个 AWS 服务都由一个团队管理，每个团队都专注于“准确解决我们客户的需求，并从他们的需求开始逆向工作”。援引过早优化的危险，沃格尔斯警告说，在了解如何使用 API 之前就考虑为它们设计统一的格式将会“扼杀创新”，这是非常危险的

但是，每个团队首先关注客户需求的问题意味着在 API 的设计上没有集中的协调。因此，每个团队的 API 在 API 格式上可能略有不同。例如，Lambda 函数的 API 调用与 Kinesis 调用的结构不同:

`aws lambda get-function --function-name WernersFunction`

`aws kinesis describe-stream --stream-name WernersStream`

整体来看，这两者在调用 API 的方式上并不一致。这导致了开发人员生产力的损失，他们需要记住更多的 API 结构，并且需要做更多的工作来编写这些 API 调用的脚本。沃格尔斯承认，这种缺乏一致性一直是客户和合作伙伴的痛处。

所以，为了解决这个问题，公司在 9 月份发布了[云控制 API](https://docs.aws.amazon.com/cloudcontrolapi/latest/userguide/what-is-cloudcontrolapi.html) 。云控制允许用户使用一组标准化的应用编程接口(API)来创建、读取、更新、删除和列出(CRUD-L)云资源[。对于用户来说，这消除了为负责这些资源的每个服务生成特定代码或脚本的需要。对于 API 设计者来说，它提供了一种方法来继续支持旧的 API 版本，同时还保持这些服务以另一种更标准化的格式可用。](https://thenewstack.io/aws-dev-tools-head-ken-exner-one-cloud-api-to-rule-them-all/)

作为一个统一的控制平面，云控制不仅适用于 AWS 资源，也适用于第三方资源。 [HashiCorp](https://www.hashicorp.com/?utm_content=inline-mention) 例如，[发布了](https://www.hashicorp.com/blog/announcing-terraform-aws-cloud-control-provider-tech-preview)一个云控制连接器，用于自动化 AWS 上基于地形的部署。

## API 设计的六个最佳实践(和一个工具)

沃格尔斯指出，今年是 AWS 开展业务的第 15 个年头，考虑到这一点，他列出了 AWS 在创建面向客户的 API 时积累的一些经验。这里有六个:

一旦创建了 API，就不应该删除或更改它。“一旦你发布了一个 API，企业将在它的基础上建立，”沃格尔斯说，并补充说，改变 API 将基本上打破他们的业务。

*   **永不破坏向后兼容性**

向后能力是必须的。这并不是说你不能修改或改进 API。但是无论你做什么改变都不应该改变 API，这样来自以前版本的调用就不会受到影响。例如，自 2006 年推出以来，AWS 以多种方式增强了其简单存储服务(S3 ),但仍支持第一代 API。

*   **从客户用例向后工作**

设计 API 的方法是不要从工程师*认为*会做出好的 API 开始。相反，首先弄清楚你的用户需要从 API 中得到什么，然后“从他们的用例开始逆向工作”。然后想出一个你能实际提供的最小最简单的 API，”沃格尔斯说。

作为一个例子，沃格尔斯描述了一个可以用于多种活动的广告系统。不要为每个新的活动修改 API，而是用多个标志修饰它，维护一个核心活动 API 调用，然后围绕它构建其他兼容的 API。让你的 API 尽可能简单，这样它们就可以成为其他人使用的构建模块。

*   **创建自我描述的 API，并具有清晰明确的目的**

当然，文档应该始终保持完整和最新，但是 API 本身也应该一目了然。“你应该能够查看 API，并且总是能够弄清楚它做了什么，”沃格尔斯说。

*   **创建具有明确和良好记录的故障模式的 API**

说到文档，描述 API 的故障模式——错误的输入参数、安全性考虑——也需要包括在内。“因为这不仅仅是关于你的 API 做了什么，而是它是如何失败的，”沃格尔斯说。

*   **不惜一切代价避免泄露实施细节**

泄漏实现是底层实现细节成为 API 本身的一部分——例如，对特定软件的引用。沃格尔斯说，这可能会有问题，因为客户会越来越依赖这些非必要的细节，“你不能再改变这种实现方式”。

这里有一个 AWS 工具可以提供帮助，那就是史密斯公司，这是一个开源程序，可以帮助组织[在 API 设计上合作](https://www.youtube.com/watch?v=3GpZzu4guTE)。它生成的 API 模板很容易被其他格式覆盖，比如 OpenAPI。

[https://www.youtube.com/embed/8_Xs8Ik0h1w?feature=oembed](https://www.youtube.com/embed/8_Xs8Ik0h1w?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>