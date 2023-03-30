# 一个亚马逊的异常现象变成了一个吞噬服务器的怪物

> 原文：<https://thenewstack.io/an-amazon-anomaly-that-metastasized-into-a-server-eating-monster/>

当一个应用程序在几个虚拟机之间线性扩展时，它们行为中的任何特性都可能呈指数级扩展。总部位于旧金山的初创公司 [Clever](https://clever.com/) 就是这种情况，它为教育工作者和学生提供移动登录生态系统。像许多创业公司一样，聪明运行在亚马逊 EC2 上。

科林·施梅尔芬(Colin Schimmelfing)是宾夕法尼亚州斯沃斯莫尔学院(Swarthmore College)的 2010 届毕业生，几年前，他为了赢得一场纯粹的黑客马拉松，最终设计了 Quantcast 的实时质量控制测量系统。现在是一名聪明的工程师，Schimmelfing 本周在[聪明博客](http://engineering.clever.com/2014/12/10/when-your-ip-traffic-in-aws-disappears-into-a-black-hole/)上写了一个微小的行为异常，每当有人试图寻找它时，它就会消失。当 Amazon Web Services (AWS)中出现这种行为的多个实例时，这种异常就变成了一只野兽，夺走了三分之一工作实例的健康。

“就在我们需要我们的基础设施‘正常工作’的时候，”Schimmelfing 写道，“我们开始收到奇怪的错误，机器开始出现死机的情况。”他将这种现象称为“海森堡”，以纪念物理学家[沃纳·海森堡](http://www.aip.org/history/heisenberg/p08.htm)——他证明了一种能够被测量的量子现象可以真正消失，只是因为有人寻找它。

Clever 主要服务于教育工作者，但其客户群与大多数组织并没有太大的不同。像零售服务提供商一样，它的流量模式往往是季节性的。Schimmelfing 说，对于 Clever 来说，在初秋开学前后，流量将增加两倍。

Clever 选择的数据库是 MongoDB，它使用分片副本集。在一个常见的 MongoDB 设置中，至少可以有九个节点。其中，两个是副本集所分配到的数据节点。Clever 根据需要构建尽可能多的大规模 EC2 实例，充当 Clever 所称的“工作者”，与副本集节点通信，MongoDB 称之为“ [mongods](http://docs.mongodb.org/manual/reference/program/mongod/) ”

去年秋天，Clever 需要增加一船新实例，以满足其教育机构客户的需求高峰。三分之一未通过健康检查的工人无法与任何蒙古人接触。正如 Schimmelfing 所描述的，即使是普通的 **netcat** 命令(缩写为 **nc** )也无法通过 MongoDB 的默认端口 27017 找到与 mongod 的连接。

这不是 Amazon 可用性区域的问题，因为其他节点可以很好地访问相同的 mongods。这不是端口的问题，因为同一个安全组中的其他节点正在成功地使用该端口。

进入亚马逊的付费技术支持人员，Schimmelfing 对他们只有赞美。正如对来自 **tcpdump** 的输出的检查所揭示的那样，当 mongod 未能将它的 MAC 地址发送回一个工作者时，并不是因为 mongod 没有接收。相反，这个工人没有收到 mongod 的确认。此外，每当有人对行为不端的工人运行 **traceroute** 时，奇怪的行为立即消失。它可能不会消失，新启动的实例可能会再次表现出相同的行为。

像这样的一个谜可能会让像海森堡这样一个极度好奇的家伙放下薛定谔的猫，开始从事云服务管理。

亚马逊和 Clever 的调查最终找到了罪魁祸首。这可以追溯到 1982 年，远远早于人们对互联网协议网络的安全概念的设想。

> 这与 IP 地址不能直接解析为 MAC 地址这一明显事实有关。

当通过以太网发送数据包时，源地址和目的地址必须清楚地拼写出来——我指的是以太网地址，包括 MAC。所以在早期的 TCP/IP 中， [*地址解析协议*](http://www.faqs.org/rfcs/rfc826.html) (ARP)被创造出来，使一个地址上的主机能够获得给定 IP 上所有主机的 MAC 地址。

这是一个广播消息；一个主持人发过来，每个听到的人都勤勤恳恳回应。正如你所想象的，地址解析是一种发生在互联网协议上的事情…嗯，有点频繁。

> 以互联网的发展速度，到 1990 年，它可能已经演变成 ARP 广播的杂音，就像以 10 倍的速度播放菲利普·格拉斯的作品。

因此 *ARP 缓存*被创建，这是内存中的一个小表，用来存储从最后一次 ARP 广播中检索到的被认为是“最近”的 MAC 地址。如果主机要寻找的 IP 地址不在缓存中，它只会从网络中获取 MAC 地址。起初，20 分钟似乎是缓存 ARP 地址的合理时间。当然，主机不会每 20 分钟就更换一次 IP 地址。后来变成了 10 个，最近几年变成了 5 个。

事实证明，Clever 的 ARP 缓存继续包含死实例的 MAC 地址数据，仅够让整个过程超时几分钟。每当 mongod 试图回应工人，它认为它是在回应正确的地址…这可能是正确的五分钟前。

ARP 是有 30 年历史的系统架构的遗迹，是在互联网成为人权之前设计的。我们可能不会偶然发现它，除非并且直到 21 世纪的一个非常大规模的服务开始以一种从未想过的方式利用它:作为一个最新的 MAC 地址目录。

Schimmelfing 说，目前，亚马逊建议 Clever 使用一个 **cron** 命令——一个简单的预定指令——每五分钟左右手动清理一次 mongods 自己的 ARP 缓存。就目前而言，这种解决方案似乎行得通。但是明年呢，那时 Clever 的业务可能会再翻三倍。科林下次能坚持两分钟吗？一分钟？或者，Linux 工程师是否早就应该下楼，走进布满灰尘的旧 Unix 命令的地下室，进行一些大规模的微调？

*特色图片[通过](https://www.flickr.com/photos/jdhancock/4339353059/in/photolist-m2jw4v-8Bj543-7Bsju4-8K9VN7-hzTeW3-dUBYzn-e4r3FS-a2Tpbp-mGXmB4-bpYssD-daX1pi-6appeZ-9RTaVL-dEPtb1-9pzXRQ-p7jVmj-8PLawX-boSCRq-4sq9Wt-o2taS6-5FKRva-bR2h5r-buji8t-4yf6dK-4ZRnaJ-akiRYm-ei9a5Z-ahcQZN-boSCVb-4QAGjd-6TkeUf-agdj6N-aEsoyL-h8A4We-buji42-3LfQet-9dQhTQ-5BkdmG-5Db7Ar-5Db8m8-oHuYcp-obVtEt-6UbjXT-cCogxb-kdEZ5K-dtpXKA-dHcKgW-7FGCDx-393Mvg-dTJBJU) Flickr 知识共享。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>