# Kubernetes 整合对云原生的未来意味着什么

> 原文：<https://thenewstack.io/what-the-kubernetes-consolidations-mean-for-the-future-of-cloud-native/>

[云代工厂](https://www.cloudfoundry.org/)赞助本帖。

就像电视节目的舞台一样，云计算产业也在不断地重新配置自己以适应当天的版面。在剥落的体育馆上涂上一层油漆，它就变成了州长官邸；拔掉废弃宅地前院齐腰高的杂草，它就变成了一个迷人的小屋。

同样，软件和服务提供商也必须不断改造自己，以应对市场变化，保持与故事的相关性——这可能需要比增加栅栏更微妙的东西。云空间的改造需要来自用户和行业领导者的持续反馈，并可能需要在大变革的浪潮中进行大规模的变革。有时，这些变化表现为重大的整合。

### 过去的整合预示着未来的整合

 [Chip Childers

Chip 在大规模计算和开源软件方面已经花了超过 18 年的时间。2015 年，他成为云铸造基金会的联合创始人，担任技术参谋长。他是 Apache CloudStack 的第一任副总裁，在 SunGard 领导企业云服务时，他帮助推动了该平台的发展，后来又在 Cumulogic 担任产品战略副总裁。在 SunGard 之前，他领导了包括 IRS.gov、USMint.gov、美林和 SEI Investments 在内的组织的任务关键型应用程序的重建工作。](https://www.cloudfoundry.org/) 

从 2013 年到 2015 年，我们看到了一波巨大的云整合浪潮，从 IBM 收购 [SoftLayer](https://www-03.ibm.com/press/us/en/pressrelease/41191.wss) 和 OpenStack 提供商 [Blue Box](https://www-03.ibm.com/press/us/en/pressrelease/47556.wss) 到思科收购 [Piston Cloud](https://www.cisco.com/c/en/us/about/corporate-strategy-office/acquisitions/piston.html) 和 [Metacloud](https://www.cisco.com/c/en/us/about/corporate-strategy-office/acquisitions/metacloud.html) 到 EMC 投资 Cloudscaling 和 Virtustream 。科技巨头对云公司的这些收购展示了这些传统品牌对市场的精明理解，因为他们看到了拐点，并抓住机会成为变革者。

技术发展很快。现在是 2018 年，我们看到又一波整合即将到来。紧随微软 [之后，IBM](https://news.microsoft.com/2018/06/04/microsoft-to-acquire-github-for-7-5-billion/)[收购红帽](https://www.redhat.com/en/about/press-releases/ibm-acquire-red-hat-completely-changing-cloud-landscape-and-becoming-worlds-1-hybrid-cloud-provider) 收购 GitHub 的 [e，这是变革即将到来——而且来得很快——的先兆。最近，VMware](https://news.microsoft.com/2018/06/04/microsoft-to-acquire-github-for-7-5-billion/) [宣布](https://www.vmware.com/company/news/releases/vmw-newsfeed.VMware-to-Acquire-Heptio-to-Accelerate-Enterprise-Adoption-of-Kubernetes-On-Premises-and-across-Multi-Cloud-Environments.1645750.html) 将收购 Heptio，该公司为评估或使用 Kubernetes 的企业提供专业服务。

这不仅意味着云整合，还意味着开源整合——不仅仅是开源整合，而是 Kubernetes 整合。

### 为什么这预示着 Kubernetes 的合并浪潮

 [艾比·科恩斯

艾比·卡恩斯是云铸造基金会的执行董事。她是一位真正的技术老手，在财富 500 强和初创公司的产品营销、管理和咨询领域拥有 18 年的职业生涯。在 Cloud Foundry Foundation，Abby 负责构建和执行运营和战略计划，并领导用户咨询委员会和行业特殊兴趣小组。在加入基金会之前，她是 Pivotal 产品管理团队的一员，主要负责 Pivotal Cloud Foundry。](https://www.cloudfoundry.org/) 

正如大多数人所知，Kubernetes 是一个开源容器编排系统，最初由 Google 开发，现在作为一个开放社区在 Linux 基金会下运行。正如我们在今年 1 月预测的那样， [Kubernetes 已经成为消费基础设施的下一代方法](https://thenewstack.io/2018-year-kubernetes-interoperability/) 。这样一来，它几乎被云提供商和企业技术公司普遍采用，因为他们致力于简化容器在企业中的采用。

Kubernetes 的技术成熟很快，公共云提供商和大型企业技术公司都将积极寻求任何机会来扩大各自的份额。因此，这标志着 Kubernetes 的市场采用阶段，在这一阶段，整合将认真发生。

从纯技术的角度来看，Cloud Foundry 和 OpenShift 在 IBM 的云产品中的结合事实上可能是一个有趣的组合。IBM 在 Cloud Foundry 技术社区中扮演了领导角色，推动与 Kubernetes 的架构融合。在 Kubernetes(很可能是 OpenShift 版本)的基础上构建 Cloud Foundry 的开发人员体验，IBM Cloud 用户将同时拥有容器和以应用程序为中心的开发人员体验。

最近，IBM 的 Cloud Foundry 开发团队率先创建了 [项目 Eirini](https://www.cloudfoundry.org/project-eirini/) ，这是一个开源项目，使运营商和产品供应商能够使用 Kubernetes 作为 [Cloud Foundry 应用运行时(CFAR)](https://www.cloudfoundry.org/application-runtime/) 的底层容器调度程序。上个月，IBM 在 Cloud Foundry Summit 上发布了 IBM Cloud Foundry Enterprise Environment，它允许用户创建和管理隔离的 Cloud Foundry 环境，用于托管专门为其组织提供的应用程序。

我们已经看到 Pivotal、SAP 和 SUSE 在将 Kubernetes 与云铸造项目结合起来时进行了类似水平的投资。很明显，客户和用户越来越多地使用以开发者为中心的 PaaS 和以基础设施为中心的容器即服务(CaaS)。这些平台的架构融合展现了统一操作和开发体验的潜力。

除了 IBM 和 Red Hat 的合作之外，VMware 还宣布收购 Heptio，以增强其 Kubernetes 的专业知识。这将是 VMware 产品组合的强大补充，此次收购表明 VMware 致力于通过 PKS 将 Kubernetes 引入企业，这是一个与 Pivotal 联合开发的 Kubernetes 发行版，基于上游云铸造项目 CFAR。

### 这一切的根源是:对多云战略的渴望

**组织希望能够自由部署到多个云环境中，并使用私有云和公共云以及内部云的组合。Cloud Foundry 和 OpenShift 等技术已经提供了多年的多云解决方案。事实上，许多公司同时使用 Cloud Foundry 和 OpenShift 来解决他们的特定需求。我们称之为多平台现实。**

主要的云提供商已经注意到企业间的这种增长战略，即使用来自整个市场的各种平台和功能，现在他们正在采取行动。IBM 和 VMware 对 Red Hat 和 Heptio 的收购表明，这些公司从根本上理解多云是他们的客户已经生活的世界。他们也获得了将这种类型的开源领导加入到他们自己的 OSS 投资组合中的价值。

IBM 和 VMware 是 Cloud Foundry 生态系统中的关键角色，从一开始就参与了项目的方向。因此，毫不奇怪，他们看到了我们看到的同样的多云未来；这是我们一直在讨论的事情。VMware 开发人员创建了 Cloud Foundry，然后将其作为 Pivotal 创建的一部分剥离出来，几年前它还没有开源。IBM 也是 Cloud Foundry 的长期贡献者——无论是以平台承诺的形式，还是作为开源方面的业务和营销合作伙伴。

我们认为，IBM 对 Red Hat 的兴趣和 VMware 对 Heptio 的投资等同于他们对 Cloud Foundry 项目家族的承诺，因为我们正在共同走向两个独特且互补的行业标准开源项目的统一。虽然 2018 年肯定有它的时刻，但 2019 年确实将是非常令人兴奋的一年。

Linux 基金会、Red Hat、Pivotal 和 VMware 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>