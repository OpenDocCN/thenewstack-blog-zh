# John Deere 收获 Def Con 嘲弄疲惫的网络安全

> 原文：<https://thenewstack.io/john-deere-harvests-def-con-mockery-for-lax-web-security/>

农业设备巨头 [John Deere](https://www.deere.com/en/index.html) 在一个面向公众的网站上留下了一个极其敏感的 [Okta](https://developer.okta.com/?utm_content=inline-mention) 生成的数字证书，这可能会危及一系列远程访问的农业设备的安全，据匿名独立研究员 [Sick Codes](https://sick.codes/) 在[上周为 Def Con 29 举行的一次演示](https://youtu.be/zpouLO-GXLo)中称。

这组漏洞表明了农业设备提供商以及其他工业物联网设备制造商为充分保护其互联网连接设备仍必须做的工作。守则警告说，这种松懈可能会危及我们自己的食物供应。

用于引导网站的漏洞甚至不是特别新。一位研究员被派去编码他们发现的五个跨站脚本(XSS)漏洞，这些漏洞使他们能够进入 John Deere 网站和相关数据库。在被联系到这些漏洞后，该公司在其黑客一号计划下授予两人“安全港”，让他们进一步研究该网站，而无需承担法律责任。

Codes 表示:“这表明[John Deere]没有考虑到基本的漏洞。”。

一个基于 DOM 的 XSS 让他们进入该公司供应商门户的网页。通过通常的渗透测试(pentesting ),研究人员发现提供采购订单编号将获得关于该采购的信息列表，输入随机发票编号将提供一些关于后端 IBM DB2 数据库的有用导航信息。

该网站还提供员工教育网站和预订演示单元的页面。在这里，攻击者可以预订单位，取消预约，重新分配拖拉机交付。他们能够调出每件设备的每一个数据库行，以及预订这些设备的每个人的电子邮件。

该网站还有一个来自 Pega 的[消息服务器，带有一个默认的管理员密码，如果](https://www.pega.com/insights/resources/unified-messaging)[没有被更改的话](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-27653)可能会被攻击者用来获得完全访问权限。这种访问允许 Codes 和他的同伴收集该网站上所有有趣的信息，包括管理员密码和安全审计日志，这些信息不应该被外人访问。

这也是他们找到 Okta 签名证书的地方，还有原始的解密密码。

此类证书可在 John Deere 网络的其他地方使用，以向 John Deere 用户上传或下载任何文件，或以任何用户身份登录、销毁数据、登录第三方账户。“在 John Deere 运营中心，我们可以随心所欲地做任何我们想做的事情，”Codes 推测道。

鉴于 John Deere 一直在积极为其工业拖拉机配备远程控制和数据收集功能，从网站轻松访问是有问题的。远程控制能力可以包括向农作物、植物种子、直接自推进拖拉机喷洒肥料的能力。同样，该设备收集运营数据，并上传给农民和 John Deere 本身，这可以提供关于正在种植的作物的详细信息。

Codes 警告说，薄弱的安全不仅会为随机攻击者的潜在恶意行为——例如将一件农业设备开进河里——打开大门，还会为更多协调的国家支持的攻击打开大门，这些攻击可能会削弱一个国家的食品供应。

[https://www.youtube.com/embed/zpouLO-GXLo?feature=oembed](https://www.youtube.com/embed/zpouLO-GXLo?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>