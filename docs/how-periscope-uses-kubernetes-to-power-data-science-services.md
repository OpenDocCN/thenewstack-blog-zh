# Periscope 如何使用 Kubernetes 为数据科学服务提供支持

> 原文：<https://thenewstack.io/how-periscope-uses-kubernetes-to-power-data-science-services/>

[汤姆·奥尼尔对潜望镜数据科学家做什么和为什么关心数据](https://thenewstack.simplecast.com/episodes/tom-oneill-of-periscope-data-on-what-data-scientists-do-and-why-you-care)

在本期 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中，我们采访了 Periscope Data 的联合创始人兼首席技术官[汤姆·奥尼尔](https://www.linkedin.com/in/tomoneill2/)，他负责监督该公司的技术愿景。[潜望镜数据](https://www.periscopedata.com)是现代数据团队的平台。

随着数据的爆炸，O'Neill 的任务是找到最快的方法使万亿字节的数据对 Periscope 的客户有用，他们中的许多人是数据科学家、数据分析师、数据工程师，他们使用 SQL、Python 或 r。

由于可用数据的爆炸，数据科学家变得越来越重要。Airbnb 不是一家酒店公司。这是一家伪装成酒店公司的数据公司。但数据的好坏取决于公司挖掘数据的能力。在这种环境下，是数据工程师在做决策。

奥尼尔解释说，数据科学家正在回答一些问题，如“在第 4 级结束时，在宝箱中放置多少令牌，以优化每个人口统计数据的终身价值”。他们今天回答的问题比以前复杂得多。

他说，有两种数据团队。

一个是面向内部的数据团队，即商业智能(BI)合作伙伴。这些团队了解销售和营销，确定产品的哪些部分是最有价值的，并确定什么导致流失或追加销售？

> "本质上，Tinder 是一个排名问题."

此外，面向外部的数据团队是工程团队的一部分。“这些是 Tinder 的数据科学家，他们帮助优化 swipe 算法来确定排名顺序，”他说。"本质上，Tinder 是一个排名问题."

Tinder 算法试图最大化连接。数据科学家观察历史上什么可行，什么不可行，并由此确定精确度和召回曲线。他们会回答类似“我们应该向这个用户展示多少人？我们应该向这个用户展示什么样的人？什么最有可能带来成功的结果？然后调整算法来支持它。”奥尼尔说，“它可以基于机器学习，可以基于规则，或者基于静力学，或者基于这三者的结合。”

## 潜望镜如何工作

数据分析师平均每周花 20 个小时在 Periscope 的平台上。规模令人印象深刻。除了处理平台上已经存在的数百万个查询之外，他们平台上的分析师每 24 小时就要编写 300，000 行新的 SQL 语句。该公司在其车队中运行 30TB 的工作内存(RAM)，仅用于执行分析。它每天管理大约 2000 万个查询。

那么 Periscope 是如何管理这个规模的呢？首先，奥尼尔说，你必须把所有的数据放在一个真实的来源中，然后对其进行分析。因此，该公司使用 ETL(提取、转换和加载)工具将客户数据复制到 Periscope 平台，在那里可以建立跨越不同维度的复杂连接。它还可以连接来自其他第三方数据源的数据，包括 Salesforce.com、 [Marketo](https://www.marketo.com/) 和 Google Analytics into Redshift 和雪花。

除此之外，他们还构建了 Periscope 数据平台，帮助数据科学家利用 SQL、Python & R 建立数据模型并进行分析。

这都是与 Kubernetes 精心策划的。

奥尼尔说，该公司以多种方式使用 Kubernetes。一种是管理服务器以保持持久的网络状态。它使用 Kubernetes 来分割同一服务的许多不同部署。该公司的 BI 产品在任何给定时间都可以连接到 5-6，000 个活动数据库，每个数据库都有十几个或更多的连接需要保持不间断。“在不复制连接池的情况下获得冗余和可伸缩性是一个有趣的挑战，”O'Neill 说。

### 在这个版本中:

[2:10:](https://thenewstack.simplecast.com/episodes/tom-oneill-of-periscope-data-on-what-data-scientists-do-and-why-you-care?t=2:10) 工具。
[五点:](https://thenewstack.simplecast.com/episodes/tom-oneill-of-periscope-data-on-what-data-scientists-do-and-why-you-care?t=5:00)栈。
[11:01:](https://thenewstack.simplecast.com/episodes/tom-oneill-of-periscope-data-on-what-data-scientists-do-and-why-you-care?t=11:01) 在潜望镜数据中使用 R 和 Python 及其对安全性的影响。
[16:24:](https://thenewstack.simplecast.com/episodes/tom-oneill-of-periscope-data-on-what-data-scientists-do-and-why-you-care?t=16:24) 内存网络状态的持续性。
[17:15:](https://thenewstack.simplecast.com/episodes/tom-oneill-of-periscope-data-on-what-data-scientists-do-and-why-you-care?t=17:15) 他们在创建 CI/CD 渠道时应该考虑什么，他们应该寻找什么样的东西。
[18:55:](https://thenewstack.simplecast.com/episodes/tom-oneill-of-periscope-data-on-what-data-scientists-do-and-why-you-care?t=18:55) 数据团队做什么，他们给不是工程师的人提供什么服务。

[Raygun](https://raygun.com/) 赞助了这个播客，由新栈独立制作。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>