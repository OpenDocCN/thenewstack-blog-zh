# Datadog 和 PagerDuty 让 Airbnb 的扩展变得更容易

> 原文：<https://thenewstack.io/datadog-and-pagerduty-make-scaling-easier-for-airbnb/>

在刚刚发布的一项案例研究中，云监控服务 [Datadog](https://www.datadoghq.com/) 与事件管理公司 PagerDuty 合作，以确保 Airbnb 服务的可靠性。

Airbnb 允许旅行者预订沙发或城堡，它为网站的一些组件开发了自己的基于服务的架构，而其他组件仍然是其主要应用程序的一部分。创建了独立的工程团队来支持独立的组件和功能，每个团队负责运行自己的软件。

尽管团队负责向中央仪表板应用程序提供他们自己的运营和业务指标，但随着时间的推移，团队使用更多的开源项目和他们自己的仪表板，这使得获得整个基础架构的广泛概览变得更加困难。

“当我们意识到这种方法很难(如果不是不可能的话)扩展时，我们决定寻找一种全面、更全面的运营绩效解决方案。但我们不想只是增加一个没人会用的工具，”Airbnb 的工程经理戴夫·奥古斯丁说。

Datadog 首席技术官兼联合创始人 Alexis lê-quc 解释道:

“他们在寻找实时服务，这对于他们来说非常重要，并且能够尽可能扩展到他们的基础架构和应用程序中。在这一行，你不知道的事会害死你。

“我们可以围绕他们感兴趣的数据类型和性能指标为他们提供很大的灵活性，而且我们可以实时完成。事实上，我们与 PagerDuty 整合得很好，这对他们来说尤其有效。”

lê-quc 说，在 Airbnb，团队可以就软件应该是什么样子、使用什么技术做出很多决定，但他们为这种自由付出的代价是他们必须运行自己的软件。

借助 Datadog 和 PagerDuty，随叫随到的工程师和支持人员可以定制要监控哪些指标，以及在得到通知之前需要达到哪些阈值。PagerDuty 可以确保呼叫了正确的人，并且通过升级规则，如果最初的人没有及时接听，则通知队列中的下一个人。

Augustine 说:“通过全面的事件趋势数据来识别关键问题和讨厌的问题，我们能够消除额外的噪音，专注于那些需要立即关注的问题，并将它们发送给正确的工程师，这样我们就不会打扰错误的人了。”"所以现在当工程师们听到 PagerDuty 的消息时，他们知道这是真的了."

lê-quc 提到了 [SmartStack](https://nerds.airbnb.com/smartstack-service-discovery-cloud/) ，它旨在确保组件间连接的高可用性，这是 Datadog 为 Airbnb 监控的服务之一。

"如果您有一个带有数据库的 web 应用程序服务器，如果数据库关闭了怎么办？"他解释道。“即使您有一个备用节点准备接管，应用程序也不知道要去哪里，它不知道有一个备用节点可以连接到它并恢复其工作。所以他们建立了这个连接，在这个例子中，在 web 应用服务器和数据库之间，它将重新路由流量。因此，我们监控 SmartStack 的运行状况，以确保它能够正常工作。”

Augustine 表示，Datadog 正在寻找以前不知道的相关细节和依赖关系。其自动化流程不仅帮助提高了工程团队的生产力，还让公司更好地了解了团队和服务的表现。

Datadog 在 1 月下旬宣布，它已经为自己的金库增加了 3100 万美元，收入和员工人数是去年的三倍。Datadog 联合创始人兼首席执行官奥利维尔·波梅尔(Olivier Pomel)当时表示，该公司预计 2015 年的规模将再翻一番或三倍。

它与[边界](https://gigaom.com/2011/11/15/boundary-launches-with-a-new-network-monitoring-angle/)、 [Cloudyn](https://gigaom.com/2014/01/28/which-is-cheaper-for-your-work-amazon-or-google-cloud-ask-cloudyn/) 、 [Finally.io](https://gigaom.com/2013/07/15/finally-io-does-a-cannonball-into-the-cloud-server-monitoring-pool/) 、[服务器密度、](https://gigaom.com/2014/01/27/server-density-adds-multi-cloud-dashboard-to-its-monitoring-mix/)和 [Stackdriver](https://gigaom.com/2014/01/30/stackdriver-names-cisco-vet-to-board-amazon-alum-as-advisor/) 等竞争。

在宣布融资两周之后，Datadog 宣布[收购纽约大数据初创公司 Mortar Data](https://thenewstack.io/datadog-adds-big-data-analytics-mortar-data-buyout/) ，以进一步将机器学习整合到其产品中。

今年 3 月，它发布了一款名为 Host Maps 的可视化工具，可以快速、轻松地查看您的主机和其中的任何问题。

Datadog 是新堆栈的赞助商。

通过 Flickr Creative Commons[获取专题图片。](https://www.flickr.com/photos/pujan/3709449469/in/photolist-cWPguY-5WDAmR-r6RDtW-pYLhhu-6VGHJe-aW1Cok-2KGbN-6P7imh-ofuEeL-72b66a-6DMU6k-fw8wRV-Fyw4-o9tzp8-bvoxeM-f9FZGu-6Pn7Z3-eRsapX-abepdU-6KxTtV-e4NMds-c128kq-6osH5m-565NAy-eBdXQu-dqoLKi-4ZnGyt-dmpMXS-3Szag-cxGuGC-5xE1yy-9jpe7Q-d6Yeo9-ckemTq-4gB2Hi-e6oHv2-o1mb8X-h4ipuw-nYaFX8-29QjpQ-dSRBAn-7s9Vsh-dtp6J6-7TLHaP-4b382z-eqXL2-9xE1Ne-c33Pf-9y7FAL-8LZFYW)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>