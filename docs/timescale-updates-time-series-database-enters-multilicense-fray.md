# 时标更新时间序列数据库，进入多许可证之争

> 原文：<https://thenewstack.io/timescale-updates-time-series-database-enters-multilicense-fray/>

在一片关于开源许可未来的意见声中，时序数据库供应商[时标](https://thenewstack.io/timescaledb-focuses-query-power-scale/)发布了其最新版本，采用了多层许可模式。

[TimescaleDB 1.2](https://blog.timescale.com/timescaledb-1-2-analytical-functions-advanced-data-lifecycle-management-improved-performance/) 现在不仅出现在[开源项目](https://github.com/timescale/timescaledb) (Apache 2.0)中，还带有社区特性(时标许可)和企业特性(商业许可)。

该公司还宣布在由 Icon Ventures 牵头的 A1 轮融资中获得 1500 万美元，使其融资总额超过 3100 万美元。

时标认为，公共云的主导地位允许一些人将开源视为免费的研究和开发，他们可以使用而无需为其做出贡献。“如果正在开发技术的公司不能围绕它建立一个可持续的业务，他们不会存在太久，”时标联合创始人兼首席技术官[迈克·弗里德曼](https://github.com/mfreed)说。

反过来，云供应商指出他们对开源项目的贡献。

争议涉及公共云供应商的一种做法，一些人称之为剥离开采——本质上是提供开源技术而不添加任何东西，如 AWS 的[托管 Kafka 服务](https://aws.amazon.com/msk/)和[亚马逊 DocumentDB](https://aws.amazon.com/documentdb/) ，一种类似 MongoDB 的数据库。

对此， [Redis](/redis-pulls-back-on-open-source-licensing-citing-stingy-cloud-services/) 、[合流](https://www.confluent.io/blog/license-changes-confluent-platform)、[蟑螂实验室](https://www.cockroachlabs.com/cockroachdb-community-license/)、[弹力](https://www.elastic.co/blog/doubling-down-on-open)等公司纷纷修改了授权模式。

Joyent 的布莱恩·坎特里尔(Bryan Cantrill)批评了 T2 的这一观点，他说:“我们可以接受这些公司本质上是专有软件公司，尽管它们的开源软件是亏损的。但相反，这些公司正试图通过许可进入这个自相矛盾的世界。”

甲骨文公司的 [Andrew Mendelsohn](https://www.oracle.com/corporate/executives/andrew-mendelsohn.html) 说[说](https://www.theregister.co.uk/2019/01/17/oracle_exec_opensource_vendors_locking_down_licenses_proves_they_were_never_really_open/):“无论他们有什么样的开放外表，他们都在试图夺回…因为如果任何人都可以拿起他们的代码，然后用它来构建云服务，他们将很难在云世界中生存。”

基于开源软件的公司的基本模式是[开放核心](https://docs.google.com/spreadsheets/d/17nKMpi_Dh5slCqzLSFBoWMxNvWiwt2R-t4e_l7LPLhU/edit#gid=0)——部分开源，但其他功能是开源的，是付费计划的一部分。弗里德曼说，这让不喜欢拥有黑匣子的客户感到沮丧，也让不得不维护基本相同的东西的两个版本的供应商感到沮丧。

Freedman 说，Timescale 的模式最接近于 Elastic，后者在中间创建了一个称为社区的层，除了云提供商之外，任何人都可以免费使用。

“[你]定义你的许可——这是纯开源的——比如说 Apache 2——而另一部分，在专有许可下，它仍然是开放代码，对于大多数用户来说，它仍然可以免费使用。受限制的人是那些希望提供 it 即服务而不增加任何价值的云提供商，”弗里德曼说。

TimescaleDB 1.2 所有基本代码都在 TimescaleDB GitHub 存储库中提供源代码，并打包在一个二进制文件中。

新的社区功能包括:

*   高级时间序列分析功能:间隙填充、上一次观察结转(LOCF)查询、插值
*   数据重新排序以实现更快的查询
*   自我调整数据区块大小以优化性能

企业服务包括:

*   自动化数据生命周期管理
*   模式设计和查询优化
*   生产部署协助
*   企业级 SLA
*   担保和赔偿

根据 DB-Engines 的数据，时间序列数据库是过去两年中增长最快的数据库领域。

它面临着一系列的[竞争对手](https://db-engines.com/en/ranking/time+series+dbms)，包括[涌入](/flux-influxdatas-new-language-for-time-series-data/)、[动物群](https://thenewstack.io/faunadb-harnesses-serverless-cloud/)，以及亚马逊新发布的[时间流](https://aws.amazon.com/timestream/)。

“在现代网络和物联网规模的时间数据需求的驱动下，时间序列数据库正在从一种利基技术发展成为一种主流产品类别，其重要性与交易和分析数据库相当。但在 TimescaleDB 之前，时序数据库正在进行不幸的权衡，这损害了它们作为通用应用平台的效用，”Icon Ventures 的普通合伙人迈克尔·穆拉尼(Michael Mullany)谈到其投资时说。

该公司将建立在近 30 年历史的 Postgres 之上的 TimescaleDB 吹捧为唯一一个不仅可伸缩，而且支持 SQL 和关系数据模型的时间序列数据库。

[https://www.youtube.com/embed/FazTji7l9JI?feature=oembed](https://www.youtube.com/embed/FazTji7l9JI?feature=oembed)

视频

时标联合创始人兼首席执行官 Ajay Kulkarni 说:“当我们推出这款产品时，人们认为我们疯了。“但在我们看来，如果你想要一个支持完整 SQL 并可以使用所有工具的东西，这是唯一的方法——可视化选项，如 Tableau 和 Kafka 和 Spark out of the box。

“关系数据模型对我们也很重要，因为我们有时序数据，也有描述时序数据的元数据。元数据可以是机器，可以是用户，也可以是系统。这就是我们选择这种方法的原因。”

时间刻度客户包括**康卡斯特**、LED 技术厂商 [**Cree**](https://www.cree.com/) 、超级计算机厂商 [**Cray**](https://www.cray.com/) 以及 [**欧洲航天局**](https://blog.timescale.com/european-space-agency-postgresql-geospatial-time-series-9cced899c41d/) ，它们使用时间刻度来存储太阳和日光层的时间序列数据。

专题图片:José Javier Polo 的《时间流逝》。公共领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>