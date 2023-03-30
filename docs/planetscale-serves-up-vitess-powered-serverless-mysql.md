# PlanetScale 提供 vitesspowered 无服务器 MySQL

> 原文：<https://thenewstack.io/planetscale-serves-up-vitess-powered-serverless-mysql/>

Vitess 的起源故事广为人知:到 2010 年，YouTube 增长如此之快，其数据库已经跟不上了，因此该公司创建了 Vitess，这是一个用于 MySQL 横向扩展的数据库集群系统。现在，随着[加入](https://thenewstack.io/cncf-host-vitess/)和[从](https://thenewstack.io/from-borg-to-kubernetes-vitess-cloud-native-mysql-graduates-cncf/)[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)毕业，该项目的一些最初的创造者已经在开源项目的基础上创建了 [PlanetScale](https://planetscale.com/) ，该项目在今年早些时候推出测试版后，于本周发布了其企业平台。

PlanetScale 是一个无服务器的 MySQL 数据库，由 Vitess 提供支持，用户可以在几秒钟内启动一个数据库，该公司称之为“可伸缩性无限制”一年多前加入 PlanetScale 担任首席产品官的萨姆·兰伯特(Sam Lambert)现在担任 PlanetScale 首席执行官，他说正是这种能力和其他许多能力让他加入公司。

“我们已经建立了一个令人难以置信的开发者体验，”兰伯特说。“激励我并让我如此兴奋的不可思议的事情是，当我们为您提供数据库时，我们将这种开发人员体验与我们为您提供的支持 Slack、GitHub、Roblox 和 Square 等的堆栈相结合。这是前所未见的。第一天的最佳选择也是 IPO 的最佳选择。”

## **不同的因素**

虽然去年已经推出了其他几个无服务器数据库产品，从 [DataStax Astra](https://www.datastax.com/?utm_content=inline-mention) 到 [MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) 到 [CockroachDB](https://www.cockroachlabs.com/?utm_content=inline-mention) ，Lambert 解释说，PlanetScale 以 Vitess 为基础，它以一个独特的因素脱颖而出:它证明了大规模操作的能力。

“我们有一个非常有趣的问题，那就是，我们已经拥有了我们最大的客户，除非有人决定成为互联网上第二大网站，”兰伯特说。“所有其他数据库提供商都可能在本季度接受他们最大的客户，然后是下个季度，再下个季度，这是烧钱问题，烧钱错误，所有这些都是为了满足那个客户的需求。我们的情况正好相反。”

随着全面上市，PlanetScale 还推出了 Next.js 入门应用程序，可以轻松地将 PlanetScale 部署到 Netlify，类似于该公司已经推出的与 Vercel 的[集成，以及与](https://vercel.com/integrations/planetscale) [Prisma](https://www.prisma.io/) 、Node.js 和 JavaScript ORM 的集成。该公司还推出了外部数据库导入工具的测试版，该工具使用 Vitess 的 vReplication 功能从任何现有的 MySQL 数据库中导入数据。

## **徐达云**

除了其无服务器产品，PlanetScale 最近还推出了 PlanetScale 托管云，这使得有监管要求的组织能够在他们自己的云上使用 PlanetScale，而不是在 PlanetScale 的共享租赁模型上。兰伯特说，PlanetScale Managed Cloud 在推出时与亚马逊网络服务(AWS)合作，并希望很快加入谷歌云平台(GCP)，为用户提供了两个世界的最佳选择。

“传统上，这是一个非此即彼的选择:SaaS 或本地。我们实际上弥合了两者之间的差距，并说两者都是。其实都是。Lambert 说:[数据](https://thenewstack.io/category/data/)平面在您的环境中，您可以直接与它对话，它由我们来协调、管理和维护。

## 行星尺度的现在和未来

当我们一年多前最后一次与 PlanetScale 交谈时，他们讨论了他们为 Kubernetes 开发 PlanetScale 的计划，但 Lambert 说该公司现在已经采取了不同的方向，并从该计划中继续前进。由于 Vitess 最初是为 Kubernetes 的前身 Borg 建造的，Lambert 说他们开玩笑说它“在 Kubernetes 之前就为 Kubernetes 准备好了”现在，PlanetScale 完全在 Kubernetes 上运行，但该公司打算为其用户完全抽象出 Kubernetes 方面。

“本地数据库是我们想要留下的遗产。兰伯特说:“我们相信云的未来，我们甚至相信未来不会再有本地开发。“我们由 Kubernetes 提供动力，我们使用 Kubernetes。我们认为，我们应该利用 Kubernetes 的力量和 Vitess 的力量，以一种精致而简单的方式向客户提供这种服务，他们不知道，他们也不关心，我们只是把内部碎屑和其他任何东西留给其他任何想参与这一游戏的人。”

至于 PlanetScale 的下一步，Lambert 说人们只看到了 Vitess 能力的“大约 10%”，PlanetScale 计划揭示这些能力。

“我们只让你看了很小很小的一部分。我们的路线图就是要揭示这种力量，”兰伯特说。“我们明年路线图上的一些东西，从来没有被顶级超大规模公司以外的工程师掌握过。除非你在那里工作过，否则你从未见过或体验过这些技术，因此我们将这些技术带给那些将在创业第二天的人们。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>