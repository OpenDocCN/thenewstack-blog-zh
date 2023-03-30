# 对比安全性为 AWS Lambda 增加了无服务器安全性

> 原文：<https://thenewstack.io/contrast-security-adds-serverless-security-for-aws-lambda/>

[对比安全](https://www.contrastsecurity.com/)已经扩展了其[对比应用安全平台](https://www.contrastsecurity.com/solutions/devsecops)，将无服务器添加到其方法列表中，之前包括代码扫描、[应用安全测试](https://thenewstack.io/category/security/)、开源安全和运行时保护。

引用其自己的[无服务器应用安全状态报告](https://c212.net/c/link/?t=0&l=en&o=3327284-1&h=2447026230&u=https%3A%2F%2Fwww.contrastsecurity.com%2Fserverless-report&a=State+of+Serverless+Application+Security+Report)，Contrast 在一份声明中表示“超过 70%的受访者报告说，他们的开发团队中有六个或更多的人在开发无服务器应用程序，”Contrast Security 的首席产品官 Steve Wilson 表示 [Contrast 无服务器应用安全](https://www.contrastsecurity.com/contrast-serverless-application-security)在很大程度上是由客户需求驱动的。

“我们有数百家大型企业客户，他们去年开始告诉我们，他们需要对这些无服务器环境的支持，”Wilson 说，并指出随着公司应用程序的现代化，向无服务器的迁移越来越多。“我们的一个测试客户正在为他们的物联网基础设施重写一组应用程序，这是一种真正受益于无服务器环境的典型应用程序，因此当他们升级到真正的云原生环境时，他们开始利用亚马逊上的功能即服务，并真正要求我们帮助提供一些工具，我们可以为他们提供安全保证。”

## **新的安全挑战**

Wilson 将这种向无服务器的转变称为“自 enterprise Java 和应用服务器以来应用程序开发中最大的转变之一”，他解释说，这为进行这种转变的公司带来了新的安全挑战。

“它允许你创建非常数据密集型的大规模应用程序，而成本只是旧方法的一小部分，它已经变得非常受欢迎，但挑战之一是这是一种非常不同的构建应用程序的方法，”他说。整个行业的企业都依赖应用程序安全测试工具来帮助他们在交付应用程序之前检查代码，但是这些工具都不能在无服务器环境中工作

到目前为止，Contrast server less Application Security 已经工作了一年多，作为这项工作的一部分，Contrast Security 于去年年底收购了 CloudEssence，并在过去的一年中将其技术构建到平台中。

## **提前添加安全性**

虽然 Contrast Security 不是第一家承担无服务器应用程序安全性的公司，但它表示，它的与众不同之处在于不专注于运行时安全性，而是专注于在软件开发生命周期的早期提供安全性，具有三个主要特征。

“这是检查这种基于云无服务器技术的新程序，同样，我们对其他环境所做的是，以自动化的方式彻底检查和测试你的无服务器功能，以找到可能的安全漏洞，然后给你的开发人员非常直接的反馈，告诉他们需要做什么来修复它们，”威尔逊说。

首先，Contrast server less Application Security 执行动态环境扫描，它会根据实时引入测试环境的任何特定更新自动运行。Wilson 解释说，无服务器功能容易受到您在其他地方看到的许多相同的攻击，特别是考虑到它们的访问权限，这就是为什么这些扫描基于 [OWASP 十大基准](https://owasp.org/www-project-top-ten/)，其中包括 SQL 注入、代码注入、命令注入和本地文件包含等风险。

威尔逊说:“无论技术是什么，你试图捍卫的关键是捍卫对你数据的访问。”“这些无服务器的功能，通常它们存在的主要原因是快速插入或提取数据库中的数据。特定的事务可能是短暂的，但它们可以非常广泛地访问您基础架构的其他部分，因此我们在基于应用服务器的程序中看到的传统类型的漏洞，例如注入攻击，在无服务器环境中仍然是可能的。”

接下来，Contrast server less Application Security 执行资源映射，自动发现 S3 存储桶、API 网关和数据库等资源，以及它们与您的环境的关系。最后，Contrast 执行代码扫描来发现漏洞，如过度许可的功能或由开源依赖项引入的漏洞。

在发布时，对比无服务器应用安全将为 T4 的亚马逊网络服务工作，但是 Wilson 说 Azure 和谷歌云已经在路线图上了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>