# MicroK8s 如何帮助部署到物联网

> 原文：<https://thenewstack.io/how-microk8s-helps-deployment-to-the-internet-of-things/>

[](https://twitter.com/microk8s1)

 [阿马尔·纳克维

阿马尔·纳克维是 Ubuntu 的出版商 Canonical 的 MicroK8s 产品经理。在加入 Canonical 之前，Ammar 曾在微软、Zoom 和诺基亚担任产品管理职务。Ammar 也是一家区块链创业公司的顾问和产品学校的老师。他拥有计算机科学硕士学位和 MBA 学位。](https://twitter.com/microk8s1) [](https://twitter.com/microk8s1)

Gartner [预测](https://www.gartner.com/en/newsroom/press-releases/2019-08-29-gartner-says-5-8-billion-enterprise-and-automotive-io)到 2020 年，物联网(IoT)将增长到 58 亿个企业和汽车终端，比今年增长 21%。显然，物联网正在从未来的宣传转向现实世界的运营。

然而，房间里的一头大象总是笼罩着物联网项目:开发、管理和更新物联网应用程序的复杂性。物联网有多种基础设施考虑因素:如何从不同的设备和传感器收集数据，通过各种网络传输数据，在云中处理数据，并与现有的后端系统集成。

这种复杂性常常被组织低估，可能会延迟物联网项目，因为开发人员会陷入处理底层基础设施的困境，而不是构建具有商业价值的应用程序。

一个很好的解决办法是集装箱化，它在最近几年席卷了 IT 界。通过将应用程序与其运行的计算、存储和网络环境分离，容器化使开发团队能够快速、高效、大规模地部署软件，并且可以在任何地方部署，无论是在私有数据中心、公共云、edge 还是单台笔记本电脑。

将物联网设备视为分布式容器化应用程序可以创造奇迹，让开发人员专注于应用程序而不是基础设施，并让面临物联网配置和更新任务漩涡的运营团队的生活更加轻松。

众所周知， [Kubernetes](https://kubernetes.io/) 作为基于容器的应用程序的头号编排平台，已经迅速走红，自动化了这些应用程序的部署和扩展，并简化了维护工作。然而，Kubernetes 也有自己的复杂性挑战。简单来说，用起来远不简单。

那么，企业如何利用容器化来解决物联网的复杂性，而不会最终遭遇 Kubernetes 带来的更多复杂性难题呢？

MicroK8s 是一个强大的、经过云计算原生计算基金会认证的 Kubernetes [发行版](https://www.cncf.io/certification/software-conformance/)，它为物联网带来了巧妙的技巧。MicroK8s 是一个单一的 Kubernetes 包，具有较小的磁盘和内存占用量，最初是为了在部署到云之前在桌面上进行 Kubernetes 应用程序的离线开发、原型制作和测试而构建的。然而，它已经成为一个强大的企业工具，并作为一个边缘计算平台成长起来。

MicroK8s 在边缘的设施的一个原因是它能够作为类似容器的[snap](https://snapcraft.io/)——用于桌面、云和物联网的应用程序包，易于安装并通过自动更新保护——并安装在 42 个支持 snap 的 Linux 发行版中的任何一个上。这使得 MicroK8s 非常适合在组成物联网的各种硬件上运行。它甚至可以安装在一个 Raspberry Pi 上，使开发人员能够使用一个低成本的主板，该主板足够强大，可以在边缘使用 MicroK8s 协调工作负载。

对于具有少量服务器的边缘云，MicroK8s 允许您将 Kubernetes 安装集群在一起，以便它们可以形成单个集群，并将工作负载放置在一个或多个节点上。本质上，这意味着您可以将云分解为迷你云，并将它们分布在任何地方，以处理和管理物联网数据。

第二个原因是 MicroK8s 中为边缘计算设计的新功能，称为严格限制。这确保了与底层操作系统的完全隔离和一个紧密安全的生产级 Kubernetes 环境，所有这些都在一个非常适合边缘网关的小空间内。因此，现在只需一个命令，不到一分钟就可以在边缘安全地部署 MicroK8s 插件。

第三个原因是 MicroK8s 配备了强大的生产级附加软件，如 [Istio](https://istio.io/) 、 [Knative](https://cloud.google.com/knative/) 、 [CoreDNS](https://coredns.io/) 、 [Prometheus](https://prometheus.io/) 、 [Jaeger](https://www.jaegertracing.io/) 、 [Linkerd](https://linkerd.io/) 、 [Cilium](https://cilium.io/) 和 [Helm](https://helm.sh/docs/) ，这些附加软件设置起来很简单，只需几行命令。这些附加组件使 MicroK8s 成为一个完整的小型企业 Kubernetes 包。

此外， [Kubeflow](https://www.kubeflow.org/) 可作为 MicroK8s 的附加产品，用于改进人工智能(AI)和机器学习(ML)能力。这很重要，因为需要人工智能和人工智能模型来帮助管理物联网设备，并从所有这些端点涌入的数据中获得洞察力。

通过 MicroK8s，开发者可以快速设置、开发、测试、部署和扩展 AI 和 ML 应用。

凭借其提高 Kubernetes 生产力和降低复杂性的能力，MicroK8s 是加速物联网和边缘部署的独特有趣的技术。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>