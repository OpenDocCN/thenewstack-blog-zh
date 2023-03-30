# 为什么城堡和护城河式的安全方法已经过时

> 原文：<https://thenewstack.io/why-the-castle-and-moat-approach-to-security-is-obsolete/>

以下节选自 New Stack 的最新电子书《不要相信任何人，自动化(几乎)一切:建立现代零信任策略》

[Register here](https://thenewstack.io/ebooks/security/trust-no-one-and-automate-almost-everything-building-a-modern-zero-trust-strategy/)

免费下载我们的电子书，由 Torq 赞助。

曾几何时，IT 资源生活在城堡(也称为“数据中心”)中，受到护城河(防火墙)和骑士(您友好的安全专家)的保护。在过去的日子里，假设很简单:城堡里的一切都是温暖而模糊的；城堡墙外的一切都是充满敌意的荒野。

在很久以前，也就是 20 世纪 90 年代之前，这种方法很管用。[尽管零信任](https://thenewstack.io/why-cloud-native-systems-demand-a-zero-trust-approach/)作为一种实践或理论，直到很久以后才得到发展，但直到 20 世纪 90 年代，城堡的墙壁才开始出现裂缝。

这一背景很重要，因为尽管零信任经常在[云原生](https://thenewstack.io/category/cloud-native/)系统方面被讨论，但对[零信任](https://thenewstack.io/what-is-zero-trust-security/)和远离基于边界的[安全性](https://thenewstack.io/category/security/)的需求早就开始了。

## 城堡

当整个 IT 系统位于一个中央数据中心时，网络安全就容易多了。

IAM 和 API 安全技术提供商 [Curity](https://curity.io/?utm_content=inline-mention) 的销售工程总监 [Jonas Iggbom](https://www.linkedin.com/in/iggbom/?trk=eml-msg_digest-body-view_profile&midToken=AQGjwNFX7Vsm2Q&midSig=0GsTWhjjX0Xq81&trkEmail=eml-email_premium_inmail_reply_single_01-null-1-null-null-17zici%7El0r8rwba%7E85-null-neptune%2Fprofile%7Evanity%2Eview) 说:“外围类型的方法，即历史方法，效果相当不错。"这是防火墙可以控制的一个入口."

由于所有 IT 资产都在一个受防火墙保护的网段上，并且可以严格监控有限的接入点，因此该系统运行良好。仍然有局限性——如果防火墙被攻破，网络内部就没有安全可言，所以一旦突破防火墙，攻击者就几乎可以完全控制系统。

问题首先从笔记本电脑和出差族开始。IT 安全部门应该如何看待销售人员 20 磅重的笔记本电脑上的文件？当你从黑莓手机上访问公司邮件时会怎样？

“我们是不是应该把它当成里面的？”安全自动化公司 [Torq](https://torq.io/?utm_content=inline-mention) 的联合创始人兼首席技术官 Leonid Belkind 问道。“企业数字化的现实——采用移动性，允许人们从任何地方、通过任何设备工作——是这破坏了非常明确的‘谁在外面，谁在里面’的整个方法。”"

他指出，接下来是云，以软件即服务(Saas)和基础设施即服务(IaaS)的形式出现。

在[容器](https://thenewstack.io/category/containers/)或[微服务](https://thenewstack.io/category/microservices/)或任何我们现在称之为云原生的东西出现之前，这座城堡正滑向废墟。它需要一种完全不同的安全方法。

## 一个人的堡垒

起初，安全策略的转变是从保护一个单一的城堡到“多个城堡”的方法。在这种情况下，您会将每个销售人员的笔记本电脑视为一种卫星城堡。

SaaS 的供应商和云提供商利用了这一想法，试图说服潜在客户，他们不需要一种完全不同的方式来考虑安全性，而是通过使用 SaaS 的产品，他们在供应商的城堡中租用了一个位置。

问题是，一旦你有了这么多的城堡，相互联系就变得越来越难以保护。很难说清楚什么是你的网络“内部”,什么是敌对的荒野。

零信任假设城堡系统已经完全崩溃，因此每个单独的资产都是一个人的城堡。一切总是充满敌意的荒野，你在无法完全信任任何人的假设下运作。

对社会来说，这不是一个有吸引力的愿景，这就是为什么我们可能应该放弃城堡和护城河的比喻。因为在我们的网络安全方法中消除人类的信任概念，将每个用户都视为潜在的敌人是有意义的。

## 采用零信任

根据微软 2021 年 7 月发布的[调查](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWGWha?utm_source=thenewstack&utm_medium=website&utm_campaign=platform)，96%的安全决策者认为零信任对于有效的安全态势至关重要。但是，尽管对零信任理念的支持几乎是普遍的，但很少有公司能有效地实施这一理念。

![Infographic titled "IT Leaders Believe Zero Trust Is Critical." On the left is a pie chart showing that 96% of IT leaders believe zero trust security is "very or somewhat critical." On the right is a table showing top motivators for zero trust: 47% say it improves security posture. 44% say it improves end user experience and productivity, 38% say it transforms the way security teams work together, and 35% said it improves the security stack and reduces security costs. Data from 2021 "Zero Trust Adoption Report" by Microsoft, 2021, ](img/f368b9a2f3795cd65946818958217858.png)

技术决策者普遍认为零信任安全方法对他们的组织至关重要。

根据 strongDM 的 2022 年调查，65%的公司使用共享登录，42%的公司使用共享 SSH 密钥；这两种做法都与零信任原则完全背道而驰。零信任不仅需要重新思考您的安全程序，还需要重新设计您的应用程序，以使新策略成为可能。

实现从粒度认证系统开始，这意味着强制任何想要访问资源的用户，无论是人还是服务器，证明他们是他们所说的那个人。

一旦对用户进行了身份验证，下一步就是授权或强制执行:是否允许用户执行它想要执行的操作？根据 Iggbom 的说法，身份验证被广泛采用，但是很少有组织跟进零信任授权系统。

大多数系统之前已经设置好了，这样人们就可以认证进入城堡——一组动作。零信任与众不同的一点是，它需要极高的粒度，允许用户在他们请求访问的特定时间，只访问或更改他们请求访问的特定资源。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>