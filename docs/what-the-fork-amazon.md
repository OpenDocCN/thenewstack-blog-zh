# 什么叉子，亚马逊？

> 原文：<https://thenewstack.io/what-the-fork-amazon/>

[](https://twitter.com/shar1z)

[Sharone Revah Zitzman](https://twitter.com/shar1z)

[Sharone Zitzman 是一名营销技术专家和开源社区构建者，他喜欢与团队一起开发开发人员喜欢的产品。她已经从头开始建立了 DevOps Israel 和 Cloud Native & OSS Israel 社区，她花时间寻找技术和人员的交汇点，并以专注于工程卓越和质量的文化为后盾，确保出色的开发人员体验。你可以在 Twitter 或者 Github 上找到她的@shar1z。](https://twitter.com/shar1z)

[](https://twitter.com/shar1z)[](https://twitter.com/shar1z)

自从本周[AWS elastic search](https://aws.amazon.com/blogs/opensource/keeping-open-source-open-open-distro-for-elasticsearch/)开放发行版宣布以来，我一直试图收集我的想法，并解释为什么我认为这对整个开源世界来说是一个毁灭性的举动。

我想借此机会概述一些经常被误解的开源世界的细微差别——并为我们如何继续支持和维持开源提供一些思考的食粮，开源运动在很大程度上使世界变得更好。

因此，我将简要地谈一谈在这整个惨败过程中出现的一些评论，并提供我的观点，我认为我们可以做得更好。

在一篇出色的文章"[公司价值创造和获取基础](https://medium.com/open-consensus/9-coss-company-value-creation-and-capture-fundamentals-9f0689c32ab0)"中， [Joseph Jacks](https://twitter.com/asynchio) 讨论了商业开源(COSS)公司和专有软件公司之间的根本区别。我还认为在这个复杂的行业中需要定义或更好地理解的是 COSS 公司和自由开源(FOSS)之间的细微差别。我认为这是开源行业经常被误解的细微差别，需要重新思考，以确保优秀开源技术的可持续和可行的生态系统向前发展。

## 开源软件基础

最近，开源倡议发布了一个帖子来重申开源的定义，过去的一年对于开源社区来说是特别痛苦的一年，继 [Redis](https://www.zdnet.com/article/redis-labs-and-common-clause-attacked-where-it-hurts-with-open-source-code/) 和 [MongoDB](https://www.mongodb.com/press/mongodb-issues-new-server-side-public-license-for-mongodb-community-server) 改变许可之后，再次提出了什么是开源的基本问题。

另一方面，微软、VMware、F5 和谷歌等公司巨头在今年迄今为止的一年中加倍投资开源软件，这让人怀疑你是否能“为自己购买”一个社区。Cloudify 创始人 [Nati Shalom](https://www.linkedin.com/in/natishalom) 在优秀的“[亚马逊对开源的影响](https://thenewstack.io/the-amazon-effect-on-open-source/)”(写于收购 Heptio 和 Nginx 之前)中讨论了这一趋势。我在波士顿 OpenStack 上主持了一个关于这个主题的小组讨论，也在特拉维夫 DevOpsDays 上做了一个关于开源挑战的演讲。

我相信自由开源软件的原则是非常清楚和无可争议的，在 OSI 的帖子中得到重申，在 Chef [的前首席技术官 Adam Jacob 的帖子](https://link.medium.com/xSfF4lvn3U)中也得到了重申，我很大程度上不同意这一点，我将概述为什么。

自由软件的核心价值体现在四大自由中:

*   为了任何目的，按照你的意愿运行程序的自由。
*   自由 1:研究程序如何工作的自由，改变它，让它如你所愿地做你的计算。
*   自由 2 :重新分发拷贝的自由，这样你就可以帮助他人。
*   自由 3:将你修改过的版本分发给其他人的自由。

我认为以这种形式提供的技术为欠发达的社区、国家和人民实现了技术进步，这种代码正在为世界上一些最重要的基础设施提供动力。在一篇名为“[道路和桥梁:我们的数字基础设施背后看不见的劳动力](https://www.fordfoundation.org/library/reports-and-studies/roads-and-bridges-the-unseen-labor-behind-our-digital-infrastructure/)”的论文中可以找到关于这个主题的很好的阅读材料。

## 开源和货币化

一个非常有利可图的模式是发布模式，它使得这种形式的开源能够持续下去。这实际上指的是由一个著名的开源基金会托管的开源项目—仅举几个例子，Apache Software、OpenStack、Linux Foundation、Eclipse —商业公司围绕这些项目建立，以提供附加的功能集、产品级支持，并长期维护项目。Kafka、Spark、Hadoop、Git、Linux 发行版等项目都是以这种方式持续和维护的。

对于许多公司来说，这是一种非常有利可图的模式，并且在很大程度上是一种双赢的开源格式，使那些想要采用普通版本并自己完成的公司，以及那些喜欢更稳定和受支持版本的公司，能够拥有一个能够支持其开源发行版的供应商市场。此类开源公司包括盈利性开源红帽的典型代表，以及 Canonical/Suse、Github、Hortonworks(以及以前的 Cloudera)、Databricks、Confluent、Heptio 和许多其他公司。(亚马逊开放发行版不属于这一类，稍后我会详细解释原因)。

开源还有另一种变化，我们需要开始承认，而不是把所有开源都归为一类——这同样有益和可行，但出于某种原因受到了攻击和审查，需要认真反思。

这就是属于 ***商业开源*** 技术的范畴。这些技术建立在开源原则的基础上，寻求利用开放技术的价值，同时得到商业实体的支持，以使技术能够长期可持续发展。我能想到的一个以这种方式提供急需创新的类似类比是社会企业家精神——商业医疗或环境创新没有受到同样程度的反感。

概念和价值是明确的，提供这些技术或大规模创新的能力要求这些公司盈利或有资金支持。这种技术的例子包括:Elastic、Redis Labs、InfluxData、Jenkins、MongoDB、Chef、Mesosphere、ScyllaDB、Cloudify 和许多其他技术。

我想更深入地了解这些技术。虽然自由/开源软件技术和商业发行版公司一样，也是依靠许多无私的维护者的血汗和泪水来维护的，但商业开源公司常常是由一个有着优秀想法的创始人发起的，他们希望为其所有的价值和利益提供开源，但缺点是必须不断地抵御滥用者。我想 Elastic 的首席执行官和创始人 Shay Banon 在他上一篇关于“开放”发行版、开源和建立公司的博客文章的前几行总结了建立这样一个项目和公司的一些内容:

*2009 年，我坐下来写了 Elasticsearch 的前几行，并将其开源。我辞掉了工作，花了两年时间投资开发这个产品，并围绕它建立了一个令人惊叹的社区。2012 年，我们围绕它成立了一家名为 Elastic 的公司。*

为了理解围绕开源的一些政治问题，我将简要地谈一下什么被归类为分叉。2010 年，当甲骨文收购 Sun 时，他们一起购买了当时流行的 CI 工具，由 Kohsuke Kawaguchi 编写，名为 Hudson。由于在如何维护 Hudson 社区的问题上产生了分歧，Kohsuke 将 Hudson 社区分成了两部分，并创建了一个名为 Jenkins 的新 CI 工具。在 Hudson 社区备受推崇——他基本上成功地团结了整个社区，Jenkins 基本上是当今最受欢迎的开源 CI 工具。川口现在受雇于支持詹金斯的商业公司是 CloudBees。

另一个例子是 MySQL 社区的 MariaDB fork，它也是在 Oracle 收购 MySQL 引起关注后出现的。这只是几个流行的例子，还有很多。

## 为什么亚马逊开放发行版是一个分支——这是不对的

亚马逊声称对围绕 Elastic 开源承诺的担忧是边缘攻击性的。作为一家因对开源贡献甚少而遭到强烈反对的公司，他们多次利用市场优势推出开源技术的托管服务，如 PostgreSQL、Redis 和 MongoDB 等流行数据库，甚至是他们之前尝试的弹性搜索托管服务。这最终促使一些最受欢迎的 COSS 公司改变了许可方式。

凭借 AWS 拥有的市场份额和忠实的受众，不费吹灰之力就能赢得来之不易的社区和客户。这显然是对信任的滥用。这些 COSS 公司以开源和免费的方式提供他们的代码，以建立一个强大的社区，由在产品方面具有深厚专业知识的聪明人组成，使那些没有资源购买高级功能的人能够免费使用产品的核心功能，并使代码具有灵活性、可定制性和开放性。许多公司，甚至是那些有钱的公司，经常选择 DIY 的方法，而不用支付 COSS 公司一分钱——这仍然被认为是合理使用。

对我来说，什么被认为是不公平使用，这就是我反对在这种情况下自由/开源软件的干巴巴的定义的地方，是当一个更大、更赚钱的公司为了他们自己的利益滥用这种开放性，并且没有对整个社区作出任何贡献。这是 AWS 长期以来的工作方式。

> 我想，免费提供别人的技术真的很容易。

虽然微软和谷歌在内部开源提交者和维护者的数量上一直在竞争，但 AWS 的倾向要小得多。即使他们雇佣了大量的内部开源开发者，推出了大量的技术，这些公司对开源的承诺还是有很多疑问的(微软，比谷歌更有疑问——但是这种观点一直在改变)。

如果亚马逊真的对真正改变他们的方式感兴趣，就像微软一次又一次证明的那样，并交付一个真正有价值且急需的开源社区——他们本可以像微软和谷歌一样，通过开源**自己的**专利技术开始。天知道开源云经历了多少困难，从 Solaris 到 CloudStack，甚至 OpenStack。为什么不开源你核心业务的一部分呢？让我怀疑你的“开放发行版”背后的真正动机我想，免费提供别人的技术真的很容易。

这就是为什么我理解 Redis、MongoDB 和其他公司，如 InfluxData，他们发现自己不得不改变许可证或关闭一些高级功能的源代码，以便能够建立一个可持续的业务，并保护自己免受这种愤世嫉俗和敌对的公司行为的影响。

向一个充满活力、深深植根于 OSS 价值观的开源公司鼓吹开源——这个公司已经完全公开了他们对赚钱和维护一个明星产品的需求，并对其真实性做出可疑的声明，这完全是不诚实的。这是亚马逊看到某人闪闪发光的玩具，就想把它据为己有。我的我的我的。这叫叉子。

这就是开源的黑暗面。这是我们希望开源世界没有的负面影响，因为它将对一切已经建立起来的东西产生破坏性影响，并可能在开源的支持下被概念化和创新。

自从 2017 年在[开源峰会北美](https://www.youtube.com/watch?v=zd9FnRjR9Xk)上听了[约瑟夫·高登·莱维特](https://twitter.com/hitRECordJoe)的精彩演讲，我就不停地思考我们可以尝试让开源更可持续的方法——无论是通过向原创作者和维护者支付版税，还是某种奖励制度，这将防止这个世界被滥用，吃力不讨好，毫无价值。

这是 AWS 正在带领我们走下去的道路，如果世界将锁定其所有的开放创新，这将使我们倒退数光年。我们的工作是防止这种情况发生，并找到一个公平的系统来实现开源技术带来的创新，亚当·雅各布[对此](https://medium.com/sustainable-free-and-open-source-communities/we-need-sustainable-free-and-open-source-communities-edf92723d619)直言不讳，纳蒂·沙洛姆、盖伊·柯兰德和许多其他开源技术领导者也是如此，我非常同意。

如果我们想长期支持开源，我们需要将这种讨论推到最前沿。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>