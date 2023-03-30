# 为什么分布式测试是测试微服务的最佳方式

> 原文：<https://thenewstack.io/why-distributed-testing-is-the-best-way-to-test-microservices/>

[](https://www.linkedin.com/in/aviv-kerbel/?originalSubdomain=il)

[Aviv Kerbel](https://www.linkedin.com/in/aviv-kerbel/?originalSubdomain=il)

[Aviv 是太阳神公司的开发者倡导者。Aviv 是一名经验丰富的开发人员和研发领导者，他热衷于现代环境中的开发以及趋势开发工具和技术。在加入 Helios 之前，Aviv 是多家初创公司的高级软件开发人员，也是总部位于以色列的风险投资公司 Amiti 的合伙人，他参与了科技初创公司的尽职调查和投资流程。](https://www.linkedin.com/in/aviv-kerbel/?originalSubdomain=il)

[](https://www.linkedin.com/in/aviv-kerbel/?originalSubdomain=il)[](https://www.linkedin.com/in/aviv-kerbel/?originalSubdomain=il)

我开始全职开发已经有将近十年了，其中将近四年是在基于微服务的环境中开发的。但是，尽管我们都接受了测试重要性的教育，随着时间的推移，我发现为我的代码编写测试变得越来越复杂，直到变得几乎不可能。或者可能只是不值得，因为我发现这比写代码本身要花更多的时间！

毕竟，由于服务之间有如此多的异步调用，很容易遗漏异常——因此测试的准备工作和基础设施的构建变得冗长而耗时，更不用说为这些类型的测试准备数据了。

想象一个包括 Kafka 主题、Postgres、DynamoDB、第三方 API 和多个微服务的流程，它们在某种程度上都相互依赖。任何变化都可能影响许多其他人。这里不再是 monolith-land 了，在这里我们将从服务器获得 HTTP500 状态代码。在这种情况下，我们可能有 100 个微服务，但仍然找不到在没有通知的情况下被抛出到另一个微服务的异常。

当我们尝试构建后端 E2E 测试时，我们尝试并测试了以下选项:

**选项一:基于日志的测试**

我们尝试的第一个选项是获取特性开发人员添加的日志。这些日志应该验证相关的服务数据。

例如:

```
class OrderTest(unittest.TestCase):
   def test_process_order_happy_flow(self):
         with self.assertLogs('foo',  level='INFO')  as cm:
               requests.get(f'/process_order/{TEST_CLIENT_ID}')
               self.assertEqual(
                     cm.output,
                     [f'INFO:send email to {TEST_CLIENT_ID}',
                      f'INFO:Charge {TEST_CLIENT_ID} succeeded!']
               )

```

**优点**:这种方法随时可用，不需要额外的工具。

**缺点**:

1.  日志并不总是可靠的，它们依赖于创建它们的开发人员(这并不总是发生)。
2.  基于日志的测试受到设计的限制，因为它们只测试日志而不测试操作本身。

**选项二:数据库查询**

如果我们将操作指示保存在数据库中，我们可以在测试期间查询数据库，然后基于数据库更新创建我们的测试:

class OrderTest(unittest。测试用例):

```
     def test_process_order_happy_flow(self):
          requests.get(f'/process_order/{TEST_CLIENT_ID}')
          client  =  Client.get_by_id(TEST_CLIENT_ID)
          assert client.charged_successfully is True
          assert client.email_sent is True

```

**优点** :

1.  它比基于日志的测试更可靠。
2.  副作用—这些数据稍后可以帮助我们在真实环境中生成分析。

**缺点** :

1.  将数据库暴露给测试项目并不总是容易的，因为这需要重新设计数据库方案，从数据库设计的角度来看这是错误的。
2.  就像前一种选择——这是一种“二手测试”我们测试 DB 对象而不是实际的操作，所以我们可能会遗漏一些问题。

可能有更多的选择，但它们都有类似的问题——它们不够可靠，而且太耗时。

这将我们带到了底线——这就是我所知道的大多数开发人员没有正确测试他们的代码的原因。

**选项三:合同测试**

契约测试是一种基于两个系统之间的契约以确保兼容性的测试方法。两个服务之间的交互存储在一个契约中，然后在通信过程中使用它来确保双方都遵守契约。 [Pact.io](https://docs.pact.io/) 是一个流行的契约测试开源解决方案。

**优点**:

1.  它确保了一致性。
2.  这是一个存储架构变更的单一位置。

**缺点**:

1.  它没有涵盖所有的用例——测试是基于实际的消费者行为而创建的。
2.  这需要嘲笑。

**选项四:端到端测试**

端到端(e2e)测试提供了系统组件以及消息如何在它们之间传递的全面概述。通过 e2e 测试，开发人员可以确保应用程序按预期运行，并且没有错误的配置阻止它在生产中运行。

**优点**:

1.  它提供了强大的测试。
2.  保证了微服务是真正为用户服务的。

**缺点**:

1.  维护和调试都很困难。
2.  它的成本很高。

选项五:基于痕迹的测试——一种新的测试范式

在过去的几年中，分布式跟踪技术的发展势头越来越猛。像[open telemetry](https://opentelemetry.io/)这样的标准允许以不同的方式看待微服务:从跟踪的角度。

分布式跟踪允许监视一个操作被激活时发生的所有事情。通过使用这种方法，我们可以处理每一个操作，并获得由该操作触发的应用程序中发生的所有事情的整体视图，而不是单独查看。

在 OpenTelemetry 术语中，轨迹由跨度构成。一个 span 代表一个操作——发送一个 HTTP 请求，进行一个 DB 查询，处理一个异步事件，等等。理想情况下，使用 spans 可以帮助我们回顾任何我们想要为测试验证的属性。此外，该跟踪还显示了连续的流程和操作之间的关系，而不是单个操作，这对于测试来说是非常有用的。

## **如何创建基于跟踪的测试**

当使用跟踪进行测试时，首先需要部署一个跟踪解决方案。如前所述，业内常见的寻人方案是 [OpenTelemetry](https://gethelios.dev/blog/opentelemetry-otel-is-opening-new-possibilities-for-developers/) ，或 OTeL。它还允许搜索功能。

让我们回顾一下，如果你想在 OTeL 测试中取得成功，你应该做些什么:

1.  部署 OTeL SDK。
2.  构建处理器服务，将 OTEL 数据转化为您可以使用的资产。
3.  创建一个可以保存所有痕迹的 ELK 服务。
4.  创建一个测试框架，允许您在跟踪中搜索特定的范围。

仅此而已。请注意，我们没有讨论任何可以帮助您研究痕迹的可视化工具，例如[【Jaeger】](https://www.jaegertracing.io/)上的 [Zipkin](https://zipkin.io/) ，但是您也可以使用它们。

但是到了最后，另一个工具还是不见了。

查看该领域中基于 OpenTelemetry 的相关开源工具，我们发现它们中的大多数都需要实现 OpenTelemetry 作为先决条件，这让我们感到同样的头疼。

## **太阳神**

Helios 是一个免费的工具，可以检测 OpenTelemetry，并允许开发人员为每个轨迹生成测试代码。

通过 spans，Helios 收集每个请求和响应的所有有效载荷。使用这一功能，开发人员可以在不更改任何代码行的情况下生成测试。

它也是以一种智能的方式构建的，允许从一个 bug 创建一个测试。更好的是，使用跟踪可视化工具，开发人员可以直接从跟踪中可视化地创建测试。

一句话:如今开发者测试微服务的方式已经被打破。既费时又低效。使用分布式跟踪测试是正确的答案——它允许开发人员正确地测试他们的微服务，因为它提供了所有微服务的整体视图。无论您选择哪种工具，都要确保利用它的能力。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>