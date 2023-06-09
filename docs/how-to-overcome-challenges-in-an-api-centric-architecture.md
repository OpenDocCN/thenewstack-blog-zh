# 如何克服以 API 为中心的架构中的挑战

> 原文：<https://thenewstack.io/how-to-overcome-challenges-in-an-api-centric-architecture/>

这是两部分系列的第二部分。有关典型架构的概述、如何部署以及使用的正确工具，请参见第 1 部分。

大多数 API 对每月的请求数量和速率限制施加了使用限制，例如每分钟最多 50 个请求。系统的许多部分都可以使用第三方 API。处理订阅限制要求系统跟踪所有 API 调用，并在即将达到限制时发出警报。

通常，提高限制需要人工参与，并且需要提前发出警报。部署的系统必须能够持久地跟踪 API 使用数据，以便在服务重启或失败时保留数据。此外，如果多个应用程序使用同一个 API，那么收集这些计数并做出决策需要仔细的设计。

费率限制更复杂。如果交给开发人员，他们会无一例外地添加睡眠语句，这将在短期内解决问题；然而，从长远来看，当时间改变时，这会导致复杂的问题。更好的方法是使用限制速率的并发数据结构。即便如此，如果多个应用程序使用同一个 API，控制速率就更加复杂。

一种选择是为每个 API 分配一部分速率，但这样做的缺点是会浪费一些带宽，因为当一些 API 在等待容量时，其他 API 可能会空闲。最实际的解决方案是通过一个可以处理所有限制的呼出代理发送所有呼叫。

使用外部 API 的应用程序几乎总是会遇到这种挑战。即使是内部 API，如果被许多应用程序使用，也会面临同样的挑战。如果一个 API 只被一个应用程序使用，那么让它成为 API 就没有什么意义了。尝试提供一个通用的解决方案来处理订阅和费率限制可能是一个好主意。

## **克服高延迟和尾部延迟**

给定一系列服务调用，尾部延迟是花费最多时间完成的少数服务调用。如果尾部延迟很高，一些请求将花费很长时间或超时。如果 API 调用发生在互联网上，尾部延迟会越来越严重。当我们构建结合多种服务的应用时，每种服务都会增加延迟。当组合多个服务时，超时的风险会显著增加。

