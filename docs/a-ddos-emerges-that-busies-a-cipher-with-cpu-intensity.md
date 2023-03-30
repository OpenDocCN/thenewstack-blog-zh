# 一种 DDoS 出现了，它用 CPU 的密集度忙于一个密码

> 原文：<https://thenewstack.io/a-ddos-emerges-that-busies-a-cipher-with-cpu-intensity/>

6 月 13 日，香港大学[民意节目](https://popvote.hk/english/project/vote_622/stat/)投票网站上线，遭遇香港有史以来最大规模的 DDoS 攻击。投票网站旨在提供一个关于宪法改革的全民公决。 [CloudFlare 的](https://cloudflare.com)首席执行官兼联合创始人 Matthew Prince 报告流量超过 300Gbps+。

据 digitalattackmap.com 称，在投票网站上线后，攻击量是显而易见的。该服务是与 Google Ideas 和 Arbor Networks 合作开发的，可以可视化和重放全球一年的 DDOS 攻击。正如 Matthew Prince 指出的，这次攻击与其他 DDoS 攻击的不同之处在于，在攻击中优先使用了强加密密码。值得注意的是，CloudFlare 观察到的攻击是应用程序级(第 7 层)HTTPS 洪水，它优先考虑 TLSv1 DES-CBC3-SHA，这是一种与正在使用的其他低级默认密码相比占用大量 CPU 的密码。

这意味着投票站点的 web 服务器被每秒十亿个请求所淹没，每个请求都有意地请求一个处理器密集型活动，导致耗时耗力的安全握手。随后，网站无法处理每个请求的更多信息，也无法满足合法选民的实际投票流量。

这在某种程度上是很有诗意的。一种旨在确保互联网机密性和完整性的安全密码算法正被用于关闭另一项服务，从而影响了 CIA 三位一体安全模型的可用性。

这一事件也表明了如今人们对 DDoS 攻击的理解和研究越来越深入。这些攻击通常被用作掩盖更多恶意和破坏性活动的幌子，包括财务和声誉方面的活动。

DDoS 攻击越来越频繁，最新的受害者是 Evernote、Deezer 和 Ancestry.com。本月早些时候，【CodeSpaces.com】遭遇攻击，被迫关闭。对于面向互联网的服务是运营其业务的基础的初创公司和企业来说，DDoS 缓解成本和恢复计划应纳入运营战略。

企业、初创公司和企业都应该监控流量，并根据任何需要审查的可疑流量建立警报机制。由于这些攻击通常会在很短的时间内达到最大规模，因此对此类攻击的响应必须快速有效。应与网络工程师和安全专家一起准备流程和自动化脚本，以实施速率限制阈值和过滤器，并与其网络服务提供商密切合作。此外，由于 DDoS 攻击如今在其表象背后隐藏着更为恶意的攻击，一旦确定了此类攻击，企业应提高对所有其他安全控制措施的警惕性。如果项目预算允许，还有来自 CloudFlare、[pro lexic](http://www.prolexic.com/)(Akamai 拥有)、[in capsula](http://www.incapsula.com/)(imper va 拥有)的订阅服务，以及其他提供高级 DDoS 缓解的专用服务。

显然，DDoS 攻击会一直存在，而且只会变得越来越聪明。针对这些攻击的防御措施也需要做出类似的响应。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>