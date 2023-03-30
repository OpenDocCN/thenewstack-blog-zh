# 有了 Heptio 和 Pivotal，VMware 在 Kubernetes 上加倍努力

> 原文：<https://thenewstack.io/with-heptio-and-pivotal-vmware-doubles-down-on-kubernetes/>

不太多年前，当容器成为如此热门的新技术时，技术行业正在谈论这对 VMware 意味着什么。容器对虚拟机技术的大型供应商是一种生存威胁吗？

在周一于三藩市举行的 [VMworld 2019](https://www.vmworld.com/en/us/index.html) 上，该公司宣布[将全力以赴 Kubernetes](/vmwares-project-pacific-integrates-vsphere-with-kubernetes/) ，这是最近用于编排和管理容器的热门技术。

凭借其庞大的客户群，首席执行官[帕特·基尔辛格](https://www.linkedin.com/in/patgelsinger/)说，“我们将成为 Kubernetes 最大的推动者。”

有迹象表明，该公司正朝着这个方向前进，11 月份收购了 Heptio 公司，这家公司由 Kubernetes 的创始人之一 Joe Beda 和 Craig McLuckie 创办。

人们在离开上午的主题演讲时表示，当贵公司拥有一些领先的 it 专家时，您会期望 VMware 会接受 Kubernetes。

尽管对 VMware 战略提出了一个假设，但“这不仅仅是拥抱 Kubernetes，更像是推动它。”

该公司推出了 [VMware Tanzu](https://www.youtube.com/watch?v=rYO4WrPKWI8) ，这是现有和新的产品和服务组合的营销名称，将帮助企业构建现代应用程序，跨环境一致地运行 Kubernetes，并从单一控制点管理所有 Kubernetes 集群。它将包括其最近收购的 [Bitnami](https://bitnami.com/) ，一个用于 web 应用程序和开发堆栈的打包安装程序库，以及计划收购的 [Pivotal](https://pivotal.io/) ，后者提供应用程序开发工具、数据管理产品和分析智能平台。

“我们将 Tanzu 视为一个全面的环境，为客户搭建起开发和运营世界之间的桥梁。这将是一个超级强大的企业级 Kubernetes 平台。Kubernetes 是这种转变的主要工具，我们现在有很多工作要做，以使它发挥作用，”Gelsinger 说。

Beda 在台上与 Gelsinger 一起说，该公司正在开发 Pivotal 应用程序，确保 Spring 在 Kubernetes 上运行良好，并参与开源项目，不仅仅是 Pivotal 的项目，还有 Knative 等项目。这项工作是在阿尔法。

“Kubernetes 非常灵活，但有时你必须成为 Kubernetes 专家才能充分利用它，”Beda 说。"企业需要的是一种安全的、自以为是的体验."

该公司的答案是 Project Pacific，现在是一个技术预览版，它将 Kubernetes 嵌入到 vSphere 的控制平面中。贝达说，这种整合并不肤浅。“我们正在将 Kubernetes 深入构建到 vSphere 中，并在此过程中使 vSphere 成为运行 Kubernetes 的更好场所。”

运营团队有一个地方可以管理他们的所有资源，包括虚拟机和 Kubernetes 资源。然后，应用程序团队将获得基于久经考验的 Kubernetes APIs 的自助式体验。他说，这种集成将深入 UI 层，但也将深入虚拟化层，增强 ESXi 以本机方式运行 Kubernetes。

“太平洋项目将 Kubernetes 嵌入到 vSphere 的控制平面中，以统一访问计算、存储和网络资源，并使用高性能、安全且易于使用的新本机 pod 来融合虚拟机和容器，”[VMware 云平台业务部门的首席技术官 Kit Colbert](https://www.linkedin.com/in/kitcolbert/) 在[的博客文章](https://blogs.vmware.com/vsphere/2019/08/introducing-project-pacific.html)中写道。“具体来说，这意味着 IT 运营人员可以从 vSphere Client 查看和管理 Kubernetes 对象(如 pod)。这还意味着所有各种 vSphere 脚本、第三方工具等都将与 Kubernetes 协同工作。”

它还将提供应用程序级别的控制，以便向开发人员应用策略和访问控制。

VMware 还发布了 [Tanzu Mission Control](https://blogs.vmware.com/cloudnative/2019/08/26/vmware-tanzu-mission-control/) ，这是一个为规模化生产提供控制和可见性的单一工具。

“Mission control 通过一个平台将操作人员和开发人员聚集在一起。运营商可以直接从 mission control 供应集群，然后他们可以为访问、备份、安全等事项设置策略。与此同时，开发商可以自由创新，在运营商设置的护栏内尽最大努力，”贝达说。

关键在于其对云健康的[收购，这有助于提供跨多云环境的可见性。](https://techcrunch.com/2018/08/27/vmware-acquires-cloudhealth-technologies-for-multi-cloud-management/)

根据 451 Research 首席分析师[杰伊·莱曼](https://twitter.com/ripcitylyman?lang=en)的说法，对 Kubernetes 的高度关注表明了一些事情。首先，VMware 已经增加了其战略，并通过有机和收购的方式关注云原生软件，如 containers 和 Kubernetes 其次，它反映了企业的现实，即许多容器仍然运行在虚拟机之上或之内。

“这在很大程度上是企业进入容器的方式——提供它们以更好地服务于开发人员并提高生产率和速度，但主要在虚拟机上运行这些容器，以向 IT 运营商提供可靠、经过战斗考验的虚拟机，这些虚拟机仍然具有良好的管理和工具，特别是隔离和安全性，”他说。“因此，虽然容器替换和虚拟机替换可能会随着时间的推移而增长，但我们预计容器和虚拟机甚至会在未来共存。”

他说，很少有公司有能力填补 Kubernetes 中的所有企业差距，但 VMware 是其中之一，他补充说，“尽管如此，VMware 不是领先的超大规模公共云提供商之一，因此随着企业云本机和 DevOps 部署越来越多地迁移到公共云，正如我们所预期的那样，VMware 在虚拟机、企业数据中心和私有云方面的优势将会减少。”

据 Gartner 分析师[保罗·德洛瑞](https://www.gartner.com/analyst/52496/Paul-Delory)称，对 Tanzu 这样的产品有非常真实的需求。

“Kubernetes 太复杂，一般 IT 商店无法有效构建和运营。我们早就知道了，”他说。“因此，公共云提供商都创建了自己的托管 K8S 产品。但是这些都是特定于云的，不可互操作。

“因此，现在 IT 部门的 K8S 基础架构孤岛分布在不同的云中。必须有人能够跨云管理所有这些基础架构，并使其协同工作。VMware 表示，他们就是这样做的人。我持谨慎乐观的态度。”

Delory 也对 VMware 走向开源的举动表示赞赏。

“这些新产品将需要与大量其他工具、工作流和应用程序堆栈集成。达到临界质量的唯一方法是让一个活跃的开发人员社区编写所有这些集成，并创建一个可重用代码库，其他人可以利用，”他说。

“关键是要具有互操作性，如果他们的实现偏离开源代码库太远，那么就失去了互操作性。所以他们没有动力去开发一个专有版本，事实上，这将违背他们的利益。”

本周，VMware 还宣布与 NVIDIA 建立战略合作伙伴关系，为 AWS 上的 VMware 云提供加速图形处理单元(GPU)服务，以支持现代企业应用，包括人工智能、机器学习和数据分析工作流。

VMware 是新体系的赞助商。

特征图像由 VMware 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>