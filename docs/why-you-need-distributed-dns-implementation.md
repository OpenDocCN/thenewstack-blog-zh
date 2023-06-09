# 为什么您需要分布式 DNS 实施

> 原文：<https://thenewstack.io/why-you-need-distributed-dns-implementation/>

[](https://www.linkedin.com/in/sheraline-barthelmy-0625b870/)

 [谢拉琳·巴塞尔米

谢拉琳是 Cox Edge 的产品、营销和客户成功主管，这是一家来自 Cox Communications 的边缘云初创公司。在 Cox Edge，她专注于开发客户和开发人员赖以构建下一代 Edge 应用的工具和系统。](https://www.linkedin.com/in/sheraline-barthelmy-0625b870/) [](https://www.linkedin.com/in/sheraline-barthelmy-0625b870/)

异地恋很难维持。距离增加了沟通失败的机会。

人脉和生活一样，也有同样的问题。

由国家或大陆分隔的源和目的 IP 地址导致数百毫秒的延迟，使得实时应用程序变得无用。

对于在线游戏、增强和虚拟现实、关键机器监控传感器或紧急医院监控设备，超过 7 到 10 毫秒的延迟可能意味着晕车、机器故障导致火灾或爆炸的风险以及可能危及患者生命的延迟治疗。

虽然边缘计算可以通过将计算、存储和分析移至更靠近终端用户及其设备的位置来在很大程度上解决距离问题，但由于域名系统(DNS)解析的延迟，事情仍然可能发生故障。

将最终用户查询发送到世界另一端的权威域名服务器的递归 DNS 解析器，或者映射到另一个国家/地区的服务器的 DNS 解析，可能会对延迟和实时应用程序响应产生负面影响。

IP 选播就是为了解决这个问题而设计的。

## 高效路由

任播是一种网络寻址和路由方法，它从网络中的多台服务器同时宣告相同的 IP 地址。边界网关协议计算源和目的地之间的最短拓扑路径，并将用户查询路由到最近的服务器。

如果选择的服务器出现故障，任播会选择下一个可用的服务器(在重新计算最短路径后)并重定向用户请求，而不改变目的 IP。

DNS 和 Anycast 是一个完美的组合。DNS 查询具有较小的数据包大小，这使得通过用户数据报协议的通信比传输控制协议(TCP)更有效。作为一种可靠的协议，TCP 需要三次握手，并执行重试和其他消耗带宽的功能。

用户数据报协议(UDP)发送数据包并将其遗忘。没有建立可靠连接的重试或尝试。DNS 查询足够小，可以包含在一个 UDP 数据包中。DNS 的任播将客户端查询路由到最近的 DNS 服务器。如果该服务器出现故障，Anycast 会自动将 DNS 请求重定向到下一个可用的(也是最近的)IP，无需客户端干预。

因为通信是通过 UDP 进行的，所以哪个 DNS 服务器响应没有区别。与 TCP 相比，不需要重新建立连接，节省了时间和带宽。

内容交付网络(CDN)提供商使用任播将用户路由到最近的可用边缘服务器，如果最初选择的服务器出现故障，则自动将用户重定向到下一个最近的可用服务器。

## DDoS 缓解

任播的另一个显著优势是分布式拒绝服务(DDoS)缓解。在 DDoS 缓解技术过滤了一些攻击流量后，任播将剩余的流量分散到数据中心，这有助于防止任何一个位置被请求淹没。随着网络规模和容量的增长，标准 DNS 流量会消耗一小部分名称服务器容量，这使得攻击者很难获得大量分布式 DDoS 流量。

虽然 Anycast 旨在保护服务器免受最复杂的 DDoS 攻击，但网络工程师应确保即使几个节点出现故障，DNS 服务器也能继续为最终用户的请求提供服务。

凭借遍布全球的服务器，许多顶级 CDN 提供商可以通过限制他们广告的任意播 IP 的数量来承诺 100%的正常运行时间。如果每个 DNS 查询都被解析到数据中心，那么崩溃的边缘数据中心可能会带走一部分互联网——如果存在点(POP)路由器宣布每个任播 IP，就会出现这种情况。

为了防止这种情况发生，Edge POPs 只宣传少数选播云 IP，旨在确保请求进入健康的数据中心。

## 享受 5G 的好处

世界上最大的 CDN 提供商将 Anycast 与几个实施选项相结合，提高了其 DNS 解决方案的性能和可靠性。Zone Apex Mapping (ZAM)就是其中之一。

ZAM 直接将顶级主机名解析为最佳边缘服务器 IP 地址，消除了 CNAME 链带来的延迟，并减少了在其平台上对主机名的 DNS 查找时间。

凭借 Anycast DNS 提供的可扩展性、可靠性和灵活的实施选项，它看起来将在采用 5G 等新技术方面发挥重要作用。

凭借 2021 年超过 5.8 亿的用户，5G 可能成为有史以来采用速度最快的移动平台。物联网、边缘计算、自动驾驶汽车、医疗保健和人工智能用例等应用将受益于 5G 的超低延迟和处理速度。

也就是说，网络运营商有他们的工作要做。部署 5G 不仅仅是从当前的 LTE 标准升级无线接入网络(RAN)基础设施。如果他们的用户想要享受 5G 的好处，运营商将需要改造他们的移动网络架构，从 DNS 开始。

当前的 DNS 架构将服务器部署在几个区域 pop 中，在延迟方面不能满足依赖于实时交互的应用程序的要求。要求超低延迟(< 5 毫秒)和需要数十毫秒的慢速 DNS 查找的 5G 应用将导致这些应用失败。

在 5G 之前，RAN 提供大约 50 毫秒的延迟，这隐藏了 DNS 延迟。但在 5G 中，延迟下降到 5 毫秒以下，缓慢的 DNS 查找会影响可能需要小于 5 毫秒延迟的关键通信。

## 向边缘靠近

边缘计算将资源移动到网络边缘，更靠近用户和生成数据的设备。这减少了延迟和通过移动网络回传到中央云的流量。

Anycast DNS 实施有助于在边缘数据中心大规模部署 DNS 服务器，使应用程序能够实现所需的较短 DNS 查找时间。Cox Edge 是一个领先的边缘开发平台，它提供的任播 DNS 解决方案为最终用户提供了极低的查询延迟。

用户几乎可以即时获得 DNS 记录更改，非常适合迁移和故障转移等使用情形。Edge Anycast 平台具有快速解析等基本功能，可从云边缘提供 DNS 数据。智能路由将 DNS 流量汇集到最佳 DNS 服务器，近乎实时的传播在几秒钟内将所有 DNS 更新推送到全球。

随着边缘计算成为新的标准，诸如任播 DNS 之类的分布式 DNS 实现将成为新一代实时应用的基础。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>