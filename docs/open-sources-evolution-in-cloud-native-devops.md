# 开源在云原生 DevOps 中的演进

> 原文：<https://thenewstack.io/open-sources-evolution-in-cloud-native-devops/>

[CloudBees](https://www.cloudbees.com/) 赞助了这个故事，作为正在进行的“云原生 DevOps”系列的一部分请回来查看这个网站的未来职位。

开源工具继续作为云原生开发运维模式和实践的基础，同时它们也在不断变化和发展。

当然，Cloud native 的起源可以追溯到亚马逊和微软开始提供所谓的云平台的时候，允许组织利用其全球数据中心的服务器网络上的大量资源。重量级人物谷歌和阿里巴巴紧随其后，为最近网飞和 Pivotal 开始描述所谓的云原生架构奠定了基础。

网飞一直非常透明地表示，它依赖于为其重要的视频共享服务构建的大型开源堆栈套件，这在很大程度上要归功于[云原生计算基金会【CNCF】](https://www.cncf.io/)提供的内容以及 [Kubernetes](https://kubernetes.io/) 和基于云原生架构构建的微服务架构。此外，在作为一个概念首次推出大约十年后，DevOps 帮助启动了团队文化，为行业向云原生部署的转变培育了开发管道和工作流。

“DevOps 实践和云原生架构的支柱围绕一致性、可移植性和可重复性走到了一起。软件定义的应用基础设施的兴起也是一个重要因素。随着技术的不断发展，开源项目的选择和灵活性将继续在以前代表不足的领域提供编纂，”[应用监控平台提供商](https://twitter.com/ravilach?lang=en) [AppDynamics](https://www.appdynamics.com/) 的技术布道者 Ravi lach man说。“Jenkins 曾经是 DevOps 世界的坚定支持者，现在正被强有力地引向云原生架构。云原生架构的稳健性似乎推动了 DevOps 领域的功能和平台。”

DevOps 在云原生工具和库上的部署显然取决于 DevOps 团队认为什么最适合他们的工作流。但是在今天的新栈环境中，这个开源和协作的时代创造了一个可能性的爆炸。虽然可以说这是一个好问题，但在选择最佳开源工具时，做出最终选择并不总是显而易见的，更不用说仔细考虑云供应商提供的云原生平台这一繁重任务了。

“开源，尤其是开源社区，不断推出新的工具、方法和最佳实践来解决云原生世界中的业务用例。“没有一天我们看不到 GitHub 上的新工具、库或框架，它们正在解决云原生的采用者在通过 DevOps 交付渠道推出更多应用时遇到的关键问题，” [Dynatrace](https://www.dynatrace.com/) 的 DevOps 活动家 [Andreas Grabner](https://www.linkedin.com/in/grabnerandi/) 说。“由于社区的开放性和与他人分享最佳实践的意愿，开源是云原生运动的核心构件。然而，另一方面，许多组织被开源产品的不断变化所淹没。”

Grabner 说，通常很难决定是否将精力和时间投入到一个开源项目中，“因为历史已经表明，只有少数项目能够在第一次宣传中存活下来”。“这就是为什么我们看到软件公司对开源做出贡献的趋势，并以此给更大的社区信心，这些项目不仅仅是个人的宠物项目，而是组织对它们的发展和保持有兴趣，”Grabner 说。“虽然这很好，并通过将它缩小到更易于管理的开源项目数量来降低一些复杂性，但我见过一些组织在试图管理不同的开源工具时遇到困难，这些工具为不同的云本机平台提供相同的功能。”

## 正确的工具包

当然，有许多开源解决方案可以帮助 DevOps 减轻与使用开源工具进行云原生部署相关的巨大复杂性和困难。

在今天的云原生世界中，“DevOps 意味着全栈开发人员和“将一切都转移到左边”，[的 Brian Dawson](https://www.linkedin.com/in/bvdawson/) 说，他是 [CloudBees](https://www.cloudbees.com/) 的 DevOps 传播者，CloudBees 为自动化软件交付系统和 Jenkins 提供一套工具因此，无论是否是云原生开发，这都意味着允许访问短暂的云基础设施，并为开发人员提供测试、提交代码和直接投入生产所需的工具，”道森说。这非常符合我们用 Jenkins access 构建的东西，这是一个开源项目，开发人员可以在从提交到生产的过程中轻松拥有该区域。"

CloudBees 还寻求开源社区和合作伙伴来帮助扩展其平台，“有点像 Jenkins 一直做的那样”， [CloudBees](https://www.cloudbees.com/) 的高级架构师、 [Jenkins X](https://github.com/jenkins-x) 的项目负责人 [James Strachan](https://www.linkedin.com/in/jstrachan/) 说。

“詹金斯总是将许多东西整合在一起，并使它们作为一个统一的东西来消费，”斯特拉坎说。“我们试图做的是扩展经典的 Jenkins 插件模型，使其更加云原生，因此你可以使用更多的微服务，使用 Kubernetes 等中的客户资源，这样任何人都可以用任何语言扩展平台。”

## 安全和其他角色

当然，在工具选择过程中，安全问题总是一个问题。“开源既是现代 DevOps 和云原生应用运动的推动者，也是挑战。开源工具、框架和服务的可用性使最佳实践、模式和受过教育的开发人员能够在全行业范围内共享，” [VMware](https://www.vmware.com/) 的前首席技术官、 [General Catalyst](https://www.generalcatalyst.com/) 的现任董事总经理 [Steve Herrod](https://www.linkedin.com/in/steveherrod) 说。"然而，这种普遍存在意味着未打补丁的安全问题是众所周知和可利用的."

然而，几乎矛盾的是，安全风险是敏捷开发和微服务运动的主要驱动力，Herrod 说。Herrod 说:“能够非常快速地测试和部署针对这些已知安全问题的修补程序，这是对更加僵化和传统的开发和部署方法的巨大改进。”

遗留的开源驱动的工具链，如[主厨](https://www.chef.io/)、[木偶](https://puppet.com/)、 [Ansible](https://www.ansible.com/) 等；Kubernetes 和微服务在开源运动中继续发挥着关键作用，但现状也可能很快改变， [Navdeep Sidhu](https://www.linkedin.com/in/navdeep) 、产品营销负责人 [InfluxData](https://www.influxdata.com/) 表示。“但是，尽管这些遗留应用程序中的一些只是被简单地迁移到了云上，但仍有相当多的应用程序被开源软件所取代。在 InfluxData，我们已经观察到了这种变化，因为我们的平台用于监控新构建的云应用程序以及 DevOps 工具链，”Sidhu 说。“我们也开始注意到使用开源工作流来为任何应用提供、保护、连接和运行任何云基础架构。”

但是，随着 DevOps 云原生部署所依赖的开源工具和平台不断发展，它们也应该继续作为从开发周期到运营的工作流的主干。

WSO2 的集成架构总监 Kasun Indrasiri 表示:“在整个云原生应用生命周期中，从设计到开发流程再到生产支持，开源技术已经并将继续深入其中。”。

AppDynamics、Chef、Cloud Native Computing Foundation、InfluxData、VMware 和 WS02 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>