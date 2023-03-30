# DNS 是攻击者容易攻击的目标:下面是您可以做的事情

> 原文：<https://thenewstack.io/dns-is-an-easy-target-for-attackers-heres-what-you-can-do/>

[NS1](https://www.ns1.com/) 赞助本帖。

 [克里斯·比弗斯

克里斯·比弗斯是 NS1 的联合创始人兼首席执行官。他领导 NS1 的行业专家团队开发产品，使公司能够使用 DNS 构建和交付令用户满意的动态、分布式和自动化应用程序。Kris 是 DNS 和全球应用交付领域公认的权威，经常谈论和撰写关于构建和部署高性能、大规模、全球分布式互联网基础设施的文章。Kris 拥有 RPI 的计算机科学博士学位，在创建和领导 NS1 之前，他在 Voxel 构建了 CDN、云、裸机和其他基础设施产品，Voxel 于 2011 年出售给 Internap(纳斯达克股票代码:INAP)。](https://www.ns1.com/) 

[DNS spionage](https://krebsonsecurity.com/tag/dnspionage/)、 [DNS 劫持](https://en.wikipedia.org/wiki/DNS_hijacking)和 [DNS 中毒](https://www.howtogeek.com/161808/htg-explains-what-is-dns-cache-poisoning/)攻击——墙上写着 DNS 已经成为针对全球企业和政府的[网络攻击](https://thenewstack.io/risks-dns-hijacking-serious-take-countermeasures/)的归零地。这些攻击将消费者数据置于风险之中，扰乱业务，造成重大损失，其程度显然不容忽视。

想想仅在过去六个月中发生的与 DNS 相关的网络活动。去年 11 月，一次与 DNS 相关的攻击通过尼日利亚、俄罗斯和中国的互联网服务提供商改变了谷歌的流量，将搜索数据暴露给了这些国家的攻击者。今年 1 月，FireEye [发布了一项研究](https://www.fireeye.com/blog/threat-research/2019/01/global-dns-hijacking-campaign-dns-record-manipulation-at-scale.html)，确定了一场全球 DNS 劫持活动“已经影响了中东和北非、欧洲和北美数十个属于政府、电信和互联网基础设施实体的域名。”接下来的一个月，ICANN(互联网名称与数字地址分配机构)发布了一份警告，呼吁企业加强努力，更好地保护他们的 DNS，包括安装更强的技术。最近,“海龟”劫持活动危害了十几个国家的组织。每一个突发新闻故事都重新引起人们的关注，并让企业疑惑为什么 DNS 越来越成为攻击目标。

## DNS:回报丰厚的简单目标

以前以其他企业系统为目标的攻击者已经认识到，在企业、政府和其他组织的网络中，DNS 可能是一个相对薄弱的环节。此外，由于 DNS 在协调所有互联网和应用程序流量方面的核心作用，恶意行为者通过对 DNS 实施攻击所造成的损害比其他攻击更大。

DNS 是企业的主要网关，因此随着基础设施变得越来越分散和复杂，它往往容易受到攻击。因此，攻击者正在探索他们能够探索的任何和所有角度，以便利用这个入口点。我们将继续看到针对 DNS 控制平面(注册服务商、权威 DNS 系统)和 DNS 缓存层次结构的攻击(例如 DNS 中毒攻击)，直到目标组织广泛实施众所周知的最佳实践域安全措施。

## 企业可以采取的保护其 DNS 的步骤

幸运的是，有具体的方法来减轻这些 DNS 威胁。尽管这些方法看起来是常识性的，但即使它们是有效的，也并不总是被付诸实践。

首先，加强访问控制:企业应首先在其 DNS 提供商和注册服务商处实施双因素身份认证和单点登录。如果公司使用脚本或 API 来更新 DNS，则应使用强身份认证密钥，并将密钥的使用仅限于有效来源(即 DNS 注册商、DNS 控制面板和 API 的 IP 白名单)。监控是另一个重要组成部分，组织应审核敏感 DNS 记录的任何更改，并将 DNS 供应商的审核记录绑定到 SIEM 或其他监控系统中。

所有这些措施都应部署在更广泛讨论的 DNS 安全措施之上，包括实施 DNSSEC，通过顶级域对其进行数字签名和验证来保护 DNS 信息的完整性，并部署冗余 DNS 以避免因 DDoS 或网络故障而导致的停机或中断。

## 克服 DNS 安全障碍

毫无疑问，DNS 已经成为一个目标，但企业对关键安全措施的采用却滞后了。事实是，直到最近，组织有效保护 DNS 所需的技术，如 DNSSEC、DNS 冗余或自动审核管道，都难以实施，导致性能或功能折衷，或者根本得不到提供商的支持。幸运的是，来自现代 DNS 技术提供商的创新使得更容易地实施这些控制成为可能，来自 ICANN 等全球监管组织的支持将推动继续关注优先考虑安全性。随着 DNS 日益成为攻击者的诱人目标，企业现在应该采取措施来保护其 DNS 部署的可用性和完整性。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>