# Redis 着眼于缓存之外的一切数据

> 原文：<https://thenewstack.io/redis-looks-beyond-cache-toward-everything-data/>

Redis ，最著名的是数据缓存或实时数据平台，正在[演变成更多的](https://thenewstack.io/redis-is-not-just-a-cache/)， [Tim Hall](https://www.linkedin.com/in/timehall) ，该公司的产品主管在最近的 TNS Makers 播客中告诉新堆栈。

[Redis 将目光投向缓存之外的一切数据](https://thenewstack.simplecast.com/episodes/redis-looks-beyond-cache-toward-everything-data)

Redis 是内存数据库或内存优先数据库，这意味着数据存放在那里，人们使用我们进行缓存和持久化。然而，如今，该公司有许多灵活的数据模型，但 Redis 的品牌承诺之一是开发人员可以在使用数据时存储数据。因此，与 SQL 数据库相反，在 SQL 数据库中，你可能必须将数据结构转换成列和表，你实际上可以将你正在处理的数据结构直接存储到 Redis 中，Hall 说。

[https://www.youtube.com/embed/L5xhzIXIwYg](https://www.youtube.com/embed/L5xhzIXIwYg)

视频

## 主数据库？

“今天，我们大约 40%的客户将我们作为主要的数据库技术，”他说。“这可能会让一些人感到惊讶，如果你是一个典型的 Redis 用户，你从内存缓存中知道我们，你可能没有意识到我们多年来添加了各种持久化机制。”

同时，为了存储数据，Redis 确实将数据存储在磁盘上，有点像是在后台，同时在内存中保留一份副本。因此，如果出现任何类型的故障，Redis 可以从磁盘上恢复数据，并将其重放到内存中，让您恢复正常运行。这是一种已经存在了大约五年的机制。

然而，Redis 正在玩霍尔所说的“长期游戏”，特别是在继续接触开发者并向他们展示最新功能方面。

“如果你看看这个星球上的前 10 个数据库，它们都进入了多模态类别。从这个角度来看，Redis 也没有什么不同。“因此，如果你看看 Oracle，它传统上是一个关系数据库， [Mongo](https://thenewstack.io/mongodb-6-0-brings-encrypted-queries-time-series-data-collection/) 传统上只是 JSON 文档存储，而 Redis 显然是一个键值存储。我们现在都去球场了。我们为什么要这么做？我们都在寻求简化开发人员的世界，对吗？”

然而，每个供应商都在努力利用他们的核心优势，并以此为基础进行扩张。对 Redis 来说，好消息是速度是它的核心优势。

“您为什么想要一个缓慢的数据平台？你没有，霍尔说。因此，我们越是能够提供这些扩展功能来处理 JSON 之类的东西，或者我们刚刚推出了一个名为 [t-digest](https://github.com/usmanm/redis-tdigest) 的数据结构，人们可以一起使用，我们已经支持[布鲁姆过滤器](https://redis.com/blog/bloom-filter/)，这是一个像所有这些东西一样的概率数据结构，我们有点扩大我们的足迹，我们说如果你需要速度，减少延迟，并且拥有高交互性是你的目标，Redis 应该是你的起点。如果您想要一些深奥的 edge case 功能，需要以非常奇怪的方式操作 JSON，那么您可能应该使用 Mongo。我可能很长一段时间都不会支持那个。但是如果你只是处理基本的数据结构，你需要能够查询，你需要能够更新你的 JSON 文档。我们非常非常好地支持那些简单的用例，并且我们以一定的速度和规模支持它们。"

## 客户视图

作为 Redis 的客户， [Alain Russell](https://www.linkedin.com/in/alainrussell/?originalSubdomain=nz) ，新西兰奥克兰数字电子商务机构 [Blackpepper](https://www.blackpepper.co.nz/) 的首席执行官，说他的公司也经历了同样的转变。

“我们一开始把 Redis 作为一个缓存，这帮助我们加快了比我们想要的慢的传统数据的速度，”他说。“几年前，我们走上了云之路。迁移的一部分包括我们成为所谓的“原生云”我们开始使用所有这些不同的数据存储和数据结构，处理它们实际上很复杂。你知道，从开发人员的角度来看，这可能有点痛苦。"

因此，Blackpepper 开始寻找如何使事情变得更简单，同时保持他们的平台非常快，他们查看了 Redis 堆栈。“老实说，它在一个平台上满足了我们的所有需求。我们现在正处在这条路上，我们正在使用它的基础。我们的旅程才刚刚开始，对吧？我们仍在学习事物如何运作以及如何正确使用它。但我们也有一个很大的列表，我们正在使用其他数据存储来存储传统数据，并且正在努力，好吧，这将是我们将迁移到的东西，你知道，因为我们现在在 Redis 中大量使用持久性。”

20 岁的 Blackpepper 与主要的传统零售商合作，并帮助他们实现全渠道之旅。

## 商业与开源

Hall 表示，有三种方式可以访问 Redis 技术:Redis 开源项目、Redis 堆栈(该公司建议开发人员从今天开始使用),然后是 Redis 企业版，它可以作为软件或在云中使用。

“这是连续六年来全球最受欢迎的 NoSQL 数据库，”霍尔说。“人们喜欢它是因为它的简单。”

同时，维护商业产品和开放源码都需要付出努力。曾在 Hortonworks，InfluxData 工作过的 Allen 说:“在你如何决定你的商业产品中有哪些内容是开源的，贡献来自哪里以及谁参与其中方面，不是每个开源公司都是一样的。”

例如，“如果有人想要贡献的东西会违背我们的商业利益，我们可能不会合并它，”霍尔说。

Redis 由项目创始人 Salvatore Sanfilippo 经营了很多很多年，他是 Redis 本身的唯一仲裁者。然后，在过去几年中，Redis 创建了一个核心指导委员会。它由来自 AWS 的一名个人、来自阿里巴巴的一名个人和三名 Redis 员工组成，他们负责管理来自 Redis 开源社区成员的贡献，这些成员希望贡献这些东西。

“然后，我们从商业利益的角度来协调我们想要的东西，或者是上游的，或者坦率地说，可能已经商品化的东西，我们希望将下游推向开源产品，”霍尔说所以你问的问题是我一直面临的核心生存挑战，那就是从商业角度弄清楚我们要去哪里。我们想先在那里降落什么？我们如何才能创造一个商业机会的传送带，让我们作为一个软件公司保持业务，创造与潜在竞争对手的差异？然后，随着时间的推移，确保这些东西变得商品化，或者不再与众不同，我想把它们发布到开源社区。但是这种上游/下游的挑战是我们一直在努力解决的。"

Blackpepper 最初是 Redis 的开源用户，但他们开始了一段旅程，使用 [Memcached](https://thenewstack.io/how-pinterest-tuned-memcached-for-big-performance-gains/) 来加速数据。Russell 说，当他们迁移到 AWS 云时，他们迁移到 Redis。

## 听播客

Redis TNS Makers 播客继续关注 AI/ML 在平台中的使用，RESP.app 的收购， [JSON](https://thenewstack.io/building-large-scale-real-time-json-applications/) 和 RediSearch 的重要性，以及 Redis 未来的发展方向。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>