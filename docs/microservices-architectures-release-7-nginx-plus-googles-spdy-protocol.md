# NGINX Plus 第 7 版及其对微服务架构的影响

> 原文：<https://thenewstack.io/microservices-architectures-release-7-nginx-plus-googles-spdy-protocol/>

web 服务网关 NGINX Plus 的第 7 版部署了一个组件，该组件可能对微服务架构和物联网的发展至关重要。

软件开发人员着迷于微服务架构的出现所带来的可能性。首席信息官们对物联网的理想深信不疑，物联网部分是幻想，部分是营销:通过更小、分布更广、支持 IP 的传感器和其他设备，应用数量可能会激增。这两种理想都需要一个更胖、更广、更熟练的网络，如果它们想要摆脱胚胎期的话。

## 微服务快车道

R7 的主要改进是增加了对 HTTP/2 的支持，这是互联网主要传输协议[的一个姗姗来迟且有些争议的版本，去年 2 月由 IETF 正式采用](https://www.mnot.net/blog/2015/02/18/http2)。它的初衷是从根本上改进网页组装的方法，但 HTTP/2 已经成为第一代真正的非实验性微服务的渠道。

在去年 6 月 F5 Networks 的[博客文章](https://devcentral.f5.com/s/articles/microservices-and-http2)中，前网络计算记者[Lori MacVittie](https://twitter.com/lmacvittie)——现在是 F5 的技术布道者——解释了在 HTTP 上实现微服务的一个关键问题，以及 HTTP/2 如何完全解决这些问题或成倍增加这些问题，这取决于应用架构师如何采用新方案。

MacVittie 描述了 web 架构师如何创建域分片的实践——为分布式资源创建任意、独立的域——作为一种更好地促进对包含多个组件的网页的请求的方式。通过将这些组件分发到由单独的服务器处理的各个域，可以加快服务这些页面的总时间。[一些供应商吹捧域分片](https://www.maxcdn.com/one/visual-glossary/domain-sharding-2/)作为性能加速器的优点。

> Mobify 工程师 Peter McLachlan 在 2012 年写道:“域名分片是可行的，因为网络浏览器将每个唯一的互联网名称识别为不同的服务器，即使实际上所有这些域名都解析为一个服务器。”

HTTP/2 旨在通过采用 Google 的 SPDY 方法来无阻塞地并行处理无限数量的请求，从而使分片实践过时。随着 web 浏览器同时连接到服务器的数量增加，超过了最初的两个限制，这种做法的废弃变得越来越有必要。

微服务就其本质而言，将服务类别划分为不同的领域。正如 MacVittie 指出的，这也可以被认为是一种域分片的形式。从表面上看，HTTP/2 似乎也能解决这个问题，有效地一石二鸟(我不会把这称为“杀戮”，因为这会让人联想到不人道的残忍)。

但她警告说，如果任由微服务架构师自己使用，他们最终可能会将这些独立的域硬连接到他们的 DNS 模式中，将这些多个实体作为交换提供给客户，每个实体都需要自己独立的连接。

“我们能做的是在客户端和本地微服务负载平衡器之间插入一个第 7 层负载平衡器，”MacVittie 写道。客户端上的连接以 HTTP/2 指定(并且优选)的方式维护单个连接，并且仅需要单次 DNS 查找、一次 TCP 会话启动，并且仅招致一次 TCP 缓慢启动的损失。在服务方面，第 7 层负载平衡器还保持与本地域负载平衡服务的持久连接，这也减少了会话管理对性能的影响。可以优化每个本地域负载平衡服务，以便为每个服务最佳地分发请求。每个服务都有自己的算法和监控配置，以确保最佳性能。”

她没有明确地说，但是通过“第 7 层负载平衡器”，她可以简单地插入“NGINX”

NGINX 的公司网站上写道:“第 7 层负载平衡器终止网络流量并读取其中的信息”。它可以根据消息的内容(例如 URL 或 cookie)做出负载平衡的决定。然后，它与选定的上游服务器建立新的 TCP 连接(或通过 HTTP keep-alives 重用现有的连接)，并将请求写入服务器。

## HTTP/2 的第一次真正测试

最新版本的 HTTP 用一个二进制系统取代了蒂姆·伯纳斯·李最初设想的基于文本的协议，这个二进制系统本应要求使用 TLS/SSL 加密，但最终使其成为可选的。无论如何，互联网工程任务组最终还是正式采用了 Google 的 SPDY 并行请求处理提议的基础。

IETF 工作组主席马克·诺丁汉去年二月宣布“HTTP/2 已经完成”的第三段清楚地表明了并非所有人都对这个决定感到满意。

> “虽然有些人认为谷歌把协议强加给了我们，”诺丁汉写道，“但该团队中与迈克(贝尔舍)和罗伯托(佩昂，两名谷歌工程师)实际互动的任何人都知道，他们带着最好的意图来，耐心地解释他们设计背后的理由，接受批评，并与每个人合作改进协议。”

web 开发人员中剩下的反对意见，他们认为是对一个供应商技术的大规模“吞并”，去年一月由 FreeBSD 贡献者 Poul-Henning Kamp 做了最好的总结，他是[一个叫做 Varnish](https://www.varnish-cache.org/) 的 HTTP 加速器的主要开发者。

> Kamp 写道:“IETF 显然担心不相关，匆忙‘发现’HTTP/1.1 协议需要更新，并指派一个工作组在不切实际的短时间内准备它。”

“这排除了除 SPDY 协议之外的新 HTTP/2.0 的任何基础。随着 SPDY 最可怕的缺点被消除，所有其他改进的尝试都以“不在范围内”、“太晚了”或“没有达成共识”而被拒绝，IETF 现在可以通过放弃几乎所有曾经珍视的原则来宣称相关性和胜利，以换取橡皮图章式批准谷歌倡议的特权。

坎普的恐惧已经反映在黑客新闻的回音室中。一位署名为克伦威尔的撰稿人写道:“我们现在已经深入‘越差越好’的领域了。”。

> “技术杰作是好的敌人。HTTP 不太可能被彻底的重新设计所取代，就像 TCP/IP 不太可能被取代一样。”

《黑客新闻》的成员讨论了对谷歌参与 HTTP/2 的普遍沉默是否会导致类似 IPv6 的情况，即整体采用缓慢。一名成员听起来更有希望，他说只有浏览器供应商和内容提供商需要采用 HTTP/2 才能使其普及，不像 IPv6 那样需要中间路由器的支持。

所有这些政治上的争论以下列方式影响微服务的发展:只要对 HTTP/2 的总体好处仍有怀疑，HTTP 1.1 将继续作为任何广泛的、也许是联合的微服务计划的一个特征而存在。

这使得 NGINX 不得不同时跨两种协议，可能需要很长时间。去年 8 月， [NGINX 背后的商业实体开始解决人们的担忧](https://www.nginx.com/blog/early-alpha-patch-http2/)，政治争端可能会迫使微服务工程师重新思考他们如何构建自己的应用程序。

NGINX 的 Faisal Memon 写道:“有了 NGINX，只需对应用架构做很小的改动，就可以支持 HTTP/2。“NGINX 充当‘HTTP/2 网关’来简化向新协议的过渡。在前端，NGINX 与支持它的客户端 web 浏览器进行 HTTP/2 对话，在后端，它像以前一样与 HTTP/1.x(或 FastCGI、uwsgi、SCGI)对话。介于两者之间，NGINX 在 HTTP/2 和 HTTP/1.x(或 FastCGI 等)之间进行翻译。这意味着 NGINX 代理的服务器和应用程序将不会受到迁移到 HTTP/2 的影响，甚至不需要知道他们的客户端正在使用 HTTP/2。”

构建应用程序的一个大挑战是，在一个覆盖全球的基础设施上构建应用程序的栈，这一挑战是与某些其他玩家的大玩家共存的。

专题图片:[安迪·马奎尔](https://www.flickr.com/photos/andymag/)的 [7](https://www.flickr.com/photos/andymag/11400006246/in/photolist-ino1FQ-5Lids7-bEkLiM-nXxuvM-34zmuy-KUKpG-KV9TK-qKqdy4-84ZrHQ-72hkn9-ohpEub-34zmJ9-qa2v5Q-61bj9f-K3Kye-6LdmFL-dYZT4D-pQBJaX-LJ3AA-K3Ywf-9xY4QL-KUQwL-jKGDwr-KUKoN-6177ii-rL9piG-KknkL-3LqJs7-bnPGcs-nfMHpm-o4yYXW-KUUah-mde1j-piBBim-UugST-Lv3EH-uUonZY-2uqNvz-ohAsyr-5QVdmS-x27fqy-7pr9JE-czGAAq-8RmLqa-xxNtM-f9o2rE-jb4VfJ-itxek2-oTFe5g-6FhjJd) 由[CC 2.0](https://creativecommons.org/licenses/by/2.0/)授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>