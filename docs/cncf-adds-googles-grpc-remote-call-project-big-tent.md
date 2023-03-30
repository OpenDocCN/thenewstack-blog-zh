# CNCF 将谷歌的 gRPC 远程呼叫项目加入其“大帐篷”

> 原文：<https://thenewstack.io/cncf-adds-googles-grpc-remote-call-project-big-tent/>

[云原生景观](https://thenewstack.io/container-ecosystem-need-map/)给观众的印象是一个巨大的花园，充满了各种各样的项目，其中许多项目属于同一类别，彼此和谐共存。然而，[云本地计算基金会](https://www.cncf.io/)周三上午从谷歌的发起人那里获得了[gRPC](http://www.grpc.io/)——分布式系统的远程过程调用协议——的管理权，这导致了分布式应用程序内部相关组件的六层组合的出现，看起来更像是一个堆栈。

CNCF 首席运营官 Chris Aniszczyk 在接受新堆栈采访时表示:“我们特意将 CNCF 打造成为云原生技术的帐篷，这不仅包括编排部分——Kubernetes 帮助我们实现这一部分——还包括围绕云原生技术的其他内容:存储、协调、网络等等。您需要将所有这些部分缝合在一起，以构建我们认为的云原生解决方案。”

“从本质上讲，gRPC 是有助于微服务方面的产品之一，gRPC[*和*]与 Kubernetes 之间有着非常紧密的集成。Aniszczyk 说:“开放追踪社区和 gRPC 之间正在进行整合。

gRPC 协议是存放在服务器上的服务相互建立通信、协调、交换数据和共享公共数据源的一种方式。“RPC”部分意味着它总是有的:远程过程调用一直是分布式计算中最棘手的部分。

## 击退 DCOM 的幽灵

早在 web 出现之前，大规模分布式计算的第一次尝试涉及复杂的集中式资源架构——或者，代替无所不能的霸主，跨所有参与服务器复制集中式资源。在 20 世纪 90 年代早期，微软的[分布式组件对象模型](https://technet.microsoft.com/en-us/library/cc958799.aspx) (DCOM，其 Windows' COM 的分布式版本)有一个集中的注册表，其中的一部分在服务器之间共享。它为特定的组件提供了唯一的标识，并提供了指向“类型库”的指针，这些类型库对每个组件可以执行的所有功能进行了分类。开发人员在他们的源代码中使用特殊的 **#include** 宏调用这些类型库，确保所有编译的应用程序都在同一页面上。

GRPC has much the same objective today as did DCOM, and the [Common Object Request Broker](http://www.corba.org/) (CORBA) before the turn of the century. What’s missing is the element Microsoft called *marshaling*: an overseer of operations upon which the success of the interaction solely depends. When the gRPC project began in 2015, Google cited this absence as a key advantage, freeing system architects to develop or utilize their own choices of methodologies for messaging.

“The way I think about it is, there are two systems that need to talk to each other at a core level,” explained [Varun Talwar](https://github.com/zinuga), gRPC’s lead developer at Google (who will continue his work with the project). “They need to know what methods each other supports. So if I’m **A**, and I call **B**’s method, I need to know what **B**’s method is. I need to know what arguments **B**’s methods take, and whatever arguments they are, I need to serialize them and send them over the wire. **B** should understand them; **B** should be able to unmarshal them, accept them, and process them.”

In the old days of distributed systems, the type library would have resolved these requests locally. However, the library needed to be installed locally as well. Imagine if every city published its own telephone directory, such that the only way to call someone in that city is if you owned a copy of it yourself. Eventually, you’d have a wall full of useless phone books… which pretty much describes what happened to the early RPC systems.

GRPC resolves these issues through protocol-driven interaction. As Talwar explained it, the protocol enables services written using any language to negotiate with one another for common ground. Each negotiation leads to a strictly defined contract between components, ensuring that all exchanged data is of the expected type, and that handoffs are properly coordinated.

Issues that a distributed systems developer might normally encounter, such as *[circuit breaking](https://speakerdeck.com/mattheath/circuit-breaking-in-distributed-systems)* (preventing cascading failures), flow control, request cancellation, out-of-order receipt of message sequences (a common occurrence on web fabric), are all managed under-the-hood by gRPC, said Talwar. This not only negates the need for a regimental oversight component, he acknowledged, but also the impetus to build a custom message handler with every application — which the first hyperscale applications certainly did.

“当你开始将更大的整体组件分解为微服务时，”他说，“你会发现每个组件都在以自己的方式做[*事情*]，那么整体可管理性、整个系统的统一策略应用以及整体系统视图就变得非常困难。”

换句话说，当来自不同应用程序的微服务共存于一个平台时，如果您愿意，这些应用程序中没有一个能够将它们的耳朵转向同一个通信信道，这就是一个安全问题。

塔尔瓦说，有了 gRPC，“你就不必考虑，如果用户取消了对我的呼叫，我该怎么办，以及作为结果，对其他十个系统的所有十个[*或大约*]下游服务呼叫会发生什么？对于流控制，如果一个给定的请求有一个截止时间——截止时间是 20 ms，而我在 5 ms 内处理了我的部分——系统的其余部分知道它有 15 ms 来处理它的其余部分，如果它花的时间更长，那么这个请求就超时了。诸如此类的事情——我不会称之为“编排”，而是通信和连接级别的策略——会得到处理，您不必预先以一种严格的方式回答它们，也不必在它们各自的服务中找出自己的定制方式。”

## 正式批准

那么，如果我们将这个系统——借用 Aniszczyk 的一句话——围绕核心的 [Kubernetes](/category/kubernetes/) 容器编排工具缝合在一起，这些可管理性、策略应用和单一窗格监控的目标会变得更加可行吗？

塔尔瓦回应道:“管弦乐队是另一个层次的。”。“但从网络和通信的角度来看，是的……Kubernetes 更适合大规模部署和管理容器。这是一个稍微高一点的抽象层次。”

作为一个例子，Talwar 假设创建一个托管 gRPC 服务的容器。它部署在 Kubernetes 上，但是系统中容器之间的有线通信由 gRPC 处理。是的，它可能会在 Kubernetes 上上演，但这里的功能是完全解耦的。

在 [Linux 基金会](https://www.linuxfoundation.org/)赞助下创建的基金会的目的是关注一组特定的问题以及开源组件如何解决这些问题。CNCF 就是这样开始的，专注于配器。但是正如 Aniszczyk 提醒我的那样，[从它成立的时候](https://thenewstack.io/google-launches-a-separate-foundation-around-container-orchestration/)，CNCF 就把组装开源组件作为它的既定目标，组织可能需要这些组件来构建容器应用程序基础设施。

Aniszczyk(同时担任开放容器倡议的执行董事)说:“CNCF 实际上是一个与将云原生带到行业和世界其他地方相关的技术帐篷，而 OCI 则非常专注于容器格式和运行时位，更像是一个标准机构。网络和存储之类的东西完全不在 OCI 的考虑范围之内，这是故意的。”

CNCF 似乎已经收集了相当完整的堆栈。除了 gRPC 和 Kubernetes，还有 [Fluentd](https://thenewstack.io/fluentd-offers-comprehensive-log-collection-cloud-microservices-world/) 将不同的数据源聚集到一个统一的日志层； [Linkerd](https://linkerd.io/) 作为服务发现组件，取代了分布式系统中对服务注册数据库的需求； [Prometheus](https://prometheus.io/) 作为服务监控平台(【Kubernetes 加入 CNCF 后的第一个项目，去年 5 月)；以及 [OpenTracing](https://thenewstack.io/opentracing-aims-clearer-view-processes-distributed-systems/) 作为其工作流传播管理组件。

如果您将 Kubernetes 的 CRI-O 项目添加到这个组合中，您将把容器调度和部署带入堆栈中。容器的创建是留给开发人员的一个练习。

因此，尽管云原生景观呈现出拥挤的购物中心般的外观，但 CNCF 的堆栈看起来更像是它选择的首选“锚店”除了它的领导人可能希望我们不要使用这个词。

Aniszczyk 说，“我们不会把它称为‘首选’。“我们会把它作为选项之一。我们可能在 CNCF 有竞争项目。我们在那里不是为了成为国王。我们在那里整合和汇集项目，推动云原生计算的概念，像网飞、谷歌、Twitter、脸书等公司已经在他们自己的系统中运行了相当长的时间，并试图将它带到行业的其他地方。”

云本地计算基金会(CNCF)是新堆栈的赞助商。

专题图片:一幅版画，取材于弗雷德里克·亚瑟·布里奇曼(Frederic Arthur Bridgman)的一幅名为“[The American Circus in France](https://digitalcollections.nypl.org/items/a666a2c9-182a-70e4-e040-e00a180610ac)”的画作，来自纽约公共图书馆艺术、版画和照片部门 Miriam and Ira d . Wallach:Print Collection。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>