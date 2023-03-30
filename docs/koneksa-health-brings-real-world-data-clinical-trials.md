# Koneksa Health 将真实世界的数据引入临床试验

> 原文：<https://thenewstack.io/koneksa-health-brings-real-world-data-clinical-trials/>

传统上，参与临床试验的患者必须去实验室或研究医院提交数据。这可能是血压读数，一份关于新药如何影响他们睡眠的问卷，或者是对他们呼吸功能的测试。

然而， [Koneksa Health](https://www.koneksahealth.com/) 的工程副总裁 [Tom Hosford](https://www.linkedin.com/in/tom-hosford-6086b319/) 最近在 [MongoDB World 2017](https://www.mongodb.com/world17) 的一次会议上指出，通过联网设备，患者可以从任何地方提交数据，因此研究人员可以更频繁地收集更多数据，更有效地汇总数据。

这家总部位于纽约市的初创公司已经开发了一个分析平台，用于监控、聚合和分析来自可穿戴设备和设备的连续和大容量数据源，如测量肺功能的血压袖带、心率贴片或肺活量计。

该公司宣布与日本制药公司武田(Takeda)合作，在早期临床试验中使用 Koneksa 的生物传感器和可穿戴设备的远程数据收集能力。它还与提供临床级可穿戴活动和睡眠监测技术的 ActiGraph 合作。

[纽约市 Montefiore Einstein 癌症护理中心](http://www.montefiore.org/cancer)与 Koneksa Health 合作，整合来自 [Garmin Vivofit](https://buy.garmin.com/en-US/US/p/143405) 设备的数据，以跟踪癌症患者在同步放化疗期间的活动。

Koneksa 在亚马逊网络服务上使用 Linux，包括许多亚马逊服务，如用于日志记录的 [CloudWatch](https://aws.amazon.com/cloudwatch/) ，用于服务器的 EC2 等等。它将 Mongo 作为主数据存储(所有应用程序数据和数据的汇总形式), Amazon Simple 存储原始数据。例如，对于追踪器手表，原始数据存储在 AWS 的[简单存储服务](http://docs.aws.amazon.com/AmazonS3/latest/dev/Welcome.html)中，然后应用程序将数据转换并规范化为 Mongo 使用的 JSON 格式，最终供数据科学家进行分析。

在应用层，它使用 [Node.js](https://nodejs.org/en/) 和[mongose](http://mongoosejs.com/)进行对象建模。霍斯福德解释说，从 API 中的数据到数据库，一切都在 JavaScript 中。

该体系结构包括三个副本，每个副本都有主服务器和辅助服务器。身份服务器控制用户的身份验证。只有参与试验的管理员才能访问管理应用程序，但患者可以访问客户应用程序，如果不是盲法试验，患者可以看到他们的试验进展如何。API 服务器连接到设备，通过 API 或其他来源获取数据。

Koneksa 应用程序从各种设备收集数据，包括霍斯福德演示的[肺活量计](http://www.mayoclinic.org/tests-procedures/spirometry/basics/definition/prc-20012673)。它测量的数据包括一个人在一秒钟内能够排出的最大空气量。

病人对着同步到他手机上的设备吹气。API 服务器检索用于填充仪表板的数据。软件开发人员 Brenda Deverell Cortez 解释说:“研究协调员可以看到收集数据的所有端点，并在不同的时间段内深入研究，还可以深入研究单个端点的数据。

## 数据建模

因为 Koneksa 的平台从各种设备收集数据，所以数据有各种格式。

“我们如何选择一个度量模型来编写可重用的代码，比如‘获取图表上的所有数据点’或者在同一个数据模型中每个分析一个字段？Mongo 为此提供了嵌入式文档结构和灵活的模式，”Hosford 说。

有一些常见的字段，如用户 ID、设备类型、位置、测量时间。然后是一个嵌入式嵌套数组，以一对多的关系存储读数中的所有数据点，可以表示许多不同的值。在 API 服务器获取数据并将其转换成 JSON 格式后，它将被处理并规范化为一致的模式。

Mongoose 是一个 Node.js 库，它提供了一些增强的功能。

“首先，在验证层，我们可以设置必填字段——如果记录与用户没有关联，则抛出一个错误。我们可以在一组中进行验证。我们可以说，这种设备必须是肺活量计、血压袖带或心电图贴片。同样，我们可以设置默认字段，如果缺少日期，将其设置为创建时间。这让我们填补了一些 MongoDB 本身没有提供的空白，但我们在应用层从这些东西中获得了很多价值，”他说。

默认字段还支持“惰性迁移”

该公司最近在其数据模型中增加了国际时区支持。在关系数据库中，首先运行“alter table”语句向用户模型添加一个新的时区列，然后运行大规模更新来更新数据库中的所有用户。霍斯福德说，这可能会给拥有许多用户和客户机的大型应用程序带来性能问题。

使用 Mongoose 的默认字段和灵活的模式可以实现“惰性迁移”，即随着时间的推移，在保存和获取记录时迁移记录。

## 数据检索和性能

Cortez 解释说，为了找到特定用户的测量值，你必须进行左连接——将数据库中两个表的数据结合起来。您必须找到特定的用户，并从他或她那里找到所有的测量值。

您可以使用 Mongoose 的库在应用程序级别实现这一点，但是它在 MongoDB 中并没有得到本机支持。在 Mongo 3.2 中， [$lookup](https://docs.mongodb.com/manual/reference/operator/aggregation/lookup/) 调用本身就可以做到这一点。3.4 版本增加了 [$graphlookup](https://docs.mongodb.com/manual/reference/operator/aggregation/graphLookup/) ，这意味着可以将数据限制在肺活量计上。

因为希望限制对数据库的回调，该公司采用了缓存字段方法，这是对用户记录的反规范化。

“我们将最新的测量结果反规格化为用户对象上的最新数据字段。当协调者加载参与者仪表板时，他们获得所有这些用户对象，每个对象都有自己的最新数据，”Hosford 解释道。“这样我们就可以在不进行任何查询的情况下填充仪表板。然后，如果协调员想要查看这些端点的详细视图和特定图形，他们可以这样做，新的查询将在那时进行。”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>