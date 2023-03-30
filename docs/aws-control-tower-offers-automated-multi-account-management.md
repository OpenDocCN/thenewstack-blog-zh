# AWS 控制塔提供自动化的多帐户管理

> 原文：<https://thenewstack.io/aws-control-tower-offers-automated-multi-account-management/>

[Twistlock](https://www.paloaltonetworks.com/prisma/cloud) 赞助本文，由新栈独立撰写。

在上周举行的首届 [AWS re:Inforce](https://reinforce.awsevents.com/) 大会的主题演讲中，自动化是一个关键主题，虽然自动化的想法可能会立即激发[使用 Lambda 提供自动化补救](https://docs.paloaltonetworks.com/evident/evident-web-reference-help/control-panel/auto-remediation-lambda-walkthrough)的想法，但自动化也可以帮助完成不太花哨的任务，例如使用 [AWS 控制塔](https://aws.amazon.com/controltower/)设置多帐户 AWS 环境。

虽然一些用户可能喜欢提前访问控制塔，但 AWS 首席信息安全官 Stephen Schmidt 在主题演讲中宣布，该工具现在将对所有 AWS 客户开放。根据[博客文章](https://aws.amazon.com/blogs/aws/aws-control-tower-set-up-govern-a-multi-account-aws-environment/)详细介绍了该版本及其实现，Control Tower“自动化了建立一个新的基线多帐户 AWS 环境的过程，该环境是安全的、架构良好的，并且随时可以使用。”

[https://www.youtube.com/embed/daLvEb44d5Q?feature=oembed](https://www.youtube.com/embed/daLvEb44d5Q?feature=oembed)

视频

有了控制塔，安全性以着陆区和护栏的形式融入到新创建的多帐户 AWS 环境中。着陆区是由控制塔设置的整体多帐户环境，包括“一个基线环境，用于开始多帐户体系结构、身份和访问管理、治理、数据安全、网络设计和日志记录。”与此同时，Guardrails 是“策略控制的自动化实施，重点是安全性、合规性和成本管理”，它可以根据某些规则阻止用户活动，或者在检测到某些不符合规定的活动时发出警报。通过使用 Control Tower，您的基准环境将包括使用 AWS 组织的多帐户环境、使用 AWS 单点登录(SSO)的身份管理、使用 AWS SSO 的联合帐户访问、来自 AWS CloudTrail 的集中日志记录、存储在亚马逊 S3 的 AWS 配置，以及使用 AWS IAM 和 AWS SSO 的跨帐户安全审计。

在接受新堆栈采访时，[AWS market place 副总裁 Dave McCann](https://www.linkedin.com/in/dave-mccann/) 解释说，Control Tower 带来了与其他 AWS 服务的深度集成，如 [AWS 组织](https://aws.amazon.com/organizations/)、 [AWS 身份和访问管理(IAM)](https://aws.amazon.com/iam/) 、 [AWS 配置](https://aws.amazon.com/config/)、 [AWS CloudTrail](https://aws.amazon.com/cloudtrail/) 和 [AWS 服务目录](https://aws.amazon.com/servicecatalog/)。此外，控制塔配备了许多预配置的“护栏”，或规则集，还有更多。

该软件已被原生集成到 70 个 AWS 服务中。“通过整合到我们自己的服务中，我们已经能够深入整合到我们的文化中，”McCann 说。版本 1 带有 25 个标准护栏。第二波将在八月到来，第三波将在秋天到来。今年秋天，该公司将推出 am API，以便其他人可以引入他们自己的规则。

尽管控制塔的最终目标是企业客户，但 McCann 解释说，它目前最适合不打算导入现有指南的绿地客户。

“它是为扩大规模而设计的，您可以发布的帐户数量没有限制，因此我们认为它不会受到组织规模的限制。从成熟的角度来看，Control Tower 的第一个版本是针对那些早期采用 AWS 的人的，”McCann 说。“随着我们在短期内增加更多功能，到今年年底，我们打算适用于我们最成熟的客户，但现在，有一些成熟客户想要的东西我们今年不会有。”

AWS 控制塔目前对美国东部(N. Virginia)、美国东部(Ohio)、美国西部(Oregon)和欧洲(Ireland)地区的所有 AWS 用户免费开放，更多地区还将开放。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>