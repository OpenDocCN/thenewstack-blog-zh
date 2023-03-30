# Druva 为 Kubernetes 引入软件即服务数据保护

> 原文：<https://thenewstack.io/druva-introduces-software-as-a-service-data-protection-for-kubernetes/>

想要一份辛苦的工作？尝试保护每个人都喜欢的容器编排程序 Kubernetes T1。甚至它的母公司，[云本地计算基金会(CNCF)](https://www.cncf.io/) ，在其最近的 Kubernetes 安全审计中，最近报告了许多 Kubernetes 安全问题的存在，因为它的“配置和部署[是]不平凡的，某些组件具有混乱的默认设置，缺少操作控制和隐式设计的安全控制。”云数据保护和管理公司 Druva 认为它可以提供帮助。

Druva 通过其 Druva 云平台提供的新测试版数据保护服务提供了应用程序保护，可以从统一界面快速恢复、迁移或克隆 Kubernetes 工作负载。

该公司表示，它旨在保护 Kubernetes 的工作负载免受用户错误、网站中断和勒索软件攻击等数据威胁。企业无需采用另一种专门针对 Kubernetes 的点备份工具，而是可以在 Druva 中保护 Kubernetes 应用程序及其底层基础架构以及现有工作负载。

这是作为软件即服务交付的(SaaS)。其特点包括:

*   应用程序一致性数据保护
*   全面的应用程序保护，包括 Kubernetes 集群内外的资源
*   安全的 SaaS 管理，利用基于[亚马逊网络服务(AWS)](https://aws.amazon.com/) 的平台进行全球控制
*   针对开发运维人员和应用程序所有者的集中式保护、管理和对自助式恢复的合规性
*   为 Kubernetes、数据中心、云和设备工作负载提供统一保护

Druva 的首席技术专家 Stephen Manley 说，这很重要，因为我们仍然没有一个易于管理的企业数据保护解决方案来保护整个应用程序，包括对外部存储和数据库的依赖。当然，有许多 Kubernetes 数据保护程序，例如开源项目 Velero，但是 Manley 声称，“现有的保护工具是孤立的，不能满足企业保护的要求。”此外，Druva 的服务管理员“可以安全、无缝地将 Kubernetes 保护纳入其现有策略，同时支持应用所有者在必要时恢复、迁移和克隆应用。”

它通过自动获取、存储和保护 Kubernetes 环境的快照来做到这一点。您可以使用这些工具快速轻松地恢复您的应用程序。您还可以使用它们将群集恢复到新位置，以进行迁移、克隆或生产工作负载故障排除。这些备份快照也可以存储在异地，以满足合规性要求。

Manley 在一次电子邮件采访中补充道，“Druva SaaS 平台保护我们客户的 AWS 账户中运行的 Kubernetes 集群。“这包括 AWS 弹性 Kubernetes 服务(EKS)集群以及在 AWS 中手动部署的集群。Manley 写道，Druva 为 Kubernetes 数据保护工作组做出了贡献，保护客户群中跨账户和区域的应用程序的数据和元数据。

[菲尔·古德温](https://www.linkedin.com/in/phil-goodwin-4759b2/)， [IDC](https://www.idc.com/) 研究总监，负责数据管理。喜欢德鲁瓦的计划。“不幸的是，在采用集装箱的竞赛中，保护措施常常被抛在后面。Druva 旨在提供一个单一的解决方案，将 Kubernetes 的保护与现有的数据管理系统结合起来，为企业扩展其容器工作负载的使用提供一个令人信服的选择。”

Druva 的客户可以通过选择 Druva 的 AWS 备份和灾难恢复程序套件 [CloudRanger](https://cloudranger.com/) 中的“Kubernetes”选项来尝试这一新的数据保护程序。今年年底将可以提前使用。如果测试一切顺利，它将在 2021 年上半年广泛上市。

亚马逊网络服务和云计算原生计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>