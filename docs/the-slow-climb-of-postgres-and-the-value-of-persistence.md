# Postgres 的缓慢攀升和坚持的价值

> 原文：<https://thenewstack.io/the-slow-climb-of-postgres-and-the-value-of-persistence/>

那些无畏的人试图给世界带来新的创新，或者新的创业，应该记住坚持不懈的力量。即使一项技术很成功，创造者仍然必须面对许多障碍来保持和发展它的成功。

本周在波斯顿举行的 PostgresVision 会议的与会者肯定听到了对这个想法的一个很好的证明，因为数据库先驱[迈克尔·斯通布雷克](https://thenewstack.io/dr-michael-stonebraker-a-short-history-of-database-systems/)博士讲述了他如何帮助 PostgreSQL 数据库进入世界，这是一个 15 年的旅程，充满了令人惊讶的高潮和低谷。

早在十年前，Stonebraker 就已经帮助诞生了第一个[世界上第一个关系数据库 Ingres，但是他在 20 世纪 80 年代早期回到了实验室创建 Postgres(后来修改为“PostgreSQL”以反映其 SQL 能力)。安格尔是如此的成功。他解释说，事实上，用户希望将他们更随意的数据类型和操作符添加到它的模式中，用于地理定位等用例。Ingres 对此问题最初解决方法是封装逻辑(通常非常慢)应用程序逻辑。](/dr-michael-stonebraker-a-short-history-of-database-systems/)

[![](img/aba976283c8a91d12a66b6a4eca3169a.png)](https://cdn.thenewstack.io/media/2019/06/a21a86d9-stonebraker-slide.jpg)

单击以嵌入。

因此，1984 年首次推出的 Postgres 的想法是提供一个支持“高级数据类型”(ADTs)的关系数据库系统。ADT 为关系数据库的更广泛使用奠定了基础，这一新功能——建立在对象关系映射的基础上——节省了开发人员大量的时间。Postgres 也是早期的数据库系统，在需要更新时不会覆盖数据，相反，只是添加一个新条目并在以后删除旧条目，这为捕获可验证的交易历史打开了大门。

但是 Postgres 并没有立即获得成功，不管它的价值有多明显。首先，Stonebraker 和他的团队有了一个看似不错的想法，用当时最好的语言 LISP 编写这个新数据库。然而，LISP 被证明是一个糟糕的选择，因为它的性能很慢——这不是你想要的数据库特性。因此，重新编写一个性能更好的 C 语言是必要的。

他们还遇到了一个潜在的致命难题。早期用户想要的不仅仅是 Postgres 开发者创造的粗糙的 ADT。他们希望复杂的 ADT 能够与他们使用的商业应用程序协同工作，比如 Arcinfo 的地理测绘软件。但是当他们接触 Arcinfo 等公司并寻求帮助时，他们被告知 Postgres 的用户群还没有大到足以保证这样的努力。商业 ADT 的缺乏会使 Postgres 靠边站，然而软件供应商对为他们自己的产品创建 ADT 不感兴趣，不管它们对 Postgres 最终用户有多有用。

[![](img/586e2754806c760c0d7b208c45379bbf.png)](https://cdn.thenewstack.io/media/2019/06/493079ed-bruce-momjian.jpg)

如今，Postgres 的核心由 Bruce Momjian 等人维护。

数据库设计者似乎陷入了困境，至少在另一个用例出现之前是如此，它支持当时刚刚兴起但迅速发展的互联网，并为 Postgres 提供了丰富的用户基础。1996 年，Stonebraker 出售了他成立的公司 Illustra，将数据库系统商业化，并继续为其他用例创建其他数据库，如面向分析的[Vertica](https://www.vertica.com/)。

如今，Postgres 是目前第四大使用最广泛的数据库系统，[根据 DB-Engines 排名](https://db-engines.com/en/ranking)，仅领先于 NoSQL MongoDB。 [EnterpriseDB](https://www.enterprisedb.com/) ，为开源数据库提供商业支持(也是 Postgres Vision 的组织赞助商)，赞助了一个独立执行的基准测试来比较 Postgres 和 MongoDB，后者[刚刚增强了多事务处理能力](https://hackernoon.com/mongodb-transactions-5654cdb8fd24)。

尽管 MongoDB 的性能很快，但基准测试公司 [Ongres](https://www.ongres.com/es/) 发现 MongoDB 很难达到 Postgres 的事务性能。超过 16 个线程之后， [Postgres 完全将 MongoDB 甩在了身后](https://twitter.com/Joab_Jackson/status/1143940847748177920)。

“PostgreSQL 11 被发现在几乎每个基准测试中都比 MongoDB 4.0 快，”报告总结道。“吞吐量更高，从几十个百分点到一些基准的一个甚至两个数量级不等。根据基准测试，PostgreSQL 的延迟也较低。”

为 Postgres 提供多主机功能仍需努力，这将使其真正可跨多个服务器扩展。尽管如此，对于已经有 35 年历史的软件来说，它在今天的商业堆栈中的存在并不算太寒酸。

斯通布莱克说，好主意从来都不是来自“在山顶与自然交流”。它们来自与用户的交谈，许多用户。意外之喜总是有帮助的(反意外之喜总是有害的)，但这不是你能控制的。

最重要的是，Stonebraker 提醒我们，成功来自坚持，经历了不可避免的低谷和高潮。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>