# TileDB:多维度管理大数据存储

> 原文：<https://thenewstack.io/tiledb-managing-big-data-storage-in-multiple-dimensions/>

世界上的数据越来越不适合关系数据库的行和列。例如，基因组和地理空间数据涉及以二维或三维表示的大规模数据集。多维数据存储经理 [TileDB](https://tiledb.io/) 的首席执行官 [Stavros Papadopoulos](https://github.com/stavrospapadopoulos) 说:“随着应用程序的增长，你必须重新考虑存储管理，因为不是所有的数据都适合内存。

他将 TileDB 描述为一个使用熟悉的接口在任何后端存储多维数据的库。

“如果您有一个侧重于可视化的花哨的地理空间应用程序，您不必创建自己的存储管理器；它可以非常有效地在你的笔记本电脑上存储三维物体……S3 或 Azure。所有的复杂性都消失了。你可以发挥创造力，在上面构建自己的应用程序，或者在上面进行分析。…所有的神奇都发生在幕后。”

TileDB 可以处理密集和稀疏数组。他解释说，多维数据的格式与关系数据库中的格式非常不同。

在密集阵列中，例如照片，由多个单元或像素组成的阵列，例如，每个单元或像素包含关于其位置以及其中红、蓝和绿的数量的信息。另一方面，在稀疏阵列中，例如点云，许多单元不包含任何信息。它们不能像密集阵列一样对待。

他说，使用多维数组的关系数据库会带来巨大的存储和计算成本，而如果能够以其原生格式检索这些数据，则可以获得巨大的收益。

数组用于机器学习中的分析堆栈，涉及线性代数，处理矩阵、二维数组。线性代数的高性能计算库期望数据是这种二维格式。他说，所以用原生数组格式服务这些库会使事情变得快得多。

它不是像 MySQL 或 SQL server 那样的数据库。它本质上是一个库，可以嵌入到数据科学家的程序中。Tiledb 与他们使用的语言(如 Python 或 R)接口，并支持多个存储后端，如符合 HDFS 或 S3 标准的对象存储，如 AWS S3、minio 或 Ceph。你的数据可能在一个超级计算设施中，在那里你有一个分布式文件系统，其中多台机器存储你的数据，或者在云中——AWS、Azure 或 Google Cloud。

“对于这个库来说，非常重要的是要非常有效地与所有这些后端集成，这样用户就不必考虑这些了。在 TileDB 中，所有这些细节都是抽象的，”帕帕多普洛斯说。

## 分支

去年，马萨诸塞州剑桥。基于的 TileDB 是由英特尔实验室和麻省理工学院之间的大数据合作剥离出来的。它在 10 月宣布了由英特尔投资和 Nexus Venture Partners 牵头的 100 万美元种子资金。

[橡树岭国家实验室的首席数据架构师 Edmon Begoli](https://www.ornl.gov/staff-profile/edmon-begoli) 当时说:“我认为 TileDB 是我多年来见过的最复杂、写得最好的高性能科学数据管理解决方案之一。”

TileDB 早些时候与布罗德研究所合作创建了一个名为 [GenomicsDB](https://github.com/Intel-HLS/GenomicsDB) 的 TileDB 版本。布罗德研究所存储了万亿字节的基因组数据，这些数据被建模为一个巨大的稀疏 2D 阵列。

[https://www.youtube.com/embed/ZDSt9fjPsSE?start=556&feature=oembed](https://www.youtube.com/embed/ZDSt9fjPsSE?start=556&feature=oembed)

视频

在一篇[研究论文](https://people.csail.mit.edu/stavrosp/papers/vldb2017/VLDB17_TileDB.pdf)中，它宣称比 [HDF5](https://support.hdfgroup.org/HDF5/) 密集阵列存储管理器、具有密集和稀疏阵列的 [SciDB](https://ercim-news.ercim.eu/en89/special/scidb-an-open-source-dbms-for-scientific-data) 阵列数据库系统以及用于密集阵列的 [Vertica](https://www.vertica.com/) 关系列存储更快，并且至少与稀疏阵列一样快。

TileDB 中的数组在物理上存储为底层文件系统中的一个目录。

它的核心思想是将数组元素组织成有序的集合，称为片段。每个片段是密集的或稀疏的，它将相关的数组元素分组为固定容量的规则大小的块，称为数据块。一起访问的单元共同位于磁盘和内存中，以最大限度地减少磁盘寻道、页面读取和缓存缺失。

该组织将随机写入转变为顺序写入，并通过自己的算法提高读取效率。

应用程序的需求决定了全局单元格顺序的选择:例如，如果应用程序一次读取一行数据，那么数据应该按行布局，而不是按列布局。

在稀疏阵列中，用户指定数据切片容量，然后创建数据切片，使它们都具有相同数量的非空像元，与容量相等。

写入是成批执行的，这提高了性能，并且每一批都按顺序写入一个单独的片段。即使在密集阵列中，稀疏碎片也可用于加速随机写入。

TileDB 读取算法更有效地找到最近更新的片段，并在片段的一部分被较新的片段完全覆盖时避免不必要的瓦片读取。随着碎片数量的增加，性能会下降，因此整合算法会在后台运行，而其他并发读取和写入会继续进行。

帕帕多普洛斯说，根据数据的性质，每个数据块或数据块都使用多种不同的压缩器进行压缩，从而降低了存储成本。

这是一个 C++库，提供 C、C++和 Python 语言的 API。R、Java 和其他语言的 API 正在开发中。

“[他们]试图提出一个 Python 解决方案，而 R 世界也试图提出一个 R 解决方案。我们要说的是，我们应该做一个通用的解决方案来解决所有的细节——为你、为 Python、为 R、为 Java 准备一个 API。你不必担心这一点，只需使用我们，你就可以在此基础上构建自己的快速分析，”帕帕多普洛斯说。

除了基因组学方面的工作，TileDB 正在寻求扩展到其他领域，如 [Lidar](https://oceanservice.noaa.gov/facts/lidar.html) 数据——空间中的三维点——和时间序列数据，大量用于金融服务。

到目前为止，这一切都还是[开源](https://github.com/Intel-HLS/TileDB)。帕帕多普洛斯说，TileDB 公司正致力于建立一个企业就绪的商业产品，其时间取决于其下一轮融资。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>