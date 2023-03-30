# 在物联网领域开始成功职业生涯需要掌握的 5 项技能

> 原文：<https://thenewstack.io/5-skills-you-need-to-master-to-start-a-successful-career-in-iot/>

据 Gartner 预测，到 2020 年将会有 200 亿台物联网设备。如此激烈的物联网化将需要具备相关技能的物联网开发人员的才能来为这些设备提供功能软件。因此，如果你正在考虑开始物联网工程师的职业生涯，但不确定你应该磨练什么技术技能，请继续阅读——在本文中，我们收集了物联网市场上非常需要并将继续需要的顶级技能。

## 物联网架构的各层以及如何实现它们

物联网系统的复杂性决定了开发所需技能的多样性。与[典型物联网架构](https://www.scnsoft.com/blog/iot-architecture-in-a-nutshell-and-how-it-works)的层数相对应，有五个关键专业领域:

### 1.嵌入式软件开发

 [鲍里斯·希克洛

ScienceSoft 首席技术官鲍里斯·希克洛(Boris Shiklo)负责公司的长期技术愿景和创新战略。在他的管理下，该公司的开发团队成功完成了超过 80，000 工时的复杂项目，涉及医疗保健、银行和金融、零售、电信、公共部门和其他领域。Boris Shiklo 在 IT 咨询、软件开发、项目管理和战略规划方面拥有坚实的背景。](https://www.linkedin.com/in/boris-shiklo-1a323a1/) 

端点物联网设备结合了硬件和软件组件。随着处理器被集成到从烤面包机到工业机器的所有东西中，对嵌入式软件开发者的需求越来越大。工程师应该能够创建一个嵌入式软件，处理不可靠的数据(考虑[传感器漂移](https://www.solinst.com/products/dataloggers-and-telemetry/3001-levelogger-series/technical-bulletins/understanding-pressure-sensor-drift.php))，并在不受控制的物理环境中正确工作。

由于物联网设备通常计算资源有限，嵌入式软件开发的首选语言是 c 语言。它是轻量级的，不需要太多的处理能力，确保快速的性能，适合编写底层代码。

然而，由于 C 不具备面向对象的能力，C++通常被用作它的预处理程序。最近，其他语言，如 Java SE Embedded、Java ME Embedded，越来越受嵌入式工程师的欢迎。

嵌入式软件开发的另一项重要资产是 GPIO(通用输入输出)和 I2C(Inter-Integrated Circuit-读作 I-squared-C)接口的经验，这些接口用于在微控制器和连接的设备之间建立通信。

### 2.现场网关

现场网关充当物联网设备和物联网系统的云部分之间的链接。他们的任务是从连接的设备中获取数据，过滤并预处理这些数据，然后将其发送到云端进行进一步处理和存储。运行在现场网关上的代码通常是用 C 或 C++编写的。

### 3.数据管理

物联网公司公开招聘具有云计算技术工作经验的专业人士，他们可以设计、实施和维护可靠、可扩展的数据管理解决方案，以处理大量的流物联网数据。为了构建这一层，工程师应该能够执行的任务包括:

物联网设备会产生海量数据。在数据摄取阶段，数据被划分优先级并进行分类，这使得它能够顺利地流向物联网系统的后续组件:流数据处理器和数据湖。数据摄取通常使用 Azure Event Hubs、Apache Kafka 和 Amazon Kinesis 等工具来执行，这些工具需要 Java、Python 和. NET 的知识。

数据流组件允许在传入的数据记录到达时对其进行处理，并立即采取相应的输出操作。数据流是在 Azure Stream Analytics(使用类似 SQL 的查询语言)和 Spark Streaming(支持 Java、SCALA 和 Python)等工具的帮助下进行的。

数据存储组件处理数据的存储和组织。物联网的数据存储通常使用开源框架来实现，如 HDFS(支持 Java、SCALA 和 Python)、Apache Cassandra (Java 和 Python)和 Apache HBbase (Java)。

### 4.数据分析

数据分析技能非常受欢迎。雇主寻找在实施数据分析应用程序方面有经验的工程师，他们知道如何可视化通过分析物联网数据获得的见解。物联网工程师在这一级别应该能够执行的典型任务包括:

*   **批量并行处理**

批处理是指处理已经存储了一段时间的数据块，例如，在一个班次结束时处理设备利用率数据。Apache Hadoop 是批处理最常用的框架。它使用 MapReduce 编程模型，该模型为工程师提供了一个基于 Java 的编程接口。

*   **处理复杂事件**

复杂事件处理有助于聚合许多不同的数据记录(事件)，并实时建立它们之间的因果关系。从事件到达数据库到它被处理的时间通常不超过几毫秒。处理复杂事件最常用的工具是 Apache Spark Streaming。你可以选择用 Scala 或者 Java 编写 Spark 流程序。

*   **实现机器学习**

机器学习算法应用于实时或历史数据，以识别数据中的模式和异常，并基于识别的相关性自主做出决策。机器学习技能的需求在 2018 年经历了 [220%的增长](https://www.mondo.com/blog-in-demand-iot-skills-2017-2018/)，在物联网技能需求中名列前茅。常用于实现机器学习并且值得掌握的关键语言包括 Python、Java 和 r。

数据可视化是物联网的一个组成部分。它有助于以一种易于理解的形式呈现通过数据分析获得的见解。Python(及其库 Seaborn、Bokeh 和 Pygal)被认为是一种流行的数据可视化语言。它用于各种可视化任务，包括流数据的可视化。对于快速、特殊的可视化，也可以使用 r。

### 5.网络和移动用户应用

网络和移动应用允许用户与物联网系统进行交互，例如，查看从物联网数据分析中获得的见解，监控物联网设备并向其发送命令。物联网中使用的 web 和移动用户应用程序在功能上很像其他 web 和移动应用程序；这一级别的物联网特异性较低。

**网络应用**

web 应用程序的后端是使用 Java、.NET 和 PHP。前端 web 应用开发需要 HTML、CSS、JavaScript (Angular、React、Backbone、Meteor 等)的知识。).

**手机应用**

许多物联网应用都是通过智能手机来控制的。在这方面，开发人员被期望创建高性能和用户友好的**原生** (iOS、Android、Windows Phone)和**跨平台** (Cordova、Xamarin)移动应用，这些应用将可靠地与云服务器和外部硬件通信。

## 概括一下

正如你可能已经意识到的，物联网是多语言的——它使用多种编程语言，并且需要一系列框架的经验。然而，物联网工程师不一定是多面手。能够在物联网架构的一层工作已经足以在物联网领域开始成功的职业生涯。下面简单回顾一下你可以选择磨练哪些技能: [![](img/82c3a7fab3a4e10a6e9a740058fcd6d8.png)](https://cdn.thenewstack.io/media/2019/06/8c94acf8-developer-4027337_1280.png)

*   对于开发终端物联网设备的嵌入式软件，开始掌握 C 和 C++。
*   对于云开发，专注于:
    *   获得设计、实施和维护数据管理解决方案的经验。为此，精通 Java 是必须的。
    *   掌握流和批处理。习惯使用 Azure Stream Analytics、Spark Streaming 和 Apache Hadoop (Java、SCALA 和 Python)等框架。
    *   通过实施机器学习和可视化这些见解，学习如何从大数据中提取见解。流行的语言是 Python 和 r。
*   对于用户应用程序开发，学习如何开发高性能的用户友好的 web (Java，。Net，或者后端用 PHP 用于前端的 HTML、CSS 和 JavaScript)和移动(本地和跨平台)应用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>