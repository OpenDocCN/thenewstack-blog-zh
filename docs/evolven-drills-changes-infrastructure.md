# Evolven 深入了解您的 IT 基础设施的变化

> 原文：<https://thenewstack.io/evolven-drills-changes-infrastructure/>

场景:对 IT 环境的扫描发现了中午发生的更改 *—* 紧急补丁。但是没有与这些更改相关的服务台请求，因此它们是未经授权的。观察集群，可以清楚地看到，这些更改只针对一台发生了事故的服务器。因此，有人修复了一个事件，但这是一次性的，没有获得更改请求的批准，也没有对其他服务器进行更改，这可能会在以后导致一系列问题。

对于位于新泽西的 IT 运营分析(ITOA)供应商 [Evolven](https://www.evolven.com/) 来说，一切都与变化有关:什么发生了变化？谁做了什么？这会对其他事情产生什么影响？

在 IT 管理软件和服务公司 [Mercury Interactive](http://www8.hp.com/us/en/hp-news/press-release.html?id=169236#.WI842BAn_bo) (被惠普收购)[的 13 年里，Sasha Gilenson](https://twitter.com/sgilenson) 与许多客户谈论了他们在性能、可靠性和稳定性方面的问题，并发现这通常可以归结为某种改变。这可能是应用程序、基础架构、配置或其他方面的变化。

根据 MarketsandMarkets 的数据，随着企业将数据分析应用于其 IT 运营，全球市场预计到 2020 年将增长到 97.9 亿美元。

Gartner 认为，企业需要将大数据和机器辅助分析技术扩展到他们的运营管理中，而不是拥有通常用于两个领域的独立工具和流程:1)可用性和性能管理，以及 2)网络、应用程序和其他技术。这种组合方法被称为[算法 IT 运营平台](http://searchnetworking.techtarget.com/feature/ITOA-to-AIOps-The-next-generation-of-network-analytics) (AIOps)。

Evolven 的客户包括穆迪、西联、摩根大通、德勤、ING 等财富 100 强到财富 2000 强的公司，据其网站介绍，仅配置参数就可以有数千个[的海量公司。](http://www.sramanamitra.com/2013/03/13/thought-leaders-in-big-data-interview-with-sasha-gilenson-ceo-of-evolven-part-1/)

“我们的客户在生产环境中每天可能会有一百万次变更。因此，告诉他们一天有一百万个变化是没有帮助的——这只是太多的数据，”Evolven 首席执行官兼联合创始人 Gilenson 说。

Evolven 开始收集整个堆栈的数据，然后通过识别哪些更改实际上是重要的，以及这些更改将产生什么影响，来帮助组织理解所有这些数据。

Evolven 使用一组部署在整个环境中的代理来扫描服务器、网络设备、存储、应用程序等。该公司的软件收集信息，如应用程序、配置、基础设施、数据和工作负载的变化，然后将这些信息发送回运行分析引擎的中央数据库。它处理信息，关联来自现有工具(如监控或管理工具)的信息，并为每个变更提供风险评分。它可以将所有风险分值整合到一个总体风险图中，以帮助设置优先级。然后，当检测到环境中的不良变化时，它会发送报告。

根据 Gilenson 的说法，其技术在粒度级别上跟踪变化，以确定事件的根本原因，如单个配置参数的解决方案。它还提供与其他监控和管理工具的双向通信，因此数据可以双向流动。尽管一些新工具提供了“自我修复”或无需人工干预的自动修复，但 Gilenson 表示，Evolven 不会自动修复，但会向自动化工具提供关于修复内容和方式的信息。

## IT 运营分析

已经有一批供应商进入 IT 运营分析和 AIOps 市场，包括 Elastic、惠普企业、IBM、Rocana、Nyansa、Splunk、Sumo Logic 和许多其他公司。Gilenson 坚持认为 Evolven 的独特之处在于其对变化的关注、细致的洞察力以及在[任何基础设施上工作的能力](https://www.evolven.com/supported-technologies.html)。

“Evolven 在使高级分析更本地化、更有效地成为整体 IT 运营的一部分方面处于领先地位，”研究分析师 [Dennis Drogseth](https://twitter.com/dndrogseth) ，企业管理协会副总裁谈到该公司时说。

该公司于 2009 年推出其产品，并在 2013 年成为高德纳公司 IT 运营分析领域最酷的供应商之一。该公司总部位于新泽西州泽西城，其开发中心位于以色列。

Evolven 根据安全要求和政策提供软件即服务(SaaS)和内部部署模式。

特征图片:[肯特·希姆克](https://www.flickr.com/photos/22603020@N04/)的[改](https://www.flickr.com/photos/22603020@N04/5751512440/in/photolist-9Lf1gA-9qLqXq-a89hp-J4yQg-4DP4nt-j3BtP5-9GU2es-99JSv-dMc6Um-dMc6Us-5o8jHr-a7Fj5N-ntfg86-6T1vVf-a336XU-nqWmV4-7qyjto-99hLWw-99hCeY-iGNsS2-nqWeAX-99ht5f-99eqxK-99hqE7-99etgx-99hzkS-99hxmS-99hBAo-5YsrNz-99eow4-dfmq2c-99eBZX-99ewck-nqWjbr-99htAj-sqxMwP-99hpXE-99hNxE-99epiv-5zh9bo-99hubq-7c9uwb-99ezDe-99hJwu-p4J6Bz-pCTdq1-8zRM8L-bDGiYV-99enjc-aNmWDZ)，以**的 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>