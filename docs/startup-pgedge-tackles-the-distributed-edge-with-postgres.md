# 创业公司 pgEdge 用 Postgres 处理分布式边缘

> 原文：<https://thenewstack.io/startup-pgedge-tackles-the-distributed-edge-with-postgres/>

从 2005 年开始合作创建 [EnterpriseDB](https://www.enterprisedb.com/?utm_content=inline-mention) 的丹尼斯·卢西尔和[菲利普·梅里克](https://www.linkedin.com/in/phillipmerrick/)，正在推出一个名为 [pgEdge](https://www.pgedge.com/) 的新项目，以解决组织面临的一些最棘手的数据库挑战，如数据延迟、超高可用性和数据驻留限制。

通过他们称为 1 号门的 EnterpriseDB，他们试图在开源 PostgreSQL 之上添加一个 Oracle 兼容层。他们称他们最新的风险投资为 2 号门，将分布式 Postgres 数据库推向边缘。

## **什么是边缘？**

Cloudflare、Akamai 和 Fastly 等公司一直在处理更接近边缘的计算，但凿凿打击的创始人兼首席执行官 Glauber Costa 在一篇名为“[什么是边缘](https://thenewstack.io/what-the-heck-is-the-edge-and-why-should-you-care/)？”的帖子中指出，如果您要调用远处的中央数据库，将计算带到边缘只能解决一半的问题。

虽然边缘有许多方面，包括物联网设备、5G 和智能设备，但 CloudFlare Workers、Fastly、Netlify 或 Vercel 等边缘开发平台专注于通过将更多的应用程序组件放在更靠近边缘的位置来加快传统 web 应用程序和企业应用程序的速度。所以 pgEdge 也让数据库变得更近了。

Merrick 解释说:“对于试图将应用程序前端性能降低几毫秒的 web 应用程序开发人员来说，如果您有一个到数据库的往返行程，这可能是像 Amazon us-east-1 这样的地方，每次您需要访问数据库时都要花费 100 毫秒，那么无论您在前端做什么优化工作，都会被数据延迟问题淹没。”

蟑螂实验室高级软件工程师(也是 TNS 撰稿人)[保罗·斯坎伦](https://paulie.dev/)一直在跟踪数据在现实生活边缘场景中必须传输的[距离](https://thenewstack.io/the-distance-from-data-to-you-in-edge-computing/)。

pgEdge 的解决方案是通过分布式 Postgres 数据库缩短这一距离。

“您不会在网络上放置 400 个 Postgres 数据库节点。这有点过分，也没有必要。因此，您需要在网络中战略性地放置一些 pgEdge 节点，每个节点都可以处理读取或写入流量。如果你将它们与边缘平台结合使用，比如 Cloudflare Workers 或 Fastly，这就是我们设计它的目的，你将能够从数据库层获得非常好的响应时间，”Merrick 说。

## **纯 Postgres 及其标准扩展**

从使用 EnterpriseDB 的经验中，他们希望从一个强大的基础层开始。超过 35 岁的波斯特格里斯最近在[经历了一次复兴](https://thenewstack.io/from-a-fan-on-the-ascendance-of-postgresql/)。

“我们没有重写底层的数据库引擎。这是波斯特格里斯。和 Postgres 不兼容。梅里克说:“T4 是研究生入学考试，这是一个重要的区别。”。

它还使用 Postgres 标准扩展机制。它的延伸部分被称为斯波克，是对《星际迷航》中逻辑人物的引用。它是 [pgLogical](https://github.com/2ndQuadrant/pglogical) 的衍生产品，提供双向多活动(也称为多主)逻辑复制。

pgEdge 集群中的节点可以跨越多个云区域和数据中心，以实现高级别的弹性、可用性和性能。

根据 Merrick 的说法，这对开发人员，尤其是那些使用 JAMStack 架构的开发人员意味着什么:

“是的，您可以测量页面加载时间，但这也是获得高度可用的数据库应用程序的一种成本更低、更简单的方法。因为如果你在网络上有多个读/写节点，你可能会丢失一些，这取决于你有多少个，一切都会保持独立。流量可以故障转移到幸存的节点。因此，这是一个低延迟、超高可用性的分布式数据库。”

你可以在这里看到一个[演示](https://www.pgedge.com/demo-video)。

每个节点运行标准 PostgreSQL (v15 ),并通过异步逻辑复制保持更新，具有可配置的冲突解决和避免。它提供了增量冲突避免，以保持数据字段的一致性，如财务余额或库存计数。

它还提供地理分片，以帮助用户遵守 GDPR 等法规，这些法规要求某些数据保持在特定的地理边界内。它在位置字段上分解表格，因此一些数据可以保存在本地，而其余的数据则在全球范围内共享。

## **现有 Postgres 申请，即使有变化也很少**

该公司于本月早些时候悄然出现，并宣布了一轮 900 万美元的种子资金。这项技术仍处于测试阶段，只有少数客户接近生产。该公司希望在第三季度全面上市。

“对于像我们这样的领先电子商务公司来说，pgEdge 是一个游戏规则的改变者，无论我们的客户在哪里，它都将为我们提供快速的页面加载和流畅的客户体验，”Zenni Optical 的首席技术官 [David Ting](https://www.linkedin.com/in/dting/) 说，并补充说，pgEdge 还可以“通过允许开发人员在本地 Postgres 上开发，同时拥有现代分布式数据存储的优势，为我们的工程师构建新一代电子商务应用程序奠定坚实的基础。”

Merrick 说，Postgres 用户应该能够使用他们现有的 Postgres 应用程序，只需很少或不需要修改。

“…您可以使用所有与 Postgres 一起工作的工具，以及许多与 Postgres 一起工作的扩展。因此，[开发人员]可以完全按照他们今天使用 Postgres 的方式来使用它，无论他们的应用程序以什么方式访问它，无论他们喜欢使用什么工具来管理模式等等。这很管用，因为这是标准的 Postgres。”

[SaaS 媒体分析公司 PublicRelay 的首席技术官 Bill Mitchell](https://www.linkedin.com/in/bmitchel/) 表示，*我们已经使用 pgEdge 几个月了，它的性能和稳定性给我留下了深刻的印象。他们的多主机复制功能让我能够轻松管理和扩展我的 PostgreSQL 数据库，没有任何问题。该产品易于管理，为我节省了大量时间和精力。”*

 *## **全部开源**

其他人也试图将数据库移近边缘。例如，Costa 的公司 ChiselStrike 正在用兼容 SQLite 的嵌入式数据库 Turso 解决延迟问题。EnterpriseDB 也有类似 pgEdge 的产品叫做[EDB Postgres Distributed(PGD)](https://www.enterprisedb.com/docs/pgd/latest/overview/)。

据梅里克说，竞争对手如蟑螂、Yugabyte 和其他公司，在处理分布式边缘问题时，作出了使用不同数据库的设计决定，然后在其上放置一个兼容层。

“我们从与 Oracle 兼容性的工作中了解到，这只能让您实现 90%的目标，而最后的 10%有点致命，”他说。

第二个不同点是 pgEdge 的源代码都是开源的，可以在 GitHub 上获得。

该公司已经发布了其整个 PostgreSQL 发行版，这是一个名为 pgEdgePlatform 的自托管和自管理版本，它是免费的，可以下载。它还在 AWS 和 Azure 上提供了一个名为 pgEdge Cloud 的托管数据库服务。你可以在这里加入[私人测试版](https://www.pgedge.com/#cloud-beta)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*