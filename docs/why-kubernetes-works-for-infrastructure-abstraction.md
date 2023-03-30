# 为什么 Kubernetes 致力于基础设施抽象

> 原文：<https://thenewstack.io/why-kubernetes-works-for-infrastructure-abstraction/>

[KubeCon + CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 赞助了这篇文章，期待 [KubeCon + CloudNativeCon NA](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 于 11 月 18-21 日在圣地亚哥举办。

Kublr 的首席执行官 Slava Koltovich 和首席技术官 Oleg Chunikhin 无疑非常适合讨论 Kubernetes 的角色，无论是作为一个容器编排者，它在运营管理中的作用，还是未来可能会发生的事情。Koltovich 和 Chunikhin 还探讨了彼此在 Kubernetes 方面的专业领域，以及 Kublr 如何帮助实现平台管理的自动化。

## Kubernetes:超越容器编排

 [斯拉瓦·科尔托维奇

Slava 是 Kublr 的首席执行官，kub lr 是一家领先的企业级 Kubernetes 供应商，由 EastBanc Technologies 提供支持。Slava 还是 Hostme 的联合创始人和董事会成员，也是 EastBanc Technologies 的长期首席执行官。](https://www.linkedin.com/in/slavakoltovich/) 

**Koltovich:你说过，行业需要从把 Kubernetes 纯粹看作一个容器编排器转变为利用它作为一个基础设施抽象层。但这意味着什么呢？**

是的，Kubernetes 是一个容器编制器，但它能做的远不止这些。本质上与基础设施无关，您可以使用 Kubernetes 将基础设施从更高级别的服务和应用程序中抽象出来。这不仅使您的应用程序更加易于移植，而且还增加了灵活性，构建了一个急需的、面向未来的架构。

**Koltovich:这对日常运营有什么影响？**

**Chunikhin:** 您希望让团队专注于他们最擅长的事情，而在基础设施层面进行抽象确实会让这变得容易得多。运营团队可以为开发人员提供一个平台，以独立于基础设施的方式运行他们的堆栈和应用，同时仍然根据他们部门的要求微调基础设施。另一方面，开发团队可以专注于编写软件，同时仍然保留对如何建立基础设施的大量控制。

资源抽象和可插拔架构为您提供了一个非常灵活的框架，可以插入到任何基础设施中。操作员框架允许您封装与管理应用程序和中间件的特定组件相关的知识和经验。他们通过自动化大量操作任务来实现这一点，这在涉及数据存储系统的管理时尤其方便。这也使得小型组织使用托管存储变得可行。

 [奥列格·楚尼欣

Kublr 的 CTO Oleg 拥有 20 年的软件架构和开发经验，负责定义 Kublr 的技术战略和标准。在加入 Kublr 之前，Oleg 是 EastBanc Technologies 的首席软件架构师和技术合作伙伴。](https://www.linkedin.com/in/olegch/) 

Koltovich:这对未来准备有什么影响？

**Chunikhin:** 架构将最终决定任何解决方案的寿命。越灵活和可插拔，它就越有可能适应市场需求。将容器编排层与中间件和云原生或托管服务分开，可以确保您的系统架构保持模块化和开放。一旦你开始把各层绑在一起，你就牺牲了灵活性。当心固执己见的开源，这是一种越来越流行的新型技术，它否定了开源的核心优势之一！

简而言之，就像十年前一样，清晰的层分离这一古老的架构最佳实践在这里也同样适用。不同的是，Kubernetes 将这一切带到了一个全新的水平——不利用它的力量是愚蠢的。

## 自愈不等于自愈

**Chunikhin:你之前强调过，围绕 Kubernetes 和自愈似乎存在一些困惑，为什么？**

你会听到很多关于自愈和 Kubernetes 的说法。然而，它有多个层面，为了确保真正的自我修复应用程序，你需要触及所有层面。

Kubernetes 的自愈能力只适用于豆荚。如果一个 pod 关闭，Kubernetes 将重新启动一个新的。然而，如果整个节点都瘫痪了，Kubernetes 通常无法再建立一个新的节点。从自我修复的角度来看，这意味着基础架构可能会成为链条中最薄弱的一环，危及应用程序的可靠性—您的集群的可靠性取决于底层基础架构。

**Chunikhin:这些自我修复层是哪些？**

**Koltovich:** 为了确保应用程序的可靠性，您需要(1)一个自我修复的基础设施，包括工作节点和主节点；(2)通过自愈大师(不一定是工人)实现的自愈集群；(3)自愈豆荚；以及(4)自愈 Kubernetes，虽然依赖于自愈基础设施，但需要特定的配置。

此外，自我修复基础设施并不能保证自我修复 Kubernetes。在安装、配置和连接组件以创建集群之前，必须为 Kubernetes 提供基础设施。这基本上就是凯尔西·海塔尔在他的教程中描述的。自动化基础架构配置带来了一些复杂性。由于 Kubernetes 不这样做，它要么留给你或你的供应商。但是请注意，基础设施供应还不是一个标准特性(尽管我们坚信它应该是)。

**Chunikhin:为什么基础设施供应如此重要？**

**Koltovich:** 如果平台不提供基础设施，它就不能确保基础设施被正确设置和初始化。谁或什么将保证操作系统和软件组件的正确包和版本安装在节点上？这些事情真的很重要，因为 Kubernetes 集群的可靠性取决于它所运行的基础设施。这就是 Kublr 自动供应基础设施的原因。这种方法尽可能利用本机基础架构自动化工具(如 AWS 的云形成或 VMware 的 vSphere)来自动化流程。

Chunikhin:没有自我修复的基础设施意味着什么？

**Koltovich:** 如果您没有自我修复的基础设施，并且某个节点出现故障，您将面临数分钟甚至数小时的潜在停机时间；这完全取决于您的运营团队对事件的反应速度。这就是基础架构配置如此重要的原因，只要基础架构允许，就允许设置自我修复节点。对于面向客户和任务关键型应用程序，节点自我修复和可靠的基础架构供应至关重要。如果平台不提供这一点，应用程序的性能就不可能得到保证。

**Chunikhin:那么为什么这不是一个行业标准呢？**

**科尔托维奇:**好问题。我们认为应该是——这太重要了。虽然许多供应商认为已经安装了 Kubernetes，但我们的目标是消除任何限制，并提供[可靠、完全自我修复的生产级集群部署](https://kublr.com/)。最终，它可能会成为一个行业标准，因为当用户遇到上述问题时，他们会开始要求它。

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>