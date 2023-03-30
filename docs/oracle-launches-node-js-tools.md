# Oracle 发布 Node.js 工具

> 原文：<https://thenewstack.io/oracle-launches-node-js-tools/>

在 2014 年的 OpenWorld 大会上，甲骨文宣布正在为其数据库产品开发 Node.js 驱动程序。最终的代码于上周发布，作为带有 Apache 2.0 许可的开源代码。

这个驱动程序现在可以从 GitHub 获得，它包含了处理 JavaScript 对象和数组的工具，以及在 Oracle 和 JavaScript 数据类型之间进行转换的工具。它旨在处理事务，并与 Oracle 的内置扩展工具配合使用。这包括在服务器出现故障时快速结束事务的能力——允许 Node.js 应用程序快速故障转移到另一个数据库，而不会丢失用户数据。

虽然该驱动程序目前是 Unix 服务器的预览版，包括 Linux 和 Mac OS，但它正在积极开发中，对 Windows 的支持即将推出(这将允许 Azure Oracle 实例与 Azure Node.js 服务器一起工作)。其他计划中的功能包括通过批量获取或流式处理大型查询结果。Oracle 的 Node.js 支持超越了内部 Oracle 部署，如果您正在使用 Oracle 的云服务，您很快就可以在您的应用程序中使用 Node.js 驱动程序，并提供自助供应工具和对通用 Node.js 模块的支持。

Node.js 的原生 Oracle 驱动程序很有意义，因为它允许开发人员为 Oracle 应用程序快速构建可伸缩的 web 前端。将 Node 用于小型、快速、专用的 web 交换机简化了应用程序开发，尤其是与广泛可用的 Model View 控制器框架结合使用，并且应用程序的大部分代码可以使用 Oracle 自己的开发工具在数据库中构建。

设置驱动程序非常简单；首先从 GitHub 下载源代码，然后在与驱动程序相同的目录下设置 Node.js。Oracle Node.js 驱动程序作为 Node.js 模块安装，连接字符串使用代码中的`getConnection` 语句设置。一旦连接到 Oracle 数据库，Node.js 驱动程序就可以用于运行 SQL 和 PL/SQL 命令。您也可以从 Oracle 的 APEX web 应用程序框架中直接调用 Node.js。

除了提供其驱动程序，Oracle 还建立了 Node.js 开发人员中心，作为其 Oracle 技术网络社区站点的一部分。您可以找到用户问题(和答案)以及 Oracle content 的链接。使用 Node.js 驱动程序的开发人员已经提供了有用的内容，包括代码片段，这应该可以加快初始部署。

Oracle 对 Node.js 的承诺很受欢迎，它为开发人员提供了构建高度可伸缩的混合 web 应用和服务所需的工具，其中 Node.js 充当了 web 和 Oracle 数据库工具之间的接口。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>