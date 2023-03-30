# Datadog 通过日志管理采集带来了更多的数据可见性

> 原文：<https://thenewstack.io/datadog-brings-data-visibility-log-management-acquisition/>

监控和运营分析市场上越来越多的供应商希望利用人工智能，结合来自服务器、数据库、工具和服务的数据。

[Datadog](https://www.datadoghq.com/) 最近收购了法国日志管理初创公司 log matic . io[，充实了其产品组合，该公司宣传其在单一平台内提供基础设施指标、应用性能监控(APM)和日志管理的能力。](https://www.datadoghq.com/blog/datadog-acquires-logmatic-io/)

“将日志与我们已经提供的 APM 和基础架构监控相集成，是监控和分析类别发展的重要一步*。Datadog 首席执行官 Olivier Pomel 表示:“我们新的集成平台将简化对通常跨越云、容器、物联网和移动设备的现代应用的监控。”他补充说，它还提供了新的基于人工智能和机器学习的功能，以帮助客户更好地管理他们的基础设施和应用。*

在一篇[博客文章](https://www.datadoghq.com/blog/datadog-acquires-logmatic-io/)中，Pomel 解释了这家总部位于纽约市的公司的观点，即向其投资组合中添加这一新产品将提供新的见解，形成“[可观察性的三大支柱](https://speakerdeck.com/adriancole/observability-3-ways-logging-metrics-and-tracing)”:指标、跟踪和日志——并且都在一个地方。

“…最大的价值将来自在它们之间无缝转换的能力，以及轻松获得对它们所代表的基础架构、应用程序和业务的真正理解，”他说。

## 数十亿个数据点

Gartner IT 系统、安全和风险研究小组前副总裁 Cameron Haight 在 2016 年 6 月的一份报告[中写道:“许多(如果不是大多数)商业 APM 工具(以前添加的 Datadog 功能)没有能力以高频率收集潜在的数千种微服务的数百个数据点，以‘描绘’整体环境”。](https://www.gartner.com/doc/3357419/microservices-macroeffect-apm)

收购 Logmatic 应该有助于解决这个问题。

这家总部位于巴黎的公司于 2014 年由伊曼纽尔·盖丹、T2、雷诺·布提和 T4 创立。其日志管理和可视化工具每天为埃森哲、长途拼车应用 BlaBlaCar、法国付费电视频道 Canal+、视频分享网站 [DailyMotion](https://www.dailymotion.com/) 和奢侈品供应商 [LVMH](https://www.lvmh.com/) 等客户分析数十亿个数据点。

它去年参加了微软在巴黎的加速器项目。

Logmatic 将日志和指标集中在浏览器中，无论使用何种语言或堆栈，都不需要代理。它的网站上写道:“想象一下 [**grep**](https://en.wikipedia.org/wiki/Grep) 有一个展示精彩仪表板的选项。”

Pomel 将其描述为可视、直观、快速，并且与 Datadog 的核心设计原则“惊人地一致”。该公司表示，它被 Logmatic 对 UX 和简单性的高度关注以及提高云和混合环境可见性的共同使命所吸引。这两家公司已经有了一些共同的客户。

Logmatic 使用户能够:

*   进行实时分面和全文搜索。
*   使用交互式分析导航数据并查明根本原因。
*   在几分钟内制作定制或预定义的仪表板。
*   只需点击一下，即可过滤仪表板并调查事件。
*   针对任何过滤器和指标创建动态阈值、不活动或匹配警报。
*   通过电子邮件、Slack、PagerDuty 或自定义 webhooks 接收带有直接分析链接的通知。
*   用最常见的语言 JSON 自动解析，或者编写自己的自定义解析器。
*   使用自动化日志文件归档功能随时检索数据。

它有 30 多个集成，包括 Docker、HAproxy、Java、PHP、Apache、Amazon Web Services 等等。

Datadog 计划在今年秋天晚些时候推出其完全集成的产品。你可以在这里申请加入私测[。](https://www.datadoghq.com/log-management/)

## 瞄准 Splunk

Datadog 毫不掩饰其收购 Splunk 的意图。根据 IDC 的数据，Splunk 去年引领了全球 IT 事件和日志管理软件市场。

今年早些时候，Datadog 将其[应用性能监控](https://www.datadoghq.com/apm/)产品全面上市，使其与 [New Relic](https://newrelic.com/) 、 [AppDynamics](https://www.appdynamics.com/) 和其他公司展开竞争。

Logmatic 还与一个拥挤的领域竞争，包括 [SumoLogic](https://www.sumologic.com/) 、 [Logz.io](https://logz.io/) 和其他越来越多地将人工智能和机器学习应用于日志管理的领域。

今年早些时候，451 Research 的 Nancy Gohring 谈到了 APM、日志管理和基础设施监控市场。

Gohring 在她的“2017 年应用和基础设施性能市场地图”报告中指出，供应商增加的分析功能在某些情况下可以解决一系列常见问题，这导致了新的竞争战场。创新领域包括异常检测、自动基线、预测分析、复杂的查询功能和创新的后端数据管理技术。

此次收购的分析师 Chris Riley 指出，Datadog 尤其擅长为软件交付链中的一切提供元仪表板，尽管该公司受到它所创建的集成的支配。

“因此，获得一个同时也是数据来源的工具可以做几件事。在与可能还没有强大日志分析能力的公司合作时，这为他们提供了更大的灵活性。这使得解决方案更加棘手，”他说。

“我还希望它能让他们做更多有趣的事情，将日志数据绑定到更强大、更智能的分析、通知以及相关数据的关联中。我想，我关心的是其他集成合作伙伴如何看待它，这是拥有所有数据收集来源的长期战略的一部分吗？”

特征图片:[马修](https://www.flickr.com/photos/mshipp/)的《[三伏天【探索】】CC BY-SA 2.0](https://www.flickr.com/photos/mshipp/14256166416/in/photolist-nHLzAG-o6uRDp-r86DPG-gpbuRH-TcVycD-nYBQRW-nYGLja-dfaem3-bG9oj8-cEVkBU-6dWgsj-9QYGxq-peBDSz-7w8Lc1-wzNx6-qbny7M-ef2sRX-4R7Ks-4efiPb-eRHdJu-pTXoLP-qbctTT-cp54Vw-6EdtBP-CM3pi-pTPyD3-5rmKog-4efhXN-62xFMj-42uaF-9jmNqi-gdazW-q96qho-pTXoUV-kB5g5c-81cw93-qbcmoT-pTNtMQ-pTNzzm-5nKm2-75P8pL-86KRV8-CM3oV-Beddvx-C9hUG1-BJtdT9-3agw-BC5ZNv-pTXrPx-BJt6ch) 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>