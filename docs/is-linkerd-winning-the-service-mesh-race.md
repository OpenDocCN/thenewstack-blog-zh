# Linkerd 赢得了服务网格竞赛吗？

> 原文：<https://thenewstack.io/is-linkerd-winning-the-service-mesh-race/>

Linkerd 在[服务网格竞赛中的市场份额似乎处于领先地位，因为组织增加了对 Kubernetes](https://thenewstack.io/why-do-you-need-istio-when-you-already-have-kubernetes/) 的采用，并意识到没有适当的控制平面网格他们无法做到这一点。例如，根据最近 [CNCF 的一项调查](https://www.cncf.io/wp-content/uploads/2022/02/CNCF-Annual-Survey-2021.pdf)，Linkerd 在北美、欧洲和亚洲三大地理区域的采用率已经超过了 Istio。

独立于 [CNCF](https://cncf.io/?utm_content=inline-mention) 的调查，分析公司[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 注意到“Linkerd 平台的强劲势头”，EMA 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk/) 说。“其不断增长的用户群对其简单性和更多企业级功能的针对性添加赞不绝口。”

## 简单是关键

Linkerd 的创造者[威廉·摩根](https://www.linkedin.com/in/wmorgan/)、[浮力](https://thenewstack.io/buoyant-cloud-beta-brings-simplified-linkerd/)的首席执行官说，采用和使用的简单性是 Linkerd 采用率强劲增长的原因。“Istio 因其复杂性而臭名昭著，我认为这损害了很多社区的信誉。相比之下，Linkerd 从第一天起就专注于简单性——尤其是操作简单性，这是很难实现的。摩根说:“我们非常努力地不夸大这个项目。“这种简单性意味着我们不仅因为越简单越好而获得采用者，而且正如你所建议的，因为采用的低成本意味着 Linkerd 可以在更多情况下使用。如今，我们看到了 Linkerd 在三节点集群、具有成千上万个单元的大规模全球部署中的生产应用，以及介于两者之间的任何应用。”

然而，更深入的分析表明，尽管 Linkerd 的采用速度很快，但服务网格部门可能并不一定是一场由 Linkerd 领导的单场比赛。Solo.io 的首席营销官埃里克·弗里伯格(Erik Frieberg)说:“我不确定是否有足够的证据证明 Linkerd 在服务网络竞赛中明显领先。”。

## 更小的目标？

Linkerd 适用于小型和大型部署。在这方面，仅从销量来看，Linkerd 的采用率正在飙升。在这种情况下，其他领先的开源替代方案，如 Istio，通常被视为适合不同类型的应用程序，特别是 Kubernetes 管理的大规模部署。

“Linkerd 致力于让更多没有服务网格经验的组织能够访问服务网格。该产品吸引了需要服务网络来快速解决日常挑战的产品团队，而 Istio 的目标是拥有经验丰富的云原生基础架构团队的大型企业，这些团队希望自上而下地为企业的大部分部门创建一个统一的解决方案，”Volk 说。“因此，可能会有更多的小型企业在团队层面尝试 Linkerd，而 Istio 可能会对每个单独的企业有更大的整体渗透。”

互联网出版公司 [ZeroFlucs](https://zeroflucs.io/) 的创始人[史提芬格雷](https://www.crunchbase.com/person/steve-gray-c62e)也是 Linkerd 大使，根据他实施服务网格的经验，他说 Linkerd 的实施和管理相对简单。他的观察是基于 Gray 支持 Linkerd 在体育博彩集团 [Entain](https://entaingroup.com/) 澳大利亚分部的部署，当时他是交易解决方案主管，而 Entain 也在评估 Istio。

“我同意 Isitio 只适合较大规模的部署，这是因为它的重要性—在小范围内不值得这么做。然而，将相反的假设置于 Linkerd 之上，并说它不能在这些空间中发挥作用，这是不正确的，”格雷说。“Linkerd 在这两个领域都表现出色:它不仅易于上手，而且扩展起来也毫不费力。从宠物项目到为价值数十亿美元的公司的实时平台提供动力的主干系统，我都使用过它，这些系统有数千个 pod，在高度混乱的环境中每月处理数 Pb 的数据。"

面向大规模部署和多集群管理的服务网格的实现和管理也不一定复杂。“复杂或实现价值的时间长并不是适合大规模部署的要求的标志。最终，这两个网格的目标是完全相同的工作负载——你可以在规模范围的任何一端使用 Istio 或 Linkerd 问题是，对于现实世界的用例来说，这种微小的功能占用差异是否可以承载巨大的复杂性，”Gray 说。对于性能更高、对延迟敏感的应用程序，Linkerd 在基准测试中最擅长这类应用程序，这些毫秒对大型部署至关重要

## 但是 Istio 收养仍然会增长

尽管 Linkerd 的采用速度很快，而且被认为非常适合小型组织和部署，但 Linkerd 的采用速度仍在不断加快，尤其是大型组织。Frieberg 说，Solo.io 正在“与世界上一些最大的 Istio 部署合作，这些部署将功能、可扩展性、虚拟机支持和多集群视为其架构的基础”。“在经历了去年 500%的增长后，我们继续我们的爆炸式增长，”Frieberg 说。“我们认为 Istio 服务网格市场非常强劲，并将继续大幅扩张。”

沃尔克说，Linkerd 在市场上相对于开源 Istio 的地位也可以被描述为灵活的竞争者，它利用了 Istio 众所周知的挑战，即必须“为每个人提供一切”，因此努力为新加入服务网格的组织提供类似水平的可访问性。“Istio 旨在为高级 DevOps 团队提供绝对的灵活性，以连接、保护、观察和测试 Kubernetes 和 VMs 上的微服务，并且直到最近才开始降低其准入门槛，”Volk 说。“与此同时，Linkerd 增加了一些高级功能，如多集群支持、策略和遵守所需的容器启动顺序。这些新功能吸引了 Istio 的原始受众，使服务网格竞赛变得更加有趣。”

服务网格市场整体也在增长，而 CNCF 的采用数字包括沙盒项目等。因此，在 CNCF 的研究中，许多公司可能在已经采用 Istio 之后第一次报告采用 Linkerd。从这个意义上说，Linkerd 可以被视为一个“后起之秀”,同时 Linkerd 也在不断成长。Istio 的相对增长相对较慢(理论上)是因为它已经使用了一段时间，并且特别适合于在少数组织中进行大规模部署，因此部署规模更大但数量更少。

然而，沃尔克并不一定同意。沃尔克说，Linkerd 也“正在成为一个成熟的企业解决方案，同时 Istio 正在努力吸引服务网络经验较少的更多受众”。

“真正的比赛现在开始，但我们可以肯定地看到，林克尔德目前是显示出一些重要势头的竞争者，”沃尔克说。“最近，我们越来越多地看到最具自下而上势头的产品如何击败大型企业解决方案。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>