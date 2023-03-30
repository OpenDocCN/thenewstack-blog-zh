# Docker 正在开发一种新的 PaaS

> 原文：<https://thenewstack.io/docker-is-driving-a-new-breed-of-paas/>

平台即服务技术已经存在多年了。第一个品种，像 Azure 和 Heroku，为用户提供服务。然后出现了 Cloud Foundry 和 OpenShift 等产品，旨在让用户运行自己的 PaaS——无论是在内部还是在他们选择的公共云中。

现在，第三波 PaaS 正在兴起。

这些努力，如[德伊斯](http://deis.io/ "Deis")、[弗林](https://flynn.io/ "Flynn")、鹤、[黎明](https://github.com/dawn/dawn "Dawn")和 Octohost，与第二代 PaaS 计划如 Cloud Foundry 和 Openshift 有一些相似之处——即它们是开源的，旨在让用户运行自己的 PaaS。

然而，较新的项目有一个共同点，这可能会让它们比更大的竞争对手更胜一筹:它们是围绕 Docker 从头开始构建的。

带上戴斯。为 Deis 提供支持的 OpDemand 公司的首席技术官加布里埃尔·蒙罗伊(Gabriel Monroy)说，它的开发者最初提供的服务很像 AWS 的 CloudFormation。“我们一遍又一遍地听到同样的话:‘我真正想要的是 Heroku，但我希望它在我自己的服务器或我自己的 EC2 实例上。’"

Deis 的创造者开始致力于回应这一需求。“一开始有很多杂乱的原型制作，”他说。“Docker 一问世，我们就想，‘现在有了一个让这成为可能的原始人’。”

这并不是说像 Deis 和 Flynn 这样的技术是围绕容器构建的。OpenShift 和 Cloud Foundry 都是。

## 国产的

但是许多这种新型的 PaaS 都是专门围绕 Docker 从头开始构建的。

一些较大的 PaaS 公司正试图利用码头工人的热情。例如，Red Hat 的 OpenShift 战略主管 Krishnan Subramanian 说，Red Hat 已经决定采用 Docker，而不是继续优化自己的容器技术。

Cloud Foundry 的立场有点模糊。它也采用了 Docker，但有些人对这种实现持批评态度，因为它使用了 Cloud Foundry 自己开发的容器 Warden 和 Docker 的一部分。不过，Cloud Foundry 有一些第三方 Docker 实现。Docker 最近[成为了 Cloud Foundry Foundation 的成员](http://blog.docker.com/2014/05/docker-joins-cloud-foundry-foundation/ "Docker")，所以未来可能会有更多的官方活动。

除了 Docker 之外，一些新技术的开发者表示，他们比一些更大的努力更加敏捷和灵活。“Cloud Foundry 是一项巨大的企业级行业工作，它带有 OpenStack 等类似规模和组织的项目的所有包袱。Flynn 的创始人之一 Jonathan Rudenberg 说:“生态系统中的主要影响者是行业巨头(大型企业公司)，他们主导着对话和功能集。

Monroy 说，因为 Flynn 或 Deis 的技术重量更轻，所以比 Cloud Foundry 或 OpenShift 等平台更容易定制。“虽然这些表面上是开源的，但将这种改变应用到你的环境中并不总是可行的，也不总是现实的，”他说。

Pivotal 的高级技术总监 Andrew Clay Shafer Sr .说，一些批评是正确的，但使用像 Cloud Foundry 这样更成熟的平台有很多优势。“Cloud Foundry 有一点笨拙和难以建立的名声。所以，如果你看看他们在弗林和戴斯身上做了什么，他们的设置重量更轻，”他说。

然而，他说，这种简单性对一些用户来说是有代价的。

> 如果您是一家要在具有不同业务部门和合规性要求的多租户环境中运行 10，000 个应用的企业，那么 Cloud Foundry 已经在那里了。另一种选择是和其他人一起从头开始构建。

不过，较新的 PaaS 技术似乎并没有追逐这类企业客户。

Monroy 说，Deis 的目标客户群是 A 轮融资后的初创公司，他们相信自己可以通过基础设施获得竞争优势，希望用更少的硬件做更多的事情，并希望能够快速扩展。

“当你让 Deis 与 Cloud Foundry 这样的公司竞争时，密度差异真的很惊人，”Monroy 说。他说，使用 Deis 通常比一些竞争对手的 PaaS 技术需要更少的服务器。

此外，较新的 PaaS 技术的开发者希望能够让用户真正大规模扩展。“这一代平台即服务注重规模。谷歌和脸书等巨头定期发表论文，分享他们如何运行世界上最大的面向网络的系统的细节。开源 PaaS 项目可以将这些技术和见解带给大众。例如，弗林开始实施谷歌最近一篇论文的部分内容。

虽然这听起来像是更大的项目，如 OpenShift 和 Cloud Foundry 在 Docker 上追赶，但事实是，大多数基于 Docker 的 PaaS 工作都处于非常早期的阶段。

例如，Deis 还没有正式发布稳定的版本。蒙罗伊说，它的用户是对早期软件有很高容忍度的公司。Flynn 目前只发布了一个预览版本。

此外，虽然 Docker 现在非常受欢迎，但不能保证它将是满足每个人需求的唯一容器。事实上，Flynn 最近开始支持更多的容器。“我们允许用户选择其他稳定的选项，”Rudenberg 说。

新的 PaaS 技术还处于开发的早期，每种技术的目标都是稍微不同的实现和用例。未来几个月，这个领域肯定会经历许多变化。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>