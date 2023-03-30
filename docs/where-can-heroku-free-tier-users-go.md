# Heroku 自由层用户能去哪里？

> 原文：<https://thenewstack.io/where-can-heroku-free-tier-users-go/>

Heroku 取消免费服务的消息在开发者社区引起了一阵关注。

上周， [Salesforce Heroku 宣布](http://email2.sourcecodecomms.com/c/eJwVTUluxDAMe018ayAvsuWDD3PpPxRZbgazZOB40Pb3dQEuAEGQWmyMNiBl8qYWyw6qNdfiwDkgh9M9-JUyhyZBUgs5cvZLgPN4d1E56uTjca5TzV5clEzgXeDmXZKECTMpasqItSmYe9nHeJ2Lvyzuc2K7H1_rrv24vf8nZvLUn_EhO7-GdtNL5d5_7_Nw7PrU73Ow3NbrYUYJnjaWABA30Vqz2yAlqlBBMuSKsyKWOGIMVhNTiLY1ioGYMLUYUfMfvy1LGg)将停止支持 Heroku Dynos、Postgres 和 Redis 数据的免费层。该公司还公布了其[产品路线图](https://github.com/heroku/roadmap)计划，一些怀疑者认为该计划乏善可陈，是 Salesforce 正在淘汰 Heroku 的标志。

好吧，虽然这对许多人来说是个坏消息，但也许好消息是还有其他选择。

## Heroku 替代方案

正如 [FrontDoor](https://www.frontdoorhome.com/) 、[的软件工程师丹尼·汤普森](https://twitter.com/DThompsonDev/status/1562889136091979776)在推特上写道“Heroku 正在结束他们的免费等级，一些人吓坏了。没关系！

这里有六个地方你可以免费托管你的网站！

–fire base

–维尔塞尔

–cloud flare 页面

–AWS

–网络生活

–Github 页面”

在此之前，汤普森在另一条推文中称 Heroku 的举动“令人震惊”，并补充说，“我知道为什么会发生这种情况，或者至少他们的推理是什么，但至少可以说，这绝对是可悲的。”

## 消除自由层

该公司表示，改变的一个原因是为了减少欺诈和滥用免费层。

Heroku 总经理兼 Salesforce 执行副总裁 Bob Wise 在[博客文章](https://blog.heroku.com/next-chapter)中表示:“我们的产品、工程和安全团队正在花费大量精力来管理 Heroku 免费产品计划的欺诈和滥用。“为了将我们的资源集中在为客户提供任务关键型功能上，我们将逐步取消 Heroku Dynos 的免费计划、Heroku Postgres 的免费计划和 Redis 的 Heroku Data 的免费计划，并删除不活跃的帐户。”

Wise 补充说，从 2022 年 10 月 26 日开始，Heroku 将开始删除不活动的帐户以及不活动超过一年的帐户的相关存储。从 2022 年 11 月 28 日开始，该公司将停止提供免费产品计划，并计划开始关闭免费的 dynos 和数据服务。

对占 1300 万账户基础很大一部分的免费用户的直接影响是，他们需要在两个月内支付基本订阅费。此外，现在有数百万的应用程序和网站在免费层运行，它们可能会不复存在。

“这是悲伤的一天。价格变化总是很难，在 Heroku 经历过一些早期的价格变化后，你不可能让每个人都满意，” [Crunchy Data](https://www.crunchydata.com/) 产品团队的成员 Craig Kerstiens 在[黑客新闻论坛](https://news.ycombinator.com/item?id=32594533)上写道。“但如此多的开发人员在 Heroku 上部署了他们的第一个应用程序，并且是如此多的新兵训练营的主要内容。没有它，我相信世界上的开发者会更少。”

## 微妙的平衡

软件供应商必须在免费层和他们的商业产品之间取得平衡。免费服务对于软件平台的教育和评估至关重要。Constellation Research 的分析师 Holger Mueller 说，但这对供应商来说是有代价的，包括人力和技术资源成本。

“Salesforce 关于滥用免费层的借口看起来像是一个软弱的借口——因为免费总是诱人的，容易被滥用，”穆勒告诉新堆栈。“Salesforce 本可以加强监控和审计。相反，它选择消除 Heroku 的空闲层，现在我们将看到这些工作负载有多“棘手”。企业会为其 Heroku 工作负载支付更多费用，还是会考虑将这些工作负载从 Heroku 迁移出去？”

## 呈现问答

与此同时， [Render](https://render.com/) 是另一家被吹捧为 Heroku 的现代替代品的公司。Render 创始人兼首席执行官 Anurag Goel 就此事会见了新的 Stack。戈尔的回应如下。

### **他们为什么要这样做？**

简而言之，Salesforce 不再关心 Heroku 的成长。拥有一个免费层完全是为了增加漏斗的顶部，它被算作一项营销费用。如果 Salesforce 仍然关心 Heroku 客户群的增长，他们会保留免费层。黯淡的“公共路线图”进一步证明了这一点；它的新特性很少，而且大多数都与修复安全问题有关。

### **谁受益？**

对于 Salesforce 来说，这是彻底抛弃 Heroku 公共云的一步。Heroku 本身不再是 Salesforce 旗下的一个独立业务部门；在他们的博客上发布公告的总经理也是 [Hyperforce](https://www.salesforce.com/news/press-releases/2020/12/02/introducing-salesforce-hyperforce/) 的总经理，这完全是关于你自己的硬件/云帐户上的 Salesforce。Salesforce 从这一举措中受益，因为这是彻底摆脱对他们没有战略价值的产品的一步。

PaaS 提供商喜欢 Render benefit，因为它促使更多的人试用它们，并帮助他们改进和扩展他们的产品。Heroku 是启动新软件项目的默认平台。这种情况将不会继续下去。

随着更多的 PaaS 提供商填补 Heroku 衰落造成的真空，开发者和企业将受益于更多的选择和竞争。

### **谁吃亏了？**

教育工作者、学生、OSS 项目和爱好者都是输家，因为他们将被迫把目前免费的应用程序迁移到其他平台上。然而，成千上万的网站将会直接下线，因为他们的维护者可能已经转移到其他项目去了，所以不可能对他们进行迁移或升级。这是网络的一大损失。

**注**:sales force Heroku 的 Wise 在他的帖子中说，公司将维持某种学生和非营利项目。“我们感谢 Heroku 作为一个学习平台的遗产，”怀斯写道。“许多学生在 Heroku 上第一次体验了在野外部署应用程序。Salesforce 致力于为学生提供实现其潜力所需的资源和经验。我们将在 [Dreamforce](https://www.salesforce.com/dreamforce/) 发布更多关于我们学生项目的消息。对于我们的非营利社区，我们也在与我们的非营利团队密切合作。”

星座研究公司的穆勒对此表示赞同。“很高兴听到 Salesforce 计划提供免费学生层，因为教育仍然是免费层产品的关键功能，”他说。

### **有哪些竞争对手可以乘虚而入？**

对于大多数 Heroku 用户来说，Render 是最接近的选择，它有一个迁移器和几个迁移指南，供希望迁移的人使用。自从 Heroku 4 月份的安全事件以来，我们已经看到了收入和注册的巨大增长，周四打破了所有记录。甚至前 Heroku 员工[这几天都推荐 Render](https://www.linkedin.com/posts/nsmiddleton_herokus-next-chapter-activity-6968615072197709824-pulS/) 。

其他公司，如 Digital Ocean 和像 Vercel 这样的 JAMstack 提供商也可能会看到用户的涌入，因为他们自己的免费层。

### **Heroku 是否有任何锁定问题，使其难以转移到其他平台？**

数据是云中最大的锁定。Heroku 还将关闭免费的 PostgreSQL 和 Redis 服务，因此如果许多用户宁愿不升级，他们将被迫运行一个高风险、耗时的迁移过程来将数据转移到其他平台。

### 从竞争的角度来看，你对此有什么看法？

我们一直怀疑赫鲁库的日子不多了。即使在停滞不前的产品之外，Salesforce 对 2022 年 4 月安全事件的回应，他们拒绝修复甚至最基本的漏洞，以及最近的平台正常运行时间问题都加强了我们的信念，这一事件无疑是棺材上的又一颗钉子。

### **你真的认为他们在让整个事情日落吗？**

不是全部，但肯定是公共云的一部分。Salesforce 长期以来一直在推动人们转移到他们的私人空间服务，每月起价数千美元，在 Salesforce 硬件上运行。Salesforce 没有动力成为公共云提供商；他们与 Heroku 的目标一直是让 Salesforce 客户更容易运行定制代码。我怀疑 Heroku 最终会变成这样——一个运行 Salesforce 应用程序的平台，而不是通用的云工作负载。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>