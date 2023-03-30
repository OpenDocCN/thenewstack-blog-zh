# 开源和云共生

> 原文：<https://thenewstack.io/the-open-source-and-cloud-symbiosis/>

亚马逊网络服务(AWS) 赞助了这篇文章。

 [马特·阿萨伊

Matt 是 AWS 的负责人，参与了开源及其支持的所有领域(云、机器学习、数据基础设施、移动等。)近二十年来，为各种开源公司工作，并定期为 InfoWorld 和 TechRepublic 撰写文章。你可以在推特上关注他(@mjasay)。](https://www.linkedin.com/in/mjasay/) 

尽管有些人认为云是开源的克星，但几乎可以肯定，事实恰恰相反。如果我们回顾过去十年中一些最著名的开源项目，我们很难回避这样一个结论，即云培育并加速了开源的采用。从 MySQL 到 PhoneGap，再到[说出你最喜欢的项目]，云已经帮助增加了开源软件的效用和采用。

并不是所有的影响都是单向的。艾萨克·施鲁特，T2 NPM 公司的创始人。(创造了世界上最大的软件注册中心 npm 的公司)在一次采访中说，“我怀疑开源对云的影响比其他方式更大。”

或许是完美的共生关系？让我们来看看。

## **将“战争”从软件中移除**

从我们在 2020 年的优势来看，当云服务在很大程度上是既定的，很容易忘记前云软件的“胶带和创可贴”时代，正如 Brian Leroux 所描述的那样。勒鲁应该知道。虽然今天他是 [Begin](https://begin.com/) 的联合创始人，但之前勒鲁在 2009 年作为 Nitobi Software 的早期员工帮助启动了 PhoneGap 开源项目。对于像 Leroux 这样经历过前云时代的人来说，也许更容易理解云对开源的影响有多大。

为什么？因为在当时，软件基础设施的扩展和运营是痛苦的。

虽然 PhoneGap 已经可以下载和使用，但在项目启动一年后(2010 年)，Nitobi 仍然通过培训人们“如何使用 PhoneGap”来赚取大量收入，正如 Leroux 在电子邮件采访中解释的那样。“我们的教室里坐满了来自同一家公司、运行 Windows 笔记本电脑的人，他们期望开发 iPhone 应用程序，这在过去和现在都是不可能的。不用说，这是一场噩梦，人们都疯了。”

培训结束后，Leroux 去了一家咖啡馆，并开发了第一个版本的 PhoneGap Build T1，这是一种云服务，可以为移动设备编译软件，消除了开发人员不断维护原生 SDK 的需要。“具有讽刺意味的是，如果没有过多的编译器和主机操作系统，我们无法构建一个跨平台的移动解决方案，”他说。“通过将专有部分转移到云中，我们可以从任何具有 web 浏览器的开发环境中无缝构建所有平台。”他说，没有云，跨平台体验太难了。一个月后，在 [JSConf 2010](http://2010.jsconf.us/) 大会上，Nitobi 宣布了 PhoneGap Build,“第一个月就有 8 万人注册，这太荒谬了。剩下的就是历史了。”

这就是云的一个帮助:隐藏了软件的复杂性。但好处不止于此。

## **轻松缩放**

对于希望采用最新、最好的开源软件的企业来说，运行底层基础设施也存在困难。同样，我们可能不记得“管道胶带和创可贴”的时代，但它确实阻碍了开源的采用。在 2008 年的一篇博客文章中，Drupal 创始人 Dries Buytaert 指出了扩展应用基础设施的固有困难:

“扩展 Drupal 并不总是容易的——不是因为 Drupal 很糟糕，而是因为扩展 LAMP 堆栈(包括 Drupal)需要大量的技能。您需要购买合适的硬件，安装负载平衡器，以主从模式设置 MySQL 服务器，设置静态文件服务器，设置 web 服务器，让 PHP 使用操作码缓存器，绑定 memcached 等分布式内存对象缓存系统，与内容交付网络集成，观察系统中每个组件的安全建议，并配置和调整所有内容。”

Buytaert 说:“要么你可以自己做以上所有的事情，要么你把它外包给一个知道如何为你做这件事的公司。”当时最大的挑战之一是扩展像 MySQL 这样的关系数据库，这是他希望仍处于萌芽状态的 AWS(或另一家供应商)可能会解决的问题，尽管他感叹道，“我没有看到任何强烈的信号表明，对于普通人来说，扩展 MySQL 变得更加容易。”

然而它发生了。大约在 Buytaert 发表文章一年半后， [AWS 为 MySQL 推出了](https://aws.amazon.com/blogs/aws/introducing-rds-the-amazon-relational-database-service/)亚马逊关系数据库服务(Amazon RDS)。突然间，攀登灯堆中的“M”所需的神秘魔法被覆盖了。与此同时，许多严重依赖 MySQL 的公司也做出了贡献，强化了数据库并扩展了其功能。

## **更简单，更多人采用**

MySQL 在这方面也不孤单。[根据积极的 PostgreSQL 贡献者和](https://twitter.com/craigkerstiens/status/1247258161926385664)[postgresweekly.com](http://postgresweekly.com)策展人 Craig Kerstiens 的说法，“PostgreSQL 在云上变得可用时，肯定看到了一些采用的增长。”虽然证明这一点的数据有限，但 DB-Engines 数据库趋势显示 PostgreSQL 在 2014 年的受欢迎程度有所上升，这可能与 2013 年 11 月亚马逊 RDS for PostgreSQL 的[发布相吻合。](https://aws.amazon.com/about-aws/whats-new/2013/11/14/announcing-amazon-rds-for-postgresql/)

云有什么帮助？“总的来说，Postgre[SQL]社区一直缺少数据库管理员，而且启动和运行起来也不那么简单。点击一下托管云的按钮，采用率就会大大提高，” [Kerstiens 说。](https://twitter.com/craigkerstiens/status/1247262224810307584)通过促进 PostgreSQL 的采用， [Kerstiens 总结道](https://twitter.com/craigkerstiens/status/1247262428787650569)，更多的用户涌向 PostgreSQL。重要的是，他们不需要成为 DBA 或者咨询 DBA 来接受 PostgreSQL 的强大功能。

现在，在成千上万的其他开源项目中进行这样的演示，你会感觉到开源已经从云计算中受益了多少。这不是巧合。亚马逊在 2006 年最早进入云计算领域，拥有多年大规模运行各种开源项目的经验。难怪开源软件在云中运行得如此之好。正如 AWS 副总裁 Matt Wilson 所说，“云是为运行它而构建的！”

## **走开源主流**

云计算帮助企业拥抱开源还有另一个不太技术性的原因:它将对开源软件的支持集成到了各种云服务中。

根据 2019 年红帽对企业 IT 领导者的调查，当今使用开源的最大障碍之一是缺乏企业级支持。从 2000 年开始，我个人为各种开源公司工作，缺乏对开源软件的支持是公司不能从受支持的专有产品中转换的一个经常被引用的原因，这一事实在[各种企业调查](https://www.slideshare.net/blackducksoftware/the-2012-future-of-open-source-survey-results)、[政府研究](https://www.unece.org/fileadmin/DAM/stats/documents/ece/ces/ge.50/2014/Topic_1_UNESCO.pdf)和[学术研究](https://cacm.acm.org/magazines/2010/3/76300-organizational-adoption-of-open-source-software-barriers-and-remedies/fulltext?mobile=true?mobile=false)中被提到。

随着 AWS 等云公司开始提供托管和/或管理的开源软件服务，他们通过将软件支持“烘焙”到服务中来降低开源的风险。然而，不仅仅是一份支持合同，像亚马逊关系数据库服务([亚马逊 RDS](https://aws.amazon.com/rds/) )这样的云服务帮助企业跟上了开源创新的快速步伐。企业不必下载一个开源项目，摆弄旋钮使其工作，并承担任何相关的法律责任，而是可以毫不费力地运行云服务。开源和以前一样好，云让它变得更好。

但是 Schlueter 提出的云塑造了开源，开源也塑造了云的观点呢？我在一篇后续文章中深入探讨了这个问题:[为什么没有开源云是不可能的](https://thenewstack.io/why-cloud-is-impossible-without-open-source/)。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>