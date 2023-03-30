# 最新集成的 JSON: MapR 用于内存操作分析

> 原文：<https://thenewstack.io/latest-integrate-json-mapr-memory-operational-analytics/>

不管你喜不喜欢，JavaScript 不会安静地进入那个温柔的夜晚，不管狄兰·马尔莱斯·托马斯说了什么。就在 NGINX 宣布将在它的每个连接中集成一个微型 JavaScript 解释器后一周，商业 Hadoop 提供商 MapR 周二宣布，它将发布一个基于 JSON 的文档数据库的开发者预览版，供 Hadoop 内部使用。其目的将是直接通过 Hadoop 提供运营数据，绕过为 MongoDB 等 NoSQL 数据库单独处理日志文件、物联网传感器数据和其他标准化数据集的需要。

MapR 的 CMO 杰克·诺里斯(Jack Norris)在接受 New Stack 采访时表示:“在开放这种持续分析的过程中，我们谈论的是这些运营类型的应用程序，到目前为止，这些应用程序在某种程度上是相互独立的。“如果看看传统环境，您会发现生产流程被加载到运营数据存储中，而运营数据存储又被加载到数据仓库中；在数据收集和最终分析之间有很长的时间间隔。

## 回家去欧康

今天，在以 JSON 为中心的数据仓库类别中，已经出现了一个家庭手工业。不管是好是坏，JSON 已经成为传输中数据的通用表达格式。由于格式严格，JSON 表达的数据也是高度规范化的。因此，对于即席报告，将数据转换成 NoSQL 数据库可以有效应用分析的格式的工作并不复杂，只是非常庞大。

一家名为 jSONAR 的公司就是基于这一理念成立的[ [详见本 PDF 白皮书](http://www.jsonar.com/wp-content/uploads/2015/05/jSONAR_WhitePaper_3_v04_web.pdf) ]，为 NoSQL 数据库开发了一个名为 SonarW 的纯 JSON 数据仓库系统，以利用来自 Hadoop 的规范化数据。

MapR 的创新将有效地切断 SonarW 的通路，产生分析工具可以立即引用的 JSON 数据，而无需额外的步骤。

“直接获得分析的能力是关键。”诺里斯说。“无论是了解当前广告活动进展情况的开胃仪表板，还是整合到在线零售环境中的推荐应用引擎(当客户个性化其体验时)，所有这些都需要实时数据库。事实上，现在您可以直接针对 JSON 文件运行这些应用程序，这是一个巨大的优势。”

最新的 MapR DB 版本将利用开放的 JSON 应用程序接口(创建的部分原因是为了使用缩写 OJAI)通过 API 访问内存中的文档结构。[在周二](https://www.mapr.com/blog/faster-application-development-open-json-application-interface-ojai#.VgsW4JdWNuw)的一篇博客文章中，MapR 首席软件工程师 Bharat Baddepudi 解释了典型的 JSON 内存文档是如何出现的，以及如何编写 API 函数调用来执行在普通数据存储库中执行的典型 CRUD(创建、读取、更新、删除)操作。

Baddepudi 写道，“OJAI 包括一个称为表的后端文档存储接口，用于插入和检索文档以及执行其他类似的 CRUD 操作。每个这样的用户文档都存储为表中的一行，使用唯一的行键来访问它。

JSON 数据集被表示为一个文档，使用的语法可以很容易地被人类和语言解释者解析。因此，如果在一个这样的文档中，字段名被赋予表中的每个属性或列，那么可以使用 API 方法`.set`将这些字段的值写入到对象`MapRDB`中，其中字段名和设置作为参数传递。对单个记录的更新可以作为对存储器的“突变”来执行，对存储器的内容进行寻址，就好像它们是具有数字索引的数组一样。

这是一个看似简单的系统，但关键在于:与为 MongoDB 生成一组类似的脚本相比，为解析 MapR DB 直接提供的 JSON 数据而创建脚本所花费的精力肯定不会更多，也可能更少。但是，由于您是直接处理数据库，而不是渲染数据库，因此您可以获得 Hadoop 实时处理的所有好处。

## 又到了和解时间

这种处理模式可能会带来潜在的架构转变。现实世界中的数据库应用程序在过去依赖于操作分析和报告功能来触发功能，现在可能假设这些功能已经完成。也许在以后的版本中，这些应用程序可以简单地处理内存中不断更新的变量的结果。

MapR 的 Jack Norris 谈到了这一点:“在我们的平台中，我们目前支持表复制，现在支持 JSON 文档复制，不仅从数据的角度，而且以首选的格式。因此，您可以将它作为搜索索引使用——您可以拥有一个基于搜索的应用程序，与数据库表的数据空间同步。这样，当您拥有一个面向客户的应用程序时，就不存在数据加载时间的批量依赖性，因此客户可以从不同的角度查看他们的支持单或账单。”

Norris 还发现了一种可能性，即毫秒级的运营分析将变得至关重要，例如，实时欺诈检测，即零售店中服务器生成的运营日志全天候扫描异常活动。

“如何简化组织内的数据流？您如何简化应用程序，从而缩短数据创建和数据收集之间的周期？”诺里斯问道，不可否认是修辞性的。“我认为这一点越来越明显:平台的差异在更大程度上支持这种实时差异功能，并在发生时影响业务。”

特征图片: [Szabolcs](https://www.flickr.com/photos/xewboy/) 的:[Blue spirit-BY texture place](https://www.flickr.com/photos/xewboy/6875251890/in/photolist-btxsRG-p1dFth-9aXEaY-bpRq43-4WzyER-bkGkZG-95BGcn-2iu9rL-gMQDZV-5zd5RP-epkxxH-d39CQA-egTvoz-f868eV-8YVgwr-m2nsTe-2waLN-fo6EJd-fcu9vY-LC3RP-74bQpz-8cwntk-tvUMWi-8gda91-e8QX-dtbCrk-4Za7TG-xyTXfZ-5RarjN-aHqYhB-5r7gf4-4EGaoG-bvsW8m-c8oK9U-qN465y-fpXjAD-3J2Voo-7HcYX5-8tzC2y-tATzc-7GJA42-pfXkSb-37pxYj-nJfWqd-6Vai98-qaExCo-rdFNpM-qcWQeV-6eQHUV-f8ERhQ)获得 [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>