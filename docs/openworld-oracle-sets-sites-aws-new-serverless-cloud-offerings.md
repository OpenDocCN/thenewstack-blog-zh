# 甲骨文全球大会:甲骨文将目光投向 AWS，推出新的无服务器容器服务

> 原文：<https://thenewstack.io/openworld-oracle-sets-sites-aws-new-serverless-cloud-offerings/>

虽然进入云市场较晚，但甲骨文希望其新的云产品能够通过成本效益出现在企业面前。虽然该公司尚未在市场上发起一场彻底的价格战，但它已经围绕高可用性和可靠性发起了一些战斗，将它们宣传为包含的功能，而不是在每分钟实例收费的基础上增加的额外费用。

该公司还增强了对容器的云支持，并在 Iron.io 的基础上推出了无服务器服务，可以作为亚马逊网络服务 Lambda 的替代产品。

甲骨文基础设施即服务和公共云服务副总裁 Kash Iftikhar 在本周于 T2 举行的甲骨文全球大会用户大会上表示，至少在考虑性能保证的情况下，甲骨文可以以亚马逊的零头价格提供高可用性存储。“当我们将我们的存储价格与[[亚马逊弹性块存储](https://aws.amazon.com/ebs/)价格进行比较时。伊夫蒂哈尔说:“我们能够以惊人的价格比提供高得多的性能。

例如，对于 400GBs 的存储和 20，000 次 I/O 操作，Oracle 每月收费 20 美元，而 Amazon Web Services 每月收费 1，350 美元。

伊夫蒂哈尔说，甲骨文能够提供这些数字，很大程度上是因为它正在收购新的硬件。甲骨文云提供大量固态硬盘、高性能多核处理器和英伟达 P100 GPU。“甲骨文将为云定价提出一个非常差异化的定价结构，”Iftikhar 说。“这将是云行业极具颠覆性的模式，因为它涉及到提供服务。”

## 看好 K8s

甲骨文也在本周的全球大会上宣布了新的云计算服务。甲骨文容器集团副总裁 Bob Quillin 表示，甲骨文云现在提供了一个容器原生应用开发平台。

该服务链基于 Oracle 云内 Kubernetes 业务流程服务构建。 [Kubernetes](/category/kubernetes/) 是一款开源容器编排工具，最初由[谷歌](https://cloud.google.com/kubernetes-engine)开发，现在由[云计算原生计算基金会](https://www.cncf.io/)管理。这与一个持续集成和持续部署平台联系在一起，该平台是利用甲骨文 [Wercker](http://www.wercker.com/) 收购的资产创建的，再加上一个私有的 Docker 注册服务。

该服务结合了 GitHub、Slack 和其他现代开发工具，允许团队在 Oracle 云内部协作和构建，同时使用他们已经采用的外部服务。

“你可以单独使用任何组件，”奎尔林说。“您可以构建应用程序，以本机方式推送至注册表，并推送至 Kubernetes 平台。这都是基于 1.7 版本的开放 Kubernetes 标准构建的。我们有一个符合 Docker V2 标准的注册中心。这是对这个容器原生世界的完全开放的堆栈方法。”

Quillin 还表示，Oracle 正在宣布 [Fn](http://fnproject.io) 的开源可用性。这个 Apache 2 许可项目旨在将无服务器计算带到任何平台上。在目前的形式下，开发者可以将 Amazon Lambdas 部署到 Fn，并在其他云环境中运行它们。

Fn 来自甲骨文团队在 [Iron.io](https://www.iron.io/) 上做的一些工作。Fn 也将与 Cloud Foundry 整合。

Quillin 说:“Fn 是一种开放的方法，专注于功能即服务。“你可以在笔记本电脑或任何云上运行它。它原本打算独立于 Oracle 云基础架构运行。它最终将在其上运行服务，但目前还没有宣布。”

Quillin 说，Fn 支持 Go、Ruby 和 Java。(截至发稿，fn 是否支持 Python 还没有定论，Lambda 确实支持)。“我们的理念是想出一些我们可以推向开发社区的东西，围绕无服务器的开放标准展开对话。无服务器是下一个大领域之一。我们从客户那里了解到，如果他们已经选择了 Docker 和 Kubernetes，下一步会怎么做？我如何选择我的平台。”

此外，Fn 功能可以以一种协调的方式链接在一起，Quillin 说。“你可以引入一个亚马逊 Lambda 函数，并将其导入 Fn。它会将其转换为 Fn 函数。我们围绕 HTTP puts 和 get 保留了一个通用接口。”

在 OpenWorld 的其他地方，甲骨文联合创始人兼首席技术官 [Larry Ellison](https://www.oracle.com/openworld/on-demand.html) 介绍了该公司自适应智能数据库产品的计划。他抱怨其他云缺乏性能保证，并承诺甲骨文的自主数据库将自我优化和自我修复。

## 依靠云

埃里森已经在该公司的季度报告电话会议上暗示了更多基于机器学习的自动化功能。该报告断言，甲骨文将在 2018 年第一季度获得约 14 亿美元的云收入。

前四个季度，该公司基于云的收入为 45 亿美元。然而，这是在软件、实际 IaaS 和 PaaS 收入以及 SaaS 收入之间划分的。

甲骨文的 SaaS 收益继续超过 IaaS 和 PaaS 收益。SaaS 目前占当前季度收入的 10 亿美元，并且每个季度增长约 1 亿美元。

然而，在过去两个季度中，实际的 IaaS 和 PaaS 收入几乎持平，甲骨文在 2017 年第四季度为 3.97 亿美元，而 2018 年第一季度为 4 亿美元。

T2 云计算基金会 T3 和 T4 谷歌 T5 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>