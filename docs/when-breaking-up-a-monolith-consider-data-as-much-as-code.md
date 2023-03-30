# 当分解一个整体时，要像考虑代码一样考虑数据

> 原文：<https://thenewstack.io/when-breaking-up-a-monolith-consider-data-as-much-as-code/>

[在拆散一个庞然大物的时候，考虑的数据和代码一样多](https://thenewstack.simplecast.com/episodes/when-breaking-up-a-monolith-consider-data-as-much-as-code)

迁移到微服务架构最具挑战性的一个方面是决定首先将整体中的哪些部分分离成独立的服务。架构师必须理解业务目标、服务如何运行以及它们将如何与整体的其余部分相关联。然后，一旦服务启动并运行，团队将面临更多的挑战。操作复杂性增加了，因为每个服务可能有自己的语言、工具集和基础设施。

为了帮助解决迁移到微服务时出现的这些和其他问题，Dynatrace 等公司在 Prometheus 等现有开源工具的基础上推出了一套新的商业监控解决方案。通过 API 从多个来源获取数据，此类监控工具可以提供应用程序的完整视图，从网络上的流量模式和执行的数据库语句，到服务运行的容器、平台和主机。

“一旦你安装了 Dynatrace，我们就在监控和跟踪每一个服务、进程、主机、日志以及最终用户，”DevOps 活动家 Andreas Grabner 说。“我们有来自您的完整环境的完整的实时依赖关系图。”

例如，这种全面的视图可以帮助架构师确定如何最好地进一步分解代码库。Grabner 说，它还可以帮助确定特定问题的技术根本原因，并提供额外的背景，如有多少用户受到影响，以及在哪些地区帮助更快地修复问题。

Grabner 说:“基于开源工具的商业产品让你相信这些工具将会持续，而不仅仅是由一个一年后可能不复存在的小社区支持。”“他们还为您提供支持服务的最佳实践。”

Dynatrace 在其客户中观察到，将一个整体拆分为多个微服务的一个新兴最佳实践是为每个服务提供自己的数据存储。如果一个应用程序由一个大型的关系数据库支持，那么组织必须首先决定如何将与该服务相关的数据提取到自己的数据存储中。

Grabner 说:“有时，当人们谈论将整体拆分成服务时，他们只考虑代码。“但是，这项服务所依赖的数据位于何处也很重要。您必须将当前的数据存储视为另一个整体。”

了解云本机监控工具的使用案例、打破数据库垄断的最佳实践，以及如何利用新旧系统来获取团队对应用程序进行业务关键型更改所需的信息。

在采访中，Grabner 提到了如何使用亚马逊网络服务的 Alexa 部署语音监控。更多信息请点击此处:

[https://www.youtube.com/embed/ghuFQTCer7I?feature=oembed](https://www.youtube.com/embed/ghuFQTCer7I?feature=oembed)

视频

## 在这个版本中:

[1:48:](https://thenewstack.simplecast.com/episodes/when-breaking-up-a-monolith-consider-data-as-much-as-code?t=1:48) 您如何看待 Dynatrace 及其目标背景下的 DevOps 发展？
[6:35:](https://thenewstack.simplecast.com/episodes/when-breaking-up-a-monolith-consider-data-as-much-as-code?t=6:35) 组织在后台做了哪些工作，以使构建这些服务并可能具有不同技能水平的人更容易完成这些工作？
[12:29:](https://thenewstack.simplecast.com/episodes/when-breaking-up-a-monolith-consider-data-as-much-as-code?t=12:29) 探索这些有经验的人在过去几年中参与了开源软件的开发工作
[15:15:](https://thenewstack.simplecast.com/episodes/when-breaking-up-a-monolith-consider-data-as-much-as-code?t=15:15) 您希望通过哪些方式来改善对特定平台和服务的支持？
[22:16:](https://thenewstack.simplecast.com/episodes/when-breaking-up-a-monolith-consider-data-as-much-as-code?t=22:16) 您能告诉我们更多关于 Dynatrace 架构的信息吗？
[29:40:](https://thenewstack.simplecast.com/episodes/when-breaking-up-a-monolith-consider-data-as-much-as-code?t=29:40) 能给我们介绍一下丹拿大学吗？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>