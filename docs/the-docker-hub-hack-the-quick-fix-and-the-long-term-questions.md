# Docker Hub Hack:快速解决方案和长期问题

> 原文：<https://thenewstack.io/the-docker-hub-hack-the-quick-fix-and-the-long-term-questions/>

这个周末，我们了解到 Docker Hub 遭到黑客攻击，190，000 个账户受损，约占用户的 5%。不幸的是，发生这种规模的黑客攻击并不令人意外。现在就在这里。Docker Hub 数据库遭到了攻击——哈希密码和访问密钥被盗。这是码头工人的[验尸报告](https://success.docker.com/article/docker-hub-user-notification)。

“改变你的信用”是过去几天推特上常见的宣言。Docker 建议所有受影响的*用户*(通过电子邮件通知他们)采取以下措施:

Docker 的安全立场使得人们的帐户受到的威胁在攻击后如何减轻变得有点不确定。Docker 的官方图片都是署名的。Docker 不提供端到端的、经过验证的安全功能来签署非官方图像。但是非官方的图像不是——这就是问题所在。开发者可以选择验证他们下载的图像，但这不是必需的。

Twistlock 的首席技术官 John Morello 写道:[令人担忧的是，一旦黑客获得了访问权限，他们可能会做些什么。攻击者可能在被访问的数据库中的图像中植入了恶意软件，恶意软件随后可以传播，从而可能产生连锁反应。没有 Docker 的更多细节，真的无从得知。](https://www.twistlock.com/2019/04/27/twistlock-recommendations-following-docker-hub-compromise/)

Morello 写道，一种可能和现实的情况是，攻击者可能悄悄在图像中下毒，“嵌入恶意软件，他们希望在互联网上的其他人从这些转发中传播出去”。不可能知道。根据它们的受欢迎程度，这可能会产生巨大的连锁反应，或者根本不会产生什么影响。

如果没有签名的图像，开发人员必须自己验证图像。大多数人选择根本不去核实。

这个问题不仅限于 Docker Hub 用户。安全专家 Kenn White 指出，这一漏洞也可能影响许多公司、私人和 GitHub 账户:

关于黑客新闻，开发人员注意到了他们现在面临的问题。一位评论者问为什么他们只能授权他们的整个 GitHub 帐户。为什么授权不能在存储库级别执行？

GitHub 的问题反映了服务如何管理第三方访问。访问令牌从 Docker Hub 通过 OAuth 传递，OAuth 使用令牌来授权 GitHub 帐户。只有 GitHub 帐户被授权，而不是存储库。

GitHub Apps 确实允许每个存储库授权。[根据 GitHub](https://developer.github.com/apps/about-apps/) 的说法，“GitHub 应用是 GitHub 内部的一流演员。GitHub 应用代表自己采取行动，直接使用自己的身份通过 API 采取行动，这意味着你不需要作为一个单独的用户维护一个机器人或服务帐户。”

根据开发人员或他们的组织使用的工具的不同，共享的过程和授予访问权限的程度也不同。这归结为授权中设置的范围。

目前，真正令人担忧的是黑客们访问了什么。还没有关于这方面的详细汇报。长期问题不那么容易解决。Docker 的安全态势已经酝酿多年。

[#9:码头工人天生缺乏安全感，黑帽观点](https://thenewstack.simplecast.com/episodes/9-dockers-inherent-lack-of-security-the-black-hat-view)

Twistlock 是新堆栈的赞助商。

来自 Pixabay 的矢量。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>