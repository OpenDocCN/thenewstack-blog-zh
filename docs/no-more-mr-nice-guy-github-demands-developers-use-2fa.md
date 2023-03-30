# 好人先生:GitHub 要求开发者使用 2FA

> 原文：<https://thenewstack.io/no-more-mr-nice-guy-github-demands-developers-use-2fa/>

去年， [GitHub](https://github.com/) 的 CSO [Mike Hanley](https://www.linkedin.com/in/michael-hanley-b6508913/) 宣布，所有上传代码到[网站的用户必须在 2023 年底启用一种或多种形式的双因素认证](https://github.blog/2022-05-04-software-security-starts-with-the-developer-securing-developer-accounts-with-2fa/)(2FA)……否则。[许多安全问题过后](https://thenewstack.io/github-repositories-werent-hacked/)，GitHub 决定不再等待了。从 3 月 13 日起， [GitHub 用户必须开始注册 2FA。](https://github.blog/2023-03-09-raising-the-bar-for-software-security-github-2fa-begins-march-13/)

我只能说:“是时候了！”

如果你在过去的几年里一直在打瞌睡，软件供应链攻击已经变得司空见惯。保护代码最简单的方法之一是使用 2FA。 [2FA 简单](https://www.idginsiderpro.com/article/3529877/why-two-factor-authentication-doesnt-make-you-as-secure-as-you-think.html)。

## 这很复杂

在引擎盖下，2FA 很复杂。它依赖于三个标准之一:[总部位于 HMAC 的一次性密码(HOTP)](https://tools.ietf.org/html/rfc4226) 。[基于时间的一次性密码(TOTP)](https://tools.ietf.org/html/rfc6238) ，或 [FIDO 同盟](http://fidoalliance.org/)的 [FIDO2](https://www.yubico.com/authentication-standards/fido2/) [通用第二因子(U2F)标准](https://www.yubico.com/authentication-standards/fido2/)。但是，作为开发人员，您不需要担心这个问题，除非安全、身份验证和身份是您的事情。正如汉利所说，您只需要“启用一种或多种形式的 2FA”。

有那么难吗？我想是的。虽然我还没有掌握任何 2023 年的数字，但在 2022 年，只有少数 GitHub 用户使用 2FA。

幸运的是，即使您对 2FA 过敏， [GitHub](https://thenewstack.io/github-acquires-npm-buying-microsoft-a-presence-in-the-node-javascript-community/) 也能让 2FA 防白痴。好吧，或者像保安一样防白痴。

1.  2FA 设置后的第二因素验证:在 GitHub.com 设置 2F 的用户将在 28 天后收到提示，确认他们的 2FA 设置。这将有助于防止由配置错误的身份验证器应用程序导致的帐户锁定。如果您无法正常工作，您可以重置您的 2FA 设置，而不会被锁定在您的帐户之外。
2.  注册第二个因素:拥有多种可访问的 2FA 方法以确保帐户访问非常重要。用户现在可以在自己的账户上同时注册一个认证应用(TOTP)和一个短信号码。虽然我们建议通过短信使用安全密钥和 TOTP 应用程序，但启用这两个选项可以通过提供另一个可访问的 2FA 选项来降低帐户锁定的风险。
3.  选择您的首选 2FA 方法:用户现在可以为帐户登录和 sudo 提示设置他们的首选 2FA 方法。登录时将首先使用首选方法，用户可以选择 TOTP、短信、安全密钥或 GitHub Mobile。我们强烈建议尽可能使用安全密钥和 TOTPs，因为在 NIST 800-63B 下不再推荐基于 SMS 的 [2FA](https://thenewstack.io/githubs-2fa-move-was-long-overdue/) 。广泛可用的最安全的方法是那些支持 [WebAuth 认证标准](https://www.w3.org/TR/webauthn-2/)的方法，如物理安全密钥和支持 Windows Hello 或 Face ID/触控 ID 等技术的个人设备。
4.  在 2FA 锁定的情况下取消链接您的电子邮件:以前，被锁定的用户很难使用他们首选的电子邮件地址创建一个新帐户，这与他们所有的提交相关联。有了这个功能，用户可以在无法登录或恢复帐户的情况下，将他们的电子邮件地址与支持 2FA 的 GitHub 帐户解除链接。如果恢复选项(如 [SSH 密钥](https://thenewstack.io/create-and-manage-shh-keys-for-third-party-integration/)、PATs 或之前登录的设备)不可用，用户可以使用新的 GitHub.com 帐户重新开始，并保留他们的贡献历史。

## 这是值得的

让我强调一下 GitHub 多次提出的一个观点:发短信，又名 SMS，2FA 总比没有强，但如果有人真的想破解你的账户， [SMS 2FA 是最容易破解的方法。](https://www.csoonline.com/article/3674833/the-trouble-with-2fa.html)个人推荐要么免费[谷歌认证器](https://play.google.com/store/apps/details?id=com.google.android.apps.authenticator2&hl=en_US&gl=US)要么[微软认证器](https://www.microsoft.com/en-us/security/mobile-authenticator-app)；开源[bit warden](https://bitwarden.com/)；或者一个 [YubiKey](https://www.yubico.com/) 或 [Google Titan](https://store.google.com/us/product/titan_security_key) 键。

是的，我知道你们很多人会觉得这很烦人。相信我。值了。否则，你的代码库迟早会被黑客攻击。不是“如果”，而是什么时候。代码安全攻击空前高涨，您不想成为受害者之一。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>