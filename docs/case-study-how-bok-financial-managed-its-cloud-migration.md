# 案例研究:BOK 金融公司如何管理其云迁移

> 原文：<https://thenewstack.io/case-study-how-bok-financial-managed-its-cloud-migration/>

洛杉矶——当您将业务关键型应用程序部署到云中时，最好不要使用您组建的“作战室”来解决第一天的问题。

[案例分析:BOK 金融如何管理其云迁移](https://thenewstack.simplecast.com/episodes/case-study-how-bok-financial-managed-its-cloud-migration)

据 BOK[的安德鲁·劳](https://www.linkedin.com/in/andrewrau/)称，当 BOK 金融，一家在过去三年里一直将应用程序转移到云的金融服务公司，在云上推出其最大的应用程序时，其工程师用“作战室类型的情况，监控一切”来支持它。

[https://www.youtube.com/embed/QPtCAx-rqC8](https://www.youtube.com/embed/QPtCAx-rqC8)

视频

“在第一天之后，系统就像预期的那样扩展了…他们就像这样，‘好吧，我想我们不再需要这个了。’"

在 New Stack 的 Makers 播客的这一集 On the Road 中，BOK 副总裁兼云服务经理 Rau 提供了一个案例研究，介绍了他的组织在过去四年中的云之旅，以及 HashiCorp 的[Vault 和云平台在其中扮演的角色。](https://www.hashicorp.com/?utm_content=inline-mention)

Rau 采访了 New Stack 的特写编辑 Heather Joslyn，谈到了将一个高度监管行业中非常传统的组织迁移到云中，同时保持严格的安全性和弹性所面临的挑战。

这集《创客》是 10 月在洛杉矶 HashiConf 录制的，由 HashiCorp 赞助。

## 提升“一切如代码”的技能

劳说，2019 年底，BOK 金融向云部署了一个小型应用程序，这是其数字化转型之旅的第一步。从那以后，它一直在构建自己的云基础设施，很快就遇到了每个云提供商的本地工具的限制。

“我们努力的地方是我们不想以不同的方式部署和管理我们的云，”他说。“我们不希望我们的云工程师只了解一家云提供商，以及他们的技术和技术堆栈。所以从那时起，我们真正开始考虑我们还能做些什么。那时 Terraform 是我们的一个很好的选择。”

2020 年，BOK 金融开始使用 HashCorp 的开源 Terraform 来自动创建云基础设施。“我们有意识地努力真正专注于自动化，”劳说。“我们不想手动操作，这实际上是传统的数据中心，几十年来我们一直是这样操作的。”

在采用 Terraform 的同时，BOK 金融的团队开始将 GitOps 流程用于 CI/CD。但是用 Rau 的话来说，做“代码化的一切”需要我们的一些员工进行大量的技能提升，因为他们从来没有做过版本控制或者自动化能力。因此，除了学习 Terraform 和其他云概念，他们还必须学习所有这些。”

然而，这一挑战是值得的:“它真的让我们能够更快地行动，并让我们的应用程序团队能够按照他们的节奏进行部署，而不是等待其他团队。”

## 寻求自动化安全性

Rau 说，花了大约一年时间，让 BOK 金融公司的开发人员适应使用 Terraform，主要是因为许多人对版本控制程序和策略不熟悉。

由于该公司在高度监管的行业中工作，处理客户的财务数据，安全性至关重要。

“我们有用户对我们的云的凭证，我们根据[开发者]正在进行的部署类型将他们分开，”Rau 说。

“但我们很难频繁地轮换这些凭据。因此，我们真的觉得有必要制作这些简短、有限的令牌，部署时间不超过一个小时。这就是我们看跳马的地方。”

HashiCorp 的秘密存储和管理工具被证明是 Terraform 的一个简单附件。“这真的让我们有能力在那里有效地没有凭据——长期凭据，”劳说。“更好地保护我们的环境。”因为 BOK 的团队不想自己管理 Vault 及其复杂性，它选择了 HashiCorp 云平台来管理它。

对于云原生之旅中的其他组织，Rau 建议花时间做正确的事情。“我们回去定期返工一些东西，因为我们学到的东西太晚了，”他说。

此外，他建议，让利益相关者参与进来:“你需要站在与业务合作伙伴、IT 领导沟通的前面，这将需要更长的时间来建立这种关系。但一旦你做到了，这是不可思议的。”

查看播客，了解有关 BOK 金融云原生转型的更多信息。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>