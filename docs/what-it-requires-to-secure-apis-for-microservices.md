# 保护微服务的 API 需要什么

> 原文：<https://thenewstack.io/what-it-requires-to-secure-apis-for-microservices/>

API 和微服务在云原生环境中都扮演着关键角色。微服务是分布式和共享计算资源的基石。同时，API 作为一种非常有效的方式来简化 DevOps 团队的许多操作和开发任务。

然而，微服务和 API 都有各自的安全风险。只要一个受损的 Kubernetes 节点允许入侵者通过 API 获得跨多个集群的组织的整个容器基础设施的根访问权限(最坏的情况)。

在本期新的 Stack Makers 播客中，我们将探讨如何使用 API 保护微服务，以及如何依靠 API 将某些安全任务委托给可信的第三方。我们的嘉宾是 Viktor Gamov，他是一家 API 连接公司 Kong 的首席开发顾问。这一集由 TNS 创始人兼发行人 [Alex Williams](/author/alex/) 和营销主管、开发者关系[Okta](https://developer.okta.com/?utm_content=inline-mention)Bharat Bhat 主持。

[保护微服务的 API 需要什么](https://thenewstack.simplecast.com/episodes/what-it-requires-to-secure-apis-for-microservices)

加莫夫将保护 API 比作将奶酪从一个港口运输到另一个港口的船只。安全检查包括确保奶酪确实是奶酪，而不是违禁品，并监控路线，以检查指定的船只将到达正确的港口。

Gamov 解释说，对于安全管理，微服务的 API 网关可以允许 DevOps 团队成员声明性地仅启用一些插件和一些集成，如第 7 层通信。更具体地说，这种 API 管理的功能可能涵盖应用级协议，如 HTTP、HTTPS 或 gRPC。

Gamov 说，“你需要有某种安全的通道或途径”，防止有人意外破坏或窃取微服务数据。

保护 API 网关包括保护端点之间的路由数据。Gamov 说，这是“我们如何确保登录我们系统的人是他们所说的那个人”。

身份访问的管理可以分配给第三方安全 API 提供者，后者反过来可以帮助控制和验证对微服务环境中不同 API 的访问。Gamov 说，“我们可以将一些工作交给身份提供商(IdPs)”，这样开发者就不必管理这个过程。

再次使用奶酪的比喻，标识服务可以检查 API 是否“带来了帕尔马干酪”。“这是我们检查一切的地方，比如你能不能带这个部门……羊乳干酪、高达干酪或其他一些东西，”加莫夫说。“所以，这就是我们扩展它的地方(以确定)你可以用这个系统做什么。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>