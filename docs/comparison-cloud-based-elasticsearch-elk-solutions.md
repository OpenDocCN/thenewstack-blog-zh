# 通过 ELK 和云简化弹性搜索部署

> 原文：<https://thenewstack.io/comparison-cloud-based-elasticsearch-elk-solutions/>

本月早些时候，亚马逊网络服务推出了自己的[托管 Elasticsearch](https://aws.amazon.com/blogs/aws/new-amazon-elasticsearch-service/) 来支持日志分析和实时应用程序监控，使这家云巨头成为最新一家提供托管 Elasticsearch 的服务提供商。

这个想法很可靠。Elasticsearch 主要用于网站搜索、应用程序搜索和日志管理，以及其他功能。在大规模部署中使用 Elasticsearch 和完整的 ELK (Elasticsearch、Logstash、Kibana)堆栈可能会充满复杂性。维护和支持这样一个堆栈需要大量的知识和工作，因此公司越来越多地选择托管或即服务解决方案。

当您利用 ELK 的托管或自助式云解决方案时，您将获得许多优势，包括一个极其重要的优势—让您高枕无忧。无需花费不必要的精力，您就可以始终依靠该平台的高可用性、可伸缩性和安全性。

## 你自己的麋鹿……简直说不通

虽然外包 Elasticsearch 堆栈看起来是一个明确的选择，但这种方法也有一些复杂之处，特别是对于要求苛刻的工作负载。管理私有堆栈[包括任务](http://blog.takipi.com/hosted-elasticsearch-the-future-of-your-elk-stack/)，如部署和设置、入门、集成、UI、可扩展性、稳定性和维护。在麋鹿的私人环境中，后三个方面的问题会变得棘手。

适当的缩放需要工程师投入无数小时的工作。当困难的查询导致异常并导致无响应的 [Kibana](https://www.elastic.co/products/kibana) 仪表板时，稳定性受到影响。此外，当不同团队的成员必须访问您的仪表板，并且您面临着实施和跟踪每个团队成员的限制时，身份验证和授权可能是一个挑战。最后，系统应该始终保持不同 ELK 组件的最新版本。

总的来说，最好让团队来发展公司的核心竞争力，而不是浪费宝贵的时间来争论 ELK 的部署。

重要的是首先验证您的用例，并确定您是否需要 Elasticsearch 或完整的 ELK 堆栈。有许多指南可以指导您如何使用[部署 Elasticsearch](https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-logstash-and-kibana-4-on-ubuntu-14-04) 或[部署完整的 ELK 堆栈](http://logz.io/blog/install-elk-stack-amazon-aws/)，但选择正确的解决方案取决于您的具体要求。以下是一些常见的 Elasticsearch 和 ELK 用例以及相应的解决方案供您参考:

## 用例:搜索引擎

作为一个搜索引擎，Elasticsearch 非常通用；凭借其高可扩展性和速度，它可以用于为您的网站或应用程序创建内部搜索选项，既可以作为传统的搜索引擎，也可以作为更复杂的推荐引擎的基础。Elasticsearch 可以对文档进行排序，根据相关性对它们进行评级，根据受欢迎程度对它们进行排名，并实现不同的插件来进一步扩展功能。

使用 Elasticsearch，您可以存储客户信息以便于访问，运行基本的 CRM 分析搜索，甚至存储用于医学研究的数据，以便关联和快速获取信息。

为了享受高度可扩展和可用的生产级搜索引擎，你应该看看领先的解决方案: [compose.io](https://www.compose.io/) (被 IBM 收购)、 [qbox.io](https://qbox.io/) 、 [found.no](https://www.elastic.co/found) (被 Elastic 收购)以及亚马逊最近宣布的[托管 Elasticsearch 解决方案](https://aws.amazon.com/about-aws/whats-new/2015/10/introducing-amazon-elasticsearch-service/)。这些解决方案还丰富了基本的 Elasticsearch APIs，帮助您定制和增强用户的搜索体验。

## 用例:日志分析

日志分析是完整 ELK 堆栈的主要用例之一。Elasticsearch、Logstash 和 Kibana 的结合使得日志分析对大多数用户来说更加直观。然而，与日志分析相关的挑战不同于与搜索引擎功能相关的挑战:

*   **映射:** Elasticsearch 对模式冲突(映射)非常敏感，通常会因为映射中的冲突导致百分之一到百分之二的日志丢失。这可以使用各种映射适应方法来解决。
*   **突发管理:**根据定义，日志是“突发的”。一个数据库日志被清除，一个流量峰值或一个服务的失败都会导致过多的日志生成，需要 ELK 堆栈在几分钟内将 Logstash 和 Elasticsearch 的容量增加一倍或两倍。
*   **解析:**日志解析和丰富是专有日志解决方案的常见产品；否则，它需要用复杂的 Grok (Logstash)脚本独立解析日志，这是一项平凡且容易出错的工作。
*   **日志来源:**根据定义，日志可以来自不同的来源、地理位置和类型。日志可以由代理运送，也可以由 ELK stack 提取。这需要与 Logstash 插件集成，这些插件可以定期有效地从 S3、Heroku 和其他资源中提取数据。
*   **扩展日志存储:**这可能很有挑战性，可能需要严格的负载平衡、监控和错误纠正。
*   **索引管理和数据监管:**日志分析代表结构化和非结构化数据流，需要特殊的索引管理和自动清除旧的和不相关的数据。
*   **排队:**如果没有额外的组件，例如强大的、高度可用的排队系统，ELK 堆栈本身就无法运行，该系统允许伸缩、突发和输入控制。
*   **访问控制:**日志数据可以包含敏感数据，并支持研发、支持和开发运维团队之间的协作。认证和授权不是 ELK 堆栈的一部分。
*   **法规遵从性:**对于许多组织来说，将日志存档更长的保留期(几个月或几年)是强制性的。

推动 ELK 和专有软件之间竞争的厂商之一是 Logz.io。作为一个新的日志分析市场参与者，Logz.io 似乎是唯一一个在云即服务中为企业提供完整 ELK 堆栈的供应商。话虽如此，重要的是要注意，在日志分析领域，你可以找到其他专有的解决方案，如 [Splunk](http://www.splunk.com/) 和 [Sumo Logic](https://sumologic.com/) 。

## 最后一个音符

首先必须理解你的用例。你需要 Elasticsearch 还是一个完整的日志管理解决方案？了解每种选择的差距和挑战，并决定哪一种适合你。随着 Elasticsearch 和 ELK stack 的成功，公司现在提供这种开源软件的托管或服务版本。因此，它们可以帮助减轻维持弹性搜索的负担。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>