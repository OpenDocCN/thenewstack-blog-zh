# API 的现状:货币化 API 部署正在兴起

> 原文：<https://thenewstack.io/state-of-the-api-monetizing-apis-deployment-is-on-the-rise/>

与前几年相比，开发人员正在构建更多供外部使用的 API，近一半的开发人员表示他们构建供外部使用的 API，这一数字增加了近 5 个百分点。

RapidAPI 的 2022 年[API 状态](https://stateofapis.com/)报告调查了 850 个人，其中近一半是开发人员。虽然大多数人(75 %)都在开发面向内部的 API，但开发面向合作伙伴的 API(49%)和第三方 API(54%)的开发人员数量有所增加，这两个类别的年增长率都接近 5 %。

调查还发现，超过四分之三的受访开发者认为“API 经济”是组织的首要任务。59%的人说这是当务之急，另有 16.4%的人回答说这很快就会成为当务之急。

这可能会增加 IT 研究公司 Forrester 的预测，即更多的[商业领袖将在未来一年利用 API](https://thenewstack.io/pro-coders-key-to-stopping-citizen-developer-security-breach/)。

“他们将开始收到来自企业的请求，说…‘为我构建我想要的数据 API，为我构建我想要的事务 API’，开发人员将被要求在开发 API 的同时构建这些不同的部分，”研究总监克里斯·加德纳告诉 New Stack。

RapidAPI 指出，与前几年相比，2022 年将 API 货币化的组织数量增加了约 5%。金融服务业尤其如此，API 货币化增长了 16%。

该公司在新闻稿中写道:“来自金融服务、技术、电信和医疗保健等行业的开发者报告称，API 的货币化速度高于平均水平。”“在使用超过 10 个 API 的组织中工作的人的收入也显著增加。”

## 流行的 API 语言

这里的故事是，使用 [TypeScript](https://thenewstack.io/key-concepts/typescript/) 正在篡夺[PHP](https://thenewstack.io/php-has-survived-for-26-years-because-it-keeps-evolving/)；16%的人报告说使用过它，而去年只有 12%。与此同时，今年 PHP 的使用率下降了一个百分点，至 14%。

该公司在报告中指出:“[[JavaScript](https://thenewstack.io/2022-a-golden-year-as-javascript-moves-to-the-edge/)]今年失去了阵地，而 TypeScript 自 2021 年以来增长了 4%”。“旧语言的使用率持续下降——参见 [Java](https://thenewstack.io/javas-history-could-point-the-way-for-webassembly/) ，PHP，C#和[。网](https://thenewstack.io/what-net-maui-can-do-for-frontend-and-web-developers/)下移。"

尽管如此，JavaScript 仍然是编写 API 最受欢迎的语言，使用率为 48%，其次是 Python，使用率为 36%。19%的人选择 Java 作为他们的 API 语言。。Net 在这次调查中只获得了 4%的份额，比 2021 年下降了一个百分点。Go 和 C 排名最低，使用率都在 4%以下。

## API:Rest、Webhooks、Websockets 等等

调查还关注了 API 工具——特别是 [REST](https://thenewstack.io/graphql-and-rest-can-coexist-author-will-lyon-says/) 、 [Webhooks](https://thenewstack.io/webhooks-the-building-blocks-of-an-event-driven-architecture/) 、 [Websockets](https://thenewstack.io/an-introduction-to-websockets-with-ballerina/) 、 [SOAP](https://thenewstack.io/solo-io-adds-legacy-soap-integration-for-gloo-edge-1-8-release/) 、 [GraphQL](https://www.redhat.com/en/topics/api/what-is-graphql) 、 [Kafka](https://thenewstack.io/where-elasticity-meets-open-source-and-how-to-adapt/) 、 [AsyncAPI](https://thenewstack.io/asyncapi-2-0-enabling-the-event-driven-world/) 、 [serverless](https://thenewstack.io/serverless-vs-kubernetes-the-peoples-vote/) 和 [FaaS](https://thenewstack.io/add-it-up-serverless-faas/) ，以及 [gRPC](https://thenewstack.io/grpc-a-deep-dive-into-the-communication-pattern/) ，所有这些工具的使用情况

毫不奇怪，69%的人使用了 REST——比去年增加了 10%。其次是 Webhooks 的部署，占 35%，WebSockets 占 30%。

软件工程师 [Chameera Dulanga](https://www.linkedin.com/in/chameeradulanga/?originalSubdomain=lk) [将 API 定义为不同于 Webhook 和 Websockets](https://blog.bitsrc.io/apis-vs-websockets-vs-webhooks-what-to-choose-5942b73aeb9b) ，因为 API 源自消费者。

“它们(API)非常适合像保持状态或执行快速操作以从后端操作接收即时响应这样的应用程序，”杜兰加写道。但是，如果服务器需要与浏览器进行通信，则在使用 API 时没有直接的方法，除非浏览器定期检查任何更新

它可以通过报告生成或连续轮询来实现这一点，但 WebSockets 更适合处理这种实时挑战，因为它们允许“消费者和服务提供商之间持久的双向通信，”他说，并补充说现代浏览器都支持 WebSockets。

据 Dulanga 称，WebHooks 有时被称为反向 API，“主要用于服务器或后端进程之间的通信”，例如，当你需要推送通知时，比如在移动部署上，就可以发挥作用。

“WebHooks 通过提供一种断开的机制来接收来自服务提供商的响应，为 WebSockets 中的过度杀戮问题提供了一个解决方案，”他写道。

其他 API 工具的使用率低于 30%，其中 27%使用 AsyncAPIs，25%使用无服务器或 FaaS，23%使用 SOAP。GraphQL、Kafka 和 gRPC 各收到不到 20%的回复。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>