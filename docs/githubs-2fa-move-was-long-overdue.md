# Github 的 2FA 迁移早就应该进行了

> 原文：<https://thenewstack.io/githubs-2fa-move-was-long-overdue/>

5 月 4 日， [GitHub](https://github.com/) 的首席安全官[迈克·汉利](https://www.linkedin.com/in/michael-hanley-b6508913/)宣布，所有上传代码到[网站的用户必须在 2023 年底前启用一种或多种形式的双因素认证](https://github.blog/2022-05-04-software-security-starts-with-the-developer-securing-developer-accounts-with-2fa/)(2FA)……否则离开。是时候了！

如果你在过去的几年里睡着了，软件供应链攻击已经变得司空见惯。保护它最简单的方法之一是使用 2FA。 [2FA 简单](https://www.idginsiderpro.com/article/3529877/why-two-factor-authentication-doesnt-make-you-as-secure-as-you-think.html)。除了使用用户名/密码对来识别您自己，您还可以使用第二个因素来证明您的身份。

## 三个标准

在表面之下，2FA 变得复杂起来。他们依赖三个标准中的一个:[基于 HMAC 的一次性密码(HOTP)](https://tools.ietf.org/html/rfc4226) 。[基于时间的一次性密码(TOTP)](https://tools.ietf.org/html/rfc6238) ，或者 [FIDO 联盟](http://fidoalliance.org/)的 [FIDO2](https://www.yubico.com/authentication-standards/fido2/) [通用第二因子(U2F)标准](https://www.yubico.com/authentication-standards/fido2/)。但是，作为开发人员，您不需要担心这一点，除非安全性、身份验证和身份是您的事情。正如汉利所说，你只需要“启用一种或多种形式的 2FA”

## 顽固无知的开发者

没那么难。尽管如此，“今天，只有大约 16.5%的 GitHub 活跃用户和 6.44%的 npm 用户使用一种或多种形式的 2FA。”[为什么开发者都那么固执的愚蠢](https://thenewstack.io/why-open-source-project-maintainers-are-reluctant-to-use-digital-signatures-two-factor-authentication/)？

正如 GitLab 高级安全研究员马克·洛夫莱斯最近所说，“二级认证因素采用率低的主要原因是，开启任何多因素认证(MFA)都是一个额外的步骤，因为它很少被任何软件包默认开启。”我们讨厌多走一步。

请注意，更大项目中更聪明的开发人员确实明白这一点。GitHub 的产品安全工程总监 Patrick Toomey 最近观察到“成熟项目的开源维护者(超过 100 个贡献者)使用 2FA 的可能性是普通用户的三到四倍这并不奇怪，因为“更大和更受欢迎的项目意识到它们在开源软件供应链中的地位和责任。此外，这些项目通常成为 GitHub 组织，能够使用团队管理对其存储库的访问，并设置安全策略，包括启用 2FA 的要求。”

人们拒绝得到 2FA 线索的另一个因素是简单的无知。例如，关于这个问题的 Reddit 编程 subreddit 上的一个讨论显示，许多人认为 2FA 要么很难(剧透:它不是)要么不那么安全，因为它使用电话。没错，[使用短信的 2FA 相对容易破解](https://appdevelopermagazine.com/5590/2017/10/4/Sending-out-an-S.O.S.-for-SMS/)。问问推特的创始人杰克·多西就知道了。由于 SIM 卡互换攻击，多尔西自己的推特账户被劫持。

## 不仅仅是短信

但这里重要的一点是，你不需要使用你的短信，又名短消息服务(SMS)。对于 [2FA，GitHub 明确告诉你也可以使用](https://github.blog/2021-08-16-securing-your-github-account-two-factor-authentication/):

*   物理安全密钥，如 [YubiKeys](https://yubico.com/github)
*   内置于个人设备中的虚拟安全密钥，例如支持 WebAuthn 技术的笔记本电脑和手机，如 Windows Hello 或 Face ID/触控 ID
*   TOTP 认证器应用，如 [Authy](https://authy.com/) ，开源、[FreeOTP](https://freeotp.github.io/)；[谷歌认证器](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2&hl=en_US&gl=US)，或者[微软认证器](https://www.microsoft.com/en-us/security/mobile-authenticator-app)。

## 没那么难

没那么难，伙计们！真的不是。至于那些抱怨“这会扼杀项目”的人—任何因为开发人员不能做到基本的 2FA 安全性而被扼杀的项目都不如死了好。

长期以来，在开源社区中，我们太倾向于认为黑客只攻击专有程序。正如詹姆斯·阿尔伦、[艾文·CISO](https://aiven.io/)(首席信息安全官)所观察到的，“过去 30 多年来，开源软件开发的现实一直基于开发者之间的信任网络。这在早期是通过个人关系来维持的，但已经发展到超出人类认识所有其他人的能力。随着 GitHub 向开发者提供更深入的身份验证要求，它将大大降低开发者遭受帐户接管的可能性以及违反信任的可能性。”简而言之， [Angel Borroy](https://www.linkedin.com/in/angelborroy/?locale=en_US) ，一个 [Hyland](https://www.hyland.com/en) 开发者传道者，告诉我，“坏人也能看到开源代码”。

GitHub 给你的期限是 2023 年。他们真是太好了。你的 GitHub 账户被劫持是一个真实存在的危险。今天采用 2FA。不仅要在 GitHub 上采用 2FA，还要在你所有的代码库和在线服务上采用 2FA。这是当今保护您自己和您的代码免受攻击者攻击的最佳方式。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>