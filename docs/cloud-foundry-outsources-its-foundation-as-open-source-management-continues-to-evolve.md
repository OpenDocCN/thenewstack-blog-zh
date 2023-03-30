# 随着开源管理的不断发展，Cloud Foundry 将其基础外包出去

> 原文：<https://thenewstack.io/cloud-foundry-outsources-its-foundation-as-open-source-management-continues-to-evolve/>

平台即服务(PaaS)项目 [Cloud Foundry 宣布其基金会](https://www.cloudfoundry.org/foundation/)将作为 Linux 基金会合作项目进行管理，并将在“贡献治理”模式下运营。

该项目在二月份宣布了建立基金会的计划。该项目由 VMware 发展而来，VMware 将这部分业务分拆为 Pivotal。它很快获得了关注，并拥有超过 50 家公司，其中几家公司提供商业服务。

“把我们想象成 PaaS——基金会即服务——的 FaaS，”Linux 基金会的执行董事吉姆·泽姆林开玩笑说。“严肃的回答是，这是一场大赌注、大规模的合作。…它需要大量的基础设施来促进。它有数百万美元的投资；它有大约 600 万美元的年度运营预算，负责数百万美元的代码库。我认为它的代码价值数千万甚至数亿美元。PaaS 是一个数十亿美元的市场。

正如南希·戈林[几个月前为新堆栈](https://thenewstack.io/docker-is-driving-a-new-breed-of-paas/)所写的，PaaS 技术已经存在多年了。第一个品种，像 Azure 和 Heroku，为用户提供服务。然后出现了 Cloud Foundry 和 OpenShift 等产品，旨在让用户运行自己的 PaaS——无论是在内部还是在他们选择的公共云中。

最近几个月，Docker 已经成为一种新的 PaaS 的蜂巢，它使用容器技术来运行该技术。

根据 Gohring 的帖子， [Deis](http://deis.io/ "Deis") 、 [Flynn](https://flynn.io/ "Flynn") 、鹤、 [Dawn](https://github.com/dawn/dawn "Dawn") 和 Octohost 与 Cloud Foundry 和 OpenShift 等第二代 PaaS 计划有一些相似之处——也就是说，它们是开源的，旨在让用户运行自己的 PaaS。

但是这些运行在 Docker 上的服务不同于 Cloud Foundry 构建的 PaaS。在 Gohring 的帖子中，安德鲁·克莱·谢弗(Andrew Clay Shafer)说，它服务于将在具有不同业务部门和合规要求的多租户环境中运行数千个应用程序的企业。谢弗是 Pivotal 的高级技术专家之一。

Zemlin 说，像 Cloud Foundry 这样的开源 PaaS 需要一个严肃的基础设施，即持续集成测试-构建基础设施，一个管理知识产权的法律框架，一个管理代码来源的法律框架。

“它需要基础设施来促进开发人员协作、黑客马拉松、开发人员培训……对于这种规模和范围的开源项目来说，需要进行大量的协调活动——而 Linux 基金会恰好在这方面超级擅长，”他说，并补充说，除了自己的开源项目，Linux 基金会还管理着大约十几个与 Cloud Foundry 类似规模的其他项目。

这是一个热门领域，预计 2015 年将会更加火爆。研究公司 IDC 预测，到 2018 年，年增长率将达到 27%。在对 2015 年的预测中，它预见了竞争对手之间吸引开发者和软件即服务(SaaS)玩家的“死亡竞赛”。它还预计，供应商之间会出现“奇怪的伙伴”，联手扩大市场机会。

Cloud Foundry 社区贡献增长了 36 %,在过去一年中收到了超过 1，700 个拉取请求。

它被认为是 PaaS 的 OpenStack 等价物，观察人士认为使用 Linux 基金会不仅可以摆脱单一供应商的影响，还可以促进一些知名公司之间的合作。

此举与 Docker 形成对比，Docker 作为一家公司拥有这种流行的容器技术的商标。

该基金会的白金会员——EMC、HP、IBM、Intel、Pivotal、SAP 和 VMware——已承诺在三年内各向该项目捐赠 150 万美元。其他公司也承诺以较低的黄金和白银水平出资。

“对于堆栈的每一层，在软件定义的网络中，您拥有 OpenDaylight 对于网络功能虚拟化，……对于大数据，您有 Hadoop 泽姆林说:“在操作系统中，你有 Linux。“在每一层，你都有大型项目，这些项目本质上是在进行外部研发，因为软件太多，任何一家公司都无法自己编写。这项工作需要真正的基础设施来促进发展，这就是我们在这里所做的。…当竞争对手在一起工作时，他们并不总是相互信任，我们扮演着中立的角色。”

该基金会刚刚开始致力于其认证项目，旨在消除困扰 OpenStack 项目的不兼容性问题。

IBM 负责开放技术和云性能的副总裁安吉尔·路易斯·迪亚兹(Angel Luis Diaz)在《连线》上撰文，吹捧云铸造基金会的灵活性、多供应商支持以及在包容性和快速创新之间找到正确平衡的承诺。

RedMonk 的高级分析师 Donnie Berkholz 解释说:“为了获得其他供应商和用户的广泛支持，开源项目在一个中立的场所而不是在一家公司的控制下运行会有很大的帮助。“这给了社区信心，他们可以影响项目的方向。它还增加了项目继续存在的可能性，即使创作者改变了策略，被收购，或倒闭，”他说。

基金会还为新成员理解参与规则提供了一个有用的框架，这些规则通常是隐含的和没有记录的。Cloud Foundry Foundation 是其中的一个案例，它将作为一个交换中心，以确保代码库中不存在版权或专利侵权行为。

“我曾在两家开源基金会——Gentoo 和 X.Org——的董事会任职，我学到的最重要的事情是，运营自己的基金会会耗费大量时间和精力。伯克霍尔茨说:“他们将大部分工作外包给像 Linux 基金会这样的外部实体，这无疑是一个正确的举措，因为这使得云计算铸造社区能够专注于自己的目标。”

尽管如此，开放的 PaaS 市场仍然广阔，而且还没有完全定义。Docker 运动势头强劲，其提供的 PaaS 功能有能力为企业进行销售。但是在过去的几个月里，关于 Docker 开源社区的问题越来越多。Cloud Foundry 曾经由 VMware 控制。问题是:作为一个在开源框架中管理的项目，Docker 将如何发展？

Pivotal 是新堆栈的赞助商。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/ronkroetz/14637426929/in/photolist-jtMME6-ee3Hqp-gnnsg5-ayhNZh-ouUzkQ-avZUVo-oisD4P-8vKtZy-ebPGq5-5eM3NG-nLkPb8-7PFpXi-nJ9E9r-pbcV4N-7RSaV9-85y9Ue-c4tGyG-fPnoU4-ntR6WR-8mbfQh-arutEc-7vi2kA-ei1Yp7-pFmvE2-nYzkVh-ouEn95-9ezWKj-fDHoe8-9g9t2J-8ykKPg-8pmxGb-Lwh6x-5cJMaP-acVtWG-dLyhsy-f71KwG-8UJNRB-5UGohx-dWQJdE-Bn9Vf-qfV5X8-9gF7mf-cCHe5S-agauxq-7Cknth-pFq8n6-dJRd6v-amknhj-oV9yP1-auidbQ)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>