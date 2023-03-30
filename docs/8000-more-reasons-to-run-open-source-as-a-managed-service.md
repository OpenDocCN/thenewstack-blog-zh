# 8，000 多个将开源作为托管服务运行的理由

> 原文：<https://thenewstack.io/8000-more-reasons-to-run-open-source-as-a-managed-service/>

亚马逊网络服务(AWS) 赞助了这篇文章。

 [马特·阿萨伊

Matt 参与了开源及其支持的所有领域(云、机器学习、数据基础设施、移动等。)近二十年来，为各种开源公司工作，并定期为 InfoWorld 和 TechRepublic 撰写文章。你可以在推特上关注他(@mjasay)。](https://www.linkedin.com/in/mjasay/) 

趋势科技最近[报告](https://blog.trendmicro.com/trendlabs-security-intelligence/more-than-8000-unsecured-redis-instances-found-in-the-cloud/)称“8，000 个 Redis 实例[…]在世界各地不安全地运行，甚至是部署在公共云中的实例。”但这不是真实的故事。趋势科技小心翼翼地指向[官方 Redis 文档](https://redis.io/topics/security)，其中强调“Redis 旨在由可信环境中的可信客户端访问。”因此，让这样的服务器直接连接到互联网上并不是一个好主意，也不是一个“不受信任的客户机可以直接访问 Redis TCP 端口或 UNIX 套接字的环境”

然而很明显，这些最佳实践有时会被忽视。在各种各样的开源软件中，关于不安全软件导致的安全漏洞的故事经常出现——通常是由错误配置的权限导致的。这并不是因为软件本身不安全，也不是因为相关的供应商在安全方面不够聪明。这是因为我们人类并不总是很擅长应用正确的配置或投入精力来保护我们的软件，开源或其他。

但这没关系，因为对于 TCP 端口受损的 Redis 服务器和开源软件中无数其他安全问题，有一个非常简单的解决方案:运行一个完全托管的服务。

## **按下简单按钮**

但首先，让我们明确一点:Redis 从未如此安全。Redis Labs 的 [Itamar Haber 在评论趋势科技的报告时指出](https://redis.com/blog/fewer-unsecured-redis-servers/)“[ 8，000]这个数字很大，但它表明了总体上被暴露的服务器数量保持不变，如果不是下降的话。”每个 Redis 版本都导致不安全的 Redis 服务器数量减少，4.0 版本引入了[保护模式](https://redis.io/topics/security#protected-mode)——这极大地提高了默认的 Redis 安全性。

这很棒，但可以说它甚至不是 Redis 最重要的安全改进。正如 Haber 继续建议的那样，“Redis 实验室提供的托管服务是开箱即用的安全服务，无需用户自己找出安全措施。”

是的，没错。Redis 安全问题的最简单的答案，比如 TLS 没有默认开启或者没有设置密码，只有两个字:托管服务。例如，Redis 实验室服务解决了这些现成的问题。

如果你倾向于 Redis(你很可能是——[官方 Redis Docker Hub 图像](https://hub.docker.com/_/redis)至今已注册超过 10 亿次下载),你已经被选择宠坏了。Redis 实验室[提供全面管理的 Redis 服务](https://redis.com/redis-enterprise-cloud/)。同样如此的还有[艾文](https://aiven.io/redis)、[数字海洋](https://www.digitalocean.com/products/managed-databases-redis/)以及其他——包括亚马逊网络服务(AWS)。这是否意味着我有偏见？当然了。毕竟，我为 AWS 工作，我们为 Redis ( [亚马逊 elastic cache](https://aws.amazon.com/elasticache/))、Apache Kafka ( [亚马逊 MSK](https://aws.amazon.com/msk/) )和其他开源项目提供托管服务。我会喜欢你用它们吗？没错。

但实际上，我更担心的是你会使用某种东西——任何东西——来保证你的数据安全。

如前所述，这不仅仅是一个 Redis 的事情。也许你已经读过 MongoDB 的安全问题，就像《赤裸裸的安全》中报道的那些问题。MongoDB 从版本 2.6 开始就提供了关闭远程访问的能力，从版本 3.6 开始默认开启。这是不是意味着 MongoDB 不会被黑？不，因为公司(在我看来是正确的)试图平衡用户自由和安全。正如 MongoDB 的一位发言人告诉 Naked Security 的那样，“我们相信默认设置 localhost 会让用户处于这样一种模式，他们必须有意识地决定自己通向网络安全的适当途径。”

或者，你知道，开发者可以运行 [Atlas](https://www.mongodb.com/cloud/atlas) ，MongoDB 的托管服务。问题:已解决。

### 开源并不意味着“开门”

自由是开源软件的基石。从(免费和)开源软件的最早期开始，[最基本的权利就是](https://en.wikipedia.org/wiki/The_Free_Software_Definition):“首先，复制一个程序并将其重新分发给你的邻居的自由，这样他们就可以像你一样使用它。第二，改变一个程序的自由，让你可以控制它，而不是它控制你……”。后来，这被理查德·斯托尔曼称为“四大自由”，一个独立的开发团队阐明了[开源定义](https://opensource.org/osd-annotated) (OSD)，它概述了它自己的一套基本自由。

虽然四大自由和 OSD 都没有建立“错误配置开源以使其不安全的权利”，但是“自由”已经被太多的开发者无意中接受了。

在开源中——是的，在 AWS 中也是——一个核心原则是允许开发人员灵活地改变我们的默认配置，以适应他们正在构建的任何类型的应用程序。与在内部或任何其他地方运行软件的情况一样，当设置新的访问控制配置时，开发人员应该确保它以他们预期的方式保护访问。然而，很明显，许多开发人员没有这样做，无意中打开了安全漏洞的大门。

所以让我们简单点:将开源作为托管服务运行，不要再担心打补丁、配置错误等等。无论什么开源软件——无论是 Apache Kafka、Redis、MySQL，还是许多许多其他软件——你都很有可能将其作为托管服务。当你这样做的时候，你将不必担心像“在云中发现超过 8，000 个不安全的 Redis 实例”这样的标题，因为你的不会在其中。

MongoDB 和 Redis 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>