# GrafanaCon Pancake 播客:构建新监控堆栈的复杂性

> 原文：<https://thenewstack.io/grafanacon-pancake-podcast-intricacies-composing-new-monitoring-stack/>

随着容器和微服务架构的出现，许多问题开始围绕通常安静的监控领域产生。你应该建立自己的堆栈吗？你应该监控什么？在现场还是在云中？

为了启动上周在[无畏号](https://www.intrepidmuseum.org/)退役战舰上举行的 [GrafanaCon](http://grafanacon.org/) 2016 用户大会，我们举办了一场[特别煎饼和播客小组讨论](https://thenewstack.io/podcasts/)，来思考这些非常重要的话题。为了这次活动，我们邀请了 [InfluxData](https://www.influxdata.com/) 的首席技术官 [Paul Dix](https://twitter.com/pauldix) ，他是 [InfluxDB](https://github.com/influxdata/influxdb) 时序数据库的管理员；[Raj Dutt](https://www.linkedin.com/in/radutt),[rain tank](http://raintank.io/)的联合创始人兼首席执行官，该公司提供开源 [Grafana 可视化监控软件](http://grafana.org/)的商业发行版；办公用品零售商史泰博(Staples)的软件开发人员西奥多·斯塔克(Theodore Staack)；英特尔开发人员倡导者 Matthew Brender 。

[# 122:GrafanaCon Pancake 播客:构建新监控堆栈的复杂性](https://thenewstack.simplecast.com/episodes/122-grafanacon-pancake-podcast-the-intricacies-of-composing-a-new-monitoring-stack)

监控作为一个整体已经远远超出了它的起源，开发人员和运营团队使用“单一窗口”等行业术语来描述许多监控解决方案努力提供一体化、易于使用的用户体验的方式，这种体验是由多个来源组成的单个框架。

“监控基础设施由许多不同的方面组成。将所有这些整合到一个视图中变得越来越重要。这些数据可能位于不同的数据库或特定领域。随着 DevOps 的兴起，将数据整合成一幅完整的画面变得更加重要，”Dutt 说。

Grafana 是一个开源仪表板工具，可与各种指标收集代理一起工作，包括时间序列数据库，如 [Graphite](https://graphiteapp.org/) 和 InfluxDB。Brender 解释说，流式数据集不仅在查询方面具有更大的灵活性，而且在确定团队需要关注哪些数据方面也具有更大的灵活性。

然而，最终，度量标准归结为一个人试图观察的东西。“我经常开玩笑说，我把 DevOps 称为度量系统的门户药物，”迪克斯说。然而，人们必须问:这些指标是针对应用程序开发人员、IT 运营团队还是业务线团队的？他们是否希望从被监控的资源中推出指标(这是时序数据库的首选方法。)或者，就像普罗米修斯的建筑一样，[拉是一种方式吗](https://prometheus.io/blog/2016/07/23/pull-does-not-scale-or-does-it/)？

随着围绕各种可用的开源监控解决方案的讨论持续升温，专家组对整个社区的状态表示了谨慎的怀疑。特别是，围绕数据收集缺乏标准化的问题引起了争论，因为隐藏的成本可能会让开发人员惊讶地将开源工具拼凑成一个完整的堆栈。“我不认为围绕监控和可见性的开源工具已经到了非开发人员可以自助使用的地步。我认为那是我们必须去的地方，”杜特说。

“开源是免费的，就像‘这是一只免费的小狗’，维护它需要大量的成本、时间和精力，”Brender 补充道。Staack 以积极的语气结束了讨论，希望激励其他开发者为开源做出贡献，分享他们自己的经验和专业知识。“如果你打算把所有这些黑盒拼在一起，为什么不走完全程呢？这要有趣得多，如果你让人们为开源项目做贡献，你会有一个更好的工作环境。”

英特尔赞助了该播客。

特征图像和声音编辑由[贝利数学](http://baileymathsound.com/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>