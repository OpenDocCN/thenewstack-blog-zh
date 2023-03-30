# NetApp 的开发运维难题和经验教训

> 原文：<https://thenewstack.io/netapps-devops-struggles-and-lessons-learned/>

[NetApp](https://www.netapp.com/us/solutions/devops/index.aspx) 赞助了这篇文章。

 [麦克·莫里斯

Michael 是 NetApp 的 IT 基础架构高级总监。他负责领导 NetApp IT 部门的计划，以确定和评估支持 NetApp 产品战略、支持 IT 数据管理和利用混合云能力的下一代和新兴技术。Mike 的团队负责管理 IT 工具、软件平台和方法，以提供开发运维、CI/CD、自动化和服务管理，从而充分利用云的当前和未来优势。](https://www.linkedin.com/in/michaeljmorris/) 

当你想在任何问题上看起来像个权威时，给出建议是最简单的策略。然而，当然，以身作则更难。本着这种精神，多年来，NetApp 一直在自己的系统中采用自己的 DevOps 方法和技术。在其内部 IT 团队的领导下，NetApp 宣布采用软件定义的基于云的数据中心，实现端到端 DevOps 工作流自动化；换句话说，它开始构建和运行技术平台，以允许软件开发者利用 [DevOps](https://www.netapp.com/us/solutions/devops/index.aspx) 。

但是到达那里并不总是容易的。

在本帖中，我们描述了 NetApp 的开发运维之路，以及任何组织在实现这一目标的过程中都会遇到的困难。

对于任何组织来说，通往 DevOps 的道路都包括三个主要环境:开发人员工具、平台软件和基础设施即服务(IaaS)。DevOps 工作流在所有三种环境中都是自动化的，允许软件开发人员推送和提取源代码、选择应用堆栈、运行 CI/CD 工作流并快速产生业务成果。最终，开发人员有望创建云感知应用，这些应用使用微服务架构，在与基础设施无关的设计中运行在容器中。通过这种方式，它们可以在公共云提供商和私有云之间进行云移植，同时将应用程序工作负载路由到开发人员想要使用的任何云基础架构。

由 Sumardi Fu 创建的 DevOps 成熟度模型反映了通常的行动过程以及组织在实施 DevOps 时通常会经历的情况。组织对实施 DevOps 的承诺程度通常在 1 级或“临时”范围内，这意味着组织除了说它已决定开始 DevOps 之旅外什么也没做。第 5 级承诺，类似于网飞和脸书所做的，包括持续更新，没有明显的停机时间。NetApp IT 符合 3 级分类，即可以创建、部署和支持实际应用程序的自动化开发运维。

然而，在 NetApp，我们的能力、经验和速度仍然不成熟。达到第 5 级将需要多年的旅程来改善我们的特性、能力和人类技能。

在应对 DevOps 实施挑战时，我们从 NetApp IT 之旅中学到了三条宝贵的经验:

*   构建基础环境:从最初的设想到第一次发布，这已经花了一年的时间。我们很早就意识到，跨开发人员工具、平台软件和基础架构即服务(IaaS)实现开发运维工作流自动化非常复杂，因此需要时间。
*   **培训应用开发团队**:培训适用的云感知应用和开发运维团队至关重要。通过花时间提供教育重点，您可以在基础架构和业务应用程序团队之间培养一种值得信赖的工作关系。这可能会导致构建或迁移新的和现有的应用程序。
*   **让关键工程师保持专注**:使用 DevOps 构建云感知企业是一项通常需要数年时间的服务。因此，参与初始构建的工程师需要全程参与。这种运营模式使用敏捷实践和频繁发布来保持参与度。

作为第一客户，NetApp 的目标是尽早、频繁地使用自己的产品、服务和参考设计。这意味着要花大量时间与产品团队交流，提供关于功能的反馈，分享好的/不好的实施结果，并影响新的路线图，从而确保持续的反馈循环，以改善 NetApp 的客户体验和满意度。

在下一阶段，NetApp IT 部门打算实施 ONTAP [Ansible 行动手册](https://netapp.io/2018/08/08/second-major-ansible-module-release/)以实现基础架构自动化，并实施 [NetApp Trident](https://www.netapp.com/us/media/ds-netapp-project-trident.pdf) 插件以在 OpenShift 中创建卷。使用各种内部技术的私有云的最终结果包括:

*   [超融合基础设施(HCI)](https://www.netapp.com/us/products/converged-systems/hyper-converged-infrastructure.aspx) 为容器化应用组件提供计算、内存和(本地)存储。
*   [全闪存 FAS (AFF)](https://www.netapp.com/us/products/storage-systems/all-flash-array/index.aspx) 用于数据库和高性能工作负载的状态存储平台(Flash FAS)
*   [StorageGRID](https://www.netapp.com/us/products/data-management-software/object-storage-grid-sds.aspx#storageGRID-software) 是重型对象存储使用的存储库，因为云感知应用程序本质上是无状态的，应该使用无状态存储机制。

这些云友好的技术与现有的客户群产品无关，对于云之旅尤为重要。最终，开发运维工作流创建的所有开发运维工具、软件和应用都需要基础架构。采用基础架构产品，对其进行简化并使其软件化，可以轻松地为 DevOps 环境添加插件。

这就是 IT 的未来——通过 API 和自动化将好的产品插入现有的 DevOps 环境中。当 NetAppIT 在自己的组织内测试各种 [DevOps](https://www.netapp.com/us/solutions/devops/index.aspx) 和[私有云](https://www.netapp.com/us/private-cloud/index.aspx)解决方案时，它真正概括了一句谚语，“吃自己的狗粮”但这也是一个权威的证明，如果解决方案在内部失败，那么它们就不适合公众消费。到目前为止，这是一项艰巨的工作，但毫无疑问的成就。

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>