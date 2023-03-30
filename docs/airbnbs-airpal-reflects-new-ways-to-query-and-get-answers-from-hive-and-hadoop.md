# Airbnb 的 AirPal 体现了从 Hive 和 Hadoop 中查询和获取答案的新方式

> 原文：<https://thenewstack.io/airbnbs-airpal-reflects-new-ways-to-query-and-get-answers-from-hive-and-hadoop/>

Airbnb 的数据存储累积规模接近 1.5 与脸书的 300 相比只是沧海一粟，但仍然是一个庞然大物。当 Airbnb 需要一个工具来查询和可视化这个不那么无限的数据池时，它为自己建立了一个名为 [AirPal](https://nerds.airbnb.com/airpal/) 的工具。这个可视化工具是开源的，它检查来自数十 Pb 集群的记录。

AirPal 的发展故事很好地说明了互联网规模的公司是如何合作建立自己的数据基础设施的。这些公司不得不构建自己的工具，这些工具比来自 Oracle、微软或任何其他数据库和数据仓库巨头的工具更适合他们的需求。AirPal 展示了正在发明的工具是如何超越第一代的，并享受着成熟，允许 Airbnb、脸书、Dropbox 和其他许多公司的数千名工程师存储、管理和利用其数据。

## 唤醒沉睡的巨人

在 Airbnb 的数据中心内外，“bnb”代表“床和早餐”。移动设备用户依靠这项服务从提供住宿的好心人那里找到住处。这也是一个来自美国宇航局的前数据可视化专家可以感觉宾至如归的地方。

Airbnb 不仅仅是一个应用程序，还是一个支付系统，促进了房东和房客之间的货币交易。这是一个被称为共享经济的平台。为了让 Airbnb 的员工能够跟踪经济中发生的事情，该公司的开发人员——包括软件工程师 Andy Kramolisch，他曾在美国宇航局兰利研究中心工作；之前在脸书数据库团队工作的产品经理 James Mayfield 为分布式数据查询引擎构建了自己的前端，用于监控他们的 Hadoop 集群。

“我一直是一个试图确保决策发生在组织的正确级别的人，”梅菲尔德在与新堆栈的对话中说。“其中一部分是确保人们根据数据做出最佳决策。”在他的职业生涯中，包括在脸书，他说他的目标是推广分布式数据模型。

他告诉我们，这种推广的一部分包括建立一种神经中枢，“在这里，人们觉得他们可以自己去写问题并回答问题，而不是在一个环境中，有一些精选的、指定的人必须为每个人回答问题。”

员工倾向于将数据视为一个地方，而不是一个设备、一个引擎、一个运输仓库、一个机场跑道或任何其他在过去十年中用于数据存储的隐喻。当时在雅虎工作的软件工程师首先构建了一个系统，在这个系统中，任何地方的所有数据都可以被视为一个地方。

但是是脸书的一个重要贡献使得这个地方成为你可以参观的地方。

## 旧的，新的蜂巢

早在 2009 年，Hive 是第一个可以像其他数据仓库一样查询的 Hadoop 数据仓库。它表明，与集体数据存储相比，巨型关系数据库几乎没有真正的质量优势。

在大量数据用户中，脸书可能处于独特的位置。虽然它经常吹嘘其蜂巢集群的大小，但 Mayfield(前脸书工程师)指出，它实际上拥有能够永久存储所有数据的奢侈品。处理仅仅 1 或 2 Pb 数据的小型机构必须有更好的战略。

因此，Airbnb 将其最新数据存储在 EC2 实例上的 Hadoop 分布式文件系统(HDFS)集群中，延迟较低。然后，按照设定的时间间隔，它将老化存储从“热”区“退役”到“冷”区 S3 存储。梅菲尔德表示，这种策略有助于减少 Airbnb 的总数据集大小。

“就像亚马逊的大用户，像 Dropbox 和网飞，我们都经常聊天，我们都有相同的方法，”Kramolisch 说。“有些人有较小的 HDFS 集群，有些人有较大的集群，但将大部分历史数据保存在 S3 的基本想法就像是一种屡试不爽的做法。”

Hive 是 Airbnb 最初的单一真实来源。但是由于速度和延迟问题，它后来切换到亚马逊红移，这[消耗来自 S3 桶](http://docs.aws.amazon.com/redshift/latest/dg/tutorial-loading-data.html)的数据。

“这有它自己的问题，”他说，“比如并发查询的数量有限，每天晚上从 Hive 到 Redshift 复制我们所有数据的 ETL(提取/转换/加载)过程非常痛苦，这或多或少增加了我们系统必须做的工作量。”

## 床和早餐来拯救

是脸书在 Hive 的其他用户之前发现了这个问题。正如这家社交巨头的软件工程师[马丁·特拉弗斯在 2013 年的一次公司会议上解释的那样，“Hive 的问题在于它是为批处理而设计的。”他的演讲引用了一位未透露姓名的脸书数据科学家的话说，“一个好的一天是我可以运行六个 Hive 查询的时候。”房间里的其他数据科学家也笑着表示同意。](https://www.youtube.com/watch?v=qZsfpK9bafY)

脸书将是第一个为脸书几年前的第一个解决方案所引起的问题创造解决方案的国家。起初它开发了 [PrestoDB](https://prestodb.io/) ，这是一个 SQL 查询引擎，可以聚合来自多个来源的数据，包括 Hive，但也包括 Cassandra。根据梅菲尔德的说法，该公司后来实际上接触了 Hive 的一级客户，包括 Dropbox、网飞和 Airbnb，提出成为 PrestoDB 的早期采用者，甚至在它向开源社区发布查询引擎之前。

他说，迁移到 PrestoDB 对 Airbnb 来说非常有效，关键原因是因为 Redshift 不是开源的。获得 PrestoDB 的源代码使 Airbnb 能够在早期调试问题，并将其补丁发送回上游。

但是少了点什么。Hive 确实有一些前端查询 UI 工具可用，[比如 Hue](http://gethue.com/) ，但是 PrestoDB 没有。

在脸书期间，梅菲尔德为 Hive 使用了一个名为 HiPal 的前端。它是脸书基础设施堆栈的内部部分，不会开源。尽管如此，梅菲尔德说，Airbnb 通过将其可视化工具 AirPal 配音向 HiPal 致敬。

它为用户提供了一个简单的 Web 界面，不仅可以搜索数据表，还可以搜索元数据和模式。它能够在 Hive 中基于从检索到的数据中过滤出的结果创建新的表格，或者它可以将查询结果流式传输到可以在 Excel 中打开的 CSV 文档中。

“当安迪和我在 Airbnb 建造这个时，我们实际上去了脸书，会见了那里的 Presto 团队和数据工具团队，向他们展示了我们的工作，并与他们讨论了开源 AirPal 的可能性。他们真的很支持这个想法。部分原因是他们希望世界上存在一个类似 HiPal 的工具，但这可能不是他们实现这一目标的路线图的一部分。”

正如梅菲尔德在 Airbnb 的企业博客中写道，“我们站在巨人的肩膀上制作了这个工具，我们感谢脸书的数据基础设施和数据工具团队能够提供的影响和投入。”

讲述 Airbnb 迅速崛起的金融出版物[称其为“网站”这似乎可以称芝加哥小熊队为“运动俱乐部”更准确地说，Airbnb 突然成为了世界数据可视化专家。顺便说一句，你可以用它来预订房间。](http://www.telegraph.co.uk/technology/news/9525267/Airbnb-The-story-behind-the-1.3bn-room-letting-website.html)

特色图片[通过](https://www.flickr.com/photos/ouishare/7920234298/in/photolist-roFRBC-qrMz4s-roM2Hc-roFPMq-r7dxib-o9Mbyd-o9S5wg-o9S67e-dhxxA4-9PNNsD-dy8JL9-nRZ6Wb-heGaqy-e9cTaq-nJBrUL-pXspiP-ePdTEo-peyRRR-d4TgHL-dy3icR-ojyJBa-r7jYpv-r7jXkB-pkzErq-9x5UBm-bYZT51-duQ61v-jfWP5F-hwPhLC-e2aaZE-e23G2z-fbnqVw-duVwyh-bWyhmQ-dNfgXU-nnsSsF-nkpdGh-nnsRQ8-qV1GrE-a6nKnJ-pkzKR3-qSciqx-pVcepf-pKaScK-oNy2ay-psV1re-pC3XjW-fboch5-fbnZMC-fb8JBt) Flickr 知识共享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>