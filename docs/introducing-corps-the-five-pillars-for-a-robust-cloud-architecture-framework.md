# CORPS 简介:强大的云架构框架的 5 大支柱

> 原文：<https://thenewstack.io/introducing-corps-the-five-pillars-for-a-robust-cloud-architecture-framework/>

本文反映的观点是作者的观点，不一定代表全球 EY 组织或其成员公司的观点。

[](https://www.linkedin.com/in/snarang/?originalSubdomain=in)

 [桑杰·纳朗

桑杰·纳朗是一位充满激情的技术领导者，一直在推动大规模的数字和云转型。他是 EY 云计算架构和战略的全球负责人。他的主要工作是加速云创新和敏捷性的应用，并在 ey 面向客户的解决方案中最大限度地发挥现代技术的优势。最近，他一直专注于帮助客户的多云战略和实施。在 EY 之前，他在微软工作，在那里他带领客户进行云转型，并帮助了一些最大的企业和初创企业。](https://www.linkedin.com/in/snarang/?originalSubdomain=in) [](https://www.linkedin.com/in/snarang/?originalSubdomain=in)

云提供商一直在高速创新，并不断发布新的服务和功能。你有多个服务来做同样的事情。此外，使用不同的服务、特性和模式，您有多种方法来设计和架构您的应用程序和工作负载。越来越多的选项增加了设计和构建云应用程序的复杂性。

此外，不同的云架构师可以针对相同的业务需求提出完全不同的架构。没有明确一致的方法来确认该架构是否满足现代业务应用程序的需求，如安全性、可靠性和性能。随着您的业务随着时间的推移而增长或变化，您的工作负载需要扩展并适应新的业务要求，这给您的技术架构增加了相当大的开销和复杂性。

幸运的是，三家超大规模云提供商已经意识到这种日益增长的复杂性。这三家公司:[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)，微软 Azure 和谷歌云平台(GCP)，都为各自的云提出了一个云架构框架。

这些云架构框架为在云中设计和操作应用程序提供了架构指南、设计原则、最佳实践以及其他工具和资源。有趣的是，它们都基于共同的架构支柱，我称之为**云军团**。三个主要的提供商正在为架构良好的应用程序推荐这些公共支柱。您还应该在您的组织中制定措施和流程，以确保您的云架构师基于这些支柱设计和审查应用程序。

在这篇文章中，你会发现三个最大的提供商的云架构框架的细节:AWS，Azure 和 GCP。它们还提供了相关的工具和框架。您将了解框架和工具的完整情况，以及它们提供的特性。您可以使用这些信息来制定在您的组织中如何利用这些框架和工具的策略。

在本文的第二部分(将在后面发表)，我将深入探讨为什么所有的提供商在他们的框架中选择完全相同的支柱。它们之间的共同点是什么，如何在您的应用程序中使用它们，以及您可以做些什么来充分利用它们来满足您组织的特定业务需求。

## 云军团——定义和前景

三家超大规模提供商(AWS、Azure 和 GCP)提供不同类型的资源，如框架、工具和插件，以帮助您采用云，并设计架构良好的云应用。这些资源大多使用公共支柱，我称之为云军团(你很快就会知道为什么)，对它们的指导和建议进行分类。因此，我将所有这些资源统称为云团队环境，这将在本文和相关图表中进行描述。

## 公共支柱

所有三家提供商的云架构框架都基于五个共同的支柱:

1.  成本优化
2.  卓越运营
3.  可靠性
4.  性能效率
5.  安全性

根据剑桥词典，单词“[军团](https://dictionary.cambridge.org/dictionary/english/corps)”的定义之一是“一群因为参与特定活动而联系在一起的人”以上五大支柱协同工作，让您的云架构变得强健、故障安全且面向未来。因此，我称他们为云军团，每个字母代表一根柱子，柱子的名字以那个字母开头。此外，军团这个词很容易记住每个支柱的名字。

## 架构框架

架构框架是景观的核心基础。它们为构建高质量、安全、高性能、弹性和高效的云应用程序和工作负载提供了一套指导原则。你不可能有一个单一的方法来设计一个适合所有需求的架构。然而，无论架构、技术或云提供商如何，都有一些通用概念适用。因此，它们可以帮助您制定一致的方法来评估和实施云架构。它们提供了指导原则和最佳实践，这些原则和实践分为五大支柱:云团队。

不仅仅是支柱在框架中是通用的，事实上，两个提供商(AWS 和 Azure)给他们的框架起了完全一样的名字:架构良好的框架。尽管 GCP 给它起了不同的名字:谷歌云架构框架。GCP 也有一些略有不同的支柱名称。公司工程师称安全支柱为“安全、隐私和合规”而且，他们将“性能效率”和“成本优化”这两大支柱合二为一，称之为“性能和成本优化”

有趣的是，去年(2020 年)在架构框架方面发生了很多事情。谷歌在 2020 年 5 月推出了他们的云架构框架。AWS 在 2020 年 7 月发布了其架构良好的框架的第八个版本。他们最初在 2015 年发布了它，这是第四个版本(因为前三个版本是内部版本)。微软也在 2020 年 7 月推出了他们的 Azure 架构良好的框架。他们保留了 AWS 中的框架名和支柱名。

## 架构框架工具

AWS 和 Azure 还提供工具，根据其架构良好的框架提供的最新指导来评估您的工作负载和应用程序。这些工具是评估问卷，您可以在问卷中回答公司每个支柱下的许多问题。这些问题有多项选择。根据您的回答，该工具会为您提供建议，其中包含详细描述以及实施这些建议的资源列表。我预计谷歌也将很快发布类似的评估工具。

## 架构框架附加组件

附加组件将基础架构框架提供的指导扩展到特定的行业和技术领域，如机器学习、分析、无服务器、高性能计算(HPC)、物联网(物联网)和金融服务。您可以添加适用的附加组件来全面评估您的工作负载。在这一点上，只有 AWS 提供这样的插件，称为 AWS 良好架构的镜头。考虑到 AWS 在其第六个版本中将镜头添加到其良好架构的家族中，我预计其他提供商也会在未来的版本中发布类似的附加组件。

## 顾问工具

AWS 和 Azure 也有相关的工具，分别叫做 AWS 可信顾问和 Azure 顾问。架构框架工具依赖于您提供通用评估问题的答案，以提供建议，这些建议本质上也是通用的。另一方面，顾问工具不依赖于您。他们扫描、检查和分析您部署的工作负载，并针对您的部署提供个性化的可行建议。这些建议被分为不同的领域，这些领域与保护团的支柱相同或相关。虽然 Google 目前没有提供这样的工具，但我希望它将来会发布一个。

## 云采用框架

架构框架假设您已经在您的组织中采用了云，因此主要关注于成功地设计和操作您的工作负载。因此，他们的主要目标受众是云架构师、工程师和开发人员。但是，如果您需要关于如何在您的组织中采用云以实现最大收益的指导，所有三家提供商也都有他们的“云采用框架”谷歌还提供了云成熟度评估调查，作为其采用框架的一部分。云采用框架可帮助您确定关键的云采用活动、差距以及人员、技术和流程方面的目标。他们提供最佳实践、文档和工具来帮助您创建和实施必要的业务和技术战略，以便您的组织在云计算中取得成功。因此，他们的主要目标受众是云架构师、IT 专业人员和业务决策者。

架构和采用框架这两种框架是相互联系的。云采用框架有助于三个高层战略:业务、平台和工作负载。架构框架可以被视为工作负载策略级别的采用框架的一部分。

## 利用云团队环境

这三个云提供商在不同的时间以不相交的方式在云团队环境中发布了这些不同类型的资源。然而，由于大部分都是基于基本的军团支柱，我希望它们在未来的几个月里会变得更加完整，相互联系更加紧密。微软已经开始这么做了。他们的 Azure Advisor 工具提供了完全按照公司支柱分类的建议。他们的采用框架指的是架构良好的评估。我预计 AWS 和 GCP 可能会遵循类似的方法，在所有这些资源之间提供一致的连接。

作为云专家或企业所有者，了解这一领域中不同类型的资源以确保您的云之旅和投资的成功非常重要。您还应该了解它们之间的关系，以及如何以及何时在您的云之旅中利用它们。即使您的组织或应用程序只针对一种云，也值得看看其他云提供商的框架和指南，看看是否还有其他方面可以利用。例如，GCP 目前还没有架构框架评估工具。如果您的应用程序部署在 GCP，您仍然可以使用 Azure 或 AWS 的调查问卷，因为许多问题都与流程和一般架构指南有关，并且对于云提供商来说是不可知的。即使有关于使用特定云服务的建议，你也应该能在 GCP 找到类似的服务。类似地，Azure 和 GCP 也不提供特定领域的附加组件。如果您的应用程序部署在这些云中，您仍然可以利用 AWS 架构良好的透镜来获得这些领域的一般指导。

在本文的第二部分，我们将深入探讨架构良好的框架的不同方面，以及如何利用它们来满足组织的特定业务需求。

## 参考

2020 年—云架构框架发布的重要一年

自动警报系统

蔚蓝的

GCP

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>