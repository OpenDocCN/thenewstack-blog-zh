# 主要目标:保护应用程序工作负载

> 原文：<https://thenewstack.io/the-main-goal-secure-the-application-workload/>

去年底，在公司的 Ignite 大会上， [Prisma Cloud](https://www.paloaltonetworks.com/prisma/cloud) 、[Palo Alto Networks](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention)的首席技术官 [Ory Segal](https://www.linkedin.com/in/orysegal/?originalSubdomain=il) 说:“网络安全行业存在问题。“这就是我们短暂的注意力持续时间。新技术使我们偏离了主要目标。我们的主要目标是保护应用程序的安全。仔细想想，我们的客户正在构建应用程序。他们不做造云的生意。因此，向他们销售云安全不是我们应该做的。我们应该向他们销售应用安全性。”

客户保护应用程序，但是开发人员面临一个迫在眉睫的问题。，即具有易受攻击的第三方依赖性的不安全的软件供应链。应用安全环境看起来更像是一个网络，具有以 API 为中心的架构和需要保护的多层。

“如果我们回顾一下上世纪 90 年代末和本世纪初的应用，我们有物理基础设施，有网络，应用程序和数据层，”Segal 说。“应用程序看起来非常简单。我们有网络服务器、网络后端、数据库，差不多就是这些。保护这些应用程序非常容易。你可以从外围或防火墙布线，差不多就是这样。”

今天，有数以千计的应用安全点工具。PAN 的目标是帮助客户整合成端到端的方法，PAN[称之为代码到云。目标:提供一个平台来保护基于依赖于多个 API 的微服务构建的云原生架构。](https://thenewstack.io/a-look-at-the-palo-alto-networks-upcoming-code-to-cloud-summit/)

Segal 说，攻击者知道如何遍历应用程序来访问数据。他们将从应用层开始，例如，一个将文件存储在云中的 web 表单。一个 API 调用将从应用层发送到工作负载，工作负载将执行其逻辑并从存储桶中提取文件，从而允许信息泄漏。

## 检查数据包

点工具提供微观视图，查看链中的每个点。可能有一个用于 API 调用的工具，或者在 web 应用防火墙(WAF)前面有一个工具。

Segal 说，有两种替代点工具方法的方法。服务提供商可以采用管道方法，从不同的供应商那里获取数据来创建覆盖洞察。

“我认为从安全供应商的角度来看，弊大于利，”Segal 说。主要是因为你必须依赖来自其他人的信号，它们的质量，它们的格式，你必须不断更新你消费数据的方式。更容易开发。"

西格尔说，潘遵循“一环”的方法。它允许 PAN 控制平台和底层分析。反过来，这提供了更好的安全性，因为供应商拥有信号，在这种情况下，PAN。

“是的，这更难，因为你必须拥有建立所有这些分析中心的技术、知识和诀窍，”西格尔说。“但是作为安全供应商，您从中获得的好处是巨大的。”

“Prisma cloud 是一个有助于保护云原生应用的平台，”Segal 说。“它不是云安全平台。我知道这个名字有误导性。这是一个云原生应用保护平台，它从左到右提供不同的模块，从检测漏洞、秘密、基础设施、代码问题，一直到我们提供 web API 安全模块来防止针对 API 的攻击。”

## 集成安全性

旅游行业的长期软件提供商 [Sabre Technologies](https://www.sabre.com/) 的首席信息安全官 Scott Moser 在大会上表示，已经集成的安全工具比跨多个工具及其各自的 API 工作更适合 Sabre。

“我宁愿让我的团队使用安全工具，而不是花时间集成这些安全工具，”Mosier 说。

Segal 说，团队使用的工具通常因应用程序安全性而异，这取决于应用程序堆栈中的层。CI/CD 环境的动态性和新工具的不断增加进一步增加了复杂性。这个过程如此之快，以至于代码从存储库到生产可能只需要几分钟。

潘收购[苹果酒安全](https://www.paloaltonetworks.com/company/press/2022/palo-alto-networks-completes-acquisition-of-cider-security#:~:text=SANTA%20CLARA%2C%20Calif.%2C%20Dec,and%20software%20supply%20chain%20security.)体现了该公司的左倾策略。Cider 是一个软件供应链安全的平台。Cider 安全服务为开发人员提供了 CI/CD 中使用的基础设施和工具的视图，以确定他们带来的风险。代码不是苹果酒的焦点；它知道开发人员使用的无数工具。

[https://www.youtube.com/embed/_kZ8Bo6TKaY?feature=oembed](https://www.youtube.com/embed/_kZ8Bo6TKaY?feature=oembed)

视频

CI/CD 工具的选择为攻击者提供了充足的攻击机会。所有的工具都会给代码带来风险。开发人员需要对工具配置有更多的了解。苹果酒安全减轻了这些风险。它充当与客户解决方案集成的总体元素。

默认情况下，整个 CI/CD 工作流是可编程的，这为 Cider 提供了一种为 Jenkins、GitLab 或 GitHub 等平台提供 PAN 集成的方式。通过提供更深层次的集成，PAN 提供了在与工程师打交道时管理复杂性的能力。

苹果酒技术仍然需要集成到 Prisma Cloud 中。

多伦多地区 [Omdia](https://omdia.tech.informa.com/) 的高级首席分析师 Fernando Montenegro 说:[应用程序安全的平台方法正在兴起。他说，潘与趋势科技、CheckPoint 和 Rapid7 等公司竞争。来自 Sysdig、Lacework、Snyk、Orca 等公司的竞争日益激烈，这些公司提供集成了安全工具的持续交付工具。](https://omdia.tech.informa.com/authors/fernando-montenegro)

Montenegro 表示，需要考虑一些细微差别，例如，客户是否可以使用现有供应商提供的用于 CI/CD 或其他应用程序安全方面的产品。

在一篇 Twitter 帖子中，我向人们询问了 CI/CD 安全性、其复杂性以及如何保护它。让我们看看人们都说了些什么。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>