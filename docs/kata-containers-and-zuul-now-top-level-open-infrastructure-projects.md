# 卡塔集装箱和祖尔现为顶级开放式基础设施项目

> 原文：<https://thenewstack.io/kata-containers-and-zuul-now-top-level-open-infrastructure-projects/>

[红帽 OpenShift](https://www.openshift.com/) 赞助本帖。

在本周的[开放基础设施峰会](https://www.openstack.org/summit/denver-2019/)之前， [OpenStack 基金会(OSF)](https://www.openstack.org/foundation/) 董事会投票[确认](https://wiki.openstack.org/wiki/Governance/Foundation/OSFProjectConfirmationGuidelines)其两个试点项目 [Kata Containers](https://katacontainers.io/) 和[Zuul](https://zuul-ci.org/)——为顶级开放基础设施项目。项目的确认标志着一种成熟，无论是在采用 OpenStack 的四个核心原则方面，还是在活动、关注和治理水平方面。

OpenStack 基金会董事会成员 Allison Randal 在一份公司声明中表示:“Kata Containers 和 Zuul 是两个令人兴奋的、非常有用的软件项目，它们通过提供具有开源组件的生产基础设施，为用户解决现实世界的问题。“在确认 Kata Containers 和 Zuul 为已确认的开放基础设施项目时，我们承认这些软件项目的稳定性和成熟度，并庆祝它们各自协作社区的增长和发展势头。”

Kata Containers 通过使用轻量级虚拟机为容器工作负载提供隔离，在多租户环境中为容器提供了额外的安全层。该项目[于今年早些时候](https://thenewstack.io/kata-containers-now-works-with-aws-firecracker-for-ephemeral-workloads/)宣布采用亚马逊在 2018 年末[开源的 AWS 鞭炮管理程序。本周，该项目提供了下一个版本的更新，预计在未来几周内发布。](https://thenewstack.io/aws-firecracker-a-micro-vm-for-serverless-deployments/)

根据 Kata Containers 架构委员会成员兼英特尔首席软件工程师[塞缪尔·奥尔蒂斯](https://github.com/sameo)和鞭炮项目维护者兼 AWS 软件工程师[安德里亚·弗洛雷斯库](https://www.linkedin.com/in/andreea-florescu-670a4a75/)的主题演讲，Kata Containers 自 2018 年 5 月以来发布了六个更新，改进了硬件架构支持，增加了其中的安全性。此外，两人表示，该项目正在努力提供 ARM 和 AMD 的支持，以集成[鞭炮容器](https://github.com/firecracker-microvm/firecracker-containerd)，并将重构其代码库，以提供独立的虚拟化组件供其他项目使用。此外，Ortiz 还推出了 [rust-vmm](https://github.com/rust-vmm) ，这是一个用 rust 编写的定制容器管理程序，旨在增加该项目支持的容器工作负载的数量。

至于 Zuul，来自惠普的 OpenStack 项目基础设施团队的核心成员 James Blair 也在 Open Infrastructure Summit 的舞台上宣布，该项目不仅仅是一个 CI/CD 工具，而是一个“项目门控系统”，它“改变了我们开发容器化软件的方式”，具有“投机性执行”。一份公司声明将 Zuul 描述为使用“项目控制，以安全的方式自动化相关软件项目的持续集成、交付和部署，同时交付复杂的项目控制，特别是在涉及具有集成可交付成果的多个存储库的场景中。”

Blair 解释说，这种“假设”是 Git 多年来的标准，但 Zuul 现在将这种能力引入容器，允许开发人员在复杂系统中发现问题并验证解决方案，然后将单个更改提交给生产。它通过创建推测性的短暂容器映像来做到这一点，他说这使测试更像生产，而不是相反。只有当使用这些映像的测试作业通过时，才允许将更改推送到生产中。

Kata Containers 于 2017 年 12 月成为 OSF 的试点项目，Zuul 于 2018 年 5 月加入，投票确认就在会议开始前一天。根据公司声明，Zuul 已经“发布了 15 个版本，提供的功能包括支持 AWS，OpenShift 和多个 Ansible 版本，推测性容器执行，以及作业控制哪些子作业运行的能力。”Zuul“拥有强大的贡献者基础和用户社区，包括 Ansible 社区、BMW、GoDaddy、GoodMoney、Leboncoin、OpenLab、OpenStack、Red Hat、SUSE、钨织物和维基媒体基金会。”

OpenStack 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>