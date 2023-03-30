# Cortex 1.0 提供“企业级”分布式 Prometheus 监控

> 原文：<https://thenewstack.io/cortex-1-0-offers-enterprise-ready-distributed-prometheus-monitoring/>

在过去三年的大部分时间里， [Grafana Labs](https://grafana.com) 的团队一直在使用 [Cortex](https://cortexmetrics.io/) 来为 [Prometheus](https://prometheus.io/) 监控后端的指标和日志记录 [Grafana Cloud](https://grafana.com/products/cloud/) 提供支持，该公司现在已经发布了供通用的 Cortex 1.0，声称它提供了许多新功能和保证，使其为企业使用做好了生产准备。

“Cortex 实际上已经为生产做好准备很长时间了。Grafana 实验室产品副总裁、Cortex 作者 [Tom Wilkie](https://www.linkedin.com/in/tomwilkie/?originalSubdomain=uk) 说:“1.0 的主要信息是，现在你不必成为 Cortex 专家就可以在生产中运行它。“到目前为止，我们一直被批评为难以操作，因为有很多移动的部分，而且通常是一个移动的目标，因为皮层的发展一直在以相当快的速度前进，”

在 1.0 中，公司引入了稳定性保证，即围绕配置和管理软件的保证。它还包括文档以及预打包的仪表板。“总的来说，我们认为现在有足够的社区、足够的文档、足够的帮助和支持，让其他人来运行 Cortex，”Wilkie 说。

Cortex 是一个开源项目，是 Cloud Native Computing Foundation 的沙盒级成员，它提供了从许多 Prometheus 服务器查询指标的能力，而不会因为服务器故障而在图形中出现任何间隙。一篇[博客文章](https://grafana.com/blog/2020/04/02/cortex-v1.0-released-the-highly-scalable-fast-prometheus-implementation-is-generally-available-for-production-use/)详细介绍了该版本带来的新功能，包括详细介绍构建生产就绪 Cortex 部署所需步骤的生产文档、前面提到的[仪表盘和现成的 Prometheus alerts](https://github.com/grafana/cortex-jsonnet/) 、新的[稳定性和向后兼容性保证](https://cortexmetrics.io/docs/configuration/v1guarantees/)，以及为 Cortex 入门提供单个二进制可执行文件的单进程“飞行”模式。

关于这最后一点，Wilkie 指出了一个大大简化的启动和运行 Cortex 的流程，以及使用[微服务架构](https://thenewstack.io/kelsey-hightower-and-ben-sigelman-debate-microservices-vs-monoliths/)不容易获得的新用例。

“Cortex 是一种微服务架构，所以直到大约一年前，你还必须运行 15 种不同的应用程序，并将它们协调在一起，才能获得一个工作的 Cortex 集群，”Wilkie 说。“最近，我们将其作为单一流程模型引入。您可以在单个进程中运行单个命令、单个二进制文件，并获得完全正常工作的 Cortex 集群。这极大地简化了 Cortex 的操作复杂性。我们只在 Kubernetes 上运行过 Cortex，但现在我们有用户在裸机上运行 Cortex。”

上个月， [Sysdig 为可扩展的 Prometheus 支持提供了自己的解决方案](https://thenewstack.io/sysdig-offers-full-prometheus-capability-to-monitor-cloud-scale-workloads/)，称 Cortex 太复杂，实际上没有提供“支持整个云规模实施的规模水平”威尔基驳斥了这一评估，称“Cortex 具有难以置信的可扩展性和难以置信的成熟性”，并再次提到他们自己在过去几年中“大规模”使用 Cortex。

Cortex 维护者 [Goutham Veeramachaneni](https://github.com/gouthamve) 补充道:“我们在查询缓存和查询并行化方面投入了大量精力，Sysdig 后端现在使用我们的查询前端，其中一名工程师为我们做出了贡献。因此，他们使用我们的堆栈来改进他们的平台。”

作为其处理大规模数据能力的证据，Grafana Labs 不仅指出了自己的使用，还指出了印度尼西亚呼叫中心 [Gojek](https://www.gojek.com/) 的使用，据称该中心有 40 多个租户，每秒处理约 120 万个样本，如案例研究中所详述的。

云计算原生计算基金会是新堆栈的赞助商。

由[李中清](https://unsplash.com/@picsbyjameslee?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/s/photos/observe%5C?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>