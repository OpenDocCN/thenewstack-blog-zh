# 案例研究:Fabric 如何使用无服务器来扰乱人寿保险市场

> 原文：<https://thenewstack.io/case-study-how-fabric-uses-serverless-to-disrupt-the-life-insurance-market/>

公司联合创始人兼首席技术官 [Steven Surgnier](https://www.linkedin.com/in/stevensurgnier/) 表示，Fabric 是一家专为初为人父母者设计的保险初创公司，其目标是成为“所有家庭开始财务生活的地方”。目前，该公司提供自愿服务和“简单、快速的意外和人寿保险”这两种产品都完全使用无服务器技术提供。

## 选择无服务器

Surgnier 说:“我们在开发环境中有一台服务器用于暂存，但在生产环境中我们完全没有服务器。

Surgnier 说，作为一个早期阶段的创业公司，决策归结为以最小的复杂性快速执行的能力。“我们需要缩短从最初的想法到最终产品到达客户手中的时间，”Surgnier 说。无服务器使这种产品开发速度得以实现。

此外，作为一个小团队，Fabric 不需要在其业务早期将他们的工程团队分成太多的特定角色。“我们是一个小团队，所以我们没有专门的 DevOps 团队，我们只有全栈工程师，”Surgnier 说。“我们寻找具有良好系统设计技能的工程师:理解整个系统如何工作非常重要。因为我们使用 AWS 的基础 API，比如云形成，所以我们使用的工具箱是 AWS 的工具箱。因此，这并不像我们的运营团队所说的，这是您将使用的数据库。我们希望我们的工程师熟悉 AWS 的技术。手握的不多。”

Surgnier 说，在过去几年中，对团队的这一要求变得越来越容易。作为 AWS Lambda 的早期采用者，从四年前开始，织物工程师开始使用最小的无服务器工具调色板进行绘画。依赖无服务器，尤其是在最新一代工具出现之前，给了 Fabric 的工程师们一个构建健壮的标准化流程的机会。“在过去的几年里，我们开发了良好的内部库和良好的内部实践。例如，我们有很好的内部方法来支持新的 API，所以我们能够利用那些痛苦的前期工作，我们不必一直这样做，”Surgnier 说。

Surgnier 说，该团队在 [AWS 云形成](https://aws.amazon.com/cloudformation/)中指定了 API，允许 [Swagger](https://swagger.io/) (又名[开放 API 倡议](https://www.openapis.org/)规范)作为导出，该团队尚未充分利用这一点。在定义 API 时，首先要支持 API 方法和资源，然后尽可能快地模仿，这样就可以用模仿数据来暴露它。然后他们就可以建立亚马逊网络服务的无服务器产品。

## 成本与速度

Surgnier 和 Fabric 在选择无服务器作为他们的架构技术方面肯定是站在速度一边的。“老实说，我对价格不太敏感。我们处理大量的 pdf 文件，如人寿保险的客户申请，使用这些数据必须被设计到我们的工作流程中。这些函数是用 Java 编写的，这可能是我们最慢的 API 调用。总的来说，这一切都是为了更快地执行和快速推出新产品。Lambda 的成本节约是一件好事。”

Surgnier 说，将产品送到客户手中的时间更快，部分原因是后端代码专注于业务逻辑。“代码更少，与基础设施的交互更少。所以有更多的机会关注契约和 API 的语义，”Surgnier 解释道。

## 管理安全性

Surgnier 指出了无服务器安全的两个元素，它们改变了团队从传统软件设计中的工作方式:身份访问管理(IAM)和 API 网关中安全问题的分离。

“在无服务器中，没有服务器位于数据库前面，是数据库的守卫，这就是传统 RESTful 微服务的外观，”Surgnier 逐步介绍了该架构。“我们有一个 DynamoDB 工作台和 S3。S3 直接与 DynamoDB 表对话，因此我们转到 IAM 来设置属性以允许对该表的访问。这是 Lambda 的一个独特阶段。您需要预先定义对数据的访问，因此您需要设置最小访问权限。默认情况下，我们的 Lambda 函数没有特权。然后我们有“已知商品”开始模板。然后，每个工程师都有责任为 IAM 设定适当的责任级别。”

Surgnier 还指出 API 网关是另一个安全方面。Surgnier 解释说:“API Gateway 的一个特性是安全问题的分离。“您可以将安全属性封装在一个单独的 Lambda 函数中，该 Lambda 函数可以 100%专注于安全逻辑。因此，安全团队可以专注于此，而后端团队则专注于业务逻辑。我预计在 Fabric，随着我们团队的壮大，我们将朝着这个方向前进。”

关注点的分离也适用于数据和分析。使用无服务器，可以分离数据和分析。建立一个 DynamoDB 流并消耗数据更改是可能的，因此工程师不需要在业务逻辑中记住托管分析数据。

## 前方的路

“所有这些都表明，老年退休金计划并没有消失，只是现在出现了一类不同的问题，”苏尔涅尔说。“我们真的希望后端工程师专注于业务逻辑，但他也能够专注于 Lambda 调用。要问这个 Lambda 函数需要为自己保留多大的并发份额？对于 DynamoDB 表，合适的写吞吐量和读吞吐量是多少？为此，我们在内部使用 Cloudwatch 来获取日志和指标。对于数据工程，我们正在使用 Kinesis 和 Athena。”

Surgnier 还计划继续构建他们的身份访问管理流程。随着工程变得足够大，以保证一个专门的安全团队，Surgnier 看到了一个点，该团队将拥有云形成模板的 IAM 权限。Surgnier 补充说:“理想情况下，这将从源代码中生成，而不是一堆与 API Gateway 中的自定义授权器配对的 JSON 文件，这些授权器是 Lambda 函数。”

总的来说，Surgnier 认为无服务器是 Fabric 的最佳决策，因为初创公司正在进入一个成熟的市场，并重振现有的产品供应。该公司正专注于倾听特定客户市场(年轻家庭)的声音，并满足他们的需求，这在更大的同质化行业方法中被边缘化了。

Surgnier 总结了 Fabric 的做法:“我们试图让默认情况下为你的家庭做出好的决定变得容易。保护你的家人应该不难，而且当你完成后，你应该感觉很好。我们希望这种体验能在品牌中得到体现。因此，我们专注于更好地倾听客户。每个伟大的公司都知道如何处理好这个问题。这只需要同情心和精力，不需要服务器。”

特征图片:截图来自[面料](http://meetfabric.com)网站。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>