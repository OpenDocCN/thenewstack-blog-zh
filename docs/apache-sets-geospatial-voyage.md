# 阿帕奇开始了地理空间之旅

> 原文：<https://thenewstack.io/apache-sets-geospatial-voyage/>

一些地理空间专家正聚集在一起，在五月份的 ApacheCon 北美会议上制定一个地理空间轨迹。

他们中的一些人在 9 月份的 [Apache Big Data Europe](http://events17.linuxfoundation.org/events/apache-big-data-north-america) 上会面，开始讨论如何在 Apache 内部提高地理空间意识，并协调项目间的合作。

“目的是在 Apache 内部开始一个跨领域项目的对话，”乔治·帕西瓦尔说，他是位于马里兰州安纳波里斯的[开放地理空间联盟](http://www.opengeospatial.org/) (OGC)的首席工程师。

根据项目征集，这将是一个考虑使用开放标准来提高互操作性和代码重用的机会。

这个地理空间轨迹的始作俑者包括珀西瓦尔；克里斯·马特曼(Chris Mattmann)，加州帕萨迪纳喷气推进实验室仪器和数据系统部门的首席数据科学家和首席架构师；Ram Sriharsha 是 Hortonworks 的高级技术人员；Sergio Fernández，奥地利萨尔茨堡 Redlink 软件工程师；以及法国阿尔勒 Geomatys 公司的开发商 Martin Desruisseaux

“有一系列项目，其中一些旨在对地理空间进行更复杂的理解，以解决一些复杂性。有些甚至只是使用一个点的位置。这太好了。我们只是想确保它始终如一地完成。珀西瓦尔说:“即使只是使用一个点的位置也会引起问题——首先是经度还是纬度——信不信由你，这是一个持续的问题。”OGC 一直致力于创建基于共识的开放标准

德勤估计，到 2020 年，[基于位置的服务将成为价值 1.3 万亿美元的产业](http://government-2020.dupress.com/driver/geospatial-technology/)，包括 GPS 在内的地理位置数据的使用将产生 5000 亿美元的消费者价值。一份市场和市场报告预测，GIS 系统的年复合增长率为 10 %,其中软件占 48%。它表示，对开源软件的偏好将是这一增长的驱动力之一。

根据《地理空间世界》杂志的 2016 年行业报告，地理空间应用将越来越需要大数据解决方案和分析技术。

这些项目包括:

**[空间信息系统(SIS)](http://sis.apache.org/)** 项目是一个用于开发地理空间应用的免费 Java 语言库。它可用于表示搜索、数据聚类、存档和其他空间功能的坐标。这项工作的重点是实现 OGC GeoAPI 实施规范 3.0 接口，用于桌面或服务器应用。

据 Desruisseaux 说，SIS 在气象学、土地利用和其他领域有广泛的应用，他说他正在全职研究它。实施 ISO 元数据标准的工作已接近完成，坐标参照工作正在进行中。他说，它将继续向上移动，下一个是成像。

Apache SIS 还支持从地理标记语言(GML)文档中读取和写入坐标参考系统(CRS)对象，并使用这些 CRS 执行地图投影。他说这是第一个实现坐标参考系统文本表示新标准 [ISO 19162](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=63094) 的开源项目。

“如果我试图自己开发软件，了解如何使用它对我来说很重要，”Desruisseaux 谈到这项工作时说。“对我来说，OCG 标准就像一个骨架，一个蓝图，它允许我设计 Apache SIS，以服务于现在以及未来 5 年或 10 年的方式服务于公众。”

他在一个叫做星座的沙盒里工作，在那里他做了一个演示。(对于密码/用户名，使用 demo/demo。)

**[Apache Marmotta](http://marmotta.apache.org/)** 旨在为希望发布关联数据或在关联数据上构建定制应用的组织提供一个[关联数据平台](http://www.w3.org/TR/ldp/)的开放实现。

“我们来自一个完全不同的世界。我们来自语义网的研究，所有这些数据都来自高层，”费尔南德斯说。

Fernández 说，去年夏天，谷歌代码之夏的一名学生在 Marmotta 中实现了一个版本的 GeoSPARQL，它将在 2 月份发布 3.4 版本。

它使用 KiWi，这是一个高性能的事务性三重存储后端，用于在关系数据库之上构建 Sesame。它支持基于规则的推理和版本控制。KiWi 的新扩展利用了 PostgreSQL 中的 PostGIS 扩展。

Fernández 说，Marmotta 最常用于旅游应用。

“比方说，如果你在一个镇上，你可以说，‘让我找一家可以吸烟的最好的餐馆，步行五分钟或乘车十分钟’或诸如此类的话。它提供了特殊的功能。我们使用来自不同数据库的小块知识。我们将它们放在一个数据模型中，然后我们可以进行查询，”他说。

**[Open Climate work bench](https://climate.apache.org/)**is**开发一个软件库，除其他外，该软件库使评估气候模型变得更加容易，这些模型基于来自各种来源的异构格式和分辨率的模型和观测数据集。这些来源可能是地球系统网格联合会、美国国家气候评估等，以及美国航天局、诺阿和其他机构的遥感数据的时间/空间尺度。该工具包包括数据提取和处理、指标计算和可视化功能。**

 **喷气推进实验室[从之前的区域气候模式评估系统(RCMES)捐赠了这项技术](https://opensource.com/life/14/6/NASA-Earth-science-open-source)。该项目随后添加了 Apache 面向对象数据技术(OODT)来管理大量数据集，这使得该项目能够超越气候模型评估。

最后，还有 **[Magellan](https://www.youtube.com/watch?v=rP8H-xQTuM0&index=2&list=PL-x35fyliRwi8TqkQ_dZjoNSkUWkcl01e)** 是一个地理空间分析引擎，旨在轻松解析和高效查询大规模空间数据集。

例如，如果用户在没有位置感知的应用程序中搜索“峡谷酒店”，结果可能是德克萨斯州峡谷的酒店，而不是大峡谷附近的酒店。该项目旨在将搜索词与位置上下文配对，以提供更相关的结果。

它使用 Spark SQL、DataFrames 和 Catalyst 作为底层引擎。

*专题图片:* [美国地图上的图钉](https://www.flickr.com/photos/mil8/380092713/in/photolist-zA5jD-omJP1Y-89mARf-897Nko-7184P5-4k5keX-5GdMWp-cwqyrQ-cwqwt3-49THk6-6PxpCE-dtZ29T-dwAERi-9wjFLU-aVMMnz-5C7x8r-6VqVhF-5KNcGs-7eYFby-iV27sX-4TZf9n-55nEde-79bfzz-87ERnN-6EFaca-bdSLvn-9cvNcW-5973D7-79bfBe-6rtD7e-dAad1E-6EHfKt-7i1yKu-79bfwV-9VW5qD-dyDkRa-cwqwYL-9fLRVv-C3C52-fGRHZt-5RqkuT-89816h-dCGzj2-mt6Nyc-msVG4Q-osZRPh-bykxQY-5Wf4H4-6SLgjb-a7sM7)作者 [Marc Levin，](https://www.flickr.com/photos/mil8/) *授权于 **CC BY-SA 2.0** 。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>**