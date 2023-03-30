# HashiCorp 为小型团队扩展 Terraform 云

> 原文：<https://thenewstack.io/hashicorp-expands-terraform-cloud-for-smaller-teams/>

哈希公司赞助了这篇文章。

随着其 [Terraform 云基础设施管理服务](https://www.terraform.io/docs/cloud/index.html)的新定价层的推出，HashiCorp 希望允许较小的团队充分利用将基础设施作为代码进行管理所带来的好处。Terraform Cloud 的新部分增加了开源 Terraform 项目之外的商业基础设施管理功能，并允许五人以上的团队使用该产品进行协作。

[Terraform](https://www.terraform.io/) 可能是[hashi corp](https://www.hashicorp.com/)的企业基础设施管理工具系列中最知名的产品，其企业版被大型组织用来使用代码定义和管理基础设施。去年，HashiCorp 宣布计划向较小的团队提供协作功能(它认为这是该工具最引人注目的部分)，今年早些时候推出了一个基于 SaaS 的 Terraform 云功能后，它扩展了免费层中的可用功能，并于上个月在西雅图的 HashiConf 上推出了新的付费层。

Terraform Cloud 的产品营销经理 Anthony Davanzo 在接受 New Stack 采访时表示:“迄今为止，Terraform 的两种风格是开源和企业，Terraform Cloud 的目标是介于两者之间的所有人。Terraform Cloud 的免费版本最初是为单个用户设计的，[现在可供多达五个用户使用](https://www.hashicorp.com/products/terraform/pricing)，并对开源项目进行了一些扩展，例如，允许小组用户连接他们的 GitHub 存储库并一起处理 Terraform 文件。

“有时我们注意到，实践者最终会花更多的时间来尝试部署(Terraform)和了解部署方面，而不是真正花时间在实际的用例和功能上。因此，我们也想消除最初的问题或拖延，让他们使用产品，”HashiCorp 的产品营销副总裁 Amith Nair 说。

## 基础设施作为代码

需要跨更大团队协作的团队现在可以向 HashiCorp 支付每个用户每月 20 美元的 Terraform Cloud Team，其中包括基于角色的访问控制，小型但专业的团队需要这些控制才能正确使用协作工具。客户还可以以每个用户每月 70 美元的价格升级到“团队和治理”层，其中包括团队功能以及成本估计工具和 Sentinel，用于管理代码策略的合规性规则。

“就像 GitHub 为开发团队提供主分支的共享概念一样，Terraform Cloud 所做的是提供一组共享的状态，这样您就可以对您的基础架构有一个主概念。它成为一个协作点，就像 GitHub 为发展所做的那样，”HashiCorp 联合创始人兼首席技术官 [Armon Dadgar](https://www.linkedin.com/in/armon-dadgar/) 在[9 月在 hashi conf](https://www.hashicorp.com/resources/keynote-terraform-cloud-and-cost-estimation)介绍新层级的主题演讲中说道。

Terraform Cloud 只是 HashiCorp 基础设施管理产品服务名单中的最新成员，该名单还包括用于管理敏感数据的[保险库](https://www.vaultproject.io/)； [Consul](https://www.consul.io/) ，一个服务网格，旨在提高基于微服务的应用的可管理性；以及用于应用部署的 [Nomad](https://www.nomadproject.io/) 。该公司还创建并维护了另外两个面向基础设施的开源项目，包括用于构建和测试围绕虚拟机设计的应用程序的[vagger](https://www.nomadproject.io/)和用于应用程序打包的 [Packer](https://www.packer.io/) 。

![](img/62594ccf815db692b402632735649759.png)

根据最近对 Dadgar、联合创始人兼首席技术官 [Mitchell Hashimoto](http://mitchellh.com/) 和首席执行官 [Dave McJannet](https://www.linkedin.com/in/dmcjannet/) 的采访，HashiCorp 的企业版产品被用于正在进行数字化转型的大公司。桥本在采访中说，Terraform 是该公司发布的第一款产品，但采用速度比预期慢，这实际上给了 HashiCorp 更多的时间来完善产品，直到企业意识到为什么它对他们的基础设施战略有意义。

Davanzo 说，Terraform Cloud 正在小型精品云咨询公司、刚刚起步的 SaaS 提供商以及较大公司的个人团队中使用。

Nair 说:“根据我们对 Terraform 开源的总体经验，随着从业者进入并习惯于将基础设施作为代码的想法，组织中越来越多的人正在使用它。”

Terraform Cloud 还通过引入一种新的工作流程来推进 HashiCorp 不断发展的 SaaS 战略，该公司认为这是中小型企业使用 Terraform 的最有效方式。新的工作流程为用户提供了一个如何启动和运行 Terraform 的模板，首先是使用 HashiCorp 的脚本语言定义基础架构，并链接版本控制系统以自动提供应用程序。

借助新的 Terraform Cloud 功能，“我们正在让每个人都可以访问该工作流，而不仅仅是那些可以支付我们很多钱的大型企业。它所做的是帮助创建一个真正稳定的管道，让人们标准化这些工作流，然后在适合他们的时候采用企业产品，”Davanzo 说。

Davanzo 说，使用性能非常重要的应用程序的公司可能仍然希望在他们自己的服务器上或他们选择的云提供商上使用 Terraform Enterprise。他说，有一天，Terraform Cloud 可能会发展成为一种产品，甚至更大的企业都希望以服务的形式消费，但目前围绕为关键任务应用程序提供服务的技术挑战太复杂了。

“现在你有许多组织有许多遗留应用程序，这不是一夜之间的转变，这些应用程序需要与不在 SaaS 的资源对话，”Davanzo 说。

此外，新的 Terraform 云层仅限于电子邮件支持，对于环境复杂或正常运行时间对业务特别敏感的公司来说，这不会减少支持。Terraform Enterprise 附带一个服务级别协议，还集成了流行的企业单点登录工具。

但另一方面，Terraform Cloud 可能成为 Terraform 内部公司的试验场，这些公司可能希望使用企业版，但对签订更昂贵的合同持谨慎态度。

专题图片:Mitchell Hashimoto，为 HashiConf 2019 拉开序幕。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>