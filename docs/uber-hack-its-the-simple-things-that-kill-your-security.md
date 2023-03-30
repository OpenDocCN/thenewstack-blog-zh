# 优步·哈克:正是这些简单的事情扼杀了你的安全感

> 原文：<https://thenewstack.io/uber-hack-its-the-simple-things-that-kill-your-security/>

在优步最近一次关于其最近黑客攻击的更新中，这家拼车公司指责 Lapsus$黑客组织对其安全惨败负责。[优步补充道，Lapsus$](https://www.theverge.com/22998479/lapsus-hacking-group-cyberattacks-news-updates) 也曾攻破微软、思科、三星、英伟达和 Okta。上周，他们还入侵了视频游戏制造商 Rockstar Games。那听起来真的很大很吓人，不是吗？好吧，攻击的结果是丑陋的，但它的方式是突出的。这是一种头脑简单的攻击，一个脚本小子少年可以拉起来。哦，这是什么？袭击者是一名绰号“茶壶”的 18 岁少年。

茶壶是怎么做到的？通过从[暗网](https://thenewstack.io/good-vulnerability-disclosure-policy-can-keep-security-flaws-off-dark-web/)上购买承包商的 ID 和密码。这里用的真正的黑客工具？大约二十分之一的比特币，或者一千英镑的真实货币，用于商业账户访问。

## 网络钓鱼攻击

最初的危害似乎是当承包商被网络钓鱼攻击所欺骗，放弃了他的用户 ID 和密码。尽管如此，由于他的优步帐户受到多因素身份验证(MFA)的保护，它应该还是没问题的。

对吗？对！？不对。

最终，承包商接受了 MFA 请求，攻击者也加入了进来。各位，加油！如果你得到一个你不承认的 MFA 请求，你不批准它！

的确，正如商业安全公司 BlackFog 首席执行官兼创始人 Darren Williams 所说，“社交工程正成为网络罪犯更流行的策略，因为它确实提供了城堡的钥匙，正如我们从最近对优步的攻击中所看到的。”这是旧闻，但由于每天都有人受到网络钓鱼攻击，我们永远不会停止重复它。

在取得成功后，攻击者找到了一个[内部网络共享](https://twitter.com/hacker_/status/1570582547415068672)和 [PowerShell](https://thenewstack.io/cross-platform-open-source-powershell-goes-net-core-runs/) 脚本，它们拥有特权管理凭证。不要问我它在那里做什么。这是一个经典的愚蠢的安全把戏。通过它，黑客获得了优步、AWS、G-Suite、谷歌云平台、OneLogin、SentinelOne 事件响应门户、Slack 和优步的 OpenDNS 资源。有一次，他甚至在优步的 Slack 上公布了他的所作所为……有一段时间，人们似乎认为这是一个玩笑。

一些笑话。

Williams 继续说道，“仅仅保护外围是不够的。组织必须假设坏人会找到进入的途径，因此重点必须放在防止他们带着皇冠上的宝石离开。”半公开目录中的根级脚本无疑是我书中的皇冠上的宝石。

## 做正确的事情

事后，优步说了所有正确的事情:识别并重置受损的员工账户；轮换密钥，锁定代码库，加强 [MFA 政策](https://thenewstack.io/multifactor-authentication-is-being-targeted-by-hackers/)，增加内部安全监控。但这是一个经典的马后炮。

优步声称，尽管黑客掌握了其 IT 王国的钥匙，但他没有进入任何面向公众的系统；用户帐户；或敏感的用户信息，如信用卡号、用户银行账户信息或旅行历史。如果你愿意，你可以相信。我不太确定。

这里的要点是，虽然听起来像是来自《碟中谍》的花哨的网络安全技巧可能会吸引你的注意，但要真正保护你的系统，你需要不断加强安全基础知识——一遍又一遍。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>