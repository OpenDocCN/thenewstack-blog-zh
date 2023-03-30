# AWS 为数据头、云原生安全性提供工具

> 原文：<https://thenewstack.io/aws-serves-up-tools-for-data-heads-cloud-native-security/>

AWS 已经为开发人员、数据分析师、安全专家、DevOps 从业者和其他人提供了一系列新工具和产品及服务预览，正如本周在拉斯维加斯举行的年度 [re:Invent](https://reinvent.awsevents.com/) 会议上的典型做法。

在两个多小时的主题演讲中，AWS 首席执行官[亚当·塞利普斯基](https://www.linkedin.com/in/adamselipsky/)以令人眼花缭乱的速度宣布了几乎每个专业的新 AWS 技术。例如，对于数据头，Selipsky 宣布了新产品，将亚马逊网络服务(AWS)推上了交付“零 ETL[提取、转换、加载]未来”的道路，他说的话赢得了观众的热烈掌声。

## 零 ETL

“这是我们的愿景，我们称之为零 ETL 的未来，在这个未来，数据集成不再是手工操作，”Selipsky 说。

客户花费最多时间构建和管理 [ETL](https://thenewstack.io/reverse-etl-can-help-companies-operationalize-data-lakes/) 管道的地方之一是在[事务数据库](https://thenewstack.io/oracle-extends-autonomous-database-to-transactional-work/)和[数据仓库](https://thenewstack.io/modernize-your-cloud-data-warehouse-with-real-time-data/)之间，这是 AWS 的目标。

“我们已经工作了几年……让分析和机器学习变得更容易，而不必处理 ETL，”Selipsky 在介绍亚马逊 Aurora zero-ETL 与亚马逊红移的集成和面向 Apache Spark 的亚马逊红移集成时说。

AWS 在一份新闻稿中表示，亚马逊 Aurora 现在支持与亚马逊红移的零 ETL 集成，以利用亚马逊红移对来自 Aurora 的数 Pb 交易数据进行近实时分析和机器学习(ML)。

AWS 表示:“在交易数据被写入 Aurora 的几秒钟内，数据就可以在 Amazon Redshift 中获得，因此您不必构建和维护复杂的数据管道来执行提取、转换和加载操作。”

此外，AWS 表示，客户可以使用亚马逊 Redshift 的分析和功能，如内置的 ML、物化视图、数据共享和对多个数据存储和数据湖的联邦访问，以从交易和其他数据中获得洞察力。

“Aurora 和 Redshift 之间的零 ETL 是我长期以来一直恳求他们做的事情，因为 AWS 需要让生活变得更简单，减轻他们客户的集成负担。 [dbinsight](https://www.dbinsight.io/) 的分析师 [Tony Baer](https://www.linkedin.com/in/onstrategies/) 说:“与 Oracle 等在同一个数据库中进行分析和 OLTP 的公司相比，他们需要消除这个痛点。

与此同时， [Apache Spark](https://thenewstack.io/the-good-bad-and-ugly-apache-spark-for-data-science-work/) 的亚马逊红移集成帮助开发者在亚马逊红移数据上构建和运行 Apache Spark 应用。AWS 表示，使用 AWS 分析和机器学习服务的客户——如亚马逊 EMR、AWS Glue 和[亚马逊 SageMaker](https://thenewstack.io/amazon-sagemaker-automates-artificial-intelligence-development-pipeline/)——现在可以构建 Apache Spark 应用程序，这些应用程序可以读写他们的亚马逊红移数据仓库，而不会影响应用程序的性能或他们数据的事务一致性。

“红移中的数据库内火花遵循类似的主题，”贝尔说。“谷歌已经用 [BigQuery](https://thenewstack.io/google-stretches-bigquery-into-a-multicloud-data-warehouse-query-tool/) 做到了这一点。AWS 做出回应只是时间问题。”

这是迈向 AWS 零 ETL 愿景的又两步。

“我们将继续增加和寻找新的方法，让你更容易地访问和分析所有数据存储中的数据，”Selipsky 说。

## 亚马逊数据区

在其他与数据相关的新闻中，AWS 推出了[亚马逊数据区](https://aws.amazon.com/datazone/)，这是一种新的[数据管理服务](https://thenewstack.io/the-new-face-of-data-management/)，它使数据生产者更容易管理和控制对数据的访问，并使数据消费者能够发现、使用和协作数据，以推动业务洞察力。该公司表示，数据区使客户能够更快、更容易地编目、发现、共享和管理存储在 AWS、内部和第三方来源中的数据。

Selipsky 说，数据区是“一种数据管理服务，有助于在整个组织中发现、共享和管理数据”。“数据区使管理员和数据管理员能够轻松管理和控制对数据的访问，从而使您能够在整个组织中安全地免费发送数据。它使数据工程师、数据科学家、产品经理、分析师和其他业务用户能够轻松发现、使用这些数据并围绕这些数据进行协作，从而为您的业务提供见解。”

早期用户对新服务的想法进行了评估。全球能源公司 ENGIE 是数据区的早期用户，参与了 Selipsky 的主题演讲。

Data@ENGIE 的首席技术官 Gregory Wolowiec 在一份声明中表示:“在过去的六个月中，我们一直以测试客户的身份与亚马逊数据区团队合作，为创建 AWS 原生服务提供意见，并期待使用亚马逊数据区在整个组织中传播数据，并简化对 AWS 分析服务和治理工具的访问。”。“这将使我们的分析师和业务线领导能够创建创新项目并做出数据驱动的决策。”

与此同时，体育、新闻和娱乐品牌福克斯公司也是数据区的测试用户。

“亚马逊数据区将有助于简化和自动化我们的数据发现和共享——通过正确的治理——因此我们可以确保在正确的时间使用正确的工具访问它,[福克斯公司数据基础设施副总裁 Alex Tverdohleb](https://www.linkedin.com/in/alex-tverdohleb-30326510/) 在一份声明中说。

AWS 表示，DataZone 通过使用[机器学习](https://thenewstack.io/how-machine-learning-works-an-overview/)来收集和建议每个数据集的元数据，并通过对客户的分类和偏好进行培训来维护目录，以便随着时间的推移进行改进。

“在您的目录中，您可以定义分类法或业务术语表，”Selipsky 说。“您可以根据您的组织层次结构按照数据集来组织这些数据，然后将数据区连接到数据源。它使用机器学习来收集和填充适当的元数据，您可以添加标签和描述来提供更多信息……”

Baer 说，DataZone 吸引了他的注意力，因为它是此次活动中最引人注目的公告之一。

“这是对 Google Dataplex 的回应。他说:“我很惊讶，这没有成为 Glue 的扩展，而这正是 AWS 的‘某种 ETL’重点。

## 亚马逊安全湖

针对数据和安全专家，AWS 还在 preview [中引入了亚马逊安全湖](https://aws.amazon.com/blogs/aws/preview-amazon-security-lake-a-purpose-built-customer-owned-data-lake-service/)，这是一个安全数据湖。

“安全湖是一个数据湖，使安全团队可以轻松地自动选择和组合 Pb 级的安全数据，”Selipsky 说。

Amazon Security Lake 自动将来自云、内部和自定义来源的安全数据集中到存储在用户帐户中的数据湖中。Security Lake 使分析安全数据变得更加容易，因此用户可以更全面地了解整个组织的安全性。它帮助用户改善对其工作负载、应用程序和数据的保护。AWS 说，它可以自动收集和管理用户在不同账户和地区的所有安全数据。

“亚马逊安全湖是第一个支持 OCSF 标准的数据湖，”塞利普斯基说。“Security Lake 自动收集和汇总思科 CrowdStrike 和 Palo Alto Networks 等合作伙伴解决方案的安全数据，以及集成到安全中心的 50 多种安全工具。”

事实上，Security Lake 已经采用了[开放网络安全模式框架(OCSF)](https://github.com/ocsf/) ，这是一种开放标准，有助于规范和组合来自 AWS 和各种企业安全数据源的安全数据。

## 集装箱安全

对于云原生集，Selipsky 强调了对其 GuardDuty 安全服务的增强，以覆盖容器。

“我真的很高兴宣布 GuardDuty 的新功能，增加了容器运行时威胁检测，”Selipsky 说。“现在，GuardDuty 将通过监控容器本身的操作系统级行为，如文件访问、进程执行和网络连接，来帮助保护容器内运行的软件免受威胁。它可以检测访问底层计算节点的尝试，并获取实例凭据或识别试图与恶意参与者的命令控制面通信的容器。”

这代表了一个连续体。今年 1 月，AWS 扩大了[亚马逊守卫职责](https://aws.amazon.com/guardduty/)的覆盖范围，以持续监控和描述[亚马逊弹性库本内特服务(亚马逊 EKS)](https://aws.amazon.com/eks/) 集群活动，以识别对容器工作负载构成潜在威胁的恶意或可疑行为。[亚马逊 EKS 保护守卫职责](https://docs.aws.amazon.com/guardduty/latest/ug/kubernetes-protection.html)通过分析用户账户中现有和新亚马逊 EKS 集群的 [Kubernetes 审计日志](https://docs.aws.amazon.com/eks/latest/userguide/control-plane-logs.html)来监控控制平面活动。

“我们利用我们的安全知识和您的反馈来建立机器学习模型，智能地持续监控和识别难以检测的威胁，通常比其他安全产品快得多，”Selipsky 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>