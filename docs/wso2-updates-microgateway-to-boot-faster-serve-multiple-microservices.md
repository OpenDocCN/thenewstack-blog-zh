# WSO2 更新微网关以更快启动，服务多个微服务

> 原文：<https://thenewstack.io/wso2-updates-microgateway-to-boot-faster-serve-multiple-microservices/>

微服务的分布式特性意味着集中式网关可能会成为瓶颈。正如 WSO2 的营销副总裁肯·奥斯特里奇(Ken Oestreich)解释的那样:

*“许多服务已经不在您的数据中心了。事实上，他们甚至不再与您的主要云提供商合作。他们到处都是。因此，在某个地方的服务器上的中央网关的概念[产生]了一个规模问题，因为你现在正在触及所有这些不同的云。…那么，为什么不将您的网关也做成分布式的呢？*

微网关位于一个或几个微服务的前面。微网关充当主网关的代理，您甚至可能不再有主网关。它们更轻，启动更快。他说，这一切都在推动市场空间走向更加分布式、更加微服务化、更加多云化。

在本周的 [OSCON](https://conferences.oreilly.com/oscon/oscon-or) 大会上，这家专注于集成的公司展示了其开源 API 微网关的 3.0 版本，该版本启动时间不到一秒钟，内置功能包括认证、授权、速率限制、服务组合、发现、转换和分析。

新功能包括:

*   使用 OpenAPI 规范的开发人员优先的运行时生成，因此 API 可以协作开发，然后独立测试。
*   运行时服务发现支持自动查找在重新部署时 IP 地址发生变化的服务。
*   支持组合多个微服务，然后通过单个 API 公开组合。
*   支持将 API 请求和响应从传统格式转换为现代格式，以便它们可以向现代消费者应用程序公开。
*   将 WSO2 API Microgateway 工具包从运行时中分离出来，以获得更好的可伸缩性和更平稳的升级。

正如奥斯特里奇所描述的那样，microgateway 启动速度更快，现在可以处理多个微服务。

去年 7 月，该公司发布了其 API 网关、企业服务总线(ESB)、身份服务器和流处理器的精简和微服务调整的容器版本。

它将微服务网关吹捧为一个组件，可以“作为微服务的专用代理，在同一主机上运行的微服务的附属设备，或者代理一个或多个微服务的 API hub。”

虽然 [Axway](https://www.axway.com/en) 工程副总裁[戴维·麦克纳、](https://www.linkedin.com/in/david-mckenna-05726b1/)在这篇 API Friends [的帖子中，](https://apifriends.com/api-security/api-microgateway/)将微网关描述为服务网格，但 WSO2 坚持认为服务网格在其原生形式中存在“API 管理差距”它通过其 API 管理产品解决了这个问题，该产品最近被宣布为与流行服务 mesh Istio 的桥梁。它说，Istio 提供数据平面和控制平面功能，而 WSO2 API Manager 提供管理平面功能。

据奥斯特里奇称，这是使微服务部署更容易的战略的一部分，将它与 DevOps、持续集成/持续交付相结合，并使集成与所有类型的容器更加兼容。

他说，作为其中的一部分，名为[芭蕾舞演员](https://thenewstack.io/ballerina-a-programming-language-for-cloud-native-computing/)的编程语言 1.0 版本将在几周内发布。它开发 Ballerina 是为了让开发人员更容易将他们的应用程序与其他服务连接起来，消除或至少最小化对 ESB 等[中间件的需求。](https://thenewstack.io/wso2-ceo-tyler-jewell-ballerina-and-the-end-of-middleware/)

Oestereich 说，芭蕾舞演员在语言本身中包含了网络分布的概念。

“这种语言是网络感知的。它理解交易。它理解网络延迟。它知道如何集成服务，以及出现错误时会发生什么。因此，集成一个服务所需编写的代码量非常少。如果你正在编写网络分布式应用程序，这是一种非常有效的语言，远远好于任何通用语言，”他说。

WSO2 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>