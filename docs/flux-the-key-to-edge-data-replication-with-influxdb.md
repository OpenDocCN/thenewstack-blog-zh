# Flux:使用 InfluxDB 进行边缘数据复制的关键

> 原文：<https://thenewstack.io/flux-the-key-to-edge-data-replication-with-influxdb/>

Flux 是用于 [InfluxDB](https://www.influxdata.com/?utm_content=inline-mention) 时间序列数据库平台的数据脚本和查询语言，支持有用的功能，如[边缘数据复制](https://www.influxdata.com/products/influxdb-edge-data-replication/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns) (EDR)。

 [阿纳伊斯·多蒂斯-乔治乌

Anais 是 InfluxData 的开发者倡导者，热衷于通过使用数据分析、人工智能和机器学习来美化数据。她收集数据，进行综合研究、探索和工程设计，将数据转化为功能、价值和美感。当她不在屏幕后面时，你可以发现她在外面画画、伸展身体、登船或追逐足球。](https://www.linkedin.com/in/anais-dotis-029623113/) 

EDR 允许开发人员自动将数据从 InfluxDB 开源实例中的存储桶复制到 InfluxDB 云实例中。这一特性改变了物联网开发人员在 InfluxDB 上构建物联网应用的想法，因为它在给定系统的这些不同元素之间创建了持久可靠的数据传输。EDR 使开发人员能够在边缘利用 InfluxDB 的全部功能。同时，它允许开发人员将相同的数据或云中数据的子集用于完全不同的目的。

EDR 可以支持多种任务，例如从边缘源收集高保真数据、在边缘清理和转换数据、整合云中的边缘数据以生成边缘整体的全局视图，以及对云中的整合数据进行时序分析和警报

## 通量优势

作为一种全功能的脚本和查询语言，Flux 拥有强大的功能。它允许您查询时间序列数据，为创建警报、管理时间序列数据生命周期以及清理、分析和转换数据设置阶段。

Flux 的优势在于它提供了执行这些查询的能力和服务器端的能力，从而提高了性能。事实上，[一些 Flux 函数将查询下推到 InfluxDB 平台](https://www.youtube.com/watch?v=ZorlId2_XEg)，在存储上执行它们以优先考虑速度和内存优化。

你可以在 InfluxDB [这里](https://www.influxdata.com/blog/top-5-hurdles-for-intermediate-flux-users-and-resources-for-optimizing-flux/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns)了解更多关于下推的内容。

## 用通量查询

一个简单的 Flux 查询如下所示:

```
```flux
from(bucket:  "bucket1") 
|>  range(start:  -10m)
|>  filter(fn:  (r)  =>  r._measurement  ==  "measurement1")
|>  filter(fn:  (r)  =>  r.tag1  ==  "tagvalue1")
|>  filter(fn:  (r)  =>  r._field  ==  "field1")
```

```

您使用一个`from()`函数来选择您想要查询数据的桶。`range()`函数指定数据查询的时间窗口或时间间隔。最后，`filter()`函数允许您指定要查询的数据子集。

InfluxDB 使用测量值将大型数据子集分组或组织在一起，使用标签存储有关时间序列数据的元数据，使用字段存储时间序列数据的实际值。

例如，要查询天气数据，流量查询可能如下所示:

```
```flux
from(bucket:  "weather")
|>  range(start:  -10m)
|>  filter(fn:  (r)  =>  r._measurement  ==  "United States")
|>  filter(fn:  (r)  =>  r.location  ==  "Austin")
|>  filter(fn:  (r)  =>  r.temperature  ==  78.0)
```

```

要了解关于编写 Flux 查询的更多信息，有大量的资源可供您使用。

## 管理您的时间序列数据生命周期

Flux 允许您以多种方式转换和聚合时间序列数据。Flux 的一个常见用途是为数据的物化视图创建任务来[缩减数据采样](https://docs.influxdata.com/influxdb/cloud/process-data/common-tasks/downsample-data/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns)。缩减采样将高分辨率数据转换为低分辨率摘要。其中，缩减采样减少了 InfluxDB 实例的整体磁盘大小，同时保留了数据的整体形状。

Flux 中的缩减采样任务可能如下所示:

```
```  flux
// Task Options
option task  =  {name:  "downsample task example",  every:  1w}

// Defines a data source
data  =  from(bucket:  "weather")
// queries data for 1w based off of the task configuration options above
|>  range(start:  -task.every)
|>  filter(fn:  (r)  =>  r._measurement  ==  "United States")
|>  filter(fn:  (r)  =>  r.location  ==  "Austin")
|>  filter(fn:  (r)  =>  r.temperature  ==  78.0)

data
// Windows and aggregates the data in to 1h averages
|>  aggregateWindow(fn:  mean,  every:  1h)
// Stores the aggregated data in a new bucket
|>  to(bucket:  "data-downsampled")
```

```

该任务获取高精度温度数据并收集一个小时的平均值，然后使用`to()`函数将该数据写入一个新的存储桶。

## 对您的数据保持警惕

鉴于最近[推出了边缘数据复制](https://www.influxdata.com/blog/edge-data-replication/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns)，我们想更深入地了解如何使用 Flux 实现从边缘到云的数据转换。Flux 提供了多种方法来检查您的数据，看它是否满足特定条件，然后就此发出警报。您可以使用 Flux 根据您在边缘使用或收集的数据以及云中整合的数据来设置警报。

有几种不同的方法来创建不断变化的警报。您可以通过 InfluxDB Cloud UI 构建阈值或“死亡”检查。此方法为您创建的每个警报自动生成 Flux 脚本，并使用 InfluxDB 检查和通知系统。此外，您可以编写自己的自定义检查和通知任务。如何检查和提醒您的数据取决于您自己。Flux 在处理数据时为用户提供了很大的灵活性。您可以向以下[通知端点](https://docs.influxdata.com/flux/v0.x/tags/notification-endpoints/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns)发送警报，包括 Flux to Slack、Microsoft teams、 [PagerDuty](https://www.pagerduty.com/?utm_content=inline-mention) 和许多其他通知端点:

![](img/2cac2f4aa8fa7af09914763705214877.png)

要了解有关[创建检查和通知](https://youtu.be/-QdldB3RxMw)的更多信息，请查看以下资源:

*   [一个提醒任务](https://awesome.influxdata.com/docs/part-3/tasks/#an-alert-task):*这一节描述了如何编写一个提醒任务来检查您的数据并向 Slack 发送一个提醒。*
**   [检查和通知](https://awesome.influxdata.com/docs/part-3/checks-and-notifications/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns):这一节“到牛逼的时候了*”*详细描述了 InfluxDB 中的检查和通知系统是如何工作的。*   [在 InfluxDB UI 中创建检查](https://docs.influxdata.com/influxdb/v2.0/monitor-alert/checks/create/#create-a-check-in-the-influxdb-ui):该文档描述了使用 InfluxDB 和 Flux 创建检查的几种不同方式。*   [自定义检查文档](https://docs.influxdata.com/influxdb/cloud/query-data/get-started/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns):InfluxDB 文档总是所有 Flux 和 influx db 内容的重要资源。*

 *## 分析、清理和转换您的数据

将统计分析转换并应用于时间序列数据，可以让您从中获得有价值的见解。在使用边缘数据复制功能并将其整合到云中之前，您可能还需要清理和准备您的数据。

Flux 有许多[不同的功能](https://docs.influxdata.com/flux/v0.x/stdlib/universe/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns)用于分析和准备时序数据。有用于统计时间序列分析的转换函数，用于动态统计和基本时间序列分析的转换函数，以及用于金融分析的技术动力指标。还有另外一些用于处理[地理时态数据的](https://docs.influxdata.com/flux/v0.x/stdlib/experimental/geo/)[数学](https://docs.influxdata.com/flux/v0.x/stdlib/math/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns)软件包。

Flux 也可以转换你的数据。例如， [joins](https://docs.influxdata.com/flux/v0.x/stdlib/universe/join/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns) ( [video](https://youtu.be/g-HY1Q11iGg) )， [unions](https://docs.influxdata.com/flux/v0.x/stdlib/universe/union/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns) 和 [pivots](https://docs.influxdata.com/flux/v0.x/stdlib/universe/pivot/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns) ( [video](https://youtu.be/LuPcShbE0J4) )改变数据的形状。

成功使用时序数据的另一个关键因素是操作时间戳的能力。有一组函数允许您操作您的时间戳并执行各种时间序列转换。

你也可以使用 Flux 来编写定制的算法。例如，以下链接演示了两种用 Flux 编写的用于异常检测的不同算法:

1.  [中值绝对偏差异常检测](https://www.influxdata.com/blog/anomaly-detection-with-median-absolute-deviation/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns)
2.  [深入探讨机器学习中的变化:朴素贝叶斯分类](https://www.influxdata.com/blog/deep-dive-into-machine-learning-in-flux-naive-bayes-classification/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns) 

## InfluxDB 中边缘数据复制的威力

最近，InfluxDB [发布了一个名为边缘数据复制](https://www.influxdata.com/blog/edge-data-replication/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns)的新功能。EDR 允许您在 InfluxDB 的开源实例中配置一个桶，以自动将数据从该桶复制到 InfluxDB 的云实例中的桶。

例如，使用 EDR，您可以在边缘或雾中运行多个 OSS 实例，并在那里收集高精度数据。然后，您可以创建任务，在将数据自动复制到 InfluxDB 云实例之前，对该数据进行缩减采样、处理或转换。您可以使用该功能来构建混合架构，并通过最大限度地减少传输到云的数据量来节省成本，或者在数据到达云数据存储之前清理数据，从而提高效率。

设置[边缘数据复制](https://docs.influxdata.com/influxdb/v2.2/write-data/replication/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-06-27_event_data-ai-summit_na&utm_content=tns)只需要几个步骤:
1。使用[流入远程命令](https://docs.influxdata.com/influxdb/v2.3/reference/cli/influx/remote/create/)创建与 CLI 的远程连接，如下所示:

```
```  flux
influx remote create  \
--name example-remote-name  \
--remote-url https://us-west-2-1.aws.cloud2.influxdata.com \
--remote-api-token mYsuP3r5Ecr37t0k3n  \
--remote-org-id  00xoXXoxXX00
```

```

2。添加任何所需的[下采样或转换任务](https://docs.influxdata.com/influxdb/v2.3/process-data/common-tasks/downsample-data/)，并将数据写入 OSS 中的新存储桶。

3.使用[流入复制命令](https://docs.influxdata.com/influxdb/v2.3/reference/cli/influx/replication/create/)创建一个从 OSS bucket 到 InfluxDB Cloud 中的 bucket 的复制流，如下所示:

```
```  flux
influx replication create  \
--name example-replication-stream-name  \
--remote-id  00xoXXXo0X0x  \
--local-bucket-id Xxxo00Xx000o  \
--remote-bucket-id  0xXXx00oooXx
```

```

## 底线

我希望这篇文章能启发您探索 InfluxDB、Flux 和边缘数据复制。要了解更多关于这些主题的信息，请查看我们即将在[数据+人工智能峰会](https://databricks.com/dataaisummit/session/introduction-flux-and-oss-replication)上的演讲，我们将在那里详细讨论这些主题，或者通过我们的社区 [Slack](https://influxdata.com/slack) 频道与我联系。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*