# 也许构建一个 DIY 日志工具并不是最好的主意

> 原文：<https://thenewstack.io/maybe-building-a-diy-logging-tool-is-not-the-best-idea/>

欢迎来到由 [Scalyr](https://www.scalyr.com/) 首席执行官 [Christine Heckart](https://www.linkedin.com/in/christineheckart/) 主持的[新堆栈制造商](/podcasts/makers):攀登新高度系列访谈，涵盖了工程经理在扩展架构以支持业务需求时所面临的挑战。

构建日志分析工具背后的想法相当简单——直到跨多个团队扩展并在第二天之后管理它的时候。然后事情变得有点复杂。构建一个日志平台的诱惑来了，因为，嗯，它能有多复杂呢？

[攀登新高度第四集——也许制作一个 DIY 测井工具不是最好的主意](https://thenewstack.simplecast.com/episodes/scaling-new-heights-episode-4-maybe-building-a-diy-logging-tool-is-not-the-best-idea)

斯卡利尔油田首席技术官[安东尼·约翰森](https://www.linkedin.com/in/ansonium/)很了解这个故事。约翰逊在金融服务公司 Ellie Mae 工作，在此之前，他为美国参议员及其助手提供立法和通信信息系统。

约翰逊说，在与政府合作的过程中，需要来自日志的指标。在 7 月 4 日的一个周末，他用 c 编写了一个程序。它自动更新并发出指标，最终进入一个循环数据库，该数据库用作事件数据、时间序列和其他指标的存储。用[仙人掌](https://www.cacti.net/)形象化。

约翰逊说，该团队使用该系统来修复中断。最终，这是一个约翰逊编写的专有代码系统。但是和他一起工作的其他人都不知道 c。

“所以在一天结束的时候，你知道，我确信这个产品消失了，被另一家公司买走了，”他说。

在 Ellie Mae，Johnson 构建了两个服务，一个使用亚马逊网络服务(AWS) Elasticsearch，然后是他和他的团队仅使用 Elastic 构建的日志工具。

“我们在 AWS Elasticsearch 服务上遇到了扩展挑战，”Johnson 说。“我们可以拥有的节点数量是有限的，我可以呈现给用户的 URL 也是有限的。他们(AWS)今天已经解决了很多这样的问题。但同样，我受到供应商的限制。”

所以他们用 Elastic 构建了自己的平台，但是“花了好几个月，”约翰逊说。

“我们建立了它，你知道，它是成功的，它运行得很好，直到它运行得不太好，”他说。“因此，我们每天大约处理 2tb 的数据，大概有 50 到 60 个数据节点。我们真的开始遇到很多问题。集群管理问题，进入系统的数据延迟问题。”

有多少工程师认为构建定制软件很简单？但是接下来是项目的开始，发布，以及第二天及以后的所有工作。构建定制软件对大型软件制造商来说是有意义的。但是在一家为政府或金融行业制作软件的公司，人们的兴趣不在于构建日志工具，而在于找到支持组织使命和目标的最佳方式。

亚马逊网络服务是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>