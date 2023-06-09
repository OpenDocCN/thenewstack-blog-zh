# 事件驱动架构的兴起

> 原文：<https://thenewstack.io/the-rise-of-event-driven-architecture/>

[](https://ably.com/platform)

 [马修·奥莱登

马修·奥莱登是 Ably 的首席执行官兼技术联合创始人，Ably 是一个实时同步数字体验的平台。Matthew 已经做了 20 多年的软件工程师，其中很多年都是担任 CTO。他第一次开始从事商业互联网项目是在 20 世纪 90 年代中期，当时 Internet Explorer 3 和 Netscape 还在争个你死我活。虽然他喜欢编程，但作为一名企业家，他面临的创业和扩大业务的挑战是他的动力。Matthew 之前创办并成功退出了两家科技公司。](https://ably.com/platform) [](https://ably.com/platform)

应用编程接口(API)正在推动数字化转型，并主导着几乎每个企业的 IT 环境。推动这种流行的是最终用户日益增长的需求，他们现在期望数字体验是交互式的、响应性的和即时的。组织正转向 API 来创建引人入胜的高效体验，并优化从运营到客户服务的所有业务领域。事实上， [Gartner](https://www.gartner.com/smarterwithgartner/gartner-top-strategic-technology-trends-for-2021/) 的 2021 年技术趋势之一是总体体验，它定义为结合多重体验、客户体验和员工体验来转变业务成果。

但是开发人员如何构建满足这些复杂需求的解决方案呢？他们使用事件驱动架构(EDA)结合面向服务的架构来设计 API。使用 EDA，客户端可以异步订阅和接收事件，如果两者都在线，则可以实时订阅和接收事件，从而使客户端不必请求更新或状态更改。通过将架构复杂性的负担从客户转移到生产者，企业可以创建现代用户现在期望的流畅体验。

## **什么是事件驱动架构？**

EDA 使用事件来触发去耦应用、[微服务](https://thenewstack.io/category/microservices/)和连接设备之间的通信，并使信息能够实时流动。为了真正理解它的全部内容，回顾一下分布式软件系统架构的历史以及它在过去几十年中是如何发展的是很有用的。

20 世纪 40 年代的第一个软件程序使用子例程，根据一组指令执行任务。众所周知，ENIAC 团队的程序员在二战期间开发了计算导弹轨迹的子程序。

> 在当前的全体验技术时代，事件驱动设计可以帮助企业满足现代终端用户的苛刻期望，并获得竞争优势。

计算架构设计随后发展到以能够远程执行多个子例程的 orchestrator 系统为中心。从这种结构中出现了请求-响应范式:一个 orchestrator 节点向另一台计算机发送一个带有请求的子例程，然后该计算机处理该请求并向原始 orchestrator 返回一个响应。

1989 年蒂姆·伯纳斯·李发明万维网后，HTTP 成为部署分布式系统的首选方法，URL 暴露和访问子例程，这自然导致了 API。随着业务优先级更加关注实时体验，API 成为当今企业创新背后的关键驱动力。

## **API 驱动的用户体验**

API 通过模拟真实世界的操作来创造体验。让我们举一个在线服装零售商的例子。开发人员可以定义一个 API 来执行订购流程的每个操作。例如，API 可以实时接受订单、管理库存、运行报告和更新交付状态。该系统将需要一个基于 web 或应用程序的界面来模拟人类操作员对操作或信息的请求。因此，用户不用打电话，而是与界面交互，触发 API 来下订单或检查交付状态。

继续以零售商为例，您可以进一步扩展服务，开发一个模拟整个订单管理流程的 SaaS 应用程序。例如，您可以定义一组 REST APIs 来创建订单，并跟踪从初始订单到交付的工作流。API 还可以管理订单履行过程中的操作和物流，并处理业务交易。

该系统生成虚拟对象，这些虚拟对象模拟订单处理中涉及的现实对象，包括订单本身、支付交易和交货通知。使用 REST APIs 建模事务性对象，API 设计变得更加合理和细致，因为您可以使用特定的端点直接查询对象，而不是用所有查询重载一个公共的单个端点。例如，您可以通过查询订单端点来查询订单的状态，API 将返回订单的当前状态。

REST APIs 也依赖于通过 HTTP 的请求-响应模式，要求客户端根据需要经常提交状态更改或更新请求。当一切顺利时，这个系统运行良好。然而，如果出现问题，比如支付失败或交付延迟，系统就会崩溃并影响客户服务。此类事件随后成为业务关键型“事件”。从客户服务的角度来看，最好让客户尽快知道任何问题，而不是让他们自己去解决。这就是为什么现代的、以人为中心的 SaaS 应用程序必须比基于传统 REST 方法的应用程序提供更高质量、更实时的交互。

## **事件驱动的 API 未来**

在 REST 框架中，API 不知道对象的状态。客户端查询 API 以找出状态，API 的作用是用信息响应客户端。

然而，使用事件驱动的 API，客户端可以订阅 API，有效地指示它监控对象的状态并报告实时更新。因此，行为从对可重复的独立请求的无状态处理转变为对基于真实世界操作建模的虚拟对象的有状态感知。

事件驱动的 API 是满足现代最终用户需求的一种很好的方式，这些用户希望定制和即时访问信息。在一次性的定制环境中应用这些 API 很容易。然而，当您需要大规模提供这种级别的服务时，事情会变得更加复杂，并且不是每个企业都准备好处理这种级别的复杂性。为了避免积累大量的技术债务，组织和开发人员应该将这种复杂性卸载给能够实时大规模同步数字体验的第三方。

有了合适的实时基础设施支持，组织可以在一系列用例中应用事件驱动的 API。它们非常适合传统架构，并提供满足现代数字交互需求所需的功能，例如:

*   ****更好的实时体验:**事件驱动的 API 吸收了许多以前分配给最终用户的职责，创造了更多的交互体验。**
***   ****更低的变更管理开销:**API 将消费者(使用 API 的应用程序)和生产者(服务器)分离开来，消费者只需要知道事件的数据格式，而不需要知道哪个服务器正在发送数据。同样，生产者对消费者的身份不感兴趣，从而降低了管理费用。*****   ****可伸缩性:** API 生产者不需要管理相互竞争的消费者——事实上，订阅者的数量与生产者无关。重要的是经纪人将信息传递给订户，不管他们是谁，也不管他们有多少。*****   ****可扩展性和弹性:**松散耦合的组件易于就地扩展，并且回归风险较低。开发人员还可以在不影响其他消费者的情况下添加功能。同样，很容易将 [容错](https://ably.com/blog/engineering-dependability-and-fault-tolerance-in-a-distributed-system) 融入到设计中，因为您可以划分组件故障。*****   ****并发的一致性:**事件驱动的 API 通过事件和消息排序的不变性和 [恰好一次交付](https://ably.com/blog/achieving-exactly-once-message-processing-with-ably) 更容易实现分布式系统内的并发。*****   ****网络资源的优化使用:**传统的面向服务的方法倾向于依赖于基于推送的方法，这些方法往往会消耗服务器的资源，例如连续轮询。本质上，事件驱动的 API 可以更有效地利用网络和计算资源。*****   ****技术成熟度:**事件驱动的方法已经存在了近 50 年，但现代在线服务交付系统却花了很长时间才赶上。我们生活在一个激动人心的时代，两种技术可以结合起来满足今天的消费者需求。**************

 ****## **EDA 作为竞争优势**

自 20 世纪 70 年代提出以来，EDA 一直在耐心等待时机。随着事件驱动的 API 的出现，EDA 正成为解决现代业务问题和提供实时用户体验的中心舞台。虽然 EDA 可能不是所有业务挑战的答案，但当应用于正确的用例时，它可以转变公司的运营和客户服务。越来越明显的是，企业要在现代市场中保持竞争力，就需要知道在哪里以及如何使用 EDA。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>****