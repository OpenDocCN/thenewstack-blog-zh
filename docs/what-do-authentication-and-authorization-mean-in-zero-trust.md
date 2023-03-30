# 认证和授权在零信任中意味着什么？

> 原文：<https://thenewstack.io/what-do-authentication-and-authorization-mean-in-zero-trust/>

编者按:以下节选自 New Stack 的最新电子书《不要相信任何人，自动化(几乎)一切:构建现代零信任策略》

[Register here](https://thenewstack.io/ebooks/security/trust-no-one-and-automate-almost-everything-building-a-modern-zero-trust-strategy/)

获得 Torq 赞助的免费电子书。

实施[零信任安全](https://thenewstack.io/what-is-zero-trust-security/)原则的基础是[认证和授权](https://thenewstack.io/how-do-authentication-and-authorization-differ/)。他们的意思实际上很简单，但是在零信任和其他系统中身份验证和授权的具体工作方式是不同的。

[https://www.youtube.com/embed/x3Uk22OZ-I0](https://www.youtube.com/embed/x3Uk22OZ-I0)

视频

认证仅仅意味着证明用户，无论是人还是计算机用户，确实是他们所声称的那个人。

授权意味着一旦我们确定了用户的身份，这个人或服务就被允许访问它请求访问的资源。

“认证和授权不一定会改变它们在零信任环境中的意义，”安全自动化公司[Torq](https://thenewstack.io/category/security/)的首席技术官和联合创始人 [Leonid Belkind](https://www.linkedin.com/in/leonidbelkind/) 说。

“如果有的话，认证会变得更加严格，如果你授权得当，授权会变得更加细致，”他说。“我可以访问我的公司数据中心并随心所欲地使用它吗？”您会要求在这个特定的时间点，从这个特定的位置，使用这个特定的设备，在这个特定的应用程序中，在我的数据中心的这个特定的部分中，访问这个特定的文档。"

授权依赖于身份验证。如果您没有任何适当的机制来确保用户或服务确实是他们所说的那样，那么授权用户是没有意义的。

大多数组织都有一些处理身份验证的机制，许多组织都有基于角色的访问控制(RBAC ),将用户按角色分组，并根据这些角色授予或拒绝访问权限。然而，在零信任系统中，身份验证和授权都要精细得多。

回到我们之前探讨过的[城堡类比](https://thenewstack.io/why-the-castle-and-moat-approach-to-security-is-obsolete/)，在零信任之前，网络被认为是一座城堡，城堡内有许多不同类型的资产。在大多数组织中，人类用户将被单独认证——不仅要证明他们属于某个特定的角色，还要证明他们确实是他们所说的那个人。

服务用户通常也可以被精确地认证。然而，在 RBAC 系统中，每个用户都是以组为基础被授予或拒绝访问权限的——例如,“admin”类别中的所有人类用户都将获得全面的访问权限。

也不可能只允许用户访问城堡内的部分资源:站在吊桥上的骑士可以进来并获得全部权限，或者被拒之门外。

换句话说，不能授予粒度访问权限。实际上，这通常意味着人类和计算机用户都被授予了过多的权限。

根据帕洛阿尔托网络公司[Prisma Cloud](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention)最近的[云威胁报告](https://thenewstack.io/unused-credentials-key-culprits-in-cloud-attacks-study-says/)，99%的云用户、角色、服务和资源被授予了他们不使用的权限，换句话说，就是他们不需要的权限。

## 越来越精细

零信任最重要的一个方面是粒度。在零信任系统中，基于角色授予访问权限是不够安全的。访问请求必须是细粒度的，并且只能在固定的时间内访问单个资源。

这需要组织将他们的城堡分解成单一资源的堡垒。这个特殊的类比很好地说明了走向零信任所必须发生的架构转变:只有在围绕它创建了适当的结构之后，授予粒度访问权才是可能的。

![Infographic: What Do Permissions Mean in a Traditional Vs. Zero Trust Architecture? On the left, shows a drawing of a castle with a bag of money, a map and a bottle that can all be accessed by one key and lock: Traditional Infrastructure and data live in a single location (or "castle"). Access is granted broadly to an authenticated user. On the right, shows three castles, each with of the items in them and three separate keys and locks. Zero Trust The network is distributed among many "castles." Authenticated users are granted granular, time-limited access to specific assets.](img/faba24f8435bfd921c4af02ffae7c8da.png)

零信任策略有助于减少授予过多不必要的权限，这些权限很容易被用来非法访问网络。

零信任策略有助于减少授予过多不必要的权限，这些权限很容易被用来非法访问网络。

将资源分成更细粒度的组件的想法与微服务背后的原则大体相同。随着服务被分解成更小的部分，数据被分解成更小的部分，更有可能进行细粒度的访问授权。

当你所有的资源都聚集在一个“城堡”里，当人们进入某个特定的房间时，没有机制把他们送走，实现零信任是不可能的。

## 自动化的作用

在谈论零信任环境中的身份验证和授权时，有时会有一个假设，即该过程必须总是 100%自动化的。不是这样的。

显然，如果没有一些自动化工具，在零信任系统中不可能完成任何事情。但是有些类型的请求可以，也应该，由人工审查。

“事实上，对于零信任网络访问的用户，该系统可以是半自动的，它可以让人们参与进来，”贝尔金德说。“我不一定认为我们在谈论机器对机器的通信。”

## 限时授权

对零信任系统最常见的误解之一是，一旦用户通过了身份验证和授权，该用户就成为了“可信”用户。用户可以在任何时候进出要塞。

然而，在真正的零信任实现中，没有可信用户或可信设备。用户每次试图访问资源时都必须经过身份验证和授权。

在真正的零信任架构中，授权会有一个时间窗口:这个用户被允许在这个时间窗口中执行这个特定的操作。用户和相关设备都不会变得可信。

在现实世界中，绝大多数安全领导者都承认零信任的重要性。IAM 和 API 安全技术提供商 [Curity](https://curity.io/?utm_content=inline-mention) 的销售工程总监 [Jonas Iggbom](https://www.linkedin.com/in/iggbom/?trk=eml-msg_digest-body-view_profile&midToken=AQGjwNFX7Vsm2Q&midSig=0GsTWhjjX0Xq81&trkEmail=eml-email_premium_inmail_reply_single_01-null-1-null-null-17zici%7El0r8rwba%7E85-null-neptune%2Fprofile%7Evanity%2Eview) 说:“你需要首先对用户和系统进行认证，但并不是每个人都实施了这一基本步骤。

“但接下来你需要重新考虑一个事实，是的，你是乔纳斯，但你被允许访问这些信息吗？这种执行在组织中更少实施。在这一点上，对于组织来说，真正实施它仍然有相当大的难度。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>