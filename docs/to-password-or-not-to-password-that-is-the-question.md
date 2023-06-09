# 设置密码还是不设置密码:这是个问题

> 原文：<https://thenewstack.io/to-password-or-not-to-password-that-is-the-question/>

密码仍然是用户认证的默认方法，但问题是它能持续多久？密码不足以防止软件威胁已经或多或少成为一个既定事实。关于密码泄露数量及其后果的统计数据证明了这一点。密码带来了严重的安全风险，即使与[多因素认证(MFA)](https://curity.io/resources/mfa/) 一起使用，它们也非常容易受到攻击。

所有这些安全问题都促使人们努力实现现代应用程序登录的无密码方法。在这篇文章中，我将解释为什么无密码方法更有利于提高安全性。但是谁需要它，一个组织应该如何以及何时实现无通行证？

## 密码困境

首先，让我来分解一下为什么密码正在成为过去的遗迹。

密码可以被视为一个共享的秘密——它是一个字符串，应该只有用户知道，但提供给应用程序或服务，以哈希或加密格式存储它们。因此，每次用户输入密码时，该应用程序都会对给定的符号组合进行哈希或加密，并将其与最初提供的密码进行比较。

虽然散列法可以保证一定的密码保护，但在用户端会出现其他一些问题。

由于密码的知识基础性质，第一个问题是密码本身。有这么多密码需要记忆，许多人选择容易记忆的序列，这并不奇怪。这通常是一个短语或数字组合，如 123456。不幸的是，这种密码很容易被使用大型字典、每秒处理数百万个单词的计算机猜到。这提示管理员需要更多包含特殊字符、大小写字母或数字的[复杂密码](https://thenewstack.io/manage-passwords-keep-online-accounts-secure/)。有些可能需要没有实际单词的密码。

然而，复杂的密码可以更安全，但是记住它就成了另一个问题。即使一个人能回忆起一长串随机的字符，他们也更有可能[在不同的网络应用中重复使用这个看似安全的密码](https://thenewstack.io/blame-it-and-security-not-end-users-for-password-problems/)。但是，如果一个 web 应用程序被破坏，密码泄露，攻击者就可以访问更多 web 应用程序的用户帐户。

此外，密码令人沮丧。它们会产生摩擦，降低用户体验。如果用户忘记了密码，他们可能会经历一个困难的密码重置过程。用户有时可能被迫联系管理员或支持人员，这需要额外的时间和精力。

使用密码管理器可以缓解这些问题。他们会记录不同帐户的密码，这样用户就不必记住它们了。然而，这需要用户将所有鸡蛋放在一个篮子里——如果密码管理器被攻破，所有密码都会被泄露。

## 无密码认证:密码的替代方案

无密码消除了与密码相关的风险。这并不意味着用户没有经过身份验证。相反，这种方法涉及使用其他选项来识别用户，而不依赖于他们的内存或存储安全。

最常见的方法是:

*   电子邮件和短信认证
*   验证器应用程序
*   认证设备和智能钥匙
*   不同形式的[生物认证](https://thenewstack.io/biometrics-brings-us-one-step-closer-to-eliminating-passwords-for-good/)

让我们更仔细地看看它们:

在登录过程中使用电子邮件和短信身份验证时，用户会收到一个数字代码、QR 代码或指向其注册电子邮件地址或电话号码的链接。这些选项相当安全且易于实现。因此，它们是最受欢迎的。然而，这种类型的身份验证伴随着一些安全风险，因为它们容易受到网络钓鱼攻击。

第二种最流行的方法是使用验证器应用程序(Google Authenticator、Duo 和 Yubico Authenticator 应用程序就是几个例子)。这些验证器应用程序不断生成一次性密码(OTP)代码，用户使用该代码进行验证。authenticator 应用程序与用户的帐户同步 OTP 仅在很短的时间内有效，一旦过期，特定代码就无法用于身份验证。

一些认证应用程序更进一步。例如，使用 Duo，请求身份验证的应用程序可以发起推送身份验证请求，这样用户就会收到在 Duo 应用程序中进行身份验证的通知提示。

最后一种选择，即使用身份验证设备和密钥卡，可以防止网络钓鱼，也是最安全的。它使用与 WebAuthn 标准相结合的硬件令牌。Yubico 及其 [YubiKey](https://curity.io/resources/webinars/phishing-resistant-passwordless-authentication-curity-yubico/) 是该领域的领先技术之一，并提供多种类型的硬件认证器。有了这个选项，YubiKey 使用的每个应用都会生成一个唯一的密钥对。结果是一个解决方案，其中“钓鱼应用程序”无法使用真实应用程序的身份验证细节，因为生成的密钥对不匹配。

越来越多的技术正在进入无密码市场。其中很多都是基于固有的认证因素(用户本身)，如指纹、语音识别、打字模式识别等等。一些开发这些身份验证类型的公司超越了 Identity、Hypr 和 Secret Double Octopus，仅举几例。

## 无通行证通行

取消登录密码可以提高系统的安全性，并降低与密码相关的风险。它还可以改善用户体验，减少用户和管理员之间的摩擦。但是，实施无密码方法不应该只是为了实施而实施。

首先，利益相关者应该就无密码方法的目标达成一致。无论是更强大的安全性还是增强的用户体验，所有参与方都必须有一个关于如何运行实施的明确计划。它还应该源于对当前身份验证方法的效率的彻底分析，您现有的系统是否能够处理无密码，以及应该如何一步一步地实现它。

第二，理解密码的流行是很重要的:它们很容易实现，不需要先决条件。然而，对于无密码，这些先决条件应该到位，无论是带有认证应用程序的移动电话、认证设备还是密钥卡。企业用户通常可以获得预先注册的身份认证设备，但接受新流程需要时间和耐心。

第三，和其他大项目一样，从小处着手是必要的。从在较小的测试组中实现无密码认证开始，并持续监控项目的成功。

与此同时，考虑使用[选择加入方法](https://curity.io/resources/learn/optin-mfa-howto/)或实施更强大的认证机制。您还可以使用[逐步认证](https://curity.io/resources/videos/2fa-step-up/)开始对关键服务和数据实施无密码选项。

要考虑的事情很多，但是无密码是未来。现在就准备吧。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>