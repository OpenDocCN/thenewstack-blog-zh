# 雪花交付了一批开发者的好东西

> 原文：<https://thenewstack.io/snowflake-delivers-bevy-of-developer-goodies/>

在今天于旧金山和网上举行的 2022 年 Snowday】活动上，雪花宣布了其云数据仓库平台的一系列酷开发功能。几个更大的公告是专门针对 [Python](https://www.python.org/) 开发者的，并且很好地搭载了今年 3 月雪花收购 [Streamlit](https://streamlit.io/) 的计划。但是 SQL 开发人员也得到了一些好东西，所有公布的特性都增强了开发人员在分析领域的实力和参与度。

[雪花产品管理总监 Torsten Grabs](https://www.linkedin.com/in/torstengrabs/) 对这一系列大获成功的公告感到非常自豪，他解释说，雪花“……在雪花的统一平台下，为构建者提供他们所需的数据访问和工具，以安全地加快他们的创新步伐。”Grabs 还简要介绍了新堆栈的这些特性，并带我们一个一个地了解它们。

## Python 诱惑

首先，Snowflake 正在向大众发布其用于 Python API 的 [Snowpark](https://docs.snowflake.com/en/developer-guide/snowpark/index.html) 。这是一件大事，因为它为似乎是世界上最受欢迎的编程语言提供了客户端和服务器端的编码解决方案，尤其是在分析和数据科学领域。Snowpark 允许开发人员编写命令式数据管道、客户端应用程序、存储过程、用户定义函数(UDF)和用户定义表函数(UDTFs)。

Snowpark 功能以前适用于用 SQL、 [Scala](https://scala-lang.org/) 和 Java 编写的代码，但今天的公告将 [Python](https://thenewstack.io/guido-van-rossums-ambitious-plans-for-improving-python-performance/) 置于这些语言的 GA 基础上。Python 开发人员非常喜欢使用 DataFrames，这种类似光标的数据结构可以让您遍历结果集，并逐行读取或操作其中的数据。而 Snowpark for Python 允许他们随心所欲地这样做，但以一种优化的方式提供了类型检查，并使用一种称为延迟执行的技术最大限度地减少了服务器往返。

UDF 代码在雪花集群上执行，即使是在客户端运行的代码，Snowpark 也支持下推操作，因此许多繁重的工作仍然委托给雪花。为了应对这样的工作负载，雪花有另一个功能，称为 Snowpark 优化仓库，今天宣布了一个公共预览(基于 AWS 的雪花集群)。

随着 Snowflake 致力于将 Streamlit 完全集成到 Snowflake cloud 中，更多 Python 的优点正在路上。它将允许成熟的应用程序托管在雪花上，并在其安全上下文中执行，尤其适用于[机器学习(ML)](https://thenewstack.io/google-adds-machine-learning-modeling-to-bigquery/) 应用程序。这一计划在 6 月份雪花宣布其[原生应用框架](https://www.snowflake.com/blog/introducing-snowflake-native-application-framework/)时首次宣布。它仍在开发中，但雪花官员告诉新的堆栈，该功能的私人预览将很快推出。

**又读:** [**雪花构建出它的数据云**](https://thenewstack.io/snowflake-builds-out-its-data-cloud/)

## 声明性、物化和动态

与 Python 不同， [SQL](https://thenewstack.io/sql-is-dead-right/) 是一种声明式语言。SQL 让开发人员用一个冗长的命令来描述和操作整个数据集，而不是强制地一行一行地做事情。因此，除了典型的 CRUD(创建、读取、更新和删除)操作之外，它还是处理各种数据的绝佳范例。这就是为什么雪花已经使用 SQL 创建了一个声明性的流数据管道功能。该特性最初被命名为物化表，但现在以动态表的形式在公共预览版中推出。

基于 SQL 的声明性管道并不新鲜，但是在动态表的情况下，它们不仅使管道更加简单，而且使处理流数据更加容易。通过在数据流上创建类似表格的抽象，并通过 SQL 读取和处理它们，不是流数据专家的开发人员仍然可以使用他们熟悉的范式，以精确的方式处理这些数据。为了更具体地了解这一切是如何工作的，Snowflake 制作了一个关于该功能的非常好的视频[和一个代码样本，你可能想看看——它只有三分多钟长。顺便说一下，Python 的动态表和 Snowpark 并不互相排斥。这两个特性可以一起使用，这为使用 ML 模型实现实时预测创造了有趣的可能性。](https://www.youtube.com/watch?v=7oLnlgWxa0o)

## 可观察性预览

说到管道，创作它们是一回事，管理它们又是另一回事。由于管道是在无人值守的基础上运行的，所以事情可能会出错，有时很难检测和解决这些异常。考虑到这一点，雪花正在推出一系列围绕管道[可观察性](https://thenewstack.io/observability-a-3-year-retrospective/)的功能。其中一个功能现在在公共预览中推出，为数据流、控制流和任务历史提供基于可视化的监控界面，以帮助开发人员和 DevOps 人员确保管道的健康运行。可观察性还包括警报、日志记录和事件跟踪，所有这些都在私有预览中启动。

Snowday 活动还带来了其他公告，围绕“[由雪花](https://www.snowflake.com/en/data-cloud/powered-by-snowflake/)驱动”计划、合作伙伴投资和与合作伙伴的联合解决方案，以及跨云数据治理和业务连续性。但是我们已经在这里广泛地介绍了开发人员的优点，而且还有很多。我们知道雪花想要建立更大的生态系统，该公司似乎非常明白，吸引和授权开发人员是实现生态系统增长的关键。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>