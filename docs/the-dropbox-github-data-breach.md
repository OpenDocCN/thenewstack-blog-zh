# Dropbox GitHub 数据泄露

> 原文：<https://thenewstack.io/the-dropbox-github-data-breach/>

即使是最古老的文件共享服务也可能遭受老式的网络钓鱼攻击。

早在 2007 年，[Dropbox 的创始人](https://www.linkedin.com/in/drewhouston/)、[德鲁·休斯顿(Drew Houston)](https://www.dropbox.com/)就厌倦了丢失 u 盘。所以，他创建了第一个个人/小型企业云存储服务。这是一个新的，令人兴奋的想法，每个人都喜欢它。他们非常喜欢它，以至于今天有几十个廉价或免费的云存储提供商和服务。但是 [Dropbox 仍然很受欢迎，正如其目前 78.7 亿美元的市值](https://finance.yahoo.com/quote/DBX/)所示。但是 [Dropbox 最近也遭到了网络钓鱼攻击](https://dropbox.tech/security/a-recent-phishing-campaign-targeting-dropbox)。

哎呦！

## 袭击

[Dropbox](https://thenewstack.io/specs-dropboxs-sixth-generation-of-custom-built-servers/) 在 [GitHub](https://github.com/) 于 10 月 14 日向该公司报告了 Dropbox 公司账户上的可疑活动后，意识到事情有些不对劲。结果是，一名攻击者“通过冒充代码集成和交付平台 circle ci 来访问[他们的] GitHub 账户。”

如果这听起来很熟悉，那应该是。GitHub 今年 9 月报告称，多名用户被假冒 CircleCI 的网络钓鱼攻击者[锁定为 GitHub 用户。然后黑客们获得了他们的用户证书和双因素认证代码。](https://github.blog/2022-09-21-security-alert-new-phishing-campaign-targets-github-users/)

同样的事情也发生在 Dropbox 身上。但是，Dropbox 报告称，这一点很重要，“这个威胁者从未接触过任何人的 Dropbox 账户内容、密码或支付信息。”

然而，Dropbox 本身就没那么幸运了。总共有 130 个私人 Dropbox GitHub repos 被打开复制。

这些被黑客攻击的存储库包括 Dropbox 修改的第三方库的副本、内部原型，以及——哦，所有这一切的耻辱！—一些安全团队工具和配置文件。

但是，该公司声称，入侵者没有获得 Dropbox 的核心应用或基础设施代码。Dropbox 安全团队表示，“对这些存储库的访问甚至更加有限和严格控制”。请注意，我原以为安全团队的工具和配置文件也会有同样的安全级别。

我担心 Dropbox 的关键文件没有被复制，与其说是好，不如说是幸运。

## 它是如何发生的

怎么发生的？这是常见的钓鱼故事。虽然 Dropbox 的电子邮件系统自动隔离了一些受感染的邮件，但“其他邮件却进入了 Dropboxers 的收件箱。这些看起来合法的电子邮件指导员工访问一个虚假的 CircleCI 登录页面，输入他们的 GitHub 用户名和密码，然后使用他们的硬件认证密钥将一次性密码(OTP)传递给恶意网站。"

Dropbox 承认了这次成功的攻击。太多的公司从来不承认他们被黑客攻击过。孩子们，每个人，最终都会被黑。不相信我？检查您在[上的电子邮件地址或电话号码是否已在](https://haveibeenpwned.com/)上显示。

很可怕，不是吗？

你能做的就是让它变得更难。Dropbox 就是这么做的。

认识到并非所有类型的多因素身份认证都是平等的，有些比其他更容易受到网络钓鱼的攻击。[我正看着你基于短信的双因素认证](https://www.csoonline.com/article/3673829/can-webauthn-and-u2f-finally-give-us-safe-and-easy-two-factor-authentication.html)、 [WebAuthn](https://webauthn.guide/) 是目前的黄金标准。

Dropbox 解释说:“在此事件之前，我们已经在采用这种更能抵御网络钓鱼的多因素身份认证形式。很快，我们的整个环境将由 WebAuthn 通过硬件令牌或生物识别因素来保护。”

哦，还有 Dropbox 的顾客？Dropbox 已经向其客户提供了 WebAuthn。访问他们的帮助中心[了解如何在您的 Dropbox 帐户上启用它。](https://help.dropbox.com/account-access/enable-two-step-verification#2fa-security-keys)

因此，请记住，正如[零信任安全](https://thenewstack.io/what-is-zero-trust-security/)公司 [iboss](https://www.iboss.com/) 首席执行官 [Paul Martini](https://www.linkedin.com/in/martinipaul/) 所说，“最近的数据泄露证明，即使是像网络钓鱼这样简单的攻击技术也能够影响像 Dropbox 这样庞大而复杂的公司。威胁参与者能够获得访问权限，并通过窃取凭据和代码库快速移动。”如果您还没有开始将您的公司迁移到零信任或 [WebAuthn](https://thenewstack.io/deprecation-from-u2f-api-to-webauthn/) 安全环境，现在就开始迁移吧。

最后，如果你觉得你的 Dropbox 账号被黑了，[你可以在这里](https://www.dropbox.com/report_abuse)向 Dropbox 举报。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>