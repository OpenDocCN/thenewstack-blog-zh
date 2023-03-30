# Apache Arrow 的柱状数据布局可以加速 Hadoop、Spark

> 原文：<https://thenewstack.io/apache-arrow-designed-accelerate-hadoop-spark-columnar-layouts-data/>

上周，Apache Software Foundation 做了一个顶层项目，名为 [Arrow，是一个内存柱状层](https://blogs.apache.org/foundation/entry/the_apache_software_foundation_announces87)。在某些情况下，开源软件有望将分析处理和交换速度提高 100 倍以上。

最初由 Apache Drill 的代码播种， [Apache Arrow](http://arrow.apache.org/) 现在是一个跨 13 个其他开源项目的合作项目，包括 Drill、Cassandra、Hadoop 和 Spark，都参与了 Arrow 项目，这是说服 ASF 应该绕过孵化器期并立即被命名为顶级项目的一个因素。

在介绍 Arrow 时，该项目的副总裁 Jacques Nadeau 明确表示，它不是一个存储或执行引擎。他说，这是一项嵌入其他项目的技术。

“您可以将[Arrow]视为一种嵌入式加速器和在系统之间移动数据的方式，因此它被设计为执行引擎和存储系统的基础组件。现在，他们都在构建自己的东西来尝试解决这个问题，但是他们自己的东西是以行为中心的。他说:“我们正试图走到一起，以内存和分栏的方式实现这一点。

几个项目已经谈到这是他们接下来想要做的事情之一，项目负责人同意内存列是实现性能提升的方式，据 [Dremio](http://venturebeat.com/2015/09/25/apache-drill-gurus-at-dremio-raise-more-than-10m-from-redpoint-and-lightspeed/) 的首席技术官纳多说，这是 Apache Drill 背后的秘密创业公司。

“我们已经看到细分和多种技术试图相互竞争，这让用户感到困惑，”纳多说。

“Arrow 不会取代今天存在的任何东西。它也不是用户必须直接采用的技术。这种技术旨在增强他们已经使用的技术。

“他们最终首先应该得到的是改进的表现，这是每个人都关心的，”纳多说。“供应商说他们在内存和诸如此类的事情上有多棒。让这些引擎在内存中列引擎使他们[供应商]非常感兴趣。但是人们有所有这些选择，如果你想使用这些东西的多个版本，那会非常昂贵。如果你想在同一个生态系统中使用 Pandas、Spark 和 Drill，你会面临两个挑战:很难在这些系统之间移动数据，而这可以解决这个问题；第二个挑战是，这是专门设计的，所以你可以避免在内存中复制多个数据，”他解释道。

## **数据的单一表示**

“一种常见的情况是，您可能让业务分析师使用 Tableau 而不是 Drill，您可能让数据科学家使用 Pandas 之类的东西，实际情况是，所有这些应用程序都试图访问相同的数据。它们都必须将其加载到内存中，然后您必须为每个系统准备内存。但是使用 Arrow，你可以在内存中保存数据一种表示，这意味着你可以使用更少的硬件，或者在内存中保存更大的活动数据集。

“通常，没有人使用一种工具。不同的工具最适合不同的用例。通过能够在工具下使用单个内存层，您不必多次支付内存成本，”他说。

在许多工作负载中，70%到 80%的 CPU 周期都花在序列化和反序列化数据上。Arrow 解决了这个问题，它使数据能够在系统和进程之间共享，而无需序列化、反序列化或内存拷贝。

通过提供数据的规范列式内存表示，每种编程语言都可以直接与原始数据进行交互。

Apache Drill 基于 Drill 现有的 ValueVectors 技术，用 Java 库作为项目的种子，Pandas 和 Ibis 的创建者 Wes McKinney 正在贡献最初的 C/C++库。其他成员正在开发 Python 库。在几个月内，它应该可以用于 R、Javascript 和 Julia。

Drill、Impala、Kudu、Ibis 和 Spark 将在今年实现箭头功能，其他项目预计将紧随其后。

## **增强的互操作性**

所有开源大数据项目都必须处理现代多核进程的有效使用，包括最大限度地减少困扰应用程序的 L1 和 L2 缓存缺失；据由 Hadoop 和 Spark 驱动的关系数据库管理系统制造商 [Splice Machine](http://www.splicemachine.com/) 的联合创始人兼首席执行官 Monte Zweben 称，Arrow 试图将所有这些想法融合在一起。

“下一代处理器将对 SIMD ( *单指令，多数据*)提供更广泛的支持，这将提高并行性，不久我们将能够将所有数据存储在非易失性、字节可寻址 RAM 中。这意味着没有磁盘。因此，优化数据表示以从处理器中获得最大吞吐量将为许多工作负载带来巨大的性能提升，”他说。

根据基于 Python 的分析平台 [Continuum Analytics](https://www.continuum.io/?gclid=CjwKEAiAgKu2BRDu1OGw3-KXokwSJAB_Yy2QUbPRSk5OOOhwHVuq2yD5innmzfn44L_yzpQ3brRQ1RoCcanw_wcB) 的联合创始人兼首席技术官王蒙杰的说法，在商业计算领域，“大数据”的低级数据工程层由 Hadoop 和基于 Java 的 Apache 生态系统等项目主导，这些项目主要涉及传统的数据仓库和流处理需求，并通过简单地提供 SQL 查询接口来支持分析。

“Arrow 无疑为这个生态系统提供了一种新的能力，在这个生态系统中，高级模拟、优化和‘硬数学’实际上并不十分有效，”他说。“毫无疑问:这些需求不是少数或小众用例，而是机器学习、深度学习、图形分析等各个方面的核心。”

他说，大多数所谓的商业分析实际上只是“数东西”

“但是当的物理学家们需要分析来自碰撞黑洞的数据来验证爱因斯坦是否正确时，的物理学家们使用了 Python 语言，”王说。

“这样做的原因是因为 Python 在 C、C++和 FORTRAN 中的高性能低级算法上包装了令人愉快和高效的接口。这些非 Java 语言互操作性很好，因为它们可以无缝地在彼此之间传递控制，而不必复制或重新格式化千兆字节或兆兆字节的数据，”王说。

“几十年来，高级分析领域的口头禅一直是‘最大限度地减少数据移动’，其从业者对在 Hadoop 中来回复制的大量数据感到恐惧。这就是为什么 Java 和它的整个生态系统在数字计算领域是局外人——或者说充其量是二等公民，”他说。

“箭头完全正确！”他说。“它通过在数据堆栈的最低层构建高效、高度兼容的表示，解决了 Java 和 Hadoop 生态系统中的这一核心弱点。即使是像 Parquet 和 Avro 这样的 Hadoop 中较新的“高效”表示也不足以解决这个问题，因为最重要的属性不仅仅是 Hadoop 堆栈中的效率*,而是与非 Hadoop 软件生态系统的互操作性。”*

王表示，Arrow 应该为数据科学家在原生 Hadoop 数据上高效运行 Python 和 C 语言的高级算法打开大门。

“我个人对(在行业中)合作形成这些生态系统之间更完美的联盟感到非常兴奋，这些生态系统从一开始就应该合作得更好，”他说。

*专题图片* [箭头](https://www.flickr.com/photos/cogdog/11923908594/in/photolist-jaF9AW-dzAwE8-oY3cBA-5cqvMW-o8t6Z2-59ym4N-i2HQFu-e2Bnu4-6wE374-rYvxe1-9v71eS-4hV6B5-6q91Q5-eCYYDZ-dXTa1E-bxJDuJ-oH4Wvc-wBbVX-rMweCG-yWoS45-21zZP1-rq3JmW-rYyQZp-q9Y8Va-5w7uwS-82b4me-zUgQw1-zAo8ET-73ERwa-Ddmv-BR5bNa-dKxATo-BR5bPn-rq3Hk7-JKW7-9doGu-cfJhJ9-9H87CT-eWkaH3-ff6scs-crcV3U-oy1xLZ-7RApp3-82ebAf-dLxo5a-8iNBA-d7em6E-aYKQfc-7YGdt7-cUgWKE)由[艾伦·莱文](https://www.flickr.com/photos/cogdog/)、*授权于 ***CC BY-SA 2.0*** 。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>