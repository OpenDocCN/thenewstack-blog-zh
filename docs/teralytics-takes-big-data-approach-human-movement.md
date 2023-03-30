# Teralytics 采用大数据方法来跟踪人体运动

> 原文：<https://thenewstack.io/teralytics-takes-big-data-approach-human-movement/>

为了减少空气污染，德国纽伦堡市与移动运营商 Telefonica 和大数据公司 [Teralytics](https://www.teralytics.net/) 合作，确定碳排放热点，并改善其交通系统。使用电信数据来了解人们如何旅行——汽车、火车、步行——与空气质量测量站网络进行比较，它能够为进一步减少碳排放的努力获得资金。

Teralytics 和地理信息系统软件公司 [Esri](https://www.esri.com/en-us/home) 利用来自手机信号塔和其他来源的数十亿个信号数据，绘制了飓风哈维前夕[休斯顿地区](http://urbanobservatory.maps.arcgis.com/apps/Cascade/index.html?appid=b6f411a699a843f1bf319a47056b8f73)的疏散图。

总部位于苏黎世的 Teralytics 与政府和私人客户合作，以了解人类运动的模式。联合创始人兼首席技术官 Luciano Franceschina 称之为“讲述人类旅程的数据”

他坚持认为，因为“每个祖母都带着一部手机”，电信掌握着最丰富的人类活动实时数据集。他指出，即使当人们被疏散时，他们也带着手机。

例如，看看这个关于苏黎世如何醒来的视频:

[https://www.youtube.com/embed/FTtaL0AdqF4?feature=oembed](https://www.youtube.com/embed/FTtaL0AdqF4?feature=oembed)

视频

“城市变得越来越密集，新的交通方式将在 10 年或 20 年后出现。拥堵越来越严重。……我们提供基础层——了解运输需求并进行优化，以便将环境影响降至最低，”Franceschina 说。

优步和 Lyft 等拼车服务将改变交通需求，长期来看，自动驾驶汽车也将如此。他说，城市需要了解并准备好更长期的交通模式，例如 [Hyperloop](https://www.theverge.com/2017/11/16/16666956/virgin-hyperloop-one-india-agreement-study) 和 [Lilium](https://techcrunch.com/2017/09/05/lilium-raises-90m/) ，一家致力于电动飞行出租车的公司。

## 随大流

这项业务的想法源于苏黎世联邦理工学院(ETH Zurich)大学，在那里，联合创始人弗朗西丝奇娜、[乔治·波尔泽和](https://twitter.com/gpolzer?lang=en)[唐纳德·科斯曼与当地一家电信公司合作，为政府分析通勤模式。](https://www.linkedin.com/in/donald-kossmann-8915b1/)

这家成立四年的公司正在建立一个在移动网络运营商的安全网络中运行的平台。它们基本上成为人类运动的传感器网络。

“我们从电信内部获得相对原始的匿名数据，并将其转化为(对客户的)预测或建议。我们有可视化的实时仪表板，例如，客户可以看到特定列车上有多少人，”Franceschina 解释说。

它报告说，使用手机信号塔 pings 和接入 WiFi，结合移动设备的点击流数据，处理了超过 4 亿人的数据。据报道，到目前为止，它已经与苏黎世、纽约、新加坡和香港的八家电信公司合作，最近还与香港三大电信公司签署了合作协议。

对于分析，Teralytics 使用专有的机器学习算法以及开源大数据技术。Franceschina 解释说，该平台基于 Apache Spark 和 Kafka，运行在 Mesos 上，通过 Ansible 和 [HashiCorp Terraform](https://thenewstack.io/hashicorp-updates-terraform-enterprises/) 部署到裸机和云，遵循基础设施即代码原则。

“我们开发了专有的 API 和处理框架来高效地存储和处理移动网络数据。这些 API 中嵌入了我们基于机器学习的在线和离线算法，这些算法可以将数据转化为对交通运营商和智能城市的见解。这些算法已经过优化，可以在数百万亿字节的数据上并行运行。

为了在仪表板上显示数据，该服务依赖于 GraphQL 和 React，运行在云上的 [Node.js](/tag/node.js/) 上，使客户可以在城市规划、交通运营或灾难响应中访问这些数据。还可以将结果输入地理信息系统软件，如 ESRI 的 ArcGIS。

数据科学家 [Javiera Guedes](https://www.linkedin.com/in/javieraguedes/) 在 2016 年欧洲 [Spark 峰会](https://spark-summit.org/eu-2017/schedule/)上发表演讲，谈到了使用移动网络数据和 Spark 构建起点-目的地矩阵:

[https://www.youtube.com/embed/VPgD8yeWH5o?feature=oembed](https://www.youtube.com/embed/VPgD8yeWH5o?feature=oembed)

视频

商业模式是与电信分享收入。在最近的[报告](https://www.gartner.com/doc/3795764/market-trends-ways-csps-exploit)中，Gartner 将基于位置的产品的机器学习列为通信服务提供商增加收入来源的方式之一。

即便如此，对电信公司使用用户数据的隐私担忧仍比比皆是。今年早些时候，美国总统唐纳德·特朗普签署了[法案](https://www.washingtonpost.com/news/the-switch/wp/2017/04/04/trump-has-signed-repeal-of-the-fcc-privacy-rules-heres-what-happens-next/)，推翻了禁止互联网提供商收集、存储、共享和出售消费者信息(包括位置数据)的规定。这项立法得到了美国互联网服务提供商的大力支持，包括康卡斯特和威瑞森，以及脸书和谷歌等，[据政治](https://www.politico.com/story/2017/03/broadband-data-victory-republicans-236760)报道。

Franceschina 表示，该公司只对人群的移动感兴趣，并且只使用匿名数据。我问他这些数据是否可以用来判断一个已婚的人是否有外遇。他没有回答这个问题，只是说公司只想把数据用在好的方面。

Franceschina 说，Teralytics(不要与农业科技初创公司 teralytics 混淆)希望扩展到更多国家，并设计出检测更多运输模式的能力。它已经可以确定车里的人是否在拼车。他说，许多城市都对区分步行和骑自行车的人感兴趣。该公司有兴趣在未来帮助组织优化自行车路线。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>