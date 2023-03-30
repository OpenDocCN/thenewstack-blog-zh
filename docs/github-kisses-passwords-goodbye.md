# GitHub 吻别密码

> 原文：<https://thenewstack.io/github-kisses-passwords-goodbye/>

我们早就知道[密码不能提供足够好的安全性](https://thenewstack.io/manage-passwords-keep-online-accounts-secure/)。然而，这并没有阻止我们仍然依赖密码来保证安全。它们是最低的共同安全标准。顶级开发者网站 [GitHub](https://github.com/) 已经有了足够的二流安全性。因此，从 8 月 13 日起， [GitHub 在认证 Git 操作](https://github.blog/2021-08-16-securing-your-github-account-two-factor-authentication/)时阻止了账户密码的使用。

相反，Git 现在要求您使用双因素认证(2FA)因素来使用其核心 Git 服务。这些因素可以包括[个人访问令牌](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token)； [SSH 按键](https://thenewstack.io/create-and-manage-shh-keys-for-third-party-integration/)，面向开发者；或者 [OAuth](https://oauth.net/) 或者 [GitHub App 安装令牌](https://docs.github.com/en/developers/apps/building-github-apps/authenticating-with-github-apps)给集成商。

人们对此很不高兴。对他们，我只能说:“算了吧。”

GitHub 并没有给我们带来惊喜。八个月前，GitHub 就警告过这种情况。我引用:“从 2021 年 8 月 13 日开始，在 GitHub.com 上认证 Git 操作时，我们将不再接受帐户密码。”

然而，人就是人，还是有很多抱怨。说真的，没那么难。

首先，[为你的 GitHub 账号启用 2FA。仅仅通过这样做，你就可以阻挡大范围的攻击。](https://docs.github.com/en/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication)

2FA 的工作原理是要求你拥有三种凭证中的两种来访问一个帐户。这些是:

*   你知道或能被给予的东西。通常这是一次性 PIN。
*   您拥有的东西，如安全的 ID 卡、移动电话或硬件安全密钥。
*   你是什么，这些是生物特征因素，如指纹，视网膜扫描，或声纹。

GitHub 为您提供了许多使用 2FA 的选项。其中包括:

虽然可以发短信，但 GitHub 强烈建议您使用安全密钥或 TOTPs。这是因为有太多的方法可以打破基于文本的 2FA。这些包括 SIM 卡交换、文本欺骗、网络钓鱼和 SS7 网络的安全漏洞，电信公司利用 SS7 网络来管理电话号码之间的通话和文本。

GitHub 是新兴的 WebAuthn 安全认证标准的最爱。在某种程度上，它被用在除了短信之外的所有现代 2FA 方法中。

该公司也倾向于使用 YubiKeys。我自己也喜欢 YubiKeys。通过一个帐户保护您的帐户后，您可以使用它们做更多事情。例如，您可以使用存储在您的安全密钥中的 [GPG 密钥](https://en.wikipedia.org/wiki/GNU_Privacy_Guard)对您的 git 提交进行数字签名。GitHub 为使用 GitHub 设置 YubiKey 提供了一个[详细指南，用于提交验证和基于 SSH 的认证。GitHub 还与](https://resources.github.com/whitepapers/GitHub-guide-to-commit-signing/) [Yubico](https://www.yubico.com/) 合作，创建了一个逐步的[视频指南](https://www.youtube.com/watch?v=Y3mLBTCiccs)来帮助您启用 SSH 密钥的安全密钥并提交验证。

最后，但同样重要的是， [GitHub 正在出售品牌 YubiKey 5 NFC 和 YubiKey 5C NFC 密钥](https://thegithubshop.com/products/github-branded-yubikey?variant=39478422241389)。它们并不便宜，价格从 45 美元到 55 美元不等，但它们可以持续数年，不仅使 GitHub 的安全登录变得容易，也使所有其他安全网站和服务变得容易。

此外，GitHub 不是唯一一家希望你放弃密码的公司。其母公司微软希望看到密码的终结越早越好。正如微软身份项目管理公司副总裁亚历克斯·西蒙斯所说，我们“今年一直在努力让密码成为过去。

考虑到可以追溯到密码的无休止的安全问题，那一天不能来得太快。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>