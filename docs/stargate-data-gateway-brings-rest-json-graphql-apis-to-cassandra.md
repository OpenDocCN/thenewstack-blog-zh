# Stargate 数据网关为 Cassandra 带来了 REST、JSON、GraphQL APIs

> 原文：<https://thenewstack.io/stargate-data-gateway-brings-rest-json-graphql-apis-to-cassandra/>

在过去的六个月里，DataStax 已经采取了一系列措施，使其开源软件 Apache Cassandra 更容易获得。首先，该公司与 [Astra](https://astra.datastax.com/register) 一起推出了基于云的数据库即服务版本 Cassandra，消除了安装和管理自己的数据库实例的痛苦。然后，[公司发布了 K8ssandra](https://thenewstack.io/k8ssandra-is-open-source-cassandra-for-kubernetes/) ，再次瞄准了这些相同的痛点，但这次的重点是 Kubernetes。现在，DataStax 表示，今年夏天早些时候推出的开源数据 API 框架 [Stargate](https://stargate.io/) 已经普遍可用，并通过 REST、JSON 和 GraphQL 向 Cassandra 提供 API 访问，无论它可能在哪里运行，也无论它可能以何种方式运行。

在[宣传材料](https://youtu.be/2ltVf2EscmM)中，该公司将 Stargate 称为“现代数据应用的第一个开源 API 数据网关。”

“今年年初，我们问为什么没有更多人使用 Cassandra？反馈是，尽管它很强大，但运行起来很有挑战性，很难开发。把它带到云上，带到 Kubernetes 上，使它更容易运行，但我们真的想让它更容易开发。为此，我们在今年早些时候启动了一个名为 Stargate 的开源项目，该项目将开发人员正在使用的 API 带到了 Cassandra 世界，”DataStax 的首席产品官 Ed Anuff 解释道。“引入开源的这一关键部分，并将其置于我们的云服务中，使任何开发人员都能够使用这些现代 API，非常快速地构建现代全栈应用。”

Stargate 作为一个数据网关，允许开发者使用他们选择的 API 方法，而不是直接使用 Cassandra。这不仅允许他们从一种访问方法转移到另一种访问方法，例如在转移到 GraphQL 之前的原型开发期间从 JSON 开始，而且他们自己也不必担心数据建模。

“开发人员只是想存储一个 JSON 对象。他们想把它放入数据存储中，放入 Cassandra 中，但是他们不想进入数据建模的复杂性。他们不想去想‘这会变成数据库表中的特定列吗？’所有的绘图都在星际之门内动态地发生星际之门只是隐藏了这一点。对于高级用户，有配置选项，但是大多数开发人员不需要处理这些。他们只是把数据存储在那里，他们可以检索它，这是非常自然的。"

[https://www.youtube.com/embed/2ltVf2EscmM?feature=oembed](https://www.youtube.com/embed/2ltVf2EscmM?feature=oembed)

视频

Anuff 解释说，在选择数据库时，一个常见的紧张点是在数据库团队和开发人员之间，他们来自不同的方向。他说，星际之门和阿斯特拉提供了一个让双方都满意的解决方案。

“平台团队说‘我们希望使用像 Cassandra 这样的东西，我们需要一种被证明可以在全球范围内推广的东西。’前端团队通常会说‘我们希望使用 Mongo 或 Firebase 之类的东西，让我们的开发人员易于使用。’”阿努夫说现在有了 Stargate，他们有了一个解决方案，因为从开发者的角度来看 Stargate 和 Mongo 或 Firebase 一样容易使用，但是它运行在 Cassandra 之上，这给了你全球范围。它让您基本上拥有了全球范围的全球可靠性，同时还拥有 REST 和 GraphQL APIs 带来的轻松开发体验，让您的开发人员只需构建和发布他们的应用程序，而无需与数据库斗争。"

DataStax 还推出了 [Astra 无服务器](https://www.datastax.com/astradb/serverless)的测试版，提供一种按使用付费的 Astra 模式，Anuff 表示该模式将于明年年初全面上市。除了财务优势之外，Astra Serverless 还可以动态扩展，使用户无需规划存储需求即可向前发展。

虽然 Stargate 的直接目标受众可能是 JavaScript 开发人员，但 Anuff 解释说，后端开发人员，尤其是使用微服务的开发人员也很感兴趣。

“当我们建造 Stargate 时，我们将它设计为可扩展的，我们的想法是随着时间的推移，我们将拥有多个 API。你很快就会看到 gRPC，”阿努夫说。“特别是对于微服务，人们正在寻找一种非常高性能的协议，这就是 gRPC 的用武之地。它不像使用 REST 或 GraphQL 这样的东西那样具有表现力，但对于真正关心性能的微服务来说，它真的正在成为首要标准。”

除了 gRPC，该公司还指出流媒体和活动是其计划在不久的将来扩展的领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>