尾部延迟是一个已经被广泛讨论的话题，我们不再赘述。但是，如果您计划在高负载条件下运行 API，那么探索和学习这一领域是一个好主意。更多信息请参见[【1】](https://accelazh.github.io/storage/Tail-Latency-Study)[【2】](https://medium.com/star-gazers/budgeting-randomness-163a4dbe77f4)[【3】](https://www.usenix.org/system/files/conference/atc18/atc18-li-zhao.pdf)[【4】](https://www.weave.works/blog/a-tale-of-tail-latencies)[【5】](https://www.section.io/blog/preventing-long-tail-latency/)*。*

但是，为什么这是一个问题呢？如果我们公开的 API 不提供服务级别协议(SLA)保证(比如在不到 700 毫秒的时间内达到第 99 个百分点)，那么使用我们 API 的下游应用程序就不可能提供任何保证。除非每个人都能坚持合理的保证，否则整个 API 经济将会崩溃。较新的 API 规范，如澳大利亚开放银行规范，将延迟限制定义为规范的一部分。

> 如果用例允许，最好的选择是让任务异步。

有几种可能的解决方案。如果用例允许，最好的选择是让任务异步。如果您正在调用多个服务，这不可避免地会花费很长时间，并且通常通过承诺在准备就绪时提供结果来设置正确的期望值比强迫最终用户等待请求更好。

当服务调用没有副作用(例如搜索)时，还有第二个选项:延迟对冲，当等待时间超过第 80 个百分点时，我们开始第二个调用，当其中一个调用返回时，我们做出响应。这可以帮助控制长尾。

第三种选择是，当我们正在进行服务调用时，不要等待响应，而是并行启动尽可能多的服务调用，从而尝试并行完成尽可能多的工作。这并不总是可能的，因为一些服务调用可能依赖于早期服务调用的结果。然而，编码并行调用多个服务，收集结果并组合它们，比一个接一个地做要复杂得多。

当需要及时响应时，您将受到依赖的 API 的支配。除非缓存是可能的，否则应用程序不可能比它的任何依赖服务运行得更快。当负载增加时，如果依赖端点无法在将响应时间保持在 SLA 范围内的同时进行扩展，我们将会遇到更高的延迟。如果相关的 API 可以保持在 SLA 内，我们可以通过支付更高的服务级别或购买多个订阅来获得更大的容量。当这成为可能时，保持在延迟范围内就变成了容量规划问题，我们必须保持足够的容量来管理潜在延迟问题的风险。

另一种选择是为同一个函数提供多个 API 选项。例如，如果你想发送短信或电子邮件，有多种选择。然而，对于许多其他服务来说，情况就不一样了。随着 API 经济的成熟，许多 API 可能会有多种竞争方案。当有多个选项可用时，应用程序可以向响应速度更快的 API 发送更多流量，从而带来更多业务。

如果我们的 API 只有一个客户端，那么事情就简单了。只要我们的系统允许，我们可以让客户使用 API。然而，如果我们支持多个客户端，我们需要尽量减少一个客户端拖慢其他客户端的可能性。这也是为什么其他 API 会有速率限制的原因。我们还应该在 API 的 SLA 中定义速率限制。当一个客户端发送太多太快的请求时，我们应该使用一个状态代码，比如 HTTP 状态代码 503，来拒绝他们的请求。这样做是向客户端传达它必须减速的信息。这个过程被称为反压力，在这个过程中，我们向上游客户端传达服务过载，消息最终将被传递给最终用户。

> 重要的是要有足够的跟踪和日志来帮助你发现错误是发生在我们的系统端还是第三方 API 端。

如果我们负载过重而没有任何单个用户快速发送请求，我们就需要扩大规模。如果我们不能扩大规模，我们仍然需要拒绝一些请求。需要注意的是，在这种情况下，拒绝请求会使我们的系统不可用，而在之前的情况下，当一个客户正在检查他的 SLA 时，拒绝请求不会被算作不可用时间。

冷启动时间(容器启动的时间)和服务请求是其他延迟来源。一个简单的解决方案是让副本一直运行；这对于高流量 API 来说是可以接受的。但是，如果您有许多低流量 API，这可能会很昂贵。在这种情况下，您可以猜测流量并在此之前预热容器(使用试探法、人工智能或两者)。另一个选择是优化服务器的启动时间，以允许快速启动。

延迟、规模和高可用性密切相关。即使是一个经过良好调优的系统也需要进行伸缩，以保持系统在可接受的延迟内运行。如果我们的 API 由于负载需要拒绝有效的请求，那么从用户的角度来看，这个 API 将是不可用的。

## **跨多个 API 管理事务**

如果您可以从单个运行时(如 JVM)运行所有代码，我们可以将其作为一个事务提交。例如，前 microservices 时代的单片应用程序可以直接用数据库处理大多数事务。然而，当我们跨多个服务(因此是多个运行时)中断逻辑时，如果不做额外的工作，我们就不能跨多个服务调用执行单个数据库事务。

对此的一个解决方案是由应用服务器提供特定于编程语言的事务实现(如 Java 事务)。另一种方法是使用 Web 服务原子事务，如果您的平台支持的话。还有一种方法是使用支持事务的工作流系统(如 Ode 或 Camunda)。还可以使用队列，通过 Atomikos 这样的事务管理器将数据库事务和队列系统事务合并成一个事务。

这个话题在微服务下面已经详细讨论过了，这里不再赘述。更多细节请参见[【6】](https://developers.redhat.com/blog/2018/10/01/patterns-for-distributed-transactions-within-a-microservices-architecture)[【7】](https://www.baeldung.com/transactions-across-microservices)[【8】](https://microservices.io/patterns/data/saga.html)*。*

最后，对于基于 API 的架构，故障排除可能会更加复杂。重要的是要有足够的跟踪和日志来帮助你发现错误是发生在我们的系统端还是第三方 API 端。此外，我们需要可以共享的清晰数据，以防需要第三方 API 的帮助来隔离和修复问题。

*感谢*[*Frank Leymann*](https://www.linkedin.com/in/fleymann/)*[*Eric 新人*](https://www.linkedin.com/in/enewcomer/) *等人深思熟虑的反馈，显著塑造了这些帖子。**

*<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*