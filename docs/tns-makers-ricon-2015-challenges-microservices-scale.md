# 来自 Ricon 2015 的 TNS 制造商:大规模微服务的挑战

> 原文：<https://thenewstack.io/tns-makers-ricon-2015-challenges-microservices-scale/>

随着越来越多的企业和初创公司在其分布式系统环境中过渡到容器，或者开始在日常工作流中使用微服务，更好地了解正在运行的服务以及在某种程度上更好地理解这些微服务如何配合在一起的需求变得至关重要。

Basho 的 Ricon 2015 上周在旧金山举行，围绕微服务、在容器中工作以及大规模使用应用程序的敏捷开发策略进行了讨论。New Stack 创始人 Alex Williams 就当前分布式系统面临的问题与,[电池风险投资](https://www.battery.com/)的技术研究员阿德里安·科克罗夫特和 [Pivotal](http://pivotal.io/) 的首席技术专家布里吉特·克罗姆胡特进行了交谈。

## 电池投资公司的艾德里安·科克罗夫特

科克罗夫特说，监控微服务是当今分布式系统面临的主要问题之一。微服务已经成为技术的最新流行语，因为它们能够将应用程序开发问题分解为更小的、可操作的任务，然后可以分配给个人并迅速采取行动。这允许企业更快地构建系统。

对于微服务，应用程序有许多小部分，通常与依赖项捆绑在一起，以确保跨各种系统的功能。如果开发人员的堆栈中只有少量的微服务，这很容易跟踪。然而，当一个生产部署中有数百个微服务时，跟踪它们可能会很快失控。

为了帮助解决微服务可见性的问题，科克罗夫特建立了一个微服务模拟器，模拟在一系列服务器上运行的复杂系统环境，每个单独的容器都生成数据以连接微服务监控工具。这将为开发人员提供一个场景，其中运行着 500 个或更多的虚拟机，以及相关的指标。

对于当前可用的数据模型，可能会有一个复杂的依赖关系链，需要费力才能找到正确的图。现有的工具如甲骨文的 [EPM](https://www.oracle.com/applications/performance-management/index.html) 试图通过系统捕捉呼叫流，其他工具如 [App Dynamics](http://www.appdynamics.com/) 和 [New Relic](http://newrelic.com/) 也是如此。这些模型通常很简单，由前端、中间层和数据库构成。

一旦有数百个微服务和数据库部署了这种系统架构，这种软件就很难跟上，因为它们的数据模型很难掌握这些微服务如何在容器之间进行数百或数千次调用。

“发展世界在你脚下变化如此之快，你不能假设一切都将保持静止，”科克罗夫特说。

[阿德里安·科克罗夫特，崎勇:《里康访谈》](https://thenewstack.simplecast.com/episodes/adrian-cockcroft-battery-ventures-the-ricon-interviews)

## 布里奇特·克鲁姆胡特，Pivotal

分布式系统正在变得如此庞大，以至于人类很难从逻辑上确定它们的规模。“如果一个人甚至不能开始理解一个系统的架构，那么他们如何决定服务位于何处，或者它们的依赖关系是否会一起工作？”克鲁姆豪特说。

这就是开发人员不得不求助于自动化来解决这些特殊问题的地方。如果软件开发团队试图通过在头脑中可视化整个系统来解决问题，那么几乎肯定会失败。大规模构建系统要求它们既有弹性又有容错能力，尽管 Kromhout 强调试图从系统中设计出故障是徒劳的。

在她在 Ricon 的演讲中，Kromhout 深入探讨了[远程团队和通信架构](http://bridgetkromhout.com/speaking/2015/ricon/)的问题。无论团队是分布式的还是内部的，开发人员都可以通过向他们的提交添加更好的文档来更好地促进团队间的交流。而不是说，“我修好了。”有人会说为什么，因为他们分散在异地工作的团队成员会感谢他们提供的额外环境。

[布里奇特·克鲁姆豪特，举足轻重:利康访谈](https://thenewstack.simplecast.com/episodes/bridget-kromhout-pivotal-the-ricon-interviews)

Basho、New Relic 和 Pivotal 是新堆栈的赞助商

特征图片:芭蕉。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>