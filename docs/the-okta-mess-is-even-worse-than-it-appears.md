# 奥克塔的混乱比看起来还要糟糕

> 原文：<https://thenewstack.io/the-okta-mess-is-even-worse-than-it-appears/>

2022 年 3 月 1 日， [Okta](https://www.okta.com/) ，基于云的身份管理公司，正在大放异彩。[Okta 2022 财年的收入](https://investor.okta.com/news-releases/news-release-details/okta-announces-strong-fourth-quarter-and-fiscal-year-2022)刚刚出炉，总计 13 亿美元，同比增长 56%。它的客户包括联邦快递、穆迪、T-Mobile、JetBlue 和 ITV，并且获得了[联邦风险和授权管理计划(FedRAMP)](https://www.gsa.gov/technology/government-it-initiatives/fedramp) 的批准。什么会出错？三周后我们发现。

黑客组织 [LAPSUS$](https://krebsonsecurity.com/2022/03/a-closer-look-at-the-lapsus-data-extortion-group/) 透露他们已经进入 Okta 的系统，并展示了截图来证明这一点。在 Telegram 和社交网络上，LAPSUS$嘲笑 Okta 说，“对于一项为许多最大的公司(和 FEDRAMP 批准的)授权认证系统的服务，我认为这些安全措施相当糟糕。”

## Okta 的回复

奥克塔回答说这里没什么可看的:

> 2022 年 1 月下旬，Okta 检测到有人试图侵入为我们的一个子处理器工作的第三方客户支持工程师的账户。这件事已由副处理员进行了调查和控制。我们认为网上分享的截图与今年 1 月的事件有关。"

Okta 总结道，“根据我们迄今为止的调查，除了 1 月份检测到的活动之外，没有证据表明存在持续的恶意活动。”

同一天晚些时候，Okta 首席安全官 David Bradbury 承认，“在对这些索赔进行彻底分析后，我们得出结论，一小部分[客户(约 2.5%)可能受到了影响](https://www.okta.com/blog/2022/03/updated-okta-statement-on-lapsus/)，他们的数据可能已被查看或采取了行动。我们已经确定了这些客户，并通过电子邮件直接联系了他们。”

对我来说，这听起来不像你通常在第三方客户支持工程师笔记本电脑上找到的信息。

## 攻击的性质

随后，Okta 表示，实际上已经有人通过一台 [Sitel](https://www.sitel.com/) 支持工程师的电脑对 Okta 发起了攻击。[攻击者在笔记本电脑上启动了远程桌面协议(RDP)会话](https://www.okta.com/blog/2022/03/oktas-investigation-of-the-january-2022-compromise/)。从那里，[攻击者使用 Okta 的客户支持工程师](https://support.okta.com/help/s/article/Frequently-Asked-Questions-Regarding-January-2022-Compromise?language=en_US&_gl=1*1scoi5r*_ga*NTAwMjUyNTA0LjE2NDg1MDE1MTc.*_ga_QKMSDV5369*MTY0ODUwMjY4NS4xLjEuMTY0ODUwMzQ2NS41OA..&_ga=2.232279835.544663910.1648501517-500252504.1648501517) [超级用户](https://support.okta.com/help/s/article/Frequently-Asked-Questions-Regarding-January-2022-Compromise?language=en_US&_gl=1*1scoi5r*_ga*NTAwMjUyNTA0LjE2NDg1MDE1MTc.*_ga_QKMSDV5369*MTY0ODUwMjY4NS4xLjEuMTY0ODUwMzQ2NS41OA..&_ga=2.232279835.544663910.1648501517-500252504.1648501517)应用程序。尽管名字很吓人，Okta 声明它只对一些文件提供读权限。更令人担忧的是，超级用户可以重置密码和多因素认证(MFA)。这是一个重大的坏消息。

Sitel 承认在一月份有一个安全漏洞，但没有证实漏洞的具体细节。Okta 最终承认攻击者有可能在五天内访问了 Okta 的数据。

尽管如此，Okta 坚持认为，虽然数据可能已经被收集，如吉拉门票和用户列表，但对 Auth0、HIPAA 或 FedRAMP 客户没有影响。

然而，Okta 承认，由于它从 1 月份就知道了潜在的安全入侵，该公司当时真的应该通知其客户。相反，该公司一直等到 LAPSUS$ fox 向世界披露它曾在 Okta 鸡舍。

## 比最初承认的更糟

现在看来，这次袭击比 Okta 最初承认的还要糟糕。独立安全研究员 [Bill Demirkapi](https://billdemirkapi.me/about/) 在推特上写道， [LAPSUS$在检索了一份标题明显为“domain ms-lastpass . xlsx”的 Excel 文档后，在 Sitel 的环境中创建了“后门用户”](https://twitter.com/BillDemirkapi/status/1508527505132515329/photo/1)

是啊，这是一个相当大的危险信号。

Demirkapi 提出了非常好的问题:“我对 Okta 的问题是:你知道你的一个客户支持成员的机器在一月份遭到了攻击。[为什么不去调查？](https://twitter.com/BillDemirkapi/status/1508527511101231107)如果您不愿意做出回应，那么检测攻击的能力是没有用的。”而且，即使 Okta 在 3 月份收到了 man diant[安全事件]报告，明确详细地描述了这次攻击，[他们仍然忽略了他们的环境遭到破坏的明显迹象](https://twitter.com/BillDemirkapi/status/1508527512271400963)，直到 LAPSUS$让人们注意到他们的不作为

他也不会放过斯特尔。" [为什么您的客户在第一次出现妥协迹象时没有立即被告知](https://twitter.com/BillDemirkapi/status/1508527513445834761) ？为什么您的客户要等两个月才能听到您被入侵的消息？”

都是好问题，没有好答案。

## 脚本小子？

至于 LAPSUS$？英国警方在牛津逮捕了一名 16 岁的少年和其他六名青少年，因为他们是该组织的幕后黑手。他们似乎利用简单的社会工程侵入了雇佣服务台人员的公司。说真的，他们还登广告招聘愿意妥协自己公司的人。

正如 Demirkapi 指出的，一旦进入，他们“[使用 GitHub 现成的工具进行大部分攻击](https://twitter.com/BillDemirkapi/status/1508527497008361472)”

因此，这个主要的网络犯罪集团在技术专长上似乎比脚本小子高出一步。

尽管如此，这使他们领先于其他群体。显然，像 Okta 这样的公司及其合作伙伴在处理企业单点登录(SSO)等重要安全事务时，必须在加强自身安全方面做得更好。安全链的安全性取决于其最薄弱的环节。

Okta 及其公司还必须在对客户的透明度方面做得更好。当用户的登录信息有可能受到威胁时，必须让客户知情。就这么简单。没有人喜欢承认安全错误，但是等到漏洞被利用后才承认只会让你看起来更糟。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>