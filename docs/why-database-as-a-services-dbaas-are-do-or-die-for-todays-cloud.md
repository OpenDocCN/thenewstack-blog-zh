# 为什么数据库即服务(DBaaS)是当今云计算的生死之战

> 原文：<https://thenewstack.io/why-database-as-a-services-dbaas-are-do-or-die-for-todays-cloud/>

[MongoDB](https://www.mongodb.com/) 赞助本帖。

 [安德鲁·戴维森

Andrew 是 MongoDB 的云产品副总裁。他之前在谷歌从事全球地图业务，拥有物理学背景，并在南亚生活过。](https://www.linkedin.com/in/andrewad/) 

也许没有比数据库更惰性的技术了。问题是日常运营维护是出了名的困难。一旦为您的应用程序选择了一个，那么迁移也是一个挑战。典型的例子:仍然占据市场大部分的传统关系数据库是基于 40 多年前设计的技术的[。](https://www.seas.upenn.edu/~zives/03f/cis550/codd.pdf)

想想看:今天使用的大多数关系数据库都是在云出现之前、移动设备出现之前、互联网出现之前创建的，而且肯定是在我们每天在工作和个人生活中使用的应用程序的数据量和数据种类出现之前创建的。在云计算的推动下，数据库即服务(DBaaS)的价值如此之高，最终足以令人信服地打破传统数据库的窠臼。当与提供弹性云体验的下一代数据模型相结合时，尤其如此。

## 云如何支持 DBaaS 消费

在大型企业之外，组织不太可能负担得起维护数据库和软件应用程序日常运行所需的大量资源(以资金、人员和工具衡量)。虽然由于这里列出的原因，人员成本很高，但他们也更有可能犯错误，例如意外导致操作问题或留下攻击媒介。因此，自动化是降低操作和安全风险表面积的关键。此外，在当今的经济中，昂贵的不是技术，而是使用技术的人才。

在满足业务需求方面，应用程序开发人员是我们这个时代的关键人物。启用自助服务并允许他们按照自己的节奏不受干扰地工作是关键。DBaaS 实现了自助式即时满足开发人员体验，这在数据库级别是不可能的，从而实现了前所未有的灵活性。

工程团队是昂贵的，技术使他们专注于通过更快地进入市场、在软件中创建差异化功能等来推动价值。显然至关重要。在开发运维之前，应用开发人员会将庞大的生产工作负载交给一个集中的运维团队来管理。然而，现在采用全栈现代 DevOps 原则的自给自足的“两个比萨饼”大小的团队的新模式能够拥有并端到端地运营他们的服务。

## 企业工作负载姗姗来迟

正如 Gartner [在今年早些时候指出的](https://blogs.gartner.com/adam-ronthal/2019/06/23/future-database-management-systems-cloud/)，“云数据库系统现在是大多数企业工作负载的标准”，并预测在未来三年内，所有数据库部署的四分之三将部署到云中。此外，摩根士丹利最近发布的新研究[指出，到 2028 年，在新堆栈技术上的支出将超过传统基础设施投资，NoSQL 数据库仍将是这一转变的最大受益者。由于我们的云优先和移动优先的世界，这些新应用需要灵活的模式和弹性的云原生基础架构，以便能够每秒响应潜在的数百万个请求，而不会使您的应用崩溃。](https://www.morganstanley.com/ideas/new-software-stack-2019)

向使用 DBaaS 的转变支持在不需要物理硬件或安装软件的情况下访问数据库。繁重的工作由构建数据库的专家来完成，这对于提供最佳性能和使安全性/合规性要求更容易处理具有不可思议的好处。向 DBaaS 和云原生的转变为精明的新贵提供了竞争优势，可以颠覆所有行业的传统供应商，这也是比特币基地、Stripe、Lyft 和 Epic Games 等公司在如此短的时间内获得大规模采用的原因。

被上述公司和无数其他公司破坏的传统机构现在正在意识到云原生和 DBaaS 可能带来的威胁。新一代的开发人员正在崛起，他们除了将数据库层抽象成一个可以正常工作的弹性服务之外，什么也做不了。DBaaS 使每个企业，无论规模大小，都专注于提供新的创新，这对于小型创业公司来说更容易扩展。

## 提高 DBaaS 的安全性和合规性优势

随着新隐私法(GDPR 和即将出台的加州消费者隐私法案(CCPA))的出台，您的数据库选择变得更加重要，利用 DBaaS 是帮助您的组织保持合规性的一种简单方法。鉴于 GDPR 对数据进行严格的控制，自我管理数据库以保持合规性就成了一项艰巨的任务。

通过使用 MongoDB Atlas 之类的托管数据库服务，您可以通过一个名为[全局集群](https://www.mongodb.com/cloud/atlas/global-clusters)的特性来精确控制数据的存放位置。您只需打开控制面板，选择公共云供应商和数据中心位置，就可以在后台自动移动数据，而无需关闭任何设备。通过将最相关的数据放在本地应用程序服务器附近，同时确保应用程序的低延迟和高性能，您正在实现数据主权要求。

## 企业工作负载现在默认为云

虽然关系数据库运行良好，但你只需要看看亚马逊最近发布的关于其长达数年(是的，你没看错，数年)从 Oracle 数据库迁移到其专有云技术的事后分析就够了。这种转变来自于花费太多时间来管理和扩展数千个遗留数据库。

这是来自世界上最大的公司之一的 DBaaS 方法的验证。随着将工作负载迁移到云(无论是多云还是混合云模式)的情况在各个行业不断增加，我们应该预计组织会增加他们正在卸载数据库管理的任务关键型工作负载的数量。

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>