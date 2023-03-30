# 如何为服务网格创建零信任架构

> 原文：<https://thenewstack.io/how-to-create-zero-trust-architecture-for-service-mesh/>

毫不奇怪，[零信任安全](https://thenewstack.io/what-is-zero-trust-security/)抓住了科技组织的想象力。前提非常简单:仅仅因为你进入了一个系统，并不意味着你可以访问任何东西。或者，事实上，任何东西。

每个请求——无论是来自个人还是微服务——都在更广泛的安全环境中进行检查，考虑的属性包括:这个用户是谁？我们如何验证这一点？现在是几点？这个用户有什么权限？

[尽管原则很简单，但实施零信任的进展证明是难以捉摸的。](https://thenewstack.io/unused-credentials-key-culprits-in-cloud-attacks-study-says/) Gartner 预测[到 2026 年，甚至十分之一的大型组织](https://www.gartner.com/en/newsroom/press-releases/2023-01-23-gartner-predicts-10-percent-of-large-enterprises-will-have-a-mature-and-measurable-zero-trust-program-in-place-by-2026)“都将实施成熟且可衡量的零信任计划”目前只有不到 1%的企业实施了这样的方案。

事实上，正如 [Christian Posta、](https://www.linkedin.com/in/ceposta/) [Solo.io 的](https://solo.io?utm_content=inline-mention)全球现场首席技术官告诉新堆栈的那样，实施零信任架构需要一种了解应用程序正在做什么并管理其安全属性的方法。这不能简单地被开发人员匆忙绕过，或被一个已存在的或新的漏洞破坏。

这就是像 [Istio](https://thenewstack.io/what-is-istio-and-why-does-kubernetes-need-it/) 这样的[服务网](https://thenewstack.io/service-mesh/)发挥作用的地方，至少对于基于[微服务](https://thenewstack.io/microservices-101/)的现代应用程序来说是这样。网格作为一个可见的基础设施层运行，可以添加到应用程序中，提供[可观察性、](https://thenewstack.io/observability/)流量管理和[安全性。](https://thenewstack.io/security/)在 Istio 的情况下，这是通过使用 [Envoy sidecar、](https://thenewstack.io/microservicing-with-envoy-istio-and-kubernetes/)实现的，它充当每个服务的代理，而不必嵌入到核心应用程序代码中。

事实上，Posta 说，服务网格的头号用例是安全性。也许这并不奇怪，因为服务网格方法支持组成应用程序的服务之间的安全通信，以及[认证和授权、](https://thenewstack.io/what-do-authentication-and-authorization-mean-in-zero-trust/)和流量管理。

但他指出，服务网“不会自动地、神奇地解决零信任。”相反，他说，“一个服务网格所做的是实现你在零信任状态下所期望的许多属性。”

简单地将像 Istio 这样的开源项目放到现实世界的企业环境中并不简单，他说:“企业并不是轮廓清晰、棱角分明、一切都完美契合的。他们是战区。”

## 新网格，粗糙边缘

因此，Solo.io 和其他 Istio 贡献者做了大量工作来“软化”一些粗糙的边缘，Posta 说。“我们在 Solo 构建的产品旨在进一步简化部署、安装 Istio 和管理服务网格的工作。”

但是即使这样也不能完全解决构建[零信任架构](https://www.solo.io/zero-trust/)时的复杂性挑战——或者开发者只是做他们想做的事情。

正如 Posta 告诉新堆栈的那样，开发人员可能会忘记在他们的应用程序中部署 sidecar。或者他们可能会误解 ii。或者 sidecar 可能不像开发人员希望的那样透明。

有时公司会推行最初与 Istio 不相容的政策或程序。他举例说，Solo.io 合作的一家公司依赖于区分大小写的应用程序之间的 HTTP 头。但是 HTTP 规范并没有涵盖头的大小写敏感性。这意味着 Istio——仍然符合规范——将它们改为小写。结果呢？应用程序崩溃了。

“所以这是一个例子，作为一名开发人员，我想部署一个 sidecar，因为我想在网格中，”Posta 说。“但现在我遇到了这些意想不到的后果，因为该企业正在做一些奇怪的疯狂的事情。”

同时，他指出，在 Istio 中用作数据平面的 Envoy 代理非常灵活。它可以打开连接，建立相互 TLS，并收集遥测数据。它还理解数据库协议，比如 [MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) 和 MySQL，并且可以用 [WebAssembly 进行扩展和定制。](https://thenewstack.io/is-webassembly-really-the-future/)

“然后它的核心基本上是围绕 HTTP 和 GPRC 做事情，请求路由，负载平衡，电路中断，”波斯塔说。

从另一个角度来看，这种灵活性开始看起来像复杂性。但是，如果安全性是实现服务网格的关键驱动因素，那么尽可能保持简单可能是有意义的，在适当的地方去掉边斗。

这是去年推出的 [Istio Ambient Mesh、](https://thenewstack.io/ambient-mesh-sidestepping-the-sidecar/)的目标，它去除了边车，而没有牺牲服务网格的安全优势。相反，各个服务通过 Ztunnels(或零信任隧道)连接，z tunnels 处理第四层连接，而更详细的策略实施则在第七层处理。Solo.io 已经宣布在自己的 Gloo 网格实现中支持 Ambient。

简单地运行安全覆盖层，Posta 将其描述为“环境的主干”，这意味着工程师不会被大小写敏感或代理如何处理某些协议的细微差别等问题分散注意力。“我们只是解决你想要的用例，使用你需要的技术数量，”他说。“如果你需要的话，以后还可以选择加入其他内容。”

## 广撒网

虽然核心 Istio 项目主要集中在 [Kubernetes](https://thenewstack.io/primer-how-kubernetes-came-to-be-what-it-is-and-why-you-should-care/) 上，支持扩展到虚拟机(VM)，但 Posta 表示 Solo.io 的技术支持跨多集群、多本地和公共云和非军事区(dmz)的复杂环境。

“我们可以整合虚拟机和物理机，”他说。“这其中有很多复杂性。我们试图保护人们远离这些。我们直接集成了像[【亚马逊网络服务】](https://aws.amazon.com/?utm_content=inline-mention) Lambdas 这样的东西，开源的 Istio 没有这样做。沿着这条路走下去，人们就不必再使用 AWS API Gateway 和[应用程序负载平衡器]。”

许多组织，尤其是金融界的组织，仍然使用几十年前编写的代码，这可能会带来安全性和集成方面的挑战。

但是 Posta 指出，服务网的重点是在网络上执行政策。“因此，如果有[简单对象访问协议]应用程序，它们可以通过网络进行通信，”他说，这意味着 Solo.io 可以应用“某种级别的策略。”

Ambient 可能支持更多的工作负载，并在更多的地方运行，因为它不是一个成熟的代理。他说，在虚拟机上部署 sidecar 可能“相当具有侵略性”。

“我们也许可以更容易地包括在 hashi corpNomad 或 AWS ECS Fargate 上运行的工作负载，”Posta 说。他补充道，从逻辑上讲，这些地方可以一直延伸到大型机。

这确实开辟了如何使用服务网格来实现零信任架构，即使在企业的“战区”中，传统应用程序和基础架构与现代的、基于 Kubernetes 的云原生应用程序一起运行。

这并不意味着边车将被完全淘汰。“在 Solo，我们相信 Ambient 最终将成为 Istio 中的默认数据平面，”Posta 说。"当需要的时候，边车将被用作一个优化."

何时需要将取决于整体架构和零信任架构实现的安全环境。

波斯塔说，这意味着，“网格的行为将由组织中多个不同的小组决定。”

这包括通常拥有网格生命周期的[平台工程](https://thenewstack.io/platform-engineering-the-ultimate-guide/)团队，当然还有安全团队，以及站点可靠性工程团队、 [API 网关](https://www.solo.io/api-gateway/)团队，当然还有应用程序所有者。

这会让生活变得复杂吗？大概吧。当人们参与进来时，生活总是更加复杂。这是尽可能简单地实现构建零信任的服务网格的另一个原因。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>