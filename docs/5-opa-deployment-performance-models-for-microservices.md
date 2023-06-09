# 微服务的 5 个 OPA 部署性能模型

> 原文：<https://thenewstack.io/5-opa-deployment-performance-models-for-microservices/>

[](https://www.linkedin.com/in/anderseknert/)

 [安德斯·埃克纳特

Anders Eknert 是 Styra 的一名开发人员支持者，在主要是分布式环境中的软件开发、安全和身份系统方面有着长期的背景。不在电脑前时，他喜欢看足球、烹饪和比利时啤酒。请在 Twitter 上关注他，地址是@ anderseknert](https://www.linkedin.com/in/anderseknert/) [](https://www.linkedin.com/in/anderseknert/)

如果你负责一个微服务应用，你可能对“延迟预算”这个概念很熟悉这是应用程序运行所需的最大延迟，以总请求时间衡量，以满足您的 SLA 并让利益相关方满意。对于股票交易或金融服务应用程序来说，这个预算可能是最少的微秒。对于一个显示来电者业务信息的销售相关服务应用程序，预算是 250 毫秒(再久一点，这个人已经拿起电话了)。

如果您在微服务应用中使用[开放策略代理](https://www.openpolicyagent.org/) (OPA)进行授权或策略决策，OPA 将成为您延迟预算中的一个“行项目”。几乎总是，最大的延迟不是“花费”在 OPA 本身上，而是到达 OPA 进行策略决策所需的网络跳数。接下来的问题是——这是最常见的 OPA 问题之一——在集群中的何处放置 OPA(或策略执行点),以最大限度地提高延迟性能，同时确保数据安全。

顺便说一句，通过遵循最佳实践，有许多方法可以优化 OPA 内部的[策略性能](https://www.openpolicyagent.org/docs/latest/policy-performance/)——比如优先选择对象而不是数组，并确保语句被正确索引。如果想完全避免网络调用，还可以在应用程序内部评估 OPA 策略。在 Go 应用中，这可以通过将 OPA 集成为一个[库](https://www.openpolicyagent.org/docs/latest/integration/#integrating-with-the-go-api)来实现。对于其他场景，您可能会选择将减压阀策略编译到 [WebAssembly](https://www.openpolicyagent.org/docs/latest/integration/#webassembly-wasm) 中。不过，总的来说，这些情况是例外，而不是规律。

当您需要在应用之外部署 OPA 时，这里有一些最受欢迎的微服务 OPA 部署性能模型，以及一些可以让您的创意架构发挥作用的*rubs hands* *实验性*模型。没有正确或错误的答案；凭借 OPA 的灵活性，只需为您的环境和延迟需求找到合适的策略模型。该是橡胶上路的时候了。

## **1。网关型号(集中式)**

OPA 最流行的策略模型是传统的网关或防火墙模型。大多数开发人员都熟悉这种体系结构，您猜对了，它将 OPA 实例放在保护您的集群的网关上。这意味着授权和策略决策有一个单一的集中位置，所有下游流量都被认为是经过授权的。与所有的[集中式模型](https://blog.styra.com/blog/centralized-vs.-distributed-authorization-the-cap-theorem)一样，所有的授权决定都必须经过一个或多个网络中继才能到达 OPA 实例。

借助 OPA 与 Kong 和 Apogee 等流行工具的集成，网关模型对许多部署都有意义。也就是说，尽管是最快的模型之一(通常只需要一次网络跳跃)，网关模型不一定是最安全的。例如，如果一个恶意实体以某种方式绕过网关，它就是通往整个集群的免费高速公路——因为在那个阶段所有的流量都是“假定授权的”。另一个权衡:网关上的 OPA 实例不能完成对内部服务的授权，比如 cron 作业，它不通过网关。

**优势:**快速、流行、熟悉、简单(几十年的老策略)。

**挑战:**单点故障，无内部保护，可能对安全过于宽容。

## **2。【接近数据】模式(集中式)**

然后是相反的情况:将 OPA 移到堆栈的后面，靠近数据。例如，如果您有一个与数据库通信的数据层，那么这就是您应该放置 OPA 实例的地方。该模型与网关模型具有相似的性能特征，因为授权或策略决策仍然由单个集中式服务点做出，这需要网络跳跃。然而，好处是您可以更好地保护您的数据；即使攻击者攻破了网关，他们也无法在未经授权的情况下获取您的数据。这种模式的一个缺点是，在您的集群中可能有您想要保护的其他项目—其他服务、API 等等—这意味着您将需要在其他地方创建额外的 OPA 实例。因此，您的集群中的 OPA 策略实施点可能变得有些武断或随意。

**优点:**速度快，为你的数据提供安全保障(不是为你的服务)。

**挑战:**当您需要保护集群中的其他服务时，任意强制执行。

## **3。“全面实施 OPA”模式(分布式)**

杰夫·贝索斯很有先见之明，他要求亚马逊的每个内部服务都要像面向公众的 API 一样构建。如果没有这一点，很难想象像 AWS 和 S3 这样的服务会取得成功。有了 OPA，你也可以采用这种方法。

在这个模型中，OPA 实例作为每个微服务的附属程序运行，通常通过特使代理或附属授权 API。每个微服务的性能都快如闪电，因为授权请求是服务器本地的，不需要网络跳跃。同时，即使集群中的某些服务被分区或“不可用”，每个单独的微服务也可以继续运行自己的本地授权请求。

然而，这种模式也面临挑战。首先，您必须意识到串行 OPA 调用的延迟。例如，即使对 OPA 的本地微服务调用仅花费 5 毫秒的“预算”，如果您串行调用 10 个微服务，那么总的附加延迟将是 50 毫秒。尽管如此，这种设置通常比集中式模式更快，集中式模式需要通过网络连接到远程服务器。其次，您必须确保每个 OPA 实例的本地策略版本与其他版本一致。例如，服务 A 策略需要匹配服务 B 策略，等等。总的来说，这个模型非常适合许多动态微服务架构。

**优势:**安全，“零信任”模式，动态—适合云原生。

**挑战:**按顺序管理请求，确保本地策略的一致性。

## **4。JSON 令牌模型(实验)**

OPA 的价值在于它的灵活性。这个模型将 OPA 带入了一个新的探索性的领域——当然，这是一个让齿轮转动起来的模型，而且是一个在您的组织中完全实用的模型。

这是 JSON web 令牌(JWT)模型——进行授权，就像 OAuth 和 OpenID Connect 进行身份验证一样。在这个模型中，OPA 用一个已签名的 JWT 来响应授权请求，然后将它发布给下游工具链。任何后续服务都可以验证可信 OPA 实例发出的 JWT，而不是通过查询 OPA 来增加额外的延迟。这种模型不一定是集中式或分布式的(可能是两者之一)，但在分布式模型中，它具有高安全性和闪电般快速的本地响应时间的优点，而没有序列化 OPA 调用的总延迟的缺点。

**优势:**面向未来，快速，高效，安全。

**挑战:**用新模式锻造路径。

## **5。“零延迟”并行查询模型(实验)**

最后，我们有了并行请求模型——与 JWT 模型一样具有实验性和令人兴奋。这里，当一个微服务有一个后端请求，需要授权决策时，它发送两个并行查询:一个直接发送到后端，另一个发送到 OPA。只要来自 OPA 的授权决策快于对数据库的调用，OPA 就不会给整个请求增加任何延迟。即使 OPA 响应比数据库请求慢，您仍然可以通过一前一后发送请求来优化尽可能小的延迟(并最大化您的延迟“预算”)。这种方法的一个潜在问题是:由于对后端的请求是在 OPA 做出授权决定之前发送的，所以即使最终被拒绝的请求仍然会被处理，从而产生不必要的负载。这可以通过使用其他网络模式来缓解，例如断路器，尽管这增加了解决方案的复杂性。尽管如此，如果减少延迟比减少后端负载更重要，这种模式是一种选择。

**优势:**后端请求尽可能接近零 OPA 延迟。

**挑战:**即使被拒绝的请求也会增加后端服务的负载。同样地，你正在用一种新的模式开拓新的领域。

微服务开发人员总是致力于最大限度地提高延迟性能。此外，随着数字化转型的持续推动，开发团队面临着越来越大的压力，他们需要更快地提供更丰富的应用服务和处理更多数据，从而提高对速度的需求。借助 OPA 的灵活性，您可以找到合适的模型来实现所需的性能，同时做出所需的策略和授权决策。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>