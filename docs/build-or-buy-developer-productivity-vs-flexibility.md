# 建还是买？开发人员生产力与灵活性

> 原文：<https://thenewstack.io/build-or-buy-developer-productivity-vs-flexibility/>

查尔斯·马勒

查尔斯是 InfluxData 网站的技术营销作家。Charles 的背景包括从事数字营销和全栈软件开发。

软件开发中的一个常见争论集中在是否使用已经可用的工具或服务，这可以提供更好的开发人员生产力，或者坚持使用较低级别的工具或定制的解决方案，这可以提供更多的控制和潜在的更好的性能和灵活性。这可以归结为是建还是买的决定。

这两种方法是当前许多科技行业意识形态冲突的根源:

*   云与运行自己的硬件
*   使用高级动态编程语言与低级语言进行应用程序开发
*   自托管服务与托管服务
*   内部定制工具与现成的软件即服务解决方案

使用开发人员工具时，在使用客户端库还是通过应用程序编程接口直接访问之间进行选择这样简单的事情就说明了这种冲突。在本文中，我将以 [InfluxDB](https://www.influxdata.com/products/influxdb-overview/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04_spnsr-ctn_restful-api_tns) 为例，介绍在客户端库和直接使用 API 之间进行选择时需要考虑的一些因素。正如我们将看到的，开发人员生产力和效率与灵活性和控制的潜在权衡也可以在软件开发的其他领域看到。

## 标准谈话要点

以下是争论双方在建设还是购买方面的一些主要观点。

团队购买论据:

*   允许更多关注核心业务。
*   团队可以更快地移动和添加功能。
*   更高效的预构建开源工具或专业托管服务可以节省成本。
*   硬件资源已经变得如此廉价，开发者的时间更加宝贵，所以提高开发者的生产力应该是重中之重。

反对这种观点的普遍观点是，这种心态导致了“软件吞噬世界”许多将软件视为应该外包的成本中心的老企业最终被重视软件并将其视为竞争优势的科技公司所取代。

Instagram 和 Dropbox 等公司(以及许多其他公司)是云服务的早期采用者，这使得他们可以更专注于产品而不是基础设施。

团队建设论据:

*   移除收取额外费用的服务提供商可以节省成本。
*   发展[内部专业技能](https://danluu.com/in-house/)带来长期利益。
*   与缺乏灵活性的通用工具相比，可以为公司的特定需求开发工具。
*   更少的外部依赖性，这可以防止停机或安全问题。

反对这一方的常见论点是，许多科技公司对用户的价值主张不是关于他们的技术如何在幕后运行。其他的批评包括“不要重新发明轮子”的建议和对“T2 不是这里发明的”综合症的诊断。大多数用户根本不关心事情在幕后是如何工作的；他们只是希望最终结果能够正常工作。

另一方面，[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)能够作为一项业务发展，是因为亚马逊开发了为其市场运营自己服务的内部知识。这种内部知识最终导致了一个万亿美元的云计算市场，彻底改变了科技行业。如果亚马逊遵循常识，试图外包这些业务，他们今天就不会领导云行业。

## 客户端库与 API

为了使事情更具体一点，让我们看一个非常简单的例子，显示双方的积极方面。开发者是 InfluxData 的 InfluxDB 的主要受众，influx db 是一个[时间序列数据库](https://www.influxdata.com/time-series-database/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04_spnsr-ctn_restful-api_tns)。它提供了[客户端库](https://docs.influxdata.com/influxdb/v2.2/api-guide/client-libraries/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04_spnsr-ctn_restful-api_tns)和通过 [API](https://docs.influxdata.com/influxdb/v2.2/api/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04_spnsr-ctn_restful-api_tns) 对数据库的直接访问，为开发人员提供了最适合其用例的选项。

客户端库提供了现成的最佳实践，因此开发人员可以快速开始读写数据。像批处理请求、重试失败的请求和处理异步请求之类的事情都被处理了，所以开发人员不必考虑它们。对于希望测试 InfluxDB 或将其快速集成到存储[时间序列数据](https://www.influxdata.com/what-is-time-series-data/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04_spnsr-ctn_restful-api_tns)的应用程序中的开发人员来说，使用客户端库是有意义的。

另一方面，需要更多灵活性和控制的开发者可以选择[直接与 InfluxDB 的 API](https://www.influxdata.com/blog/getting-started-influxdb-2-0-api-postman/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04_spnsr-ctn_restful-api_tns) 交互。一些公司有冗长的过程来添加外部依赖，或者已经有内部库来处理服务之间的通信，所以客户端库不是一个选项。有许多[公司](https://www.influxdata.com/customers/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-04_spnsr-ctn_restful-api_tns)已经将他们的产品创建为基于 InfluxDB 的扩展或平台，这是由于 API 的灵活性而成为可能。但是与使用客户端库相比，这需要更多的努力。

在微观层面上，以 InfluxDB 为例，您可以看到最佳选项将取决于具体情况。对于一家打算使用 InfluxDB 来监控其软件或不是其产品核心部分的相邻任务的公司来说，客户端库是有意义的，因为它们允许快速集成和开发人员生产率。

另一方面，如果一家公司打算使用 InfluxDB 作为其产品的核心部分，或者由于其他情况需要更大的灵活性，那么该 API 是可用的。通过提供选项，InfluxDB 试图为开发者提供两全其美的东西。

## 没有唯一正确的答案

尽管人们可能希望得到这类问题的明确答案，但事实是，这取决于每家公司以及它们在企业中的位置。要考虑的两个主要因素是:

1.  作为一个企业，你的软件项目对你的核心价值至关重要吗？
2.  就产品与市场的契合度而言，您的企业是否有能力通过构建定制软件来获得额外的优势？

对于一家仍在努力寻找产品市场契合度的初创公司来说，速度是最重要的因素，专注于此更有意义。对于一家更成熟的公司来说，构建定制工具、提高软件效率或迁移到自己的硬件上，可以提供超越竞争对手的优势。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>