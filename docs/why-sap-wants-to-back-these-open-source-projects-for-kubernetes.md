# 为什么 SAP 想要支持 Kubernetes 的这些开源项目

> 原文：<https://thenewstack.io/why-sap-wants-to-back-these-open-source-projects-for-kubernetes/>

SAP 可能是世界上最大的专有软件公司之一，但它高度致力于支持开源社区和 Kubernetes 的开发。

对于 Kubernetes 项目的[社区规模和健康评估仪表板](https://k8s.devstats.cncf.io/d/9/companies-table?orgId=1&var-period_name=Last%20year&var-metric=committers)whit 来说，SAP 在 2019 年位列 Kubernetes 的前 10 名承诺者。根据 [Knative 年度报告](https://knative.dev/community/contributing/annual_reports/Knative%202019%20Annual%20Report.pdf)，SAP 也是 2019 年 Knative 的第六大贡献者。这些贡献代表了 SAP 致力于开源和向客户提供解决方案的一个例子，这样他们就可以在企业范围内利用 Kubernetes。

## SAP 为什么选择投资 Kubernetes？

随着 SAP 的客户转向云，提供促进这种转变的解决方案促使该公司研究 Kubernetes 及其潜力，以帮助巩固所涉及的不同工具和服务的互操作性。借助 Kubernetes，SAP 能够提供易于采用的解决方案，并且能够跨公共云、私有云和混合云环境在企业范围内运行。SAP 的贡献主要集中在服务目录、消息传递和事件上。

## 使用服务目录调配云服务

Kubernetes 孵化项目服务目录允许您直接从本地 Kubernetes 工具中提供云服务，而不管服务实际托管在哪里。service-catalog 项目的最终目标是为 Kubernetes 用户提供一种方法，让他们能够消费来自代理的服务，并轻松地配置他们的应用程序来使用这些服务，而不需要关于如何创建或管理服务的详细知识。SAP 积极参与该项目，并且是服务目录特别兴趣小组(SIG)的成员。

了解有关服务目录如何工作的更多信息，并尝试在[服务目录网站](https://svc-cat.io/)上浏览。

### 将开源和云原生工具与 Kyma 项目连接起来

[Kyma](https://kyma-project.io/) 是一个 SAP 驱动的开源项目，位于 Knative 之上，支持应用程序开发人员通过开放服务代理目录使用第三方服务，同时提供与企业系统的无缝连接。它通过充当“胶水”将几个开源和云原生工具粘在一起，为扩展具有无服务器功能和微服务的应用提供了一个平台。它还为 Knative 中基于 Kafka 的事件实现提供了一个替代方案，例如当 Kafka 实现的资源消耗大于预期时:一个基于 NATS 流的事件解决方案 [Kyma 事件总线](https://kyma-project.io/docs/#details-components-event-bus)。

在这篇[博客文章](https://kyma-project.io/blog/2019/12/20/netconomy-use-case/)中，了解 Netconomy 如何利用 Kyma 构建一个大型电子商务解决方案，这篇文章概述了该公司使用 Kyma 的背景、他们如何实施以及他们对未来的计划。

### 使用 Project Gardener 大规模管理 Kubernetes 集群

 [迈尔斯·芬伦

Myles 是 SAP 全球开发人员和社区关系团队的成员，专注于开源和云开发主题。他在 SAP 担任过各种职务，从技术写作到教育和项目管理。他还写了一些新颖的工作空间，以及它们如何有助于在大型企业中培养新的协作和创新方式。](https://www.linkedin.com/in/myles-fenlon-b0137342/?originalSubdomain=de) 

随着对集群需求的增长，对管理这些集群的工具的需求也在增长。尽管超大规模集群提供了自己的集群管理工具，但 [Gardener](https://gardener.cloud/) 解决了以同构方式管理跨多个基础设施的数千个集群的需求。它是一个工具，允许在一个地方管理集群(无论它们在哪里运行)，具有高度的自动化。Gardener 是另一个 SAP 驱动的开源项目，该项目源于公司自身管理其对 Kubernetes 集群不断增长的需求的需要。

通过[点击此处](https://gardener.cloud/adopter/)了解 Gardener 被公司使用的工作负载和场景。

除了选择 Kubernetes 并将其用于越来越多的云应用程序之外，SAP 在为一系列主题的开源项目做出贡献方面也有相当长的历史。这些贡献的一个常见目标是更好地支持开源工具在企业范围内的使用，以努力使已经拥有企业工作负载、需要云计算的灵活性和优势、需要从第一天起就能够在企业范围内运营并期望从其本地体验中获得稳定和可靠性的客户和公司更容易访问云原生。

规模只是故事的一部分。基于开源原则的构建工具也非常重要。讨论、决定和实现开源工具(如 Kubernetes 和相关项目)未来版本的能力对 SAP 来说非常重要，因为它确保建立事实上的标准，帮助巩固不同工具和服务的互操作性。

欲了解更多关于 SAP 开源活动的信息并为项目做出贡献，请访问[opensource.sap.com](http://opensource.sap.com)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>