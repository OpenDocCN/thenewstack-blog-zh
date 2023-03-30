# VMware 将收购 SaltStack 以实现高级多云自动化

> 原文：<https://thenewstack.io/vmware-to-acquire-saltstack-for-advanced-multicloud-automation/>

VMware 周二宣布的对 SaltStack 的待定收购应该有助于它在其自动化功能中插入大量缺失的组件，因为该公司正在积极寻求扩大其产品组合，以与 Red Hat 的 OpenShift 和其他多云端原生平台提供商竞争。

SaltStack 将增加扩展的多云和基础架构自动化，例如，包括但不限于 VMware 的 [vRealize cloud automation 软件](https://www.vmware.com/products/vrealize-automation.html)的云原生部署。当然，VMware 不断扩大的云覆盖范围现在还包括用于迁移 vSphere 工作负载的 VMware HCX。

对于 DevOps 团队来说，这意味着当迁移到 Tanzu 上的容器化多云平台，同时继续在同一保护伞下运行遗留系统时，Salt 将作为适用于不同类型基础设施的单一自动化接口和工具。

SaltStack 正在对配置接口进行标准化，以便 VMware 可以对其产品进行标准化，从而专注于使用 Salt 作为主要的配置自动化，而不是拥有一个内部大杂烩。同时，VMware 也将继续支持其他配置管理系统，如 Chef、Puppet、Ansible 等。

[企业管理协会(EMA)](https://www.enterprisemanagement.com/) 的分析师 [Torsten Volk](https://www.linkedin.com/in/torstenvolk) 告诉新堆栈，Salt 可以帮助 VMware 填补的一个关键漏洞是通过单一工具提供自动化的入职和多环境配置和编排。

“没有自动化技术一直是 VMware Tanzu 相对于 Red Hat OpenShift 的劣势，”Volk 说。“Kubernetes 只有建立在坚实的基础设施、网络以及最终的应用生命周期自动化的基础上，才能实现扩展。现在，VMware 已经具备了与 OpenShift 正面交锋的基础。”

Volk 说，作为“声明式基础设施管理和自动化的先驱”，Salt 的声明式功能也有助于填补“当今大多数企业都在努力解决的空白，同时它也是释放快速部署和扩展能力的关键，独立于底层云或数据中心基础设施”。沃尔克说:“SaltStack 的一大秘密是它能够近乎实时地自动纠正声明状态和实际状态之间的差异。”能够以分散但集中控制的方式跨云实现这一点，可能是 VMware 应用现代化和多云战略的关键构建模块。"

Salt 作为单一配置管理工具用于多云部署和流程编排，还将有助于 VMware 将其业务扩展到更多正在使用的传统 IT 基础架构。VMware 的产品组合包括 Tanzu 作为云原生应用程序的管理层，并对 Kubernetes 提供大量支持。 [vRealize automation](https://www.vmware.com/products/vrealize-automation.html) 平台充当 VMware 虚拟化之上的云消费层，例如计算、网络和存储虚拟化，类似于公共云提供商可能提供的服务。VMware 云计算自动化总经理 [Purnima Padmanabhan](https://www.linkedin.com/in/ppadmanabhan) 表示，借助 Tanzu 和 vRealize，组织“能够为客户提供完整的内部自动化应用”。对于 Tanzu，尤其是 vRealize，Salt 提供了“一套非常强大的自动化功能来实现软件配置自动化，”Padmanabhan 告诉新堆栈。

“假设您正在部署一个基础架构，您已经将应用程序体系结构(包括虚拟机、网络和存储)缝合在一起，现在您还可以在虚拟机中运行应用程序软件。Salt 的自动化(包括安全自动化)现在完成了完整的解决方案集，这意味着对于客户来说，VMware 提供了 CI/CD、DevOps 和基础架构管理所需的所有组件。”我们致力于开源社区，不仅通过支持来自 VMware 的提交者，还通过提供一种简单的方式来检入、测试和构建代码，使更广泛的社区能够做出贡献。因此，总的来说，开源将是我们产品的关键部分，你会看到我们在这方面加倍努力。"

SaltStack 作为一家公司，最终是围绕 Salt 建立的，当然，还有该公司发起的其他开源项目，包括[面向插件编程(POP)](https://github.com/saltstack/poppy) 以及 [Heist](https://github.com/saltstack/heist/issues/17) 和 [Umbra](https://github.com/saltstack/umbra) 。借助 VMware 的资源，这些项目可以继续增长。

在一篇[博客文章](https://blogs.vmware.com/management/2020/09/saltandvra.html)中，VMware 云计算管理业务部门高级副总裁兼总经理 Ajay Singh 描述了 SaltStack 在自动化和流程编排方面的长期努力。

“VMware 正在收购 SaltStack，以显著扩展其软件配置管理、基础架构和网络自动化功能。一旦关闭，SaltStack 将帮助我们完成我们的自动化故事，使我们能够将自动化能力从基础设施扩展到整个应用程序堆栈。这将包括虚拟机和容器中的软件和软件包，”辛格说。“这些软件配置管理功能将帮助我们满足客户的全部自动化需求，并进一步增强客户利用 VMware vRealize Automation 在内部和云中自动部署和配置基础架构平台的能力。”

Red Hat、SaltStack 和 VMware 是新堆栈的赞助商。

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>