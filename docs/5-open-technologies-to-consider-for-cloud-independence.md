# 考虑云独立性的 5 种开放技术

> 原文：<https://thenewstack.io/5-open-technologies-to-consider-for-cloud-independence/>

[](https://www.linkedin.com/in/markrhinkle/)

[Mark Hinkle](https://www.linkedin.com/in/markrhinkle/)

[Mark 在新兴技术和开源领域有着悠久的历史。在共同创立 TriggerMesh 之前，他是 Node.js 基金会的执行董事，也是 Citrix、Cloud.com 和 Zenoss 的高管，在那里他领导了他们的开源工作。](https://www.linkedin.com/in/markrhinkle/)

[](https://www.linkedin.com/in/markrhinkle/)[](https://www.linkedin.com/in/markrhinkle/)

在过去的几年中，几乎所有负责新基础设施项目的人都考虑过使用云计算来解决他们的问题。更快的价值实现时间和快速解决几乎任何需求的各种服务，使最初的决策变得很容易。虽然从长远来看，著名的 Andreessen-Horowitz 风险投资家和前企业家 [Martin Casado](https://a16z.com/author/martin-casado/) 观察到，在某些情况下，一旦工作负载达到一定规模，组织就会将应用程序迁移到他们自己的数据中心，以提供一些经济效益。在他最近与 [Sarah Wingo](https://a16z.com/author/sarah-wang/) 、*、[云的成本、万亿美元悖论](https://a16z.com/2021/05/27/cost-of-cloud-paradox-market-cap-cloud-lifecycle-scale-growth-repatriation-optimization/)、*发表的博文中，Casado 指出:

*现在，人们越来越意识到云的长期成本影响。随着云成本开始对总收入成本(COR)或销售成本(COGS)产生重大影响，一些公司已经采取了“遣返”大部分工作负载的重大举措(如 Dropbox)，或者在其他情况下采用混合方法(如 CrowdStrike 和 Zscaler)。那些已经这样做的人报告了显著的成本节约:2017 年，Dropbox 在其* *S-1* *中详细介绍了在 IPO 之前的两年中，由于基础设施优化大修，其中大部分需要从公共云中迁移工作负载，累计节约了 7500 万美元。*

## **面向云独立性的开放技术**

云的采用很可能会继续增长。然而，大多数组织应该保留他们的选择，采用能够像提供到内部数据中心一样容易地提供从一个云到另一个(或多个云)的路径的技术。以下是您应该考虑的开放技术列表。

### 1.库伯内特斯

列表中的第一项技术是显而易见的，大多数云原生用户都很熟悉它。Kubernetes ，也称为 K8s，是一个用于自动化部署、扩展和管理容器化应用程序的开源系统。使用 Kubernetes 作为您的部署层允许从几乎任何云到任何其他云或您的数据中心的可移植性，而无需重写您的应用程序。Kubernetes 不仅提供了编排容器化应用程序的方法，还托管了无服务器基础设施。Kubernetes 正在成为云计算事实上的架构。

### 2.将（行星）地球化（以适合人类居住）

[来自 Hashicorp 的 Terraform](https://www.terraform.io/) 是一款开源的基础设施即代码软件工具，提供一致的 CLI 工作流来管理数百个云服务。Terraform 将云 API 编码成声明性的配置文件。Terraform 是一个独立于云的部署工具，可以在多个云提供商上工作——例如，尽管 AWS 有自己的工具(AWS CloudFormation)，但它也支持 Terraform。Terraform 允许将基础设施表示为代码。这种易读的语言被称为 HCL，是 Hashicorp 配置语言的缩写。

### 3.Knative

[Knative](https://knative.dev/) 是一个基于 Kubernetes 的平台，用于部署和管理现代无服务器工作负载。Knative 最出名的是提供了一种交付无服务器功能即服务能力的方式——类似于 Amazon Lambda。另一个非常强大的功能是 Knative eventing system，它旨在通过提供可组合原语来支持后期绑定事件源和事件消费者，从而满足云原生开发的常见需求。这意味着您可以使用这些事件来提供系统与系统之间的状态变化。在 TriggerMesh，我们使用 Knative 提供一个[事件驱动的云原生集成平台](https://www.triggermesh.com/product-overview)来自动化工作流。我们认为这是我们为 Kubernetes 构建集成并为云和本地应用提供面向未来的集成平台的合理方式。Knative Eventing 即将发布 1.0 版本，并达到产品用户所期望的成熟度。

### 4.泰克顿

Tekton 是一个强大而灵活的开源框架，用于创建 CI/CD 系统，允许开发人员跨云提供商和本地系统进行构建、测试和部署。Tekton 允许开发人员自动化所有语言和框架的云原生部署管道。因为 Tekton 是开源的，工程团队可以定制该工具，并将其与其他工具集成。Tekton 是[持续交付基金会](https://cd.foundation/)的一个项目。

### 5.阿帕奇卡夫卡

[Apache Kafka](https://kafka.apache.org/) 是一个开源分布式事件流平台，被数千家公司用于高性能数据管道、流分析、数据集成和其他关键任务应用。随着我们对数据实时可用性的依赖日益增加，它是一种工具，可以让您更快地将数据放在需要的位置。最初在 LinkedIn 开发的 Apache Kafka 是一个可伸缩的消息队列，但现在 Kafka 不仅仅是一个消息队列。这是一个处理数据流的强大工具，当您的事件流需求达到更大规模时，它会大放异彩。如果你的消息量很低，你完全可以在现有的云提供商(AWS 中的 Kinesis，Google 中的 Pub/Sub，Azure 中的 EventGrid)中使用事件流。然而，如果你想要一个用于多个云的流媒体平台，那么 Kafka 是一个很好的解决方案。

## **多云、混合云、私有云——没关系**

与任何技术一样，将对供应商的依赖作为一种风险来权衡总是需要考虑的。在有可能被商品化的细分市场中——容器托管、无服务器、存储和其他几乎没有差别的服务——允许提供商之间迁移的策略是一种良好的实践。实现这一点意味着选择支持多个云和本地托管的工具。

这并不是说一些工具不能提供更大的价值，即使这意味着冒着依赖供应商的风险。像 Salesforce for CRM 或 snow flake for cloud-based data warehousing 这样的解决方案提供了极具吸引力的价值，值得供应商依赖。但是，要确保选择一个能够持续提高生产力的解决方案，不会对其他价值较低的技术产生不必要的依赖。

属于开放模型的开源和工具(尽管从定义上来说[并不总是开源的](https://thenewstack.io/amazon-elastic-and-the-fight-for-open-source-freedom-in-the-enterprise/))是云原生环境中无处不在的重要部分。虽然并非所有工具都是开源的，甚至可能不是软件(有些可能是有用的服务，如 Splunk)，但有大量高质量的工具为成功的云原生战略提供了机会。许多组织在开始云原生之旅时应该考虑这些事情。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>