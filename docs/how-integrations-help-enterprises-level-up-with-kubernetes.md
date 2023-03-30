# 集成如何帮助企业提升与 Kubernetes 的关系

> 原文：<https://thenewstack.io/how-integrations-help-enterprises-level-up-with-kubernetes/>

在 [Kubernetes](https://thenewstack.io/category/kubernetes/) 上运行的[云原生](https://thenewstack.io/category/cloud-native/)系统可以给一个组织很多选择。哇，多么轻描淡写。

瞥一眼[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) [及其 1000 多种工具和服务](https://landscape.cncf.io/)，会让人眩晕。这么多选择！2014 年 Kubernetes 的发布催生了一个全新的项目和产品行业，旨在使基于云的系统更加高效、可观察、安全和用户友好。

今天，基础设施是可组合的:更多的开发人员和架构师正在组合来自整个 CNCF 领域的最佳选择，并大量使用开源软件，而不是组合单一堆栈解决方案(比如，通过使用像 Oracle 的 WebLogic 或 IBM 的 WebSphere 这样的应用服务器)。

对于企业及其 IT 团队来说，云原生的优势是显而易见的:它更快、更具可扩展性。正确的工具和应用程序可以提高工作效率，增强可观察性，并确保安全。

但是[越来越多的团队部署到公共云、虚拟机、裸机、内部数据中心和边缘计算资源的混合](https://thenewstack.io/serverless-multicloud-popular-with-k8s-users-survey-says/)。

“我们看到许多企业说，我有 Azure，我有谷歌和亚马逊，我有我的数据中心。我需要我的架构和应用无处不在，因为我的业务性质，”在 [Confluent](https://www.confluent.io/?utm_content=inline-mention) 从事产品管理的 [Rohit Bakhshi](https://www.linkedin.com/in/rohitbakhshi/) 说。

在 Kubernetes 管理的系统中使用的各种工具和平台会使一切协调起来变得更加复杂。

“集成是困难的，尤其是在分布式系统中，”甲骨文产品战略的产品经理 Sherwood Zern 说。他与世界各地的企业客户合作过，可以证明这些难题是普遍存在的。

“有一次我在马来西亚，我和这位首席信息官聊天，他问我，‘为什么这这么难？’”泽恩回忆道。我只是回答他，“这很难，因为你在处理分布式系统，这意味着有多个领域会失败。"

运行在多个云上的 Kubernetes 系统引入了更大的复杂性。“虽然 Kubernetes 本身是一个事实上的标准，但 Kubernetes 的实现可能因平台而异，”RedMonk 的首席分析师兼联合创始人 Stephen O'Grady 说。

## 集装箱化集成如何帮助

容器化的微服务应用程序是云原生软件的构建模块，声明式编程(其中程序列出了它们所需的结果，而没有明确列出获得这些结果的步骤)用于创建这些应用程序。Kubernetes 本身是声明性的，它抽象并处理它运行的应用程序的配置。

“人们已经接受了使用 Kubernetes API 的声明性思维。这些实践不仅适用于传统应用，也适用于集成，”专注于应用集成的 [TriggerMesh](https://triggermesh.com/?utm_content=inline-mention) 联合创始人兼产品负责人[塞巴斯蒂安·戈阿斯根](https://www.linkedin.com/in/sebastiengoasguen/)说。

Zern 说，声明性代码解放了开发人员，让他们把时间花在满足应用程序的业务用例上。“作为一名开发人员，我可以专注于我的应用程序，而不必担心，现在我需要一个测试环境。现在我需要去构建我的 Kubernetes 集群。我的社交规则是什么？我用什么硬件？”

Goasguen 说，在 Kubernetes 运行的系统中，企业团队面临的一些重大挑战是如何[使他们的应用程序](https://thenewstack.io/app-modernization-why-lift-and-shift-isnt-good-enough/)现代化，以及如何在多/混合云环境中使服务之间的集成现代化。

主要的云提供商——亚马逊、谷歌、微软——为 Kubernetes 运行的应用程序提供集成。但他们并不总是能与竞争对手的云平台兼容。

事件驱动的架构可以帮助集成应用程序，在这种架构中，事件(例如，状态的变化)被用来触发解耦的服务并在它们之间进行通信。

这样的建筑“给你一种持久性和事件的历史。它将一切建模为一个事件，并允许您重放和建模您的建筑事件，”Confluent 的 Bakhshi 说。

事件使 DevOps 团队能够从所有应用程序中获得最佳效果，并在事件驱动的架构中将它们联系在一起。CloudEvents 是一个开源项目，是一个以通用方式描述事件数据的规范。通过无缝集成，云服务本质上成为了云原生应用的库。

## 将开源作为工具的默认设置

现在让我们回到 CNCF 的风景。所有这些选择不仅提供了为每个用例选择最佳工具的机会，也带来了昙花一现的危险。

Zern 提醒我们，挤满云本地市场的产品“正在相互竞争，最终，会有一些产品被淘汰出局。我想确定我会试着选一个最后还站着的。我该怎么做呢？”

防止选择短命解决方案的一个方法是将开源作为工具的默认选择。鉴于开源项目的开发和维护是由大量的贡献者完成的，因此比起那些由小公司创建的项目，开源项目可能更有可能存活下来，不管这家初创公司吸引了多少风险资本。

基础设施即代码工具——允许用户管理其云原生基础设施并将该基础设施部署到 DevOps 团队的声明性代码——包括 Ansible、Chef、Puppet 和 Terraform 等流行的开源项目。

开源给这些工具带来了灵活性、外部开发人员检查代码的自由以及不受供应商限制的优势。但是它们也比传统的配置工具更加自动化。

如果使用声明性代码构建，工具可以使开发人员在不深入了解特定工具的情况下更容易地进行更改——这对于希望同时在许多服务器中推出更改的企业来说是一个好处。作为代码，它也可以与版本控制工具一起使用，并且在出现错误时回滚到以前的版本。

## 什么是作为代码的集成？

作为代码的集成(Integration as code)是[新开源的](https://thenewstack.io/triggermesh-integration-platform-now-an-open-source-project/) TriggerMesh 的 API 和集成背后的概念，旨在使跨越多个云和内部数据中心的[数据](https://thenewstack.io/category/data/)和云原生应用程序的连接变得更加容易和快速。

它通过 API 从应用程序接收事件来实现这一点，例如，检测状态变化，如果需要，转换该事件，以便它可以与公共云、本地服务器或两者集成。

根据 Goasguen 的说法，对于企业来说，TriggerMesh 及其作为集装箱化集成的能力可以在许多方面放大 Kubernetes 的优势:

### 日志和指标收集。

例如:Goasguen 建议，如果你想备份 Elasticsearch 中的所有 Salesforce 或 git commit 事件，以便创建一个数据湖并进行业务分析，这将是 TriggerMesh 的一个用例示例。

### 创建事件驱动的应用程序。

Goasguen 说，PNC 银行将 TriggerMesh 与其 DevOps 治理结合使用，这种做法在金融机构中越来越受欢迎。

“他们实时接收事件，然后希望能够按需触发风险控制评估，”他说。“因此，他们的风险控制是作为无服务器功能运行的。然后用 TriggerMesh API 对触发事件流的实际事件进行编码。”

### 提高传统工作流程的效率。

能够编写与任何部署环境无缝集成的云原生应用程序有助于企业从其 Kubernetes 运行的架构中获得最大优势。

Goasguen 说，TriggerMesh 将其旗舰产品开源的举动部分是为了帮助加速集成即代码工具的采用。

Confluent 的 Bakhshi 建议，这一举措有助于企业开发人员深入研究，不断改进该工具并为其找到新的用途。

Bakhshi 说，如果“作为一名开发人员，我正在构建一些新的东西，我将违背开放协议和开放 API 来完成它。因为我知道我总是可以进化的。我可以从在本地某个地方部署它开始，我可以把它部署在一个云服务器上，它使用相同的应用程序 API、相同的协议，这不会改变。

“所以这非常重要。这是一种在东西开源的时候让更多上游开发者进来的方式。他们可以拿起它，很容易部署，他们可以摆弄代码。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>