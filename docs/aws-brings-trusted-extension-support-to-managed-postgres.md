# AWS 为托管 Postgres 带来可信扩展支持

> 原文：<https://thenewstack.io/aws-brings-trusted-extension-support-to-managed-postgres/>

拉斯维加斯——云计算巨头[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)发布了 PostgreSQL 的可信语言扩展，这是一个安全工具，允许开发者使用他们喜欢的语言，在 AWS 管理的 [Postgres 数据库系统](https://thenewstack.io/the-competitive-advantage-of-postgres/)上安全地构建高性能扩展。

AWS 在本周于拉斯韦加斯举行的第三届大会的[上发布了一款新的安全工具。](https://thenewstack.io/aws-reinvent-updates-apache-spark-redshift-and-documentdb/)

用于 PostgreSQL 的可信语言扩展是一个开源开发工具包，允许开发人员安装用他们首选的语言编写的扩展，内置安全护栏，可以在用于 PostgreSQL 的 [Amazon Aurora PostgreSQL 兼容版](https://aws.amazon.com/rds/aurora/)和 [Amazon 关系数据库服务(RDS)](https://aws.amazon.com/rds/postgresql/) 上运行。

根据 AWS 的首席开发者倡导者 Channy Yun 撰写的一篇附带的[博客文章](https://aws.amazon.com/about-aws/whats-new/2022/11/trusted-language-extensions-postgresql-amazon-aurora-rds/)，可信语言扩展让“数据库管理员可以控制谁可以安装扩展以及运行它们的权限模型，让应用程序开发人员一旦确定扩展满足他们的需求，就可以提供新的功能。”

## 解决安全性和合规性难题

AWS 开源战略和营销主管 David Nalley 在产品发布后立即与新堆栈坐下来讨论产品。他对这个项目的热情显而易见，他称之为“对我来说，这是本周最激动人心的公告，因为它为任何规模的 PostgreSQL 用户解决了一个重大的安全性和合规性问题。”

他指出了对这样一个工具的需要:“如果你运行不止一个数据库，或者你需要不止一个集成，它为你解决了一个重要的问题集，因为它本质上给了你一种创建一组脚手架的方法来保持事物在适当的位置。

"尤其是从安全的角度来看，因为 PostgreSQL 扩展本质上是可信的."

这是创新从需求中诞生的又一个例子。纳利说:“我们的客户告诉我们，他们希望能够在 RDS 和 Aurora 内部运行扩展。”

## “通过创建边界实现安全性”

从表面上看，这听起来很简单。但是自定义扩展带来了巨大的安全风险。AWS 在这次发布会上明确表示:发明安全性非常重要，因此它不会授予对不熟悉代码的访问权限，尤其是当授予的访问权限与 PostgreSQL 数据库本身的安全级别相同时。那是不行的。

但 AWS 不想在这一点上给客户一个“不”，然后走开。因此，它的开发人员回到了绘图板，以创建一个解决方案，为客户提供编写扩展的机会，同时将安全性保持在需要的水平。解决方案是扩建，但有护栏。纳利简洁地解释道:“通过创建边界来实现安全。”

在完成产品之前，有一些技术上的变化需要克服。纳利说:“我们花了大量时间关注的事情之一，是确保[它]将真正与上游 PostgreSQL 的运作方式兼容。很多早期的设计时间都花在这上面。

然后是界定界限的挑战。以前没有“安全”的扩展，所以这个概念完全是纳利和他的团队发明的。创造安全的定义对他们来说是一个巨大的挑战。

目前大多数常用语言都得到支持——包括 [JavaScript、](https://thenewstack.io/typescript-vs-javascript/) Perl 和 PL/pgSQL。Nally 说，AWS 开源该产品是因为它希望“为人们提供一些明显降低 RDS 客户复杂性的东西，但对于运行 PostgreSQL 的 DBA 来说，这也是一个很大的问题。”

该产品目前在 GitHub 上[上线，可供消费。](https://github.com/aws/pg_tle/blob/main/README.md)

[https://www.youtube.com/embed/TL2HtX-FmiQ?feature=oembed](https://www.youtube.com/embed/TL2HtX-FmiQ?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>