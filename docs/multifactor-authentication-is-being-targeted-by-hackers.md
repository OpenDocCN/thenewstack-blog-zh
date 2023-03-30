# 多因素身份认证正成为黑客攻击的目标

> 原文：<https://thenewstack.io/multifactor-authentication-is-being-targeted-by-hackers/>

这只是时间问题。虽然多因素身份验证(MFA)使登录系统更加安全，但它并没有使登录变得“安全”知名黑客[](https://www.linkedin.com/in/kevinmitnick/)[known be4](https://www.knowbe4.com/)的凯文·米特尼克在 2018 年表示，[很容易诱骗用户放弃他在某个网站的 MFA 令牌](https://techcrunch.com/2018/05/10/hacker-kevin-mitnick-shows-how-to-bypass-2fa/)。但是现在自动化工具包已经来对付 MFA 攻击了。

网络安全公司 [Proofpoint](https://www.proofpoint.com/us) 发现[网络钓鱼工具包在其功能](https://www.proofpoint.com/us/blog/threat-insight/mfa-psa-oh-my)中添加了 MFA 绕过攻击。这些依赖于透明反向代理。典型的透明反向代理，如开源的 [Squid 透明代理服务器](https://linuxtechlab.com/squid-transparent-proxy-server-complete-configuration/)用于内容过滤或监控企业互联网连接上的员工网络活动。然而，在这些工具包中，相同的技术被用于运行本地[中间人(MitM)](https://en.wikipedia.org/wiki/Man-in-the-middle_attack) 攻击来窃取凭证和会话 cookies。

为什么要这么麻烦呢？因为，作为一家 MFA 公司 [Duo](https://duo.com/) 最近的研究发现，这些天来 [78%的用户现在使用 MFA，而 2017 年只有 28%](https://duo.com/blog/the-2021-state-of-the-auth-report-2fa-climbs-password-managers-biometrics-trend)。这是个好消息，但这也给了网络黑客攻击 MFA 的动机。

## 一系列套件

让想要成为黑客的人更容易。Proofpoint 发现，当今的网络钓鱼工具包包括“简单的开源工具包，具有人类可读的代码和简单的功能，以及利用多层模糊和内置模块的复杂工具包，允许窃取用户名、密码、MFA 令牌、社会安全号码和信用卡号码。”

怎么会？通过向天真的用户发送带有虚假目标网站(如登录页面)链接的网络钓鱼电子邮件。这当然是旧闻了。黑客们使用这种技术已经很久了。这种“新型套件”带来的是一种植入恶意软件的 MitM 透明反向代理。它驻留在目标的 PC 上，拦截所有流量，包括它们的凭证和会话 cookies，即使连接到真实的站点。会话 cookies 包括 MFA 代码，即使它们来自高度安全的 MFA。

其中一个叫 [Modlishka](https://www.zdnet.com/article/new-tool-automates-phishing-attacks-that-bypass-2fa/) 的程序已经实现了这些攻击的自动化。波兰安全研究员 [Piotr Duszyński](https://blog.duszynski.eu/) 谈到它时说，“通过加密的、浏览器信任的通信渠道，用正确的反向代理瞄准你的域，人们真的很难[注意到一些严重错误。](https://blog.duszynski.eu/phishing-ng-bypassing-2fa-with-modlishka/)”他补充说，这是“某种游戏规则的改变者，因为它可以用作‘点击’代理，在 2FA 的完全支持下，可以轻松实现网络钓鱼活动的自动化。:唯一的例外是 [FIDO 通用第二因子(U2F)](https://www.yubico.com/authentication-standards/fido-u2f/) 基于协议的令牌。

## 只是幻觉？

雪上加霜的是，Proofpoint 声称这种新方法使这些试剂盒更加有效。那是因为“现代网页是动态的，经常变化。因此，展示真实的网站而不是传真会大大增强用户安全登录的错觉。”

目前有三种主要的 MFA 网络钓鱼工具包。分别是 Modlishka、[mura ENA/](https://github.com/muraenateam/necrobrowser)[necro browser](https://github.com/muraenateam/necrobrowser)和 [Evilginx2](https://github.com/kgretzky/evilginx2) 。每一种都有不同的功能，用于稍微不同的目的。理论上，它们都是为了合法目的而创建的，比如渗透测试。当然，现在它们都更多地用于黑客攻击，而不是测试。

你能做什么？使用 FIDO U2F 等强化 MFM 技术会有所帮助，基于硬件的 MFA 安全设备也是如此，如 [Yubico 的 YubiKey](https://www.yubico.com/) 和[谷歌的 Titan 安全密钥](https://cloud.google.com/titan-security-key)。从长远来看，[零信任](https://thenewstack.io/zero-trust-time-to-get-rid-of-your-vpn/)将是未来个人身份认证的首选方法，但我们还没有做到这一点。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>