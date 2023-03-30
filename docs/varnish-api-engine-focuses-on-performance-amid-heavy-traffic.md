# Varnish API 引擎专注于繁忙交通中的性能

> 原文：<https://thenewstack.io/varnish-api-engine-focuses-on-performance-amid-heavy-traffic/>

Varnish Software，开源项目 Varnish Cache 背后的挪威网络性能公司，正在发布 [Varnish API 引擎](http://www.marketwired.com/press-release/varnish-software-releases-varnish-api-engine-2008252.htm)，专注于管理高调用量。

据挪威最受欢迎的分类广告网站 FINN.no 称，早期客户测试表明，Varnish API 引擎每秒可以处理多达 20，000 次 API 调用。

根据创始人兼首席技术官佩尔·帕尔的说法，Varnish 软件可以帮助 Pinterest、维基百科和《纽约时报》和 BBC 等主要新闻网站处理其网络流量——多达 20%至 25%的互联网流量。

【T2![1812f2e](img/ab30311af2cefb51cad4ba5c4bc721b3.png)

“我们已经听到了很多关于 API 管理领域产品的抱怨。它们功能丰富，但性能根本不是那个市场要解决的问题，”他在接受采访时说。

然而，在过去的几年里，API 调用的数量已经爆炸式增长，随着物联网的发展，“我们只是在曲线的开始，”他说。

帕尔在一篇博文中解释说，Varnish Cache 从一开始就被用于基于 HTTP 的 API。他说，缓存、高性能和使用 VCL 语言的灵活性的结合使它成为 API 的理想代理。

他解释说，几年前，除了基于 Varnish 的 API 代理中的缓存之外，一个客户希望在代理层中添加身份验证和授权。随着时间的推移，计量和节流功能被添加进来，Varnish Software 意识到它有一系列可以从客户特定的解决方案转变为通用产品的部分。

在过去几年中，它一直专注于高端性能(性能要求为每秒 10，000 个 API 调用以上的客户)和简单性。API 引擎可以在不到一个小时的时间内完成部署。

“清漆缓存的一个优点是它的灵活性，”帕尔说。“它被许多大型组织使用，这些组织对如何提供流量有一套复杂的规则。所以你可以把它看作是一个规则引擎。因此，我们在此基础上编写了这个软件，使得创建用于管理 API 的规则变得更加简单。

> “15 年来，网络性能一直是一个问题，我们觉得我们对此非常了解。”

Varnish API Engine 1.0 只带有一个调用级接口。三节点集群加管理服务器的起价为 47，000 美元。

将于今年秋天发布的新版本将包括一个图形网络界面，并将通过亚马逊云提供。

帕尔说，展望未来，该公司相信它能够将产品的性能推得更远。面向中小型企业的易于管理的产品也将是优先考虑的对象。

开源项目 Varnish Cache 是一个 web 应用程序加速器，由挪威小报 Verdens Gang 的在线版本发展而来。它只关注 HTTP。著名的 FreeBSD 核心开发者 Poul-Henning Kamp 是它的架构师和首席开发者。

Varnish API 引擎的竞争对手包括来自 StormPath 的 SaaS 产品和围绕这些功能提供预制库的 OSS 项目，如 T2 的 passport . js T3，Adron Hall 指出，Adron Hall 是 T4 解构 T5 的联合创始人，该网站使用 API 从多个数据流中提供用户的单一视图。

他说，对开发者来说，这些不一定是新功能。有了身份验证和授权，他们就有能力将其抽象为服务，而不是花时间自己构建系统的这一部分。结合计量和节流可以帮助 Varnish 软件脱颖而出，将缓存与其他服务结合使用可以提高性能和响应时间。

然而，霍尔认为挪威的数据保护法是该公司的潜在优势。他说，在这方面，美国国家安全局和《爱国者法案》的长臂使美国公司处于严重劣势。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/22643708@N06/4289582261/in/photolist-7x4emR-bxCtTG-7ZYm3V-7m9CB9-5JQBFf-jNKL86-c191nd-fsa5FJ-e1N3Vc-j9uRys-89fKd8-6cEQXS-nNiRzs-ku2PmV-6pMHyG-bdizii-nKsQDh-685dNg-i5zegE-GvVU5-6abUGM-nMVL7h-45gNd1-65X6PV-8WvNt4-efE3pm-4dgyr6-6DKt9B-7mak6k-7cNtgp-jKTZGV-4keKK1-54YaQp-gRypaK-fkaJWr-q4JU39-bDHcur-ihnfaJ-kg4vaF-cP8aGb-5GrFFU-dQxRst-8TRXo2-iSnUoJ-8CH215-hWpXSh-fcmVJR-nq2FMw-4Lfd9a-PKyHw)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>