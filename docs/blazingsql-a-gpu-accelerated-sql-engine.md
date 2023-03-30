# BlazingSQL:一个 GPU 加速的 SQL 引擎

> 原文：<https://thenewstack.io/blazingsql-a-gpu-accelerated-sql-engine/>

Rodrigo Aramburu 在为秘鲁政府的一个项目工作时，构建了他的第一个 GPU 加速 SQL 引擎版本。

他的哥哥费利佩和其他几个人开办了自己的咨询公司。他们正在为秘鲁公共养老金管理局开发一种欺诈检测算法，有点像美国的社会保障管理局。

它涉及 40 年的纸质历史数据，1500 万参与者提交了他们整个历史的双周工资单存根。一个由 100 名分析师组成的团队正在验证这一点，他们正在将这些记录数字化到一个新系统中。

“在秘鲁政治中，每次新政府上台，前任政府所做的一切都会被抹去。“实际上有 14 个不同的系统，”Aramburu 说，并补充说，“这有点像一场噩梦。”

仅仅通过尝试将所有这些不同的遗留系统中的表连接在一起，他们就会遇到瓶颈，因为没有办法唯一地标识参与者。

“如果我在寻找我自己，并且我生活在其中的七个系统中，我将不得不关联各种不同的数据点，以找出我实际上是否是同一个人，”他说。

所以这个巨大的连接花了大约 35 个小时来处理。它的数据量超过了 1tb。

“我们从未使用过这种规模的产品，所以当时我们不一定使用最好的工具。所以我们尝试用 GPU(图形处理器)来完成连接。这让我们明白了这个耗时 35 小时的查询——在 GPU 上，只需 30 秒钟，”他说。“当时我们说，‘我的天啊！我想我们刚刚发现了非常酷的东西。"

一年后，他们的项目被一个加速器项目接受，Aramburu 决定全力投入这个项目。

2017 年，他们开始积极与英伟达合作，并意识到他们希望为 GPU 加速的数据科学创建一个生态系统，现在称为 [RAPIDS.ai](https://rapids.ai/) 。这是一套完全在 GPU 上执行数据科学和分析管道的软件库和 API。

该公司现已发展到 15 人，总部设在旧金山，开发中心设在秘鲁利马。

BlazingSQL 最近在 Apache 2 许可下作为一个[开源项目](https://github.com/BlazingDB)发布。

### 查询原始数据

最初是一个名为 BlazingDB 的完整数据库管理系统，现在它已经改名为 BlazingSQL，专注于作为一个 GPU 加速的 SQL 引擎。

它建立在 [Apache Arrow](https://thenewstack.io/apache-arrow-designed-accelerate-hadoop-spark-columnar-layouts-data/) 的基础上，这是一个跨 13 个其他开源项目的合作，包括 Drill、Cassandra、Hadoop 和 Spark，它为平面和分层数据指定了一个标准化的语言独立的列内存格式。

它基本上是列数据如何在内存中生存的标准。通过遵守这个标准，它可以以一种非常高性能的方式接收任何其他人的列数据。

“在 Apache Arrow 之前，如果 Blazing 产生了结果，而我想把它交给其他东西，那东西就必须逐行读取我的结果，对其进行解释和解析，并转化为该工具可用的东西，”Aramburu 说。

“对于 Apache Arrow，因为我说这是一个 Apache Arrow 数据帧，所以它说我知道那是什么。它已经是我理解的格式了。我不需要一行一行的读。…现在我可以继续前进了。”

它能够从数据湖中查询原始数据——不需要模式——使用 [GPU DataFrame (GDF)将数据直接加载到 GPU 内存中。](https://blog.blazingdb.com/blazingsql-part-1-the-gpu-dataframe-gdf-and-cudf-in-rapids-ai-96ec15102240)

BlazingSQL 的核心是 [GPU 数据帧](https://blog.blazingdb.com/blazingsql-part-1-the-gpu-dataframe-gdf-and-cudf-in-rapids-ai-96ec15102240) (GDF)内存模型和 [cuDF](https://github.com/rapidsai/cudf) 的 C++ API 中的数据处理函数。它是专注于数据准备的 RAPIDS AI 库，包含 Pandas、Numpy 或 SQL 用户熟悉的功能。它与 Dask 集成，Dask 使用 Python APIs 和数据结构来轻松地在 Numpy、Pandas、Scikit-learn 和 Dask-powered 之间切换。

“创建这个数据框架，生态系统的其余部分就可以获得它，做它想做的任何事情，”他说。“我们可以在 GPU 内存中的这些数据帧上运行 SQL 查询，这使它们运行得非常快。”

在使用英伟达[T4 GPU](https://www.nvidia.com/en-us/data-center/tesla-t4/)的谷歌云平台[对比](https://blog.blazingdb.com/blazingsql-the-gpu-sql-engine-now-runs-over-20x-faster-than-apache-spark-1b0bffc990a9)中，它宣称速度比 Apache Spark 快 20 倍以上。

“通过在 GPU 上利用 Apache Arrow 并与 Dask 集成，BlazingSQL 将扩展开源功能，并在加速的数据科学生态系统中推动下一波互操作性，”NVIDIA 数据科学总经理 Josh Patterson 在开源声明中表示。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>