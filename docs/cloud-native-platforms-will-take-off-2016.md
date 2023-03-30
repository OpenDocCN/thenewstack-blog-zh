# 为什么云原生平台将在 2016 年起飞

> 原文：<https://thenewstack.io/cloud-native-platforms-will-take-off-2016/>

*This post was contributed by enterprise Platform-as-a-Service provider [Apprenda](https://apprenda.com/). The author, Chris Gaun, is writing from the perspective of a former cloud analyst and his views do not* *necessarily reflect that of Apprenda.*

[](http://www.apprenda.com/)

 [克里斯·高恩

克里斯·高恩是阿普瑞达公司的董事。他之前在 Gartner 担任分析师，负责公共 IaaS。在此之前，他是一名物理学家，从事量子化学的计算建模。他和他的狗熊猫住在布鲁克林。你可以在推特@Chris_Gaun 上关注他。](http://www.apprenda.com/) [](http://www.apprenda.com/)

两年前，我离开了 Gartner，加入了 Apprenda，这是一家我认为有潜力颠覆大型中间件、服务器操作系统和虚拟化市场的厂商，就像公共 IaaS 颠覆基础设施一样。回想起来，这是一个正确的决定。云平台市场反映了我在 IaaS 最初几年看到的关键势头，并将在 [Docker](http://www.docker.com/) 和容器编排工具的帮助(和接受)下遵循相同的轨迹。

众所周知，支持分布式云应用的平台在 2015 年大受欢迎。无论您如何称呼它们，云原生平台、企业平台即服务、私有平台即服务等。—过去几年，随着企业围绕 Docker、容器协调和新的整合途径实施战略，市场日趋成熟。

云平台本质上是下一代中间件，旨在提供在企业环境中实现分布式应用所需的所有功能。在容器和容器编排的基础上，云平台添加了日志记录、审计、安全性、策略、合规性、标准容器映像报告、入职、基于角色的访问、基础架构工具抽象以及全球 2000 强所需的其他功能。

至于增长，三家顶级企业级 PaaS 公司——Apprenda、 [Pivotal CF](http://pivotal.io/platform) 和[Red Hat open shift](https://www.openshift.com/)—都取得了令人瞩目的增长。2015 年，Apprenda 的员工人数增加了一倍，预订量增长了近 400%。Pivotal 表示，其 PaaS 产品的预订率为 1 亿美元。随着 v3 的发布，OpenShift [将其解决方案重新平台化为 Kubernetes 发行版。这对 Red Hat 来说是一个明智的举动，因为专门为该容器构建的 Docker 和编排工具，如 Kubernetes 和 Swarm，随着它们的成熟，将成为新的云原生应用程序组件(如物联网)的事实上的标准。](https://thenewstack.io/google-now-supports-red-hat-openshift/)

征求建议书(RFP)、试点以及积极关注云平台的组织数量呈指数级增长，这意味着 2016 年将是更大的增长年。在这一点上，没有市场战略的金融机构、大型制造商、政府、保险和医疗保健公司落后于形势。一些公司正在寻求构建新的下一代 Web 层、多租户 SaaS 或物联网组件，但他们看到的是中间件、操作系统的整合，以及用容器替换裸机的可能性，他们看到了潜在的节约。几乎所有这些客户都想要更多的工作流和基础设施抽象，以使开发人员更加敏捷。

以下是我对该行业现状的一些观察:

## **容器**

**进步:**2016 年，你不再需要解释容器级的应用隔离。《财富 500 强》中的大多数组织和大型政府现在对这项技术有了很高的理解。

**仍有欠缺:**最初对使用容器进行安全隔离仍有一些不信任。这种犹豫在公司钻研技术后不会持续很久，在接下来的几年里会很快消失。容器应该有助于行业减少对虚拟化的依赖，并有助于整合剩余的虚拟化。该技术还应该有助于整合服务器操作系统的数量，就像虚拟化对服务器所做的那样。因此，您几乎必须亲自指导人们进行整合计算和设置。无序扩张在我们的思维中根深蒂固，但它不应该如此。一些人利用了这种混乱。供应商对应用程序组件的每个实例的价格可能高得惊人，而客户还没有意识到他们被骗了，因为市场还很年轻。

## **公共平台即服务和企业平台即服务**

**进展:**很少有客户或认真购买企业级平台即服务的人不清楚这项技术与公共平台即服务之间的区别。有时，企业平台即服务被用作构建具有特定功能(如 SaaS 多租户)的应用的框架，而自助服务云方面是次要的。然而，大多数时候，大型企业组织建立云平台，以便开发人员获得由中央 IT 管理的类似 PaaS 的体验。(因此有了私有 PaaS 的绰号。)组织了解企业 PaaS 与公共 PaaS 的区别和使用案例。他们已经拥有基础架构，并将继续购买基础架构，无论是公共基础架构还是内部基础架构。在这些情况下，他们需要一个中间件层用于他们的分布式应用程序。公共 PaaS 主要与传统的托管服务竞争。

**仍有欠缺:**一些分析师、记者和专家对用例及竞争仍有误解。他们经常把自己过去关于私有和公共 IaaS 的知识错误地应用到平台上。当我听到“嗯，公共平台即服务的安全性提高了…”作为一个分析师，我想打自己的脸。他们采用了一些人用来反对 AWS、Azure 和谷歌计算引擎的 FUD 论点，并将其应用到一个从未做出过此类声明的市场。

## **分析师研究和权威人士**

进展:有一群出色的分析师在关注这个市场。[Gartner 的 Richard Watson](https://twitter.com/richwatson) 是最了解技术和用例的人之一。他的研究横跨 Docker、容器编排、微服务和云原生平台/私有 PaaS。更妙的是，当他不确定时，他会说出一句分析师很少会说的话——“我不知道。”新的堆栈(您现在正在阅读的！)提供了一些关于这个市场的最广泛的新闻和评论。相对较新的 Wikibon 分析师[Brian gracey](https://twitter.com/bgracely)写了一篇关于这个空间的很好的介绍作为他的第一批研究之一。其他在这里工作出色的分析师包括 451 Research 的 Donnie Berkholz、RedMonk 和 Gartner 的 Eric Knipp。当然，可能还有其他人正在进行我所不知道的杰出研究，而我无法跟踪他们所有人的事实也是爆炸性增长的另一个标志。(如果我忘记了你，请在 Twitter 上联系我。)

**仍有欠缺:**分析师有时会将快速应用开发工具与云平台混为一谈，尽管它们根本不存在竞争关系。我不确定为什么。有时他们会混淆云平台和公共平台即服务。同样，我也不确定为什么。也许是因为他们有时有相似的名字，或者供应商歪曲了他们的竞争对手？我真的不知道。

分析师通常是孤立的(我从自己的经历中知道这一点)，每个人都根据自己的覆盖范围提出建议。在实践中，这可能会导致最终用户认为实施云战略所需的解决方案和工具数量显著增加。我在 2015 年看到的一个 RFP 包括了如此多不同的工具，我只能猜测他们试图为分析师制作的字典中的每个术语获得一个工具，而不是评估他们自己的项目用例。

许多专家从虚拟机的角度分析容器。他们还不断提出持久存储是容器的一个缺点，尽管我所知道的我们市场上的每个云解决方案早就解决了这个需求。

## **运营的角色和开发者的角色**

**进展:**2015 年，所有企业级 PaaS 供应商一致认为，运营和开发人员在很大程度上需要不同的门户和独立的用户体验，以反映他们的工作职能。

**仍然缺乏:**与此同时，容器编排导致了关于运营和开发人员角色的分歧。我们仍然没有认识到 IT 世界不是二元的(双关语)，我们可能需要再次进行这样的对话。我们也会得出同样的结论。

## **最后的想法**

以上的文字并不是我对空间的全部思考。如果你曾经见过我，你知道我有很多(有时太多了！)好说。如果你在 [Twitter](https://twitter.com/Chris_Gaun) 或 [LinkedIn](https://www.linkedin.com/in/chrisgaun) 上给我打电话，我会很乐意和你见面，就这个话题详谈。但是，我的[TL；市场上的 dr](https://en.wikipedia.org/wiki/Wikipedia:Too_long;_didn%27t_read) 是云中间件市场看起来越来越像是公共 IaaS 空间的成功镜像。密切关注它。

*这篇名为《为什么云原生平台将在 2016 年腾飞》的帖子是由 Apprenda 发起的。*

Apprenda、Docker、Pivotal 和 Red Hat 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>