# SignalFx 是一款 SaaS，可监控任何规模的应用程序

> 原文：<https://thenewstack.io/signalfx-a-saas-to-monitor-apps-at-any-scale/>

互联网规模的公司发明自己的工具是一个有趣的话题，因为世界上越来越多的公司建立了自己的分布式架构，并寻找其他人在他们之前走过的路。开发这些工具的人都很有成就。正如有据可查的那样，许多人利用他们的技能和经验创造了新的工具和公司来支持他们。

SignalFx 是一家 SaaS 的现代应用监控提供商，今天宣布获得 Charles River Ventures 的 2000 万美元投资。此前，该公司从安德森·霍洛维茨基金获得了 800 万美元的融资。安德森也参加了最近一轮。他们开发的技术部分源于 SignalFx 联合创始人菲利普刘(Phillip Liu)在脸书担任软件工程师时的工作，当时他所在的团队为快速增长的社交网络开发系统管理工具。在那些日子里，脸书的大部分经验来自于开发他们自己的工具来管理不断增长的分布式架构。他们遇到的问题和今天很多公司面临的问题类似。

早期，脸书使用开源工具，如 [Nagios](http://www.nagios.org/) 和 [Ganglia](http://ganglia.sourceforge.net/) ，它们是为单个服务器实例轮询而设计的。随着访问网站的人数激增，脸书团队的工作变得更加复杂。他们经常会问自己:“港口可用吗？我可以 ping 特定的服务器吗？”

随着脸书的扩展，配置变得更加困难。很难隔绝噪音。这些配置必须保持同步，但是当同步无法实现时，总会有一个窗口。

在分布式环境中，一台特定服务器的故障并不意味着灾难。但是，较旧的传统监控环境不能适应集群中一个节点出现故障时的细微差别和对性能的影响。那些旧系统检测到故障并发出警报。这通常是一个错误的警报，因为如果有 100 个节点，其中一个发生故障，系统不会有故障的风险。最终用户通常根本不知道有问题。因此，每次一个节点出现故障就发出警报是没有任何意义的。

SignalFx 从分布式架构中收集数据，监控趋势，识别模式，然后在出现异常时通知用户。数据流引擎每天可以扩展到数十亿甚至数万亿个指标。考虑到现代应用程序往往是由几十个组件分发的，这并不令人惊讶。

SignalFlow 是该公司的数据流服务。这是一个分析管道，可以在数据进入的几秒钟内提供见解。包括 Yelp 在内的客户可以写信给 SignalFx API，以获得该服务附带的丰富分析功能。

联合创始人 Karthik Rau 昨天在一次电话采访中说，客户通常是开发商，他们越来越多地进行运营，因此更有控制权。

> 越来越多的公司正从单一应用转向微服务，随之而来的是开发者必须承担的责任。

Rau 说，这些开发人员部署应用程序，可以立即看到服务的执行情况。他们想要关于效率低下或者 API 如何被征税的即时反馈。

这不像过去那样要求运营团队密切监控现场的运行情况。如今，需要优化的不再是停机时间，而是延迟。这项工作通常由监控应用程序以确保其运行良好的开发人员来完成。

SignalFx 要面对很多竞争。这是一个拥挤的空间，但刘和劳相信，他们有一个平台，可以传输监控数据并进行分析，这是其他人无法比拟的。

那可能是真的。但是也有大量的开源项目在继续发展。App Dynamics 和 New Relic 等公司也提供应用程序监控。Datadog、Librato 和 Scout 是其中的几个。

与此同时，SignalFx 是互联网规模的公司产生深远影响的另一个例子，因为世界各地的公司都在建立自己的分布式基础设施。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/articnomad/16153058/in/photolist-2qMK1-dU5rd9-dQJkWp-5GJZTU-7Hmvwb-d6Yeo9-q8Zh6A-qb6knr-q8ZgEq-q8ZgpL-q8ZhdE-f8j4Ad-eVX6C2-odZmq1-5GK1jA-fkGDb-fkGDc-dU7HNf-dU1Vpt-dU5r8w-7HmNaR-b3g1Yn-f8j3Fs-4ywqxR-6rEBhV-mZGfF4-bHqqg8-9XMx4b-AgCF-qSyeGW-dwUK7U-7hPxsH-abVFKC-6QGGP3-6tn8FF-dAuMMF-6Hoc1L-f8j2Hh-j546FR-nMY5MY-pn3Mi4-7nP9P1-igNH37-f84NPv-f8j5aA-f84PiB-f8j6QS-f8j71J-f84Qyc-f84SmP)

SignalFx 和 Datadog 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>