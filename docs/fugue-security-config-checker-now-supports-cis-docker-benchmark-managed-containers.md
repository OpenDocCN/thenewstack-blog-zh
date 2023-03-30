# 神游安全配置检查器现在支持 CIS Docker 基准，管理容器

> 原文：<https://thenewstack.io/fugue-security-config-checker-now-supports-cis-docker-benchmark-managed-containers/>

云基础设施安全和合规引擎提供商 [Fugue](https://www.fugue.co/) 已经将来自互联网安全中心(CIS)的 [Docker 基准](https://www.cisecurity.org/benchmark/docker/)添加到其支持的指南列表中，以及由[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)和[微软 Azure](https://azure.microsoft.com/en-us/) 对托管容器服务的支持。就像其他合规性解决方案一样，Fugue 会查看公司的基础设施即代码和云配置，以确保它们符合最佳实践和法规，如 GDPR、HIPAA、NIST ISO 27001 800-53、PCI 和 SOC 2，但 Fugue 首席执行官 [Josh Stella](https://www.linkedin.com/in/josh-stella-949a9711) 表示，他的公司会更进一步，将其置于更大的环境中。

“Fugue 会查看你所有的云账户，检查你的基础设施代码和容器配置，寻找危险的错误配置。我们做到这一点，部分是通过可视化您的整个环境。如果你愿意的话，这有点像你的云基础设施的谷歌地图，”Stella 说。“在我们看来，如果你只关注容器的安全性，你就不会发现由于容器及其运行环境的组合而导致的错误配置和漏洞。与我们领域中的任何其他参与者相比，我们所做的一件事情是独一无二的，那就是，Fugue 实际上捕获了云配置每个方面的完整内存模型，然后我们可以在上下文中分析一切。”

随着 [CIS Docker 基准](https://www.cisecurity.org/benchmark/docker/)的加入，Fugue 现在检查诸如内存限制和无效挂载、是否使用了 root、根文件系统是否是只读的等等，自动化了一个过程，否则将通过手动比较您的设置和长列表中的设置来完成。运行检查后，Fugue 将提供如何修复您的配置以满足合规性规定的指导。同时，Fugue 还可以持续监控您的环境，确保基础设施不会偏离基线。

除了 CIS Docker 基准测试，Fugue 现在还包括 AWS 弹性容器服务(ECS)与 Fargate、AWS 弹性 Kubernetes 服务(EKS)、Azure 容器实例和 Azure 容器注册的连续配置可见性、安全检查和合规性报告。据 Stella 称，谷歌云平台(GCP)预计将在下个月的某个时候添加。

当我们在 2016 年第一次[看河豚的时候，该公司使用了一种自己创造的 YAML 式语言来建立其政策，但此后开始采用开源的](https://thenewstack.io/fugue-strives-bring-harmony-cloud-management/)[开放政策代理(OPA)](https://www.openpolicyagent.org/) 作为其所有规则的基础，包括平台提供的规则和终端用户创建的规则。

“我们的客户可以编写他们自己的 OPA，并以开源的方式表达他们的策略代码，而不是像许多人那样使用专有的伪语言。任何东西都可以使用 API，其美妙之处在于，因为我们可以一直检查您的基础架构即代码模板，并一直运行到生产，所以您可以在整个生命周期中使用单一策略，”Stella 说。“这真的很重要，因为否则你在运行时和开发时会有不同的检查，他们不会同意的。”

[https://www.youtube.com/embed/y54J2T-A8yc?feature=oembed](https://www.youtube.com/embed/y54J2T-A8yc?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>