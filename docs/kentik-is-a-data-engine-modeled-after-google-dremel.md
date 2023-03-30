# Kentik 是一个模仿 Google Dremel 的数据引擎

> 原文：<https://thenewstack.io/kentik-is-a-data-engine-modeled-after-google-dremel/>

总部位于旧金山的初创公司 [Kentik](https://www.kentik.com/) 在 SaaS 模式中采用大数据方法来实现网络流量智能，这些公司包括 [Box](https://www.box.com/home) 、 [Dailymotion](https://www.dailymotion.com/us) 和 [Yelp](https://www.yelp.com/) 。

它依靠其所谓的“后 Hadoop 大数据引擎”，为数十亿条记录的多个用户的同时查询提供亚分钟级响应，以提供对网络性能和安全性的洞察，特别是 DDoS 攻击。

它的客户往往是网络和 SaaS 提供商本身，因此 Kentik 提供了对他们所依赖的“数字供应链”的可见性。

“我们的客户正在寻找一些'现代'，这意味着在线，全分辨率，开放，而不是孤岛，”首席执行官阿维弗里德曼说。

“传统的方法是汇总数据，然后丢弃数据。他们不想那样。如果他们受到攻击，他们想知道流量发生了什么。他们希望[他们组织内的]其他团队能够使用它。”

其典型客户可能有数百台设备，每台设备每秒发送数百到数千条记录。他说，尽管一些人试图为此建立自己的开源系统——使用 Impala、Hadoop 堆栈上的 Drill Kudu、Elastic、Spark——但在大规模上，它们往往表现不佳，运行它们可能会令人不知所措。

## 机器对机器数据

该公司仿照谷歌 Dremel 编写了自己的列存储数据库，名为 Kentik Data Engine，旨在处理机器对机器的数据。

它从多个来源接收数十亿条 [NetFlow](https://en.wikipedia.org/wiki/NetFlow) 、 [sFlow](http://www.sflow.org/) 、 [IPFIX](https://www.whatisipfix.com/) 、 [BGP](http://www.enterprisenetworkingplanet.com/netsp/article.php/3615896/Networking-101-Understanding-BGP-Routing.htm) 和 [SNMP](https://www.manageengine.com/network-monitoring/what-is-snmp.html) 数据记录，然后在数据进入系统之前，用路由信息、地理位置和威胁情报等内容丰富数据。

它可在几秒钟内用于临时分析、警报和仪表板，并且完整的数据集可保留 90 天。数据可以在传输过程中加密，并且每个客户的实例都与所有其他实例相隔离。

它使用 Postgres 作为 API，拥有自己的查询和存储层。

用户可以跨 60 个交通领域进行查询，并设置自己的功能来根据自己的选择分割数据。他们可以编写自定义警报，可视化和过滤工具有助于更深入地挖掘攻击的根源。

还可以使用代理发送服务器基础架构数据，在内部部署该服务。

## 保持专注

弗里德曼将该公司的领导团队描述为“来自网络方面，但具有大规模运营基础设施经验的人。”

联合创始人首席工程师伊恩·派伊和首席架构师[伊恩·阿普尔盖特](https://www.linkedin.com/in/ian-applegate-b0190420)来自内容交付网络和安全提供商[cloud flare](https://www.cloudflare.com/)；互联网基础设施提供商 [Internap](http://www.internap.com/) 的联合创始人兼销售副总裁[贾斯汀·比格](https://www.linkedin.com/in/jbiegel)。弗里德曼在 CDN 和云服务提供商 Akamai 工作了十多年。

这家初创公司已经筹集了 3820 万美元，最近一次是在 8 月份宣布的 2300 万美元的 B 轮融资。

弗里德曼说，作为一家成立 2 年的初创公司，该公司正试图保持密切关注。

“我们的重点是从企业内部到最终用户或业务合作伙伴。我们不是像 [Keynote](http://www.keynote.com/about) 、[千眼](https://thenewstack.io/thousandeyes-extends-network-monitoring-internet/)和其他做“如果”( what if)场景的人那样做综合分析，而是看实际流量。因此，当我们看到问题时，我们可以指出实际问题所在。

“如果有警报，我们今天不会尝试调试，也没有数据可以在浏览器内部、应用程序堆栈内部，甚至在某种程度上在返回路径中进行调试。我们看到的数据是百分之百的出站路径。我们没有看到太多的返回路径。你通常想从流量入手，然后使用其他类型的综合分析工具进行调试。通常，我们会与其他进行综合监控的系统共存。它是来自路由器和交换机、主机、虚拟机管理程序、负载平衡器的数据，可以发送流量摘要，然后我们可以获取其他基础架构数据(SNMP 等),并向人们显示流量的路径。”

它的可视化包括时间序列折线图、条形图和堆积折线图、比较条形图和交通流量图。用户可以根据比特、包和每秒流量等指标分析流量；端点，例如唯一的源和目的 IP 地址；和抖动等网络性能。

所有数据都可以通过门户 API 在线获得。

“许多人围绕它进行整合，将 ELK (Elasticsearch，Logstash，Kibana)层的见解带给做应用程序或安全分析的人，”他说。

Kentik 通常与另一种服务一起使用，例如基于度量的监控— [新遗迹](https://thenewstack.io/new-relic-takes-configuration-errors-infrastructure-monitoring/)、[信号效果](https://thenewstack.io/signalfx-a-saas-to-monitor-apps-at-any-scale/)、[波前](https://thenewstack.io/wavefront-takes-data-analysis-scale/)、[数据狗](https://thenewstack.io/datadog-monitors-scalable-systems/)；经典的应用程序性能管理解决方案；或者弗里德曼所说的“合成监控”选项，如 [Catchpoint](http://www.catchpoint.com/) 或[千眼](https://thenewstack.io/thousandeyes-extends-network-monitoring-internet/)。

在运营方面，它的主要竞争对手是 Arbor Networks 在安全使用案例方面，它的主要竞争对手是思科收购的 Lancope，保留数据以供取证访问，但这不是它的主要使用案例。除此之外，它是 DIY-Elastic，人们试图有效利用运营数据的任何 Hadoop 堆栈。开源 [NFDump](https://github.com/phaag/nfdump) 和 [pmacct](http://www.pmacct.net/) 是单机竞争对手。在供应商领域，它正在与设备竞争。

Yelp 负责工程、运营和基础设施的副总裁 Sam Eaton 表示:“平均每月有超过 1 亿的独立访客访问 Yelp，我们看到流量达到了每秒数千兆位，因此，我们能够实时深入了解所有网络流量并获得真正的洞察力至关重要。

“这正是 Kentik 帮助的地方。我们可以看到以前根本看不到的东西。”

特征图片:[交通](https://www.flickr.com/photos/96dpi/3095251994/in/photolist-5HvYzG-8WYyUs-7RUVA5-6UhY8j-6i14LJ-t8HmX-AvScRU-5HNixE-easv3-9WdXix-6ou3pK-bmvvq-2MyHVt-dC6Tf4-J6PXd-6i14jG-6hVVap-57bbjv-bV9qz-5bjrav-6i14oy-2N6sZ-7yfpzR-6i14rq-En96-fr1NAJ-8upbZT-dX4tYH-9RRAua-8GUAR9-aCjKfL-aCh5tM-6i1489-6hVUDn-nsdCMU-8BB6WC-5QVjGc-8ijGps-6hVV8i-aCh5zg-6hVV5c-cEjbs-aCjK8s-aCh5Ap-9Vwid2-agaiso-cE44qo-3b59DY-qYe6sp-7PAweF)，由[安德里亚斯杠杠](https://www.flickr.com/photos/96dpi/)，持**下[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)。**

思科和[新遗迹](https://newrelic.com/)是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>