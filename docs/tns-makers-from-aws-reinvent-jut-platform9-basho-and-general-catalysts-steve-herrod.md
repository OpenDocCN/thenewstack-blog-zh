# 来自 AWS re:Invent 的 TNS 制造商:Jut、Platform9、Basho 和 General Catalyst 的 Steve Herrod

> 原文：<https://thenewstack.io/tns-makers-from-aws-reinvent-jut-platform9-basho-and-general-catalysts-steve-herrod/>

在上周的 AWS re:Invent 会议上，New Stack 创始人 Alex Williams 与来自 [Jut](http://www.jut.io/) 、 [Platform9](http://platform9.com/) 、 [General Catalyst](http://www.generalcatalyst.com/) 和 [Basho](http://basho.com/) 的嘉宾坐在一起。

基于容器的开发堆栈每天都在增长，特定企业在任何给定时间运行的服务数量也是如此。微服务经常被讨论，特别是集中在容器、数据库和物联网如何适应当今开发团队可用的各种基于云的平台的交叉点上。

## Apurva Davé ，Jut

威廉姆斯首先与[Jut](https://www.linkedin.com/in/apurvadave)的营销副总裁阿普娃·达夫进行了交谈。Jut 的目标是将数据栈以数字排气、日志和指标的形式呈现给开发者，告诉你应用内部正在发生什么。Jut 通过流分析和可视化来实现这一点。这有助于开发人员抽象处理数据分析的复杂性，以便更好地向他们的团队解释。

[阿普瓦·戴夫，Jut: At AWS re:Invent](https://thenewstack.simplecast.com/episodes/apurva-dave-jut-at-aws-re-invent)

Jut 有自己的数据流语言 Juttle。开发人员可以在 Juttle 中使用高级声明性语言，通过浏览器实时编译代码。uttle 还具有一个分析引擎，这对于大数据聚合很有用。这包括窗口分析、按百分比分组的能力，以及在 Jut 平台上实现附加功能。此外，Jut 可以处理事件、指标、实时和历史数据，允许用户在需要时同时结合这两个方面。

## Sirish Raghuram，9 号平台

platform 9 的联合创始人兼首席执行官 Sirish Raghuram 与 Williams 讨论了其在 Linux 和 VMware 环境下运行的 OpenStack 即服务平台。

这是 SaaS 的产品，非常强调监控。Platform9 与来自 Mirantis 和 Red Hat 等公司的 VMware 和 OpenStack 发行版竞争。专业服务提供商也可以被视为 Platform9 的竞争对手。软件管理和配置在内部运行的数据平面。这是一个基于云的系统，运行配置文件，并作为一个应用商店。它是用 Python 写的。OpenStack 被分解成运行在公司服务器上的迷你应用。这些应用程序可以用任何语言编写。

[Sirish Raghuram，平台 9: At AWS re:Invent](https://thenewstack.simplecast.com/episodes/sirish-raghuram-platform9-at-aws-re-invent)

复杂性是客户的头号问题，也是新数据中心体系结构面临的挑战。创建一些弹性基础设施的复杂性说明了 AWS 为何如此受欢迎。AWS 开放了一个新的基础设施，为最终用户降低了复杂性。OpenStack 受到了批评，但它确实为公司提供了一种方式，为内部应用程序提供类似亚马逊的环境，这些应用程序可能不需要扩展到任何程度，并且已经在虚拟化基础设施上运行。在应用程序开发领域，框架(如 Kubernetes)和技术(如容器)将更受欢迎。

Platform9 最近向 VMware [vSphere](https://www.vmware.com/products/vsphere) 提供了他们的产品。目前运行 vSphere 的企业级组织可以非常快速地运行 OpenStack，将环境迁移到可编程的基础架构。不需要重组，增加了使用 DevOps 实践的能力。

## 史蒂夫·赫罗德，通用催化剂公司

通用催化剂公司的总经理史蒂夫·赫罗德讨论了技术政策和投资的未来。世界正朝着多云平台发展，一些运行 SaaS，另一些运行亚马逊或 VMware 以及多个容器供应商。作为一名投资者，Herrod 强调，提供全行业安全策略的东西是未来大型公司的基础。

[史蒂夫·赫罗德，通用催化剂:在 AWS 重新:发明](https://thenewstack.simplecast.com/episodes/steve-herrod-general-catalyst-at-aws-re-invent)

Steve 继续说道，注意到围绕 Amazon 的 Lambda 有一个有趣的讨论，他问道，当以高抽取编写时，这样的代码如何实现真的重要吗？因此，开发人员必须不断地问，“这是正确的抽象吗？”并摆脱不必要的复杂性。这可以通过以应用程序为中心的基础架构来实现，并构建更智能的基础架构来查看数据并使其表现更好。这也要求硬件能够支持不同的应用程序类型，实现工作流之间的无缝转换。

## Adam Wray，Basho

[Adam Wray](https://www.linkedin.com/in/adamwray),[Basho](http://basho.com/)的首席执行官兼总裁花时间与 Williams 谈论物联网的未来。Basho 最近推出了 [Riak TS](http://basho.com/products/riak-ts/) ，一个运行在他们数据平台之上的时间序列数据库。Riak TS 提供了键值和对象存储特性，Apache Spark、Redis 和 Apache Solr 等插件可以与 Riak TS、Riak S2 和 Riak KV 集成。Riak TS 提供范围查询、简化的数据模型和数据协同定位，针对更快的读/写时间进行了优化，还具有无主架构和近线性扩展功能，可随着客户数据库的增长而增加容量。

[亚当·雷，松尾芭蕉](https://thenewstack.simplecast.com/episodes/adam-wray-basho-at-aws-re-invent)

Wray 指出，在物联网中，90%收集的数据从未被接触过。它经常未经审查就被搁置，或者被扔掉。他随后强调，物联网是关于终端设备的，并询问公司的数据如何才能成为有价值的工作负载？Basho 通过将数据与工作负载特别绑定来帮助公司实现这一点，这样客户就不必计算模式、大规模工作或应用分析。他们可以使用 Basho 的预设设置来拖入一个常见的案例工作负载并运行它。

这四个采访以及更多内容可以在新的 Stack 的 [Simplecast](https://thenewstack.simplecast.com/) 频道上收听。

Basho、Red Hat 和 VMware 是新堆栈的赞助商。

专题图片:(从左至右)通用催化剂公司的史蒂夫·赫罗德，新堆栈公司的亚历克斯·威廉姆斯。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>