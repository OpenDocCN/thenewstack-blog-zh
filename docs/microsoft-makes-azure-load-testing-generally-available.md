# 微软让 Azure 负载测试普遍可用

> 原文：<https://thenewstack.io/microsoft-makes-azure-load-testing-generally-available/>

微软已经让其 Azure 负载测试服务普遍可用，以帮助开发人员优化其应用程序的性能、可伸缩性和容量。

微软 Azure 开发工具合作伙伴产品总监 [Mandy Whaley](https://www.linkedin.com/in/mandywhaley/) 在[博客](https://azure.microsoft.com/en-us/blog/microsoft-azure-load-testing-is-now-generally-available/)中写道 Azure 负载测试是一个托管的[负载测试](https://thenewstack.io/simple-load-testing-with-github-actions/)服务，使开发者能够生成大规模负载，获得可操作的洞察力，并确保你的应用和服务的弹性，无论它们托管在哪里。

## 少花钱多办事

当谈到帮助[编码人员](https://thenewstack.io/pro-coders-key-to-stopping-citizen-developer-security-breach/)时，微软的总体目标是让开发人员在适用的情况下，以更少的努力和更低的成本做更多的事情。例如，当性能、可扩展性或弹性问题在生产环境中甚至接近生产环境时，解决这些问题可能会很困难，而且成本高昂。Whaley 说，通过 Azure 负载测试，开发人员可以在代码创作时发现问题，作为他们开发工作流程的一部分，从而节省时间和金钱。

Azure 负载测试使开发人员能够只为基础设施和服务方面的需求付费。开发人员还可以优化他们的基础设施，并确保他们的应用和服务能够适应客户流量的激增。你可以为你预期的客户流量做计划，只为你需要的服务付费。Azure 负载测试还帮助用户测试负载的意外增加。

微软云生态系统安全工程团队在一份声明中表示:“作为我们质量左移计划的一部分，云生态系统安全团队能够通过使用 Azure 负载测试作为我们 [CI/CD](https://thenewstack.io/a-brief-devops-history-the-road-to-ci-cd/) 管道的一部分来控制生产构建，从而防止多个独特的负载相关错误进入生产。”。“服务团队还将来自 Azure 负载测试的负载与来自 Azure Chaos Studio 的故障注入场景相结合，以复制、根本原因并防止使用常规测试框架难以捕捉的不愉快路径场景。除了服务弹性验证，Azure 负载测试有助于发现分布式系统的界限，并通过消除未使用的资源和框架节省了我们的成本。”

与此同时，微软的 Azure Synapse 工程团队也在一份声明中表示:“Azure Synapse 团队使用 Azure 负载测试来生成不同级别的工作负载，从高并发到针对 Synapse SQL 无服务器端点的大输入数据顺序执行。借助 [JMeter](https://jmeter.apache.org/) 的灵活性，我们可以启动/停止集群中可能引发不同故障的其他服务，从而真正测试我们服务的弹性。”

## 潜在用途

开发人员可以使用 Azure 负载测试来:

*   **优化他们的基础设施并确保应用弹性—**客户验证他们的应用和服务，以满足他们期望的客户流量，确保他们只为他们需要的东西付费。一旦客户优化了他们的基础设施，他们就测试他们的应用和服务的弹性，以处理负载的意外增加。
*   **捕捉回归-**客户可以通过在 Azure Pipelines 或 [GitHub Actions](https://thenewstack.io/8-github-actions-for-setting-up-your-ci-cd-pipelines/) 中运行负载测试来自动化回归测试，并比较不同负载测试的测试结果，以了解行为随时间的变化。
*   **利用客户端和服务端指标收集见解**–Azure 特有的见解有助于客户了解不同的负载场景如何影响其应用和服务的所有部分。Azure 负载测试使用 [Azure Monitor](https://www.gartner.com/reviews/market/application-performance-monitoring-and-observability/vendor/microsoft/product/azure-monitor) 创建监控数据，通过客户端和服务端遥测技术密切监控负载下的真实生产应用性能。
*   **启用高级负载测试场景**——对于更多这样的场景，客户创建一个基于 JMeter 的负载测试，这是一个流行的开源负载和性能工具。已经拥有现有 JMeter 测试脚本的客户可以在 Azure 负载测试中重用它们来创建负载测试。

## 指标、监控和可用性

此外，Azure 负载测试收集详细的资源指标来帮助你[识别 Azure 应用组件的性能瓶颈](https://aka.ms/MALT-IDperformancebottlenecks)。通过运行负载测试作为 CI/CD 工作流的一部分，您可以[自动化回归测试](https://aka.ms/MALT-AutomateRegressionTesting)。

Azure 负载测试还使用 [Azure Monitor](https://learn.microsoft.com/azure/azure-monitor/overview) 服务创建监控数据，包括应用洞察和容器洞察，以从 Azure 服务中捕获细节。

Azure 负载测试现已在 11 个地区提供:澳大利亚东部、东亚、美国东部、美国东部 2、北欧、美国中南部、瑞典中部、英国南部、西欧、美国西部 2 和美国西部 3。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>