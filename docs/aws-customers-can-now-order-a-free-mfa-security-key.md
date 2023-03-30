# AWS 客户现在可以订购免费的 MFA 安全密钥

> 原文：<https://thenewstack.io/aws-customers-can-now-order-a-free-mfa-security-key/>

在我看来，基本的用户安全始于[多因素认证(MFA)](https://thenewstack.io/githubs-2fa-move-was-long-overdue/) 。是的，很多开发商不同意。对他们来说， [MFA 只是他们开发者管道中又一个恼人的步骤](https://thenewstack.io/why-open-source-project-maintainers-are-reluctant-to-use-digital-signatures-two-factor-authentication/)。是的，[外交部可以妥协](https://thenewstack.io/multifactor-authentication-is-being-targeted-by-hackers/)。好家伙，我知道 [MFA 可以妥协](https://www.zdnet.com/article/my-instagram-account-was-hacked-and-two-factor-authentication-didnt-help/)。但它仍然比简单依赖用户 id 和密码的替代方案安全得多。

因此，当 2021 年[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS)安全[开始向美国的 AWS 账户所有者提供免费的 MFA 安全密钥](https://aws.amazon.com/blogs/security/amazon-security-awareness-training-and-aws-multi-factor-authentication-tokens-to-be-made-available-at-no-cost/)时，我很高兴。但要真正拿到钥匙并不容易。还记得我刚才说的程序员不乐意花时间在 MFA 上吗？又来了。但是现在，合格的 AWS 客户可以通过 AWS 管理控制台的订购门户订购免费的安全密钥。这简化了订购流程，尤其是对于关联账户。

目前，只有在过去三个月中每月花费超过 100 美元的美国 AWS 帐户 root 用户才有资格下订单。我希望 AWS 能让美国以外的用户也能使用它。加油， [C.J 摩西](https://www.linkedin.com/in/cjmoses/)，AWS 的 CISO，难道我们都拿不到吗？

尽管如此，这还是一个开始。

## FIDO2

AWS 使用一个 [FIDO2](https://fidoalliance.org/fido2/) 物理密钥。FIDO2 是一个开放的认证标准，是 [FIDO U2F](https://www.yubico.com/authentication-standards/fido-u2f/) 的扩展，它由 [W3C Web 认证规范(WebAuthn API)](https://www.w3.org/TR/webauthn-2/) 和[客户端到认证协议(CTAP)](https://fidoalliance.org/specs/fido-v2.0-id-20180227/fido-client-to-authenticator-protocol-v2.0-id-20180227.html) (一个应用层协议)组成。CTAP 支持客户端或平台(如浏览器或操作系统)之间通过外部身份验证器进行通信。

您可以通过将 FIDO2 安全密钥插入电脑的 USB 端口并启用它来使用它们。之后，当系统提示您安全完成登录过程时，您可以点击它。你应该注意到，如果你已经在其他服务中使用 FIDO 安全密钥，并且它有一个支持 AWS 的配置，例如, [Yubikey 5 系列](https://www.yubico.com/products/yubikey-5-overview/)，你也可以在 AWS 中使用它。当您在 AWS 中启用 FIDO 兼容的身份验证器时，FIDO 安全密钥会创建一个仅用于 AWS 的新密钥对。

每个 AWS 帐户只能使用一个这样的密钥。不过，摩西写道，[你可以将你的 AWS FIDO2 安全密钥与其他支持安全密钥的应用程序](https://aws.amazon.com/blogs/security/eligible-customers-can-now-order-a-free-mfa-security-key/)一起使用，比如 Dropbox、GitHub 和 Gmail。

## 封锁它

Moses 还建议，作为最佳实践，“您的所有用户都应该获得并启用 MFA。这可以在 AWS 身份系统的 [AWS 身份和访问管理(IAM)](http://aws.amazon.com/iam) 用户级别完成，也可以在联合身份提供者的上游完成，因为使用联合身份是最佳实践。”

所以，难道你不认为是时候拿到免费钥匙，开始锁定你的 AWS 账户了吗？我知道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>