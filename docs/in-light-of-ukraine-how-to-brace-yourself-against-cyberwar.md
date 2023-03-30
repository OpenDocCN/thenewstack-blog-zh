# 乌克兰之光:如何做好应对网络战的准备

> 原文：<https://thenewstack.io/in-light-of-ukraine-how-to-brace-yourself-against-cyberwar/>

俄罗斯入侵了乌克兰，战争正在进行。在这里，在西方，我们可能认为它很遥远。不是的。正如我的朋友兼科技记者同事迈克·埃尔根(Mike Elgan)所描述的，这是第一次抖音战争(T3)。我们将在社交网络上实时看到它。在持续的网络战中，我们的技术、商业和生活也将成为[的附带或直接损害。](https://www.computerworld.com/article/3647879/will-world-war-iii-begin-in-cyberspace.html)

在普京的领导下，俄罗斯多年来一直在发动网络攻击。早在坦克开进乌克兰之前，俄罗斯就已经注入了恶意软件并关闭了乌克兰的网站。在那之前几年，俄罗斯切断了乌克兰首都基辅的电力供应，并袭击了其他前苏联国家，如爱沙尼亚、格鲁吉亚。最后，别忘了，[俄国一直在互联网上攻击美国](https://www.nytimes.com/2021/10/25/us/politics/russia-cybersurveillance-biden.html)，俄国可能是网络安全管理软件产品攻击事件的幕后黑手[。](https://www.zdnet.com/article/solarwinds-us-and-uk-blame-russian-intelligence-service-hackers-for-major-cyber-attack/)

## 你能做什么

接下来呢。我们的网站、云服务和软件。那么你能做些什么呢？

美国风险投资和私募股权公司 Insight Partners 警告说，在战争开始之前，网络攻击的数量和复杂程度已经在增加。此外，[网络安全&基础设施安全局(CISA)](https://www.cisa.gov/) 在其最新公告中表示，[俄罗斯国家支持的网络行为者将目标对准已被清除的国防承包商网络，以获取敏感的美国国防信息和技术](https://www.cisa.gov/uscert/ncas/alerts/aa22-047a)，他们预计攻击将会增加。

我也是。

你能做些什么呢？Insight Partner 的一般建议是“保持警惕，确保保护您最重要的资产。”具体来说，公司指出您应该保护您的:

1.  电子邮件安全性
2.  多因素认证
3.  弹性系统(数据备份)
4.  端点保护
5.  勒索软件防护
6.  常规安全评估(渗透测试)
7.  安全监控
8.  网络安全性
9.  漏洞管理和修补程序
10.  制定计划(事故响应计划)

## 坚持最基本的

注意到什么了吗？这里没什么花里胡哨的。这是最基本的。但他们说得很对。这是你需要保护的基本原则。现在不是担心花哨攻击的时候。是时候为您的日常业务规划您需要的四轮马车了。

安全专家米克·道格拉斯同意这一观点。在他的推特上， [Douglas 列出了一些如何保护你的系统的基本规则。我想特别强调的一点是“](https://twitter.com/bettersafetynet/status/1496496087741480960?s=20&t=s83uEi7yOm5LZA6rp42iJw)[开始将整个互联网视为敌对……因为它确实如此。](https://twitter.com/bettersafetynet/status/1496497151635034116)“是的。强调这一点。从来没有这么安全过，但现在比以往任何时候都危险。

首先，他建议密切关注你的防火墙。您还应该记得“防火墙是双向工作的。”您必须监控发起出站流量的 DMZ 服务器。你想让你的机器“打电话回家”接受 C2 的指示吗？他们应该向谁发起分布式拒绝服务(DDoS)攻击？我不这么认为！

你也可以忘记[地理封锁](https://superuser.com/questions/1334236/what-are-the-ip-ranges-to-block-the-entire-russian-federation) [俄罗斯 IP 地址](https://superuser.com/questions/1334236/what-are-the-ip-ranges-to-block-the-entire-russian-federation)作为一种保护自己或以某种方式报复他们的方式。正如道格拉斯指出的那样，“俄罗斯集团唯一一次出现在俄罗斯知识产权领域，是在他们想要插手的时候。”所有真正的行动都将来自分散在世界各地的受损硬件。

您还需要知道在您的系统中什么是“正常的”可执行文件。应用程序控制，又名白名单，是。Douglas 说，“不再是‘很好’，而是 IMO 牌桌上的赌注。任何持相反观点的人都给出了过时且危险的建议。”

不确定您的系统上有哪些可执行文件？叹气。好吧，我不骂你。马克·巴格特的 [srum-dump](https://github.com/MarkBaggett/srum-dump) ，它将 Windows 系统资源使用监视器(srum)数据转换成 xlsx 电子表格，这对于找出你的系统上正在运行什么有很大的帮助。

如果你正在使用 Linux——你应该这样做——像 [auditd](https://capsule8.com/blog/auditd-what-is-the-linux-auditing-system/) 或 [sysmon](https://github.com/SwiftOnSecurity/sysmon-config) 这样的基本工具是你的朋友。不确定如何从中获得最大收益？查看此 [auditd](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/security_hardening/auditing-the-system_security-hardening) 或 [sysmom](https://www.lares.com/blog/sysmon-for-linux-test-drive/) 文档。

### 靠土地生活等等

你还应该注意[靠土地为生(LoL)的攻击](https://logrhythm.com/blog/what-are-living-off-the-land-attacks/)。这些攻击使用您现有的合法工具来发起攻击。通常，这是通过命令行工具完成的，比如 Windows 上的 Powershell 和 PsExec 或者 Linux 上的 Bash。当然，为了让这些工作，你的系统必须已经被高水平的渗透。是吗？你确定吗？

它不必像一个未知用户从某个远程 IP 地址登录一样明显。恶意软件，如 [Astaroth 使用 LOL 攻击](https://www.microsoft.com/security/blog/2020/03/23/latest-astaroth-living-off-the-land-attacks-are-even-more-invisible-but-not-less-observable/)，隐藏在众目睽睽之下，并且非常危险。

Douglas 警告说，你也不能依靠安全信息和事件管理(SIEM)或终端检测和响应(EDR)程序来拯救你的培根。对于精明的黑客来说，就像那些受雇于俄罗斯对外情报局(SVR)的黑客一样，在你的眼皮底下运行 LOL 攻击太容易了。

道格拉斯还建议你增加日志记录，同时过滤掉你不关心的垃圾信息，并“缩短你长期不需要的数据的保留时间”为什么缩短？因为攻击会快速猛烈地向你袭来。你不关心一个月前发生了什么，你关心的是现在是什么在打击你。

处理这一切并不容易。但是道格拉斯相信，如果你采用一种检测和应对模式来应对迎面而来的大量麻烦，我们仍然可以战胜它。

我们最好。除了随机应变，我们别无选择。要么这样，要么和我们的企业说再见。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>