# 集群 API 提供了一种管理多个 Kubernetes 部署的方法

> 原文：<https://thenewstack.io/cluster-api-offers-a-way-to-manage-multiple-kubernetes-deployments/>

使用 Kubernetes 的每个人都从单个集群开始，但几乎每个人都扩展到多个集群——正如最近的[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)最终用户[技术雷达调查](https://thenewstack.io/cncf-assesses-tools-for-kubernetes-multicluster-management/)所示，多集群管理仍然是复杂和分散的。如今，大多数组织不得不使用多种工具，如 Helm、Kustomize、GitOps 工具(如 Argo 和 Flux)、各种各样的操作符，甚至创建自己的工具，但[集群 API](https://github.com/kubernetes-sigs/cluster-api) 项目可以用 Kubernetes 级别的 API 取代其中的许多工具。

Kubernetes 联合创始人兼微软公司副总裁 Brendan Burns 告诉新的堆栈，当 Kubernetes 最初创建时，它不包括集群管理。“它只是假设机器在那里；一旦您启动了机器，并且在机器上提供了软件，Kubernetes API 就在这些机器上出现了。围绕“集群的创建是 API 的一部分吗？”的讨论由来已久或者只是假设有人创建了一个集群，然后 API 就由此而来？"

“想要创建并行集群或私有云或没有 AKS 等托管 Kubernetes 的云的人们需要工具来帮助他们。如果你只是说‘这是成套零件’，这就像凯尔西·海托华的‘艰难之路’；你学到了很多，但这不是实现自动化的好方法！"

标准的 Kubernetes 工具是 kubeadm，这是一个创建、初始化、升级和管理集群的命令行工具。但是 kubeadm 的初衷是作为一个引导工具，其他工具可以在其上构建，它既没有涵盖集群的日常管理，也没有涵盖 Kubernetes 环境的长期管理。

随着 Kubernetes 工作负载变得越来越复杂，并依赖于运营商、服务网格和 API 网关，而运营商、服务网格和 API 网关又依赖于 Kubernetes 的 API 服务器、调度程序和 etcd 的控制平面，该控制平面的可用性变得更加重要。但是因为它通常包括 etcd，这使得它有状态，并且操作需要以正确的顺序完成，使得控制平面管理足够复杂，需要自动化，特别是在有如此多不同的[Kubernetes 发行版、安装程序和托管服务的情况下。](https://www.cncf.io/certification/software-conformance/)

管理 Kubernetes 集群的不同部署机制都有不同的 API 来处理常见的集群生命周期事件，如创建和删除集群、升级主节点和节点以及添加或删除扩展容量。这可能意味着“供应商锁定、不一致和僵化，尤其是当希望在不同发行版之间水平移动时，” [Red Hat OpenShift](https://www.openshift.com/try?utm_content=inline-mention) 产品经理 [Adel Zaalouk](https://www.linkedin.com/in/adelzaalouk) 告诉我们。

伯恩斯解释说:“一般需要一个 API，这样你就可以进行 API 驱动的集群创建，就像你可以使用 AKS 这样的东西一样，但要以一种通用于所有这些不同提供商的方式进行，在裸机环境或虚拟私有云以及没有 Azure 这样的提供商的虚拟化环境中。

这就是集群生命周期特别兴趣小组的[集群 API 项目](https://cluster-api.sigs.k8s.io/)所承诺的:声明式的、Kubernetes 风格的 API，用于创建、配置和管理集群，并为平台运营商自动化集群生命周期管理。集群 API 维护者 [Vince Prignano](https://www.linkedin.com/in/vincepri/) 告诉我们，真正的目标是“让集群生命周期变得无聊”。

Kubeadm 是一个命令式的命令行工具，Prignano 称之为从零开始创建集群的瑞士军刀；"我们在上面构建的是一个更加不可变、更加易于管理的层."

## 到处都是一致的集群

伯恩斯把集群 API 称为“kubeadm 的 API 化”,并把它比作集群的操作符；它建立在 kubeadm 之上，但是可以使用任何引导提供者，并且它使用基础设施提供者来支持多种环境。

“我想创建一个虚拟机。嗯，你是想在 [VMware](https://tanzu.vmware.com?utm_content=inline-mention) 上创建它，还是在 Azure、不同的云中或 OpenStack 上创建它？为了构建一些通用的东西，我们需要从“我想要一台机器”到“我想要一台特定结构上的机器”的抽象映射。集群 API 为创建 Kubernetes 集群的人提供了集中的工具，而不必自己动手做任何事情，但这也很好，因为我可以拥有一个相对通用的本地集群 API，我可以与之交互，而不必担心“这是在 OpenStack 中创建的集群”或“这是在裸机上的集群”以及“这是在其他私有云上的集群”。"

他指出，使用具有通用 API 的基础设施提供商是一个分享最佳实践和修复漏洞的机会。“即使没有客户拥有一百个不同的集群提供者，但将他们全部整合到一个项目中，这一事实意味着大量代码将被重用，结果会更好。”

“越来越多的人发现它，发现错误并修复错误。”

集群 API 为创建虚拟机或部署虚拟机池等事情提供抽象，为每个提供商使用正确的服务，无论是[亚马逊 Web 服务](https://aws.amazon.com/?utm_content=inline-mention)自动扩展组、Azure 虚拟机规模集还是 GCP 管理的实例组，都使用自定义资源定义。

这在规模上尤其重要。脚本和命令行工具适用于处理一两个集群，“但是当你处理几十个或几百个集群，或者像 AKS 这样的几万个集群时，你必须有 API 驱动的东西，你必须有自动化。”

Burns 建议，Cluster API 最初的重点是创建工具的项目和受管理的 Kubernetes 平台，但从长远来看，它将对希望构建自己的 Kubernetes 平台的组织越来越有用。

“它使基础架构管理员能够以自动化的方式为用户调配群集，甚至构建工具以允许用户自助服务，并说‘嘿，我想要一个群集’，然后按一下按钮，群集就会弹出来。通过将集群 API 与 Arc 上的 Logic Apps 相结合，他们可以来到一个门户，按下一个按钮，提供一个 Kubernetes 集群，获得一个无代码环境，并开始构建他们的应用程序，所有这一切都通过 web 浏览器完成。这是以前他们只能在云中做的事情，而不是以可移植的方式。”

他说，Cluster API 是 Kubernetes 作为一个项目走向成熟的标志，既体现了它目前的使用方式，也体现了边缘领域的新机遇。“我们正在走向成熟，在这里你不必成为专家；伯恩斯说:“那些只想把一个数据源和一点点函数转换和输出放在一起的人，实际上可以在它需要运行的环境中实现所有这些，无论是飞机跑道、石油钻井平台、船只还是工厂。

## 集群 API 工具和概念

Cluster API 引入的第一个工具是 clusterctl，这是一个用于安装和管理集群生命周期的命令行工具；它处理资源的部署、升级和迁移。如果这听起来让人想起 kubectl，那是故意的，因为 Cluster API 故意呼应了 Kubernetes 的 API 和命令行风格。

Burns 指出:“这肯定是为了让人们感觉您正在管理您的工作负载，但您是在管理集群，而不是管理您的工作负载。

去年发布的集群 API v1 alpha 3 增加了基于 Kubeadm 的控制平面。这是一个声明式 API，用于部署、扩展和升级 Kubernetes 控制平面，包括 API 服务器、调度程序、控制器管理器、DNS 和代理服务，以及底层 etcd 数据存储，而不是手动创建机器资源来扩展，并从 etcd 集群中删除成员来缩减。

集群 API KCP 可以跨故障域分布节点。“你可以说‘我想要三个副本，我想要它们跨越多个可用性区域’，当我们收到声明性命令时，我们就去创建集群和控制平面，并在其上运行运行状况检查，”Prignano 解释道。如果某个节点因为 kubelet 进程停止、磁盘空间不足或硬件故障(或者错误或内存泄漏)而出现问题，Kubernetes 将尝试解决该故障，但如果足够多的节点出现故障，群集可能会耗尽资源，而 pods 将被驱逐。移除不健康的节点并替换它们避免了长期问题。

它还可以执行有限的自动修复。“如果真的出了问题，用户必须进行干预，但我们试图针对 80%的情况，如果一台机器坏了，我们可以检测到它，删除它并创建一台新的。”

集群 API 提供了两类集群:运行集群 API 本身的管理集群和运行用户工作负载的工作负载集群。管理集群负责跟踪它创建的所有多个工作负载集群。这允许您在多集群级别执行 GitOps，而不仅仅是针对节点或工作负载。

德国电信已经在使用[集群 API、vSphere 和 Flux GitOps](https://semaphoreci.com/blog/cloud-native-adoption-vuk-gojnic) 为集群提供 Prometheus、Grafana 和其他工具作为内部平台。他指出，管理集群不一定需要运行在与工作负载集群相同的基础设施上，这可以实现多云场景。一些用户拥有一个管理集群，该集群通过 VPN 在多个云之间进行网络连接。

“如果您有网络连接，该管理集群可以管理我们提供的所有云提供商的集群。这不是一个单一的失败点:我们从头开始建设一切，以真正重返，并确保我们可以重建这个国家。如果您有一个像 Velero 这样的备份和恢复系统[，您可以拆除管理集群，创建一个新的集群，恢复整个备份，一切都会重新开始运行。”](https://velero.io/)

## 集群 API 可以使用了吗？

Prignano 解释说，虽然 alpha 标签可能会让一些人却步，但 Cluster API 仍然在 alpha 中的原因是因为该项目为用户体验设置了很高的标准。核心概念是“让 80%的事情变得简单，让 20%的事情变得可能”，所以重点首先是让基础变得可靠，然后是为企业将拥有的高级用例提供扩展点。

新的 alpha four 版本是一个重要的里程碑，专注于稳定性和可重复性，为他预计将于 2022 年上半年发布的 1.0 beta 版本铺平了道路。“我们希望确保当我们进入测试版时，我们有更好的用户体验，并且我们真的抓住了 20%的高级案例。”

API 的稳定性和构成集群 API 的概念将允许在未来的版本(可能在 2022 年下半年)中基于集群类构建新的功能。

他将类描述为一种标记集群，然后为多个集群重用该类的方法。今天，如果您因为有了 CVE 而不得不推出新版本的 Kubernetes，您必须修改映像并就地应用 Kubernetes 升级，并且您必须检查它是否成功。一个集群类描述了几个具有相同“形状”的集群；“我可以更改一个 Kubernetes 版本，然后推广到所有集群。我们可以简化耗时的操作，并在过程中进行检查。如果我们检测到控制平面或工作节点未能成功启动，我们将停止并通知用户。”

今天，Kubernetes 用户必须为集群信息构建自己的存储库。集群 API 使用 [clusterctl describe 命令](https://cluster-api.sigs.k8s.io/clusterctl/commands/describe-cluster.html)获得它，该命令使用管理集群来检查工作负载集群。

借助集群类和简单的生命周期管理、运行状况检查以及备份和恢复，您将能够发现问题，并查看您的 Kubernetes 基础架构，以找到合适的集群来迁移工作负载。“如果您有相同形状的集群，您可以说‘我想将我的应用程序从一个集群移动到另一个集群。’我不想使用这个集群，而是想关闭我的所有应用程序，并将它们放到另一个集群中。"

用户还可以循环使用机器:“有些人不想让机器运行超过六个月。”集群 API 还将能够帮助进行证书管理，这在今天通常是手动完成的。“我们知道 Kubernetes 需要在哪里保存其证书代理和 kubelet 证书，我们正在努力使这变得更容易。”有一个建议是做节点证明和安全 kubelet 认证；“我们可以确保当节点加入群集时，它会根据您的预期进行签名和验证。”集群 API 是为增量采用而特意构建的。“你不必使用我们提供的所有功能，”Priganano 解释道。“许多公司已经投入了大量时间和精力来创建自己的 Kubernetes 管理系统。因为我们使用 Kubernetes 来管理其他 Kubernetes 集群，所以您不必马上移动所有的基础架构。”

至关重要的是，clusterctl 等集群 API 工具也作为 Go 库提供，因此工具创建者可以将它们构建到自己的产品中，并仍然利用基础架构提供商的优势，而无需了解如何在 VMware、Open Stack、Azure Stack HCI 和多个云提供商上创建机器的具体细节。

微软、Red Hat 和 VMware 已经在他们的工具中使用集群 API。他将集群 API 称为 Tanzu 的“基础”,微软的混合 Kubernetes 解决方案依赖于它，Arc 和 Azure Stack HCI 使用集群 API 来管理 Kubernetes 集群。

Burns 告诉我们，Arc 客户端是“一个非常小的集群 API 管理集群，它扩展并管理该客户集群”。“我有两个不同的地方可以运行东西；我有一个地方供我的用户运行东西，还有一个地方供我作为管理员运行东西，我不必担心用户的代码运行和我的代码运行之间的干扰。我有一个安全的空间，他们不会打破。"

Azure Stack Hub 上的微软 [AKS 引擎集群供应目前不使用集群 API，因为它是在可用之前编写的，但他建议未来将迁移到集群 API。](https://github.com/Azure/aks-engine)

Red Hat 为 OpenShift 维护一些集群 API 机器提供者的分叉。“在未来，Red Hat 倾向于提供一个无摩擦的路径来逐步将机器管理逻辑从今天在 OpenShift 中使用的[机器 API 操作符](https://github.com/openshift/machine-api-operator)转移到 Cluster-API，”Zaalouk 说。期待这是一个即将到来的技术预览功能。

集群 API 机器提供者已经在 Red Hat 的 [HyperShift](https://github.com/openshift/hypershift) 和中央基础设施管理中用于测试，这些项目将更广泛地采用它。

Prignano 指出，不仅 VMware 和微软的贡献者在集群 API 上进行合作；他们还为苹果的 Kubernetes 基础设施团队提供建议，该团队正在与阿里巴巴合作创建一个嵌套提供商，这是一个基于 pod 的控制平面。“我们正在帮助苹果公司的一些人塑造他们如何运行集群，这与人们今天所做的真的不同。”

另一个 place Cluster API 已经很有用了；Kubernetes 项目依赖于它。因为它是在 Kubernetes 的主要分支的尖端开发的，并且有生命周期 SIG 发现的上游问题的历史，集群 API 测试对 Kubernetes 本身来说是“发布通知”,作为发布新版本的反馈循环的一部分。

虽然它是为基础设施管理而设计的，但 Prignano 指出，集群 API 对开发人员也很有用，他们需要使用 Kubernetes API，但没有安装目标。" Docker 提供程序内置于集群 API 中，因此您可以在笔记本电脑上本地运行它."

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>