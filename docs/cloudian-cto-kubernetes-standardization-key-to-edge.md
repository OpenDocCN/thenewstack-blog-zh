# Cloudian CTO: Kubernetes，标准化是 Edge 的关键

> 原文：<https://thenewstack.io/cloudian-cto-kubernetes-standardization-key-to-edge/>

在过去十年的大部分时间里，IT 界的话题一直围绕着云，包括有多少数据以及哪些应用程序应该驻留在云上。然而，最近几年边缘技术的崛起已经改变了许多 IT 供应商和企业的想法，挑战他们去弄清楚 [Gary Ogasawara](https://www.linkedin.com/in/garyogasawara/) 所说的“后云”世界。

“现在的情况是，每个人都认识到，绝大多数数据都是在边缘产生的，比如自动驾驶汽车、物联网传感器等。”基于对象的存储系统供应商 Cloudian 的首席技术官 Ogasawara 告诉新堆栈。“超大规模正在从云向外移动到边缘，然后有很多从边缘向内到云的开发，尤其是硬件供应商。”

开源技术将是将云原生产品带到边缘的关键，与云环境相比，组织和开发人员能够利用更高的灵活性、更快的应用开发周期和更少的供应商锁定。[云原生计算基金会](https://cncf.io/?utm_content=inline-mention) (CNCF)已经帮助企业在私有、公共和混合云环境中采用云原生技术。

## **边缘需要标准化**

然而，硬件和软件标准化对于任何开源项目的成功都是至关重要的，目前的优势是高度分裂的，像亚马逊网络服务(AWS)、微软 Azure(T10)和谷歌云(Google Cloud)这样的公司使用不同的标准，实现有限的互操作性，Ogasawara 说。

他说, [Kubernetes 将在为云原生技术走向边缘铺平道路的过程中发挥核心作用，但即使是开源容器平台——其开发由 CNCF 管理——也面临挑战。](https://thenewstack.io/why-developers-should-learn-kubernetes/)

“我们自己一直在努力移动 Kubernetes，让它为边缘服务，”他说。“在 Cloudian，我们正在研究它的存储方面，因此它实际上是边缘基础架构的一部分。这给我们带来了一些挑战，我们看到了优势。”

随着边缘创建的数据量增加以及对人工智能(AI)、分析和自动化的需求增长，边缘将成为 IT 领域越来越重要的一部分-凳子的第三条腿，还包括内部数据中心和云。IDC 分析师预测，到 2023 年，[超过一半的新 IT 基础设施将部署在边缘。Gartner 预测，到 2025 年，](https://blogs.idc.com/2020/06/01/edge-computing-not-all-edges-are-created-equal/) [75%的企业生成数据](https://www.gartner.com/smarterwithgartner/what-edge-computing-means-for-infrastructure-and-operations-leaders)将在中央数据中心或云之外创建和处理。

## **延伸到云端之外**

云提供商和软硬件制造商争相将其产品和服务延伸到边缘领域。例如， [AWS 的 Greengrass 软件](https://thenewstack.io/how-aws-iot-greengrass-brings-cloud-capabilities-to-the-edge/)为边缘设备带来了云功能，如收集和分析数据。Azure 提供其专注于边缘的 Azure Stack Edge 硬件即服务和 Azure IoT Edge，这是 Azure IoT Hub 上的一项完全托管的服务。谷歌云物联网包括一系列工具，用于在边缘和云中连接、处理、存储和分析数据。

更传统的硬件和组件制造商也在为自己定位。英伟达试图以 400 亿美元收购低功耗芯片设计师 [Arm 就是一个例子。与此同时，戴尔、惠普企业和其他公司正在努力提供体积更小、坚固耐用的系统，以适应石油钻塔、制造车间和零售店等场所。](https://thenewstack.io/nvidias-planned-acquisition-of-arm-portends-radical-data-center-changes/)

Ogasawara 说:“有一些标准化工作，如英特尔的 MECA[模块化边缘计算架构]和 Linux 基金会的一些标准化工作，Linux 基金会有一个名为[Linux Foundation Edge](https://www.linuxfoundation.org/press-release/the-linux-foundation-launches-new-lf-edge-to-establish-a-unified-open-source-framework-for-the-edge/)的专门小组，专注于如何实现边缘硬件方面的标准化。

## **独特的优势**

边缘的独特性——来自远程位置和较小的环境——对试图将其硬件和软件转移到那里的供应商提出了挑战。他说，例如，在存储领域，软件需要有弹性，这是 Cloudian 工程师通过其可扩展软件和其他产品努力确保的。他补充说，相比之下，AWS 将其 S3 对象存储服务转移到边缘可能会更困难，因为它不是为这样的环境构建的。

API 需要在边缘以及云和数据中心工作，软件需要满足自动驾驶等工作在边缘的实时决策需求。

Ogasawara 说:“确保软件和 API 能够对实时问题做出响应是 edge 独有的另一个挑战。”“如果它不需要实时，那么我们可以慢慢来，去和云对话，然后再回来。但这是另一种独特的优势。”

他说，Kubernetes 为包括 edge 在内的混合环境带来了一系列好处。软件可以开发一次，并在任何地方运行，这意味着“软件开发人员可以编写一个应用程序，并让它在 Kubernetes 中工作，然后将在边缘工作的相同应用程序移动到数据中心，或者他们也可以移动到云中。这种灵活性非常强大，使软件开发过程非常高效，”他说。

## **Kubernetes 是关键**

作为操作系统之上的覆盖层，Kubernetes 可以运行在不同的操作系统之上，并利用任何可用的硬件资源，从具有 20 个内核和 256GB 内存的大型服务器到具有两个内核和 4GB 内存的边缘系统。组织还可以利用 [Kube-Scheduler](https://kubernetes.io/docs/concepts/scheduling-eviction/kube-scheduler/) 将工作映射到可用资源。调度程序还允许企业适当调整其环境，仅使用他们需要的资源，并根据需要进行扩展或缩减。

“这在经济上给了用户很多优势，”CTO 说。“这就是为什么这在现阶段非常重要，因为软件开发人员正在寻求构建跨边缘、数据中心和云这三层运行的应用。”

也就是说，Kubernetes 面临着挑战，它正在解决一个高度复杂的问题。compute 使用各种 API，例如用于传输数据的数据 API，这些 API 可以标准化，使开发人员和基础设施供应商能够编写相同的 API。更困难的部分是控制 API，它处理诸如定位和调度软件或指定网络选项之类的问题。

Ogasawara 说，软件平台项目在过去失败过，OpenStack 就是一个典型的例子。

他说:“这不是添加越来越多的组件和开放越来越多的功能的问题。“那就是 OpenStack 的死亡。你所需要的就像 Linux 是如何被一个非常强大的仲裁者控制着，决定什么应该进出。你需要在如何建立网络和公开什么方面做出某些设计选择，这可能不是所有可能情况下的最佳选择，但总体来说是保持一个更简单或更通用的框架供所有人使用的最佳选择。”

## **小心巴尔干化**

Kubernetes 也正在分裂，不同的供应商有自己的风格。想到[红帽带 OpenShift](https://thenewstack.io/red-hat-openshift-4-8-adds-serverless-functions-pipelines-as-code/) 、[谷歌带 Anthos](https://thenewstack.io/google-anthos-from-the-eyes-of-a-kubernetes-developer/) 、 [VMware 的 Tanzu](https://tanzu.vmware.com?utm_content=inline-mention) 和 [SUSE Rancher](https://thenewstack.io/how-rancher-will-help-give-suse-the-edge/) 以及[轻量级 K3s 发行](https://thenewstack.io/ranchers-k3s-joins-cncf-sandbox-as-first-kubernetes-distribution/)。Ogasawara 说，这些不同的产品仍然必须实现 Kubernetes API 的重要部分。

“随着需求的变化，Kubernetes 的不同口味会有这些差异，然后你会遇到同样的问题，”他说。“然后你被锁定在 OpenShift 或 Google Anthos 上，除了这些供应商，没有人想要这样。每个人都知道 API 优先是一个好策略，所以让每个人都拥有相同的控制 API 是一件非常积极的事情。它只是促进了开发，让每个人都能使用它。”

开发人员还必须处理试图简化 Kubernetes 方面的 CNCF，这可能导致细节的丢失。他们从在典型环境中创建软件转移到 Kubernetes，有时没有他们在 Linux 中习惯的细粒度控制，例如查看 [strace](https://strace.io/) 调用和系统调用。有了 Kubernetes，大部分内容都被有意地抽象出来，使之更适合 edge 这样的环境。

所有这些挑战正是 CNCF 的用武之地。该组织在确保不同的 Kubernetes 平台遵守某些通用规范方面做得很好——其认证测试套件对所有 Kubernetes 口味进行了测试，以此作为范例——以应对持续的割据挑战。此外，该集团不允许自己被一个单一的供应商所控制。

他们在会议和决策过程中小心翼翼地做到这一点。小笠原说:“他们从过去和现在的经历中受益匪浅。“但这是一个持续的挑战，因为这是一个连续性和保持这一点的问题。随着越来越多的人开始使用 Kubernetes，保持这种类型的控制将越来越难，因为随着越来越多的人希望使用它，他们希望以不同的方式使用它。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>