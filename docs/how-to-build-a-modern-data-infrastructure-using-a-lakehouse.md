# 如何使用湖边小屋构建现代数据基础设施

> 原文：<https://thenewstack.io/how-to-build-a-modern-data-infrastructure-using-a-lakehouse/>

数据仍然是小型和大型企业最重要的资产和转型驱动因素之一。然而，企业正在努力应对不断增长的[数据](https://thenewstack.io/category/data/)，这使得他们很难使用现有的数据湖和数据仓库架构进行操作和管理。

IT 和企业需要一种更好的方法来实现他们的数据平台战略，以便架构师和工程师可以花更少的时间来担心管道问题(集成不同的组件，使它们能够相互交流),并将更多的时间用于构建数据解决方案。

如果您的组织真的想要实现数据管理的现代化，您将需要一个能够帮助您实现这一目标的架构。我们都听说过最近关于湖边小屋的传言，但我们是怎么来到这里的呢？

## 数据仓库与数据湖

 [Purushottam Darshankar

Purushottam Darshankar 是位于英国伦敦的 Persistent Systems 的首席数据架构师。他拥有超过 25 年的 IT 经验，负责银行、金融服务、医疗保健、零售和公用事业领域的大数据解决方案的设计、架构和交付。在进入 Persistent Systems 之前，Purushottam 曾服务于 Wipro、西门子和 Reliance Communication 等领先的跨国公司。他获得了政府颁发的电气工程硕士学位。浦那工程学院，IIM 加尔各答管理研究。](https://www.linkedin.com/in/purushottam-darshankar-311502b7/?originalSubdomain=uk) 

在数据管理技术取得最新进展之前，数据仓库是存储和处理业务数据的体系结构标准。虽然数据仓库对于结构化数据来说非常可靠，但随着非结构化数据的引入，平台架构开始动摇。

此外，对于数据仓库模型，在您可以运行数据分析之前，有许多数据准备和 ETL 形式的数据移动(提取、传输和加载),因此洞察时间通常非常慢。

作为一种解决方案，企业开始构建数据湖，这是一种以开放文件格式存储任何类型的结构化或非结构化原始数据的低成本存储库，以便以后可以转换它来处理不同的业务用例。

与实施表模式的数据仓库不同，数据湖不实施模式，因此允许存储不熟悉的数据源，包括视频、文本文件、图像、音频等。虽然数据湖是一种有前途的策略，但由于数据治理不当，很快就出现了“数据沼泽”，即杂乱无章的数据，导致数据湖中出现陈旧、未使用的数据。

那么，组织如何才能同时获得数据仓库和数据湖的好处呢？

## 一种组合方法—数据湖库

由于数据仓库和数据湖都有好处，企业提出了一种新的[数据管理](https://www.analytics8.com/services/data-management/)架构模式——一种将数据湖的低成本、可伸缩性和灵活性与数据仓库的数据管理和数据结构相结合的湖屋。

将存储和计算分开可以以较低的成本提高可用性和可扩展性。该计算使用独立的集群，并且可以根据工作负载的类型独立扩展。

Lakehouses 支持 ACID(原子性、一致性、隔离性和持久性)事务，这确保了数据可靠性和数据完整性，以防出现故障或不同组件执行并发操作。

他们还实施模式标准和应用治理，确保数据仓库中的数据得到适当的组织、治理和保持一致。

lakehouses 允许 BI(商业智能)工具直接访问数据，这提高了用于实时报告的数据的新鲜度。

一个强大的现代企业数据架构集成了一个数据湖、一个使用 lakehouse 方法的数据仓库和其他专门构建的功能，以实现统一的数据治理和无缝的数据移动。

在过去的几年里，虽然核心数据处理系统基本保持不变，但支持工具和平台却迅速增加。单个工具和技术的正确组合应该能够为您的业务构建正确的现代数据平台。

## 现代云参考架构

由 lakehouse 支持的现代企业数据架构提供了可访问性、速度、灵活性和可靠性，因此企业可以优化每一个数据源，并将其用于更好的业务决策。现在您已经有了一个数据仓库，您仍然需要大量的支持服务。

想象一个真实的湖边小屋(比如 Airbnb 度假屋)。湖边小屋为游客提供了绝佳的视野，但仍然需要垃圾清理、清洁和维护、景观美化、安全服务等配套服务。对于数据仓库来说，当前的平台生态系统具有一系列特征，下面列出了一些重要的特征。

### 自动化工作流和流程编排

借助云上的自动化工作流和流程编排，企业可以确保数据顺畅、自由地流向组织的各个部分，同时保持数据质量和治理。

诸如[气流](https://airflow.apache.org/) / [天文学家](https://www.astronomer.io/)、[长官](https://www.prefect.io/)和[达格斯特](https://dagster.io/)等供应商提供工具来编排分析和操作工作流。

### 数据管道和 ELT 处理

这是云数据平台的核心，它保证数据以正确的格式准确、按时到达目的地。

它已经从传统的 ETL(提取、转换和加载)供应商发展成为一种新的云原生玩家(例如， [Fivetran](https://fivetran.com/) 、 [dbt](https://www.getdbt.com/) 和 [Matillion](https://www.matillion.com/) )，能够处理不同数据环境之间更复杂的依赖关系。

### 人工智能和机器学习

这包括应用 ML 和算法建模来优化业务决策的高级分析。这个领域正在蓬勃发展，这从支持它的供应商数量的增加可以明显看出。

[PyTorch](https://pytorch.org/) 、 [TensorFlow](https://www.tensorflow.org/) 、 [Rasa](https://rasa.com/) 等库为数据科学家训练数据模型提供 AI/ML 算法，而 [Jupyter](https://jupyter.org/) 和 [Zeppelin](https://zeppelin.apache.org/) 等笔记本则帮助他们定制 AI/ML 算法。

### 数据治理和安全性

随着数据堆栈变得越来越复杂，数据治理和安全性对于在整个数据生命周期中保护数据和保持合规性变得越来越重要。根据严格的数据安全准则，数据访问需要受控的数据访问和授权机制。

GDPR(通用数据保护条例)和 HIPPA(健康保险便携性和责任)条例等法律法规已由政府强制执行，以保护 PII(个人身份信息)。

像 [OneTrust](https://www.onetrust.com/) 、 [Collibra](https://www.collibra.com/) 、 [Privacera](https://privacera.com/) 和 [Immuta](https://www.immuta.com/) 这样的供应商正在帮助企业解决他们在监管下的部分安全需求。

### 数据可观察性

数据可观察性是数据平台功能列表中的新成员，指的是在整个数据流中提供监控和诊断功能。

这些工具([蒙特卡洛](https://www.montecarlodata.com/)、[远大前程](https://greatexpectations.io/)和[大眼](https://www.bigeye.com/))提供自动监控、警报和分类，以识别和评估数据质量和可发现性问题。

总之，人们对建立在 lakehouse 基础之上的现代数据架构越来越感兴趣，也越来越清晰，它得到了众多供应商的支持(包括[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)、[谷歌](https://cloud.google.com/)、 [Azure](https://azure.microsoft.com/) 、 [Starburst](https://www.starburst.io/) 、 [Databricks](https://www.databricks.com/) 等)。)和数据仓库玩家。

像 [Snowflake](https://www.snowflake.com/) 这样的云数据仓库发展迅速，主要集中在 SQL 用户和 BI 用例上。但是企业已经看到其他技术的加速采用，比如由 [Databricks](https://www.databricks.com/) 提供的数据湖库。

借助数据环境现代化产品， [Persistent Systems](https://www.persistent.com/) 帮助企业在云环境中实现数据环境现代化。

当然，选择 lakehouse 方法只是工作的一小部分。具有优化的数据处理流程的良好数据模型是数据平台性能和成本优化的必要条件。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>