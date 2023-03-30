# 微软为开发者提供更智能的数据库工具

> 原文：<https://thenewstack.io/microsoft-bringing-together-general-database-developers-sql-tools/>

微软正试图弥合软件开发和数据库编程之间的鸿沟，在 Visual Studio 代码中提供更好的 SQL 支持，并为开发人员扩展更多的 SQL Server 企业功能。

如今很少有应用程序不处理数据，但是传统上——当然是在微软的世界里——数据库开发人员与普通开发人员是完全不同的类别。

事实上，术语“数据库开发人员”可以指数据库管理员，他也编写连接到数据库的脚本和服务。

需要访问应用程序中的数据的开发人员和创建应用程序的数据库开发人员之间的这种差异，使得微软的数据库技术在当今的移动和云计算世界中显得不那么重要。

SQL Server 2016 增加 JSON 支持和 R 服务是微软旨在将这两个世界拉近的一种方式。SQL Server 内部的服务现在正在获得新的机器学习和深度神经网络功能。微软数据产品 CVP Joseph Sirosh 表示，这将带来“更高的速度、性能和规模，尤其是在处理大量文本数据和高维分类数据时”。GitHub 上有针对 SQL Server 的 [R 示例和机器学习模板](https://github.com/Microsoft/SQL-Server-R-Services-Samples)。

还有由 Polybase 实现的 Hadoop 集成，在 2016 年版本中，这成为 SQL Server 标准版的一项功能，因此不再是您必须购买分析平台系统才能获得的东西。

能够在 SQL 中创建指向 Hadoop 集群的外部表，并像查询数据仓库中的另一个表一样进行查询，这使得熟悉 SQL 的数据库开发人员更容易访问它。他们可以直接使用 T-SQL 查询运行在多个平台(包括非结构化 Azure Blob 存储)上的 Hadoop 集群，而不必学习 Hive。充其量蜂巢是不同的；最坏的情况是，它有许多限制，并且不支持您在 SQL 中习惯的所有查询类型。

微软也从另一端着手，为普通开发人员提供了更好的 SQL Server 工具。Sirosh 承诺“改善 Node.js、Java、PHP、Python、Ruby 等在 Windows、Mac 和 Linux 上的开发者体验。NET core 和 C/C++。我们的 JDBC 连接器现已发布，[可作为开源](https://github.com/Microsoft/mssql-jdbc)使用，这为开发人员提供了更多关于如何贡献和使用 JDBC 驱动程序的信息和灵活性。此外，我们还对 PHP 驱动程序的 [ODBC 进行了更新，并推出了新的 Linux 连接器 ODBC，使开发人员能够更轻松地使用基于微软 SQL 的技术。”这是在更新 SQL Server Management Studio 和 SQL Server 数据工具的基础上进行的，以便它们可以在 Linux 上与 SQL Server 一起工作。](https://github.com/Microsoft/msphpsql)

还有一个针对 [Visual Studio 代码](https://github.com/Microsoft/msphpsql)的新的官方 SQL 插件，让数据库开发人员使用微软推出的新工具——这使得 SQL 开发可以在 Linux 和 Mac 以及 Windows 上进行。

微软的 Mitra Azizirad 告诉新的 Stack:“我们将推出一个带有更新的连接器和工具的 SQL VS 代码插件，因为我们希望使它更加无缝。”“我们希望开发人员能够更加无缝地使用 SQL Server、Azure SQL 数据库和 Azure 数据仓库进行构建。能够从 VS 代码连接到 SQL Server，包括 Linux 上的 SQL Server，将使它更容易使用。Azizirad 是现在开发和数据部门的 CVP。

“数据已经进入了我的云应用程序开发平台团队，”她告诉我们，“这代表了内部围绕应用程序的文化转变，理解数据是任何应用程序的核心部分。我们认识到，我们正在从可能被认为是数据感知型应用程序转向真正的数据驱动型智能应用程序。如果你想要这种身临其境的体验，在这种体验中，你可以实时地从数据中进行推理，进行预测性分析，并具有上下文感知能力，没有数据你是做不到这一点的。没有数据，你不可能有那种身临其境的体验。因此，我们真的需要与数据开发人员和所有开发人员接触，让事情变得更容易。”

已经有一些针对 Visual Studio 代码的 SQL 扩展，但是最流行的只支持 MySQL，其他的只允许你连接到 SQL Server。能够从 VS 代码中编辑甚至执行 T-SQL 使它成为一个全新受众的强大开发工具——这意味着那些数据库开发人员可以更容易地使用 VS 代码支持的所有其他语言和模式。

您可以连接到在 macOS 或任何云中的 Linux、Windows 或 docker 上本地运行的 SQL Server，连接到 Azure SQL 数据库和 Azure SQL 数据仓库。连接配置文件帮助您管理到多个数据库的连接，并设置高级属性(如 TCP 端口和连接超时)；您可以在 VS 代码中使用标准选择列表来切换活动数据库连接。

连接后，您可以打开现有的。sql 文件或在 VS 代码中的 T-SQL 编辑器中创建新的 T-SQL 语句和查询(DML 和 DDL)。该编辑器为您提供了 T-SQL 彩色化、上下文感知模式自动完成、语法和模式错误诊断以及 T-SQL 代码片段。错误诊断在编辑器中显示为红色波浪线，在"错误列表工具"窗口中显示为错误信息。

您可以直接从 VS 代码中运行 T-SQL 查询(可以是选择的文本，也可以是编辑器中的所有内容)，并在结果预览窗口中查看结果和消息。您可以有多个结果集；它们显示在一个堆叠的、可折叠的结果窗格中，您可以将结果导出为 CSV 或 JSON 文件。

“Visual Studio 本身与 SQL Server 有丰富的集成，因此有理由开始将这种集成引入 VS 代码，”IDC 研究主管 Al Hilwa 告诉我们。“SQL Server 一直是一个广泛部署的关系引擎，在其他开发环境和语言中有相当多的使用，因此这是有意义的，因为 VS 代码面向广大的开发人员。”

微软还将发布 SQL Server 2016 SP1，该版本将为标准版带来更多新功能，以便开发人员可以在所有版本中使用单一编程模型，这是一个长期以来的要求。“这意味着 ISV、合作伙伴和开发人员在创建应用程序时可以构建一个单一的应用程序编程界面，然后使用可根据应用程序需求进行扩展的版本，”Azizirad 说。

Developer Edition 一直都有完整的 Enterprise Edition 特性可供开发，但现在您可以在 Standard Edition 甚至 Express editions 中部署内存 OLTP 和内存 columnstore 分析和分区。

通过添加基本的高可用性、2 节点单数据库故障转移和不可读辅助数据库，您可以创建更强大的系统。在标准版中获得“总是加密”选项是一个很大的安全改进；开发人员可以从 ASP.NET 网站访问加密的数据库，而无需解密，只有具有列主密钥的可信应用程序才能解密数据。这使得使用扩展数据库功能——将不常访问的数据移动到 Azure 数据库——这已经是标准版中的一个功能，更有吸引力。

微软在其 Connect 活动上宣布了一系列其他数据库技术，从 Azure Data Lake 的全面上市——大数据处理和分析服务——R Server for hdin sight 和 Operational Analytics for Azure SQL Database，到 DocumentDB 的本地仿真器，再到 Linux 上的 SQL Server 公开预览版。这些工具的目的是让这些工具与更广泛的开发者相关。

专题图片:微软的斯科特·格思里，在 Connect 2016 的舞台上。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>