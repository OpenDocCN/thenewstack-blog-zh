# Airflow，大数据的工作流编排器

> 原文：<https://thenewstack.io/airflow-a-workflow-orchestrator-for-big-data/>

Apache Software Foundation 的最新顶级项目 [Airflow](https://airflow.apache.org/index.html) ，即用于大数据处理管道的工作流自动化和调度 stem，已经在[的 200 多家组织](https://github.com/apache/airflow#who-uses-apache-airflow)中使用，包括 Adobe、Airbnb、Paypal、Square、Twitter 和 United Airlines。

“Apache Airflow 已经迅速成为工作流程编排的事实标准，”Apache Airflow 副总裁[博尔克·德·布鲁因](https://www.linkedin.com/in/bolke/?originalSubdomain=nl)说。“Airflow 已经获得了开发人员和数据科学家的认可，这得益于它对代码配置的关注。”

根据该项目的 [GitHub 页面](https://github.com/apache/airflow)，当工作流被定义为代码时，它们变得更易于维护、版本化、可测试和协作。Airflow 提供智能调度、数据库和依赖性管理、错误处理和日志记录。它吹捧命令行实用程序用于在 Dag 上执行复杂的手术，以及用户界面用于提供对生产中运行的管道的可见性，从而易于监控进度和解决问题。

2014 年，Maxime Beauchemin 在 Airbnb 创造了气流。2016 年 3 月进入 ASF 孵化器。它被设计成动态的、可扩展的、精简的和显式的，并且可扩展以处理数百 Pb 的流水线。

借助 Airflow，用户可以将工作流创建为有向无环图(Dag ),以自动化脚本来执行任务。虽然基于 Python，但它也可以执行其他语言的程序。Airflow scheduler 在遵循指定依赖关系的同时对一组工作线程执行任务。

DAG 运算符定义要执行的单个任务，但也可以创建自定义运算符。

三种主要类型的运算符是:

*   那些执行一个**动作**，或者告诉另一个系统执行一个动作的
*   **转移**将数据从一个系统转移到另一个系统的操作符
*   **传感器**保持运行，直到满足某个标准，例如特定文件到达 HDFS，Hive 中出现分区，或一天中的特定时间。

在对这项技术的介绍中， [Clover Health](https://www.cloverhealth.com/en/) 的高级软件工程师[马特·戴维斯](https://www.linkedin.com/in/jiffyclub/)解释说，它可以让多系统工作流程在任意数量的员工之间并行执行。单个管道可能包含 bash、Python 和 SQL 操作。通过指定任务之间的依赖关系，Airflow 知道哪些任务可以并行运行，哪些任务必须在其他任务之后运行。

[https://www.youtube.com/embed/cHATHSB_450?feature=oembed](https://www.youtube.com/embed/cHATHSB_450?feature=oembed)

视频

它能够在 Python 之外的语言中工作，这使得它可以很容易地与其他系统集成，包括 AWS S3、Docker、Apache Hadoop HDFS、Apache Hive、Kubernetes、MySQL、Postgres、Apache Zeppelin 等。

“Airflow 是我们在过去两年中创建的所有数据管道的一部分，充当着领班的角色，驯服了我们的机器学习和 ETL 管道。它帮助我们为客户的整个数据生态系统创建了单一视图。Data Reply 的数据工程师卡西尔·纳伊克说:“Airflow 的数据感知调度和错误处理有助于在没有任何人工干预的情况下可靠地自动化整个报告生成过程。”他指出，其配置即代码的范式使非技术人员可以轻松使用，而无需陡峭的学习曲线。

然而，文件指出，气流不是像[火花流](http://spark.apache.org/streaming/)或[风暴](https://storm.apache.org/)那样的数据流解决方案。更堪比 [Oozie](http://oozie.apache.org/) 、[阿兹卡班](http://data.linkedin.com/opensource/azkaban)、[弹球](https://github.com/pinterest/pinball)，或者[路易吉](https://www.astronomer.io/guides/airflow-vs-luigi/)。

工作流通常是静态的或缓慢变化的。从一次运行到下一次运行，它们应该看起来相似——比数据库结构稍微更动态一些。

它自带一个 SQLite 数据库，可以帮助用户快速启动并运行，提供 UI 和命令行实用程序之旅。

innerspring 经理 Sumit Maheshwari 说:“在 qu bole，我们不仅是气流的提供者，也是气流的大消费者。Qubole 提供气流管理服务。

该公司的“洞察力和建议”平台是围绕气流建立的。它每月处理来自数百家企业的数十亿个事件，并生成对 Apache Hadoop、Apache Spark 和 Presto 等大数据系统的见解。

“我们对气流的简单性印象深刻，它可以轻松地与云、监控系统或各种数据源等其他解决方案集成。”

辛辛那提的[天文学家](https://www.astronomer.io/)在气流上建造了它的平台。此外，谷歌在去年 5 月推出了测试版的[云合成器](https://cloud.google.com/composer)，这是一项管理气流的服务。亚马逊已经将其托管机器学习工作流服务 [Sagemaker](https://aws.amazon.com/about-aws/whats-new/2018/11/amazon-sagemaker-is-now-integrated-with-apache-airflow/) 与 Airflow 整合在一起。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>