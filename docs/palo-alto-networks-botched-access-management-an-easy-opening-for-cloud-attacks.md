# 帕洛阿尔托网络公司:拙劣的访问管理为云攻击打开了方便之门

> 原文：<https://thenewstack.io/palo-alto-networks-botched-access-management-an-easy-opening-for-cloud-attacks/>

众所周知，拥有身份和访问管理(IAM)系统的云必然缺乏安全性。好的，这并不完全是简·奥斯汀写的，但是你明白了。 [Unit 42](https://unit42.paloaltonetworks.com/) ， [Palo Alto Networks](https://www.paloaltonetworks.com/) 威胁情报团队在其最新的 Unit 42 云威胁报告中称，云错误配置继续困扰着数以千计的组织。具体来说，混乱的 IAM 配置会导致重大的云安全问题，这反过来会导致严重的加密劫持攻击。

[https://www.youtube.com/embed/Qr2PZkpBpwo](https://www.youtube.com/embed/Qr2PZkpBpwo)

视频

有多糟糕？在红队的一次演习中，一个简单的 IAM 错误配置“让我们的 Unit 42 研究人员危及整个大规模云环境，并绕过几乎所有的安全控制。”如果这是一次真正的攻击，可能会导致数百万美元的数据泄露。Palo Alto Networks 帮助客户解决了这个问题。

这很有趣吗？

## 无处不在的访问问题

Unit 42 团队随后继续研究这种 IAM 问题是否普遍。坏消息。确实是。

他们在数千个云账户中发现了几个常见的身份相关缺陷。Palo Alto Networks 的公共云首席安全官 Matthew Chiodi 写道，根本原因是“缺乏 IAM 治理和标准。”“在每个云帐户中创建的大量用户和机器角色以及权限和服务进一步加剧了这种情况。”

更糟糕的是，Chiodi 继续说道，“人类擅长许多事情，但理解有效的权限并识别数百个角色和不同云服务提供商的风险策略是最好留给算法和自动化的任务。”

雪上加霜的是，IAM 缺陷很难被发现。他们经常被忽视，直到为时已晚，攻击来袭。

对云与 GitHub 的进一步研究发现，开发者账户可以被用来扩大云的攻击面。通常，开发人员帐户被允许比普通用户更高级别的访问云环境。这本身没有错，但是程序员被授予的一些权限是非常危险的。

具体来说，安全探索者发现开发人员帐户可以访问名为 flowlog*的自定义组织特定 IAM 角色。这开放了所有的流日志子类型，包括过于强大的流日志角色。有了这个，攻击者就可以逃离开发人员区域，获得对整个云环境的管理权限。所有这一切都要归功于过于宽松的 admin IAM 角色。

这个故事的寓意是:在设置开发人员 IAM 权限时，您必须特别小心。

那么，这些问题有多普遍呢？太普通了。原因是搜索错误配置的 IAM 角色与搜索允许匿名登录的数据库没有什么不同。研究人员扫描了亚马逊网络服务(AWS)的账户 id。然后对照一个预先生成的列表进行检查，该列表是通过抓取 GitHub 并汇总前 500 个最常用的 IAM 角色名而创建的。

他们在 GitHub 中搜索 AWS ID 和角色名称匹配，发现了超过 145，623 个存储库、超过 175，000 个 EC2 快照、数百个 S3 桶以及许多 RDS 快照和 KMS 键。简而言之，“毫无疑问:如果攻击者发现了 Unit 42 研究人员发现的东西，他们肯定会采取措施‘拥有’这些云账户。”在这个过程中，研究人员发现了配置错误的 DevOps 角色，它们拥有接近系统的管理权限，以及配置错误的 DBAccess 角色，它们可以访问数据库服务，例如 Amazon DynamoDB 和 Amazon Redshift。

【Unit 42 的高级云研究员陈颉补充说，这种“错误配置的 IAM 信任策略是特定于 AWS 环境的，通常存在于需要跨帐户访问的更复杂的云环境中。根据我们的研究，我们发现这种错误配置在拥有数百或数千个 IAM 角色的大型客户中更常见。”简而言之，你的云越复杂，你就越有可能打开潜在的严重漏洞。

也就是说，Chen 继续说道，Unit 42 认为 IAM 错误配置会导致特权提升，这在所有 CSP 中都很常见。“正如我们在报告中指出的那样，数百个云服务之间有数千个权限，并且这些权限相互交互，因此一个用户很有可能通过滥用一组授予的权限来获得提升的权限。谷歌云也报告了类似的错误配置。

现在 AWS 尽最大努力让你不犯这种错误。默认情况下，当您创建 AWS IAM 信任策略时，它仅限于特定的 AWS 服务、帐户或身份提供者。不幸的是，这显然没有阻止那些只想完成工作而忽略安全需求的系统管理员。当您在 AWS consult 中手动编辑 IAM 信任策略时，您必须忽略多个警告——这正是人们所做的。

Unit 42 还发现，就像人们总是错误地使用密码一样，员工也在使用访问密钥 id 及其相应的秘密访问密钥时犯了大错。特别是，组织在轮换旧密钥方面做得很差。在全球范围内，Unit 42 research 发现，68%使用 AWS 的组织和 62%使用 Google Cloud 的组织的服务帐户密钥超过 90 天。有趣的是， [Azure](https://azure.microsoft.com/en-us/) 几乎没有任何严重违反用户账户政策的行为，比如不活跃的用户访问或过期的密钥。这可能是因为 Azure 使用 [Azure Active Directory (AD)](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis#:~:text=Azure%20Active%20Directory%20(Azure%20AD,thousands%20of%20other%20SaaS%20applications.) 来控制和管理用户账户。

最后，但绝非最不重要的是，他们发现日本和亚太地区高达 57%的组织没有在 AWS 中为其 IAM 用户帐户启用多因素身份认证(MFA)。美洲(46%)和 EMEA(45%)在使用 MFA 方面做得更好，但这仍然没有什么值得夸耀的。更糟糕的是，太多的组织甚至不为他们的 IAM 根帐户使用 MFA。这简直是自找麻烦。

而且，Unit 42 注意到，麻烦正在找你。Unit 42 研究表明，加密劫持影响了至少 23%使用云的组织。

## 快乐的密码窃贼

攻击者通常使用错误配置的云基础设施(如上所述)来危害云实例。这些错误配置可能导致绕过防火墙、AWS 安全组、Amazon 和 Google 虚拟专用云(VPCs)或 Azure 虚拟网络(VNet)策略，并可能暴露组织的云环境。

完成后，攻击者倾向于使用云资源进行针对流行的 Monero 加密货币的[亲缘加密挖掘](https://duo.com/decipher/kinsing-malware-targets-docker)操作。

那么，你能做些什么呢？如果你使用它的 [Prisma Cloud](https://www.paloaltonetworks.com/resources/datasheets/prisma-cloud-at-a-glance) 云原生安全平台，它的 [WildFire](https://www.paloaltonetworks.com/products/secure-the-network/wildfire) 恶意软件预防云服务，以及 [Autofocus](https://www.paloaltonetworks.com/cortex/autofocus) 攻击分析软件，帕洛阿尔托会很高兴。

该公司还有许多关于如何保护你自己和你的云的一般性建议。其中包括:

1.  尽量减少管理员凭据的使用。
2.  通过将人员分配到组或角色来简化用户管理。
3.  启用 MFA。
4.  配置[强密码策略](https://pages.nist.gov/800-63-3/)。即使在 MFA 时代，好的密码仍然很重要。
5.  定期轮换访问令牌。
6.  监控 IAM APIs。
7.  授予最低特权访问权限
8.  自动修复过多的权限。
9.  利用云原生安全平台。
10.  强化我的角色。永远不要向任何 IAM 角色授予匿名访问权限(例如，" Principal" : { "AWS" : "*" })。

如果你做到了这些，你将会比现在安全得多。你看，当他们真的要抓你的时候，这就不是妄想了。我和 42 分队向你保证，他们真的就在那里，他们真的要抓你和你的小云彩。

亚马逊网络服务公司和帕洛阿尔托网络公司是新堆栈的赞助商。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>