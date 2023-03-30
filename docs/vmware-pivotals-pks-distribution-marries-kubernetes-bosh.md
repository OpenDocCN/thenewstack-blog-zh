# VMware 和 Pivotal 的 PKS 发行版将 Kubernetes 与 BOSH 结合在一起

> 原文：<https://thenewstack.io/vmware-pivotals-pks-distribution-marries-kubernetes-bosh/>

在云原生空间中，广义地说，有两类用户:平台运营商和开发者。新产品或服务很少能同时满足这两类人的需求。

通过最近宣布的 PKS ( [Pivotal 容器服务](https://pivotal.io/platform/pivotal-container-service))、 [VMware](https://www.vmware.com/cloud-solutions/app-modernization/cloud-native-apps.html) 和 Pivotal 与谷歌云合作，致力于解决这一问题。他们的新商业支持版本[Cloud Foundry Container Runtime](https://www.cloudfoundry.org/container-runtime/)承诺让 Kubernetes 易于虚拟化管理员运行和操作，从而为开发团队提供他们所需的支持，以支持需要可靠基础设施的新计划，这些基础设施的形式是运行在 [vSphere](https://www.vmware.com/products/vsphere.html) 或 [Google 云平台](https://cloud.google.com/kubernetes-engine)上的 Kubernetes。

通过将 Kubernetes 与 VMware 的基础架构工具和多云计算功能相结合，Pivotal 和 VMware 共同打造了一款产品，可以真正将开发人员和运营人员结合在一起。

## 波什的美丽

由[Cloud Native Computing Foundation](https://www.cncf.io/)管理的 [Kubernetes](/category/kubernetes/) 容器编排系统，通常被称为“云的 Linux ”,并在各行各业广泛采用。甚至 Docker 也将它作为与 Swarm 一起的管弦乐队。然而，这并不是一个万能的解决方案。根据不同的用例，用户可能会发现 Kubernetes 的一些局限性。

例如，Kubernetes 在管理容器方面做得很好，但在虚拟机方面就不太好。如果一个节点出现故障，而 pods 正在其上运行，Kubernetes 将会意识到这个故障。它将找到一个新节点，并在其上重新部署这些单元，以维护应用层的可用性。然而，Kubernetes 永远也不会让那个工作节点重生，让那个集群恢复到最强状态。

*但是像 [BOSH](https://bosh.io/) 这样的工具可以。*

BOSH 将监控基础设施层。如果一个节点关闭，BOSH 将启动另一个实例，将其添加到集群中，并将集群恢复到其最大容量。

认识到这是 Kubernetes 社区没有解决的一个用例，Pivotal 和 Google 共同合作，将 BOSH 和 Kubernetes 的功能结合起来，创建了一个名为 [Kubo](https://pivotal.io/partners/kubo) (Kubernetes on BOSH)的项目。该项目被捐赠给了 [Cloud Foundry Foundation](https://www.cloudfoundry.org/) ，后者后来将其重命名为 Cloud Foundry Container Runtime(CFCR)，并将其用作 Cloud Foundry 的默认容器运行时。

Pivotal 和 VMware 此后合作将 CFCR 产品化为 PKS，这是一款生产级 Kubernetes，旨在通过内置的高可用性、监控、自动化运行状况检查等功能减轻“容器编排的第二天操作负担”

## 姐妹间的密切合作

戴尔旗下 Pivotal 的姐妹公司 VMware 在 PKS 看到了巨大的潜力，可以为现有的 VMware 管理员带来运营控制和舒适性。因此两家公司形成了密切的合作关系。

“这并不是说我们要制造一款关键产品。我们在 PKS 的开发工程师至少和 Pivotal 一样多；这在很大程度上是一个联合项目，”VMware 负责云原生应用产品管理的副总裁[保罗·杜尔](https://www.linkedin.com/in/pauldul/)说。

这种参与超越了代码开发。两家公司在开发人员方面和基础设施平台运营方面合作解决不同的客户群。

使用 Pivotal 对 VMware 来说有两种意义。根据 Dul 的说法，这种组合可以:1)提供更好的产品，2)满足更广泛的客户群。

在用户群方面，一方面，VMware 与平台运营商和虚拟基础架构运营商有着密切的关系。Dul 说，另一方面，Pivotal 与开发人员有着密切的关系。因此，VMware 和 Pivotal 共同满足了广大用户的需求。

Pivotal 在 PKS 之外又增加了许多东西来为客户服务。“其中之一是 PKS 控制器，这是一个控制平面，允许用户快速旋转多租户集群，并为这些集群提供滚动升级，”Dul 说。

VMware 为 PKS 带来的一个关键产品是 [NSX-T](https://docs.vmware.com/en/VMware-NSX-T/index.html) 软件定义的基础架构，它为 Kubernetes 提供网络虚拟化功能。NSX-T 带来的真正价值是，网络往往是 Kubernetes 领域中最复杂的情况之一。

“我们从客户那里听到的大多数问题都与网络层有关，”Dul 说。“NSX-T 在可视性、监控和诊断以及微分段方面带来了很多功能，能够控制 pod 之间的东/西流量。”

“我们在 pod 级别提供了微分段，允许用户在 pod 级别设置安全组来控制流量。让我们假设前端需要与一些数据库对话，这不是一个好主意。它应该与应用程序而不是数据库进行对话。我们提供了按照用户希望的方式锁定事物的能力，这提供了一种独特的价值主张，我们将这种价值主张带到了 NSX-T 的桌面上，”Dul 补充道。

根据用户需求，VMware 将通过开源项目为发行版添加更多功能，如急需的安全组件，如存储和分发 Docker 映像的容器注册服务器 [Harbor](https://github.com/vmware/harbor) 。它具有许多企业级特性，例如，与身份管理系统的集成。它还带来了漏洞扫描功能，因此可以限制未签名图像的使用。并不是所有的发行版都包含这样一个组件，并且可能依赖合作伙伴来提供这个功能。

PKS 不能打包用户可能需要的每一项功能。例如，Harbor 不提供运行时检测，但 VMware 的产品组合中确实有提供这种保护的产品。VMware 为 PKS 提供 it 各种工具的定制集成，包括 [vRealize Automation](https://www.vmware.com/products/vrealize-automation.html) 、 [vRealize Operations](https://docs.vmware.com/en/vRealize-Operations-Manager/index.html) 、vRealize Login 等等。VMware 在这方面带来的价值是，PKS 可以轻松地与 VMware 市场上可用的工具集成。

## PKS 有多香草？

凭借所有这些新增功能以及与 VMware 产品的紧密集成，说 PKS 是 Kubernetes 发行版是否公平？如果是的话，它离纯粹的库伯内特斯有多远？

虽然 VMware 提供了与 vSphere 和其他 VMware 产品的紧密集成，但事实是 PKS 是纯粹的香草 Kubernetes。“我们不像其他一些公司那样，将自己的 CLI 或界面放在它的上面。这几乎不是 Kubernetes，这是普通的香草 Kubernetes，”杜尔说。

作为一个普通的分销渠道，PKS 必须找到其他的差异化途径。这取决于对这些 VMware 工具、功能和集成的访问，它们提供了可移植性和兼容性。

“当我们考虑竞争优势时，我会说有一些，而 NSX-T 是最强的竞争优势之一，它为同一网络内的两个虚拟机之间的流量提供东西向微分段。在提供自我修复能力方面，BOSH 也是一个强大的优势。但是能够与 VMware 工具集成是一项关键优势，”Dul 说。

## 专为多重云设计

PKS 不仅仅是 vSphere 解决方案。它旨在成为多种云。“PKS 的初始版本支持 vSphere 和谷歌计算平台，”Dul 证实。“但随着时间的推移，我们还会推出其他平台。”

由于 CFCR 是多平台的，它可以在 AWS、Azure 和 OpenStack 上运行。预计随着时间的推移，PKS 将为所有这些平台提供支持。“我们的大部分工具都是多云产品，因此我们的大部分大型企业客户将通过一个非常干净的集成堆栈获得它们，”Dul 说。

有人可能会认为 PKS 与 Pivotal Cloud Foundry 有关联。事实并非如此，PKS 是独立运行的。

事实上，PCF 本身最近经历了一些重大变化，改变了术语。随着 PCF 2.0 的推出，PCF 本身也成为了一个伞形品牌，旗下有 3 个核心组件:PAS ( [Pivotal 应用服务](https://pivotal.io/platform/pivotal-application-service)，曾经是 PCF)；PFS([Pivotal Function Service](https://pivotal.io/platform/pivotal-function-service)，稍后发布)和 PKS。

现在，客户可以独立于 PAS(以前的 PCF)部署 PKS。但是，如果他们选择使用 PAS 部署它，他们将能够利用 PAS 控制面板。现有 PCF/PAS 客户可以将 PKS 部署为 PAS 部署的一部分，但新客户可以独立于 PAS 部署 PKS。

客户真正想要的是应用程序的可移植性。“有几种方法可以潜在地提供应用程序的可移植性。Kubernetes 的整个概念是围绕着应用程序的可移植性，并拥有一套跨多个云运行的 API 和通用编排层，”Dul 说。

VMware 在 PKS 做的事情之一就是他们所说的“持续兼容性”它始终兼容最新发布的谷歌 Kubernetes 引擎(GKE)和最新发布的上游 Kubernetes。

“无论你在哪里有 Kubernetes，它可能是 GKE 或任何其他服务，你可以选择你的应用程序并进入它。还有其他东西，如数据等，可能会导致可移植性的挑战，但就与应用程序架构、容器编排和容器框架完全兼容而言，PKS 的设计方式是用户可以无缝地获取东西，并具有那种水平的可移植性，”杜尔说。

Kubernetes 发展非常迅速，新的版本不断出现。CNCF 认证 PKS 与 Kubernetes 1.8 兼容。为了减少客户的延迟，Dul 表示，PKS 的目标是在 30 天内为最新发布的 Kubernetes 提供支持

与 Kubernetes 保持同步可确保 PKS 与 GKE 等普通的 Kubernetes 解决方案完全兼容，这样客户就能保证移动性并获得更多服务。

“无论哪里有 vanilla Kubernetes，无论是托管服务还是由客户部署和管理的另一个发行版，只要它在 Kubernetes 上，它都将是相同的。这是 PKS 价值主张的一部分，”杜尔说。

与 GKE 的兼容性也使 PKS 的客户能够访问谷歌计算平台上的服务。您可以在本地部署 PKS，同时使用机器学习等 GCP 服务。

是很多世界里最好的！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>