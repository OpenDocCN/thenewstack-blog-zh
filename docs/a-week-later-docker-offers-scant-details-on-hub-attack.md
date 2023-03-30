# 一周后，Docker 提供了很少关于网络中心攻击的细节

> 原文：<https://thenewstack.io/a-week-later-docker-offers-scant-details-on-hub-attack/>

引用一项正在进行的调查，Docker 在其年度 [DockerCon 用户大会](https://thenewstack.io/dockercon-2019-all-about-the-end-to-end-container-lifecycle/)上提供了一些关于[上周对 Docker Hub](https://thenewstack.io/docker-hub-compromised-users-urged-to-reset/) 的攻击的细节，该攻击导致 190，000 个用户账户被曝光——这种缺乏初始透明度的情况让一些用户担心。

在主题演讲的第二天，官方首次提到了 DockerCon 的违规行为。Docker 首席技术官 [Kal De](https://www.linkedin.com/in/kalde/) ，作为该公司正在测试的新技术演示的一部分。

“我们将尽最大努力尊重您对我们的信任，为此，作为一家公司，我们必须非常认真地对待安全问题，并将继续全力以赴。我只是想非常清楚地表明，这是我们最关心的事情，”德对人群说。

然而，除了在 Docker Success 门户网站上提供一个[常见问题](https://success.docker.com/article/docker-hub-user-notification)页面外，该公司迄今没有提供关于此次攻击的必要细节，该公司承诺会经常更新该页面。但对于攻击者进入系统多长时间，攻击如何影响其他 Docker 系统，以及攻击中损害了哪些软件(Docker 自己的或第三方软件)或进程，目前还没有消息。也没有任何可以立即做出改变的承诺，例如添加双因素身份认证(2FA)，这可能会进一步限制此类攻击的潜在损害。

在周三的 DockerCon 新闻发布会上，Docker 首席执行官兼董事长史蒂夫·辛格(Steve Singh)简要讨论了 Docker 正在采取的了解所发生事情的过程。该公司有一个调查违规行为的协议，并正在遵守。这个过程类似于辛格在他之前的公司——费用管理服务提供商 [Concur](https://www.concur.com/) 使用的剧本。辛格承认,[在回答 eWeek 记者](https://www.eweek.com/security/docker-responds-to-data-breach-and-outlines-the-container-future)[肖恩·肯纳](https://twitter.com/TechJournalist)的一个问题时,【Docker】保留了第三方法医调查员的服务。

辛格引用这项正在进行的调查，拒绝回答新堆栈提出的关于入侵者访问 Docker Hub 多长时间的问题，或者是否有任何其他系统被入侵。他强调，该公司在发现漏洞后立即通知了受影响的用户，并披露了当时可能披露的一切。

“世界上有糟糕的演员。他们做一些我们不得不应对的事情，”辛格说。他提出了为“供应链攻击”做准备的主题，这是最近的一个明显趋势，攻击者一直专注于在上游基础设施软件中嵌入恶意代码，这些代码可用于劫持组织的运营。他说，供应链公司需要研究一种“设计安全”的方法来防止这种情况发生，并补充说，“这是我们说‘让我们承认这个问题’的一个机会。”"

辛格断言，总体而言，Docker 中心的范围“非常小”。“我们以最快的速度做出了响应，并在了解违规行为和受影响者后尽快通知了我们的用户。”

## 潜在影响

至少有一名安全专家持不同观点。

“我们知道的还不够多。它可能会很有影响力。这可能会对整个世界产生很多影响，”Twistlock 首席执行官 John Morello 在接受即将到来的 [TNS 制造商播客](https://thenewstack.io/podcasts/makers)采访时说。正如其他人所指出的，攻击者可以使用暴露的 GitHub 和 BitBucket 凭据来毒害这些存储库中的整个私有软件存储库。他说，如果攻击者在他们所做的事情上是聪明和有策略的，他们可能“可能会影响很多企业”。

“Docker Hub 不是目标。这只是一个渠道，”他说。“如果你知道组织 X 正在使用 Docker Hub，并且你想打入该组织，那么 Docker Hub 将是实现这一目标的途径。”

Morello 说，这就是为什么对于 Docker Hub 用户来说，拥有攻击者首次进入的完整时间表是如此重要。有了明确的时间表——假设攻击发生在 30 天前或 3 个月前——安全管理员可以在该时间范围内检查日志中的可疑活动。他说，如果没有攻击可能发生的确切时间范围，“人们很难回过头来搞清楚什么是真实的，什么可能是可疑的”。

通常情况下，云服务提供商，如[亚马逊网络服务](https://aws.amazon.com/message/2329B7/)和[微软 Azure](https://blogs.msdn.microsoft.com/vsoservice/?p=17485) 会发布详细的“事后”报告，详细说明到底哪里出了问题，以及通常为防止类似事故再次发生而采取的措施。然而，这些详尽的报告可能需要一些时间来编译。

更糟糕的是，Docker 不愿意加入 2FA 认证，这需要另一种形式的身份识别，如指纹或电话转接密码，这是除了 DockerHub 密码之外的要求。他说，即使是小的信用合作社也有实施 2FA 的技术人才，所以这对 Docker 来说应该不成问题。

“如果我经营 Docker Hub，那将是我的首要任务，”Morello 说。

## 码头中心维护

Docker Hub 上似乎正在进行工作，可能是为了修复攻击者用来进入的漏洞。该公司周五提醒用户，美国太平洋夏令时大约上午 9 点至下午 7 点 15 分“正在进行定期维护”。

“在此期间，Docker Hub 将以只读模式运行。注册表登录和映像获取将在此时间段的大部分时间内继续工作。然而，推送通常是不可用的，”该公司在一封电子邮件中提醒用户。

TNS 出版商 Alex Williams 为本文做出了贡献。

Twistlock 是新堆栈的赞助商。Docker 支付了记者参加 DockerCon 的旅费。

专题图片:Docker 首席技术官 Kal De，在 DockerCon 2019。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>