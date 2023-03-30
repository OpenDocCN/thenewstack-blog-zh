# Cribl 处理可观察性成本，“代理疲劳”

> 原文：<https://thenewstack.io/cribl-tackles-observability-costs-agent-fatigue/>

随着 IT 组织寻求对其运营的可观察性，他们部署了更多的系统来进行日志记录和监控，从而创建了一个必须管理的数据消防队。与此同时，成本失控。

这就是总部位于旧金山的 Cribl 正在解决的问题。它的 [LogStream](https://cribl.io/blog/announcing-cribl-logstream-2-1-sso-event-schema-validation-and-a-lot-more/) 平台创建了它所谓的可观察管道，可以从任何来源摄取机器数据；动态解析、重构和丰富数据；然后将数据路由到适当目的地。

这可能包括剔除重复或不重要的数据，并将其他数据发送到廉价的存储设备。

“客户有很多不同的工具。他们将有一个时间序列数据库，他们将有一个日志存储，通常是多个日志存储，但所有这些东西之间没有连接组织。他们，你知道，他们买的所有东西都是为了只与他们买的东西一起工作而建造的。Cribl 联合创始人兼首席执行官[克林特·夏普](https://www.linkedin.com/in/clintsharp/)解释说:“所以他们有一个问题，我称之为代理疲劳，就是，你知道，每次他们想尝试一些新的东西，一个供应商就会过来说，‘嘿，把我的代理扔出去就是了。’”

这使得大型组织试图管理多个系统中的大量代理，导致了 Cribl 所说的“代理疲劳”。

“这些公司已经开始将每天数 TB 的数据纳入大数据存储系统，用于运营和安全目的的分析。他们已经在为此付出的代价下挣扎了，”他解释道。

在一篇[博客文章](https://cribl.io/blog/the-observability-pipeline/)中，他这样描述可观察性管道:

一个流处理引擎，它可以跨所有类型的可观察性(指标、日志和跟踪)统一数据处理，收集所需的所有数据，丰富这些数据，消除干扰和浪费，并将这些数据交付给组织中设计用于处理可观察性数据的任何工具

因此，他和他的联合创始人 [Dritan Bitincka](https://twitter.com/DritanBitincka) 和 [Ledion Bitincka](https://twitter.com/ledbit?lang=en) (三位前 Splunk 工程师)为日志和指标构建了一个流处理引擎，位于客户现有的接收管道内。它使用户能够在将数据发送到所需位置之前，解析和调整流中的事件，无论原始格式如何，添加上下文、聚合等。

它允许他们重用现有的投资和部署的代理足迹，以发送到多个目的地。用户可以保留单个代理，例如 Splunk 或 Elastic，并且不仅向 Splunk 或 Elastic 发送数据，还可以向 Snowflake 或 Databricks 或仅向 S3 存储桶发送数据，他们可以在这些存储桶中保留数据以实现合规性。

他说:“我们允许他们在数据最终进入任何目标系统之前，通过处理数据来控制成本。”

“日志数据的一个不可告人的秘密是，你知道，很多这种数据只是噪音。它不是特别有价值，但它作为更广泛的数据收集策略的一部分被吸收了。因此，我们为人们提供工具，允许他们获取数据流中的数据，并决定如何最好地利用这些数据。它应该被保存在便宜的地方吗，比如 S3？是否应该对其进行改造或转换，以删除不感兴趣的信息，然后将其发送到它应该到达的任何地方？”

这可以降低在多个系统中摄入和储存的成本。

### 没有模式的引擎

LogStream 从 Splunk Forwarder、FluentD、Elastic Beats、Syslog StatsD 和其他系统获取日志和其他数据。它位于日志摄取管道的中间。如果您使用 Splunk，它会使用重量级转发器或索引器。在其他系统中，它可能独立部署或在 AWS Lambda 中无服务器运行。

LogStream 是一个无模式引擎，它可以用不同的模式来规范化日志。

从仪表板上，管理员设置路线，设置要对特定数据集执行的操作，并选择数据的目的地。有十几个现成的功能，包括编辑个人信息、加密、采样、移除字段以及使用 GeoIP 等信息丰富数据。处理后，它会将数据发送到一个或多个目的地，如 Splunk、Kinesis 或 S3。

客户根据接收到 LogStream 的数据量以及发送到目的地的数据量付费。

451 Research 的高级分析师 Nancy Gohring 在最近的一份[报告](https://451research.com/search?keyword=Cribl)中写道:“我们认为 LogStream 提供了一种非常灵活的管理日志的方法，这样大型组织就可以更好地控制他们的日志记录操作，从而带来几个重要的结果，包括提高安全性、降低成本以及收集内部用户所需的大量数据的能力。”。(需要订阅)

她补充说:“像任何发展中国家的供应商一样，Cribl 面临着教育市场和快速改进产品的挑战。”

根据夏普的说法，该公司的差异化基于性能——在一篇博客文章中，它宣称比 LogStash 和 Fluentd 的效率高 7 倍，比 Apache NiFi 的速度快 55 倍。Cribl 最近还指出，它已经以每天 20pb 的速度进行了测试。

“在一个开放源代码的世界里，你只能自己构建这一切。它将如何部署？它将如何得到管理？在这些管道投入生产之前，如何对它们进行测试？例如，您实际上是如何进行蓝/绿滚动部署的？你只能靠自己来建造所有这些东西，”他说。

他[认为，如果没有大量的集成和工作，现有的开源项目还不能完全解决问题。](https://cribl.io/blog/building-an-observability-pipeline-on-top-of-open-source-apache-nifi-logstash-or-fluentd-a-journey/)

“我们的客户每天处理数百 TB 的数据量。…他们每年仅在运行这些系统的基础架构上就花费数千万。对他们来说，额外关闭 20%的数据每年可以为他们节省 300 万到 500 万美元的基础架构开支。”

与此同时，提供竞争产品的 Splunk 通过[收购 SignalFX](https://thenewstack.io/splunk-moves-into-microservices-monitoring-with-signalfx-acquisition/) 增加了其微服务和云基础设施能力。其他商业工具，包括 Datadog、Wavefront 和 AppOptics，可以更容易地将监控、日志记录和请求跟踪结合起来，以统一了解分布式系统的性能，OpsRamp 营销总监 Deepak Jannu 在之前的 TNS 帖子中指出。

它正成为一个越来越拥挤的领域。在其市场监测报告中，451 Research 预测，到 2022 年，监测[将成为集装箱市场最大的部分](https://twitter.com/ngohring/status/1177218598747725824?s=20)。

专题图片:[保罗·哈尔](https://www.flickr.com/photos/haahr/)放大的[。根据](https://www.flickr.com/photos/haahr/19687836610/in/photolist-vZKiUN-C2BnvK-7vRatk-2uR6a-7yzT34-HFx2j-79hvX1-rkUuaK-6swuFU-4zgA2-jZJrX-72MxS6-dpwoEq-z67gb-aeESG-cwZFky-cXz31Q-5hVy54-8XvfbC-6xru2C-EMvAx-pRwmWv-akyw9g-8Dz4nS-6AiEjj-8hawRk-cXz5Ws-akyvLn-cXyZiJ-4Pzi9-5JDJrd-7kQeR-naYC5-t6CEc1-5Vgzk2-hjCQjT-jZCzd-btCAxD-akyx7v-btCADk-7ZH2e9-T4cAYK-zcVDFP-7owwZi-7oAt1w-7owxjZ-P1Jxph-7erqEc-9Cybp-omtpRu) [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>