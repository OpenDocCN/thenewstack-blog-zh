# 2022 年值得关注的 5 大云趋势

> 原文：<https://thenewstack.io/5-cloud-native-trends-to-watch-out-for-in-2022/>

在过去几年中，业界见证了[云原生技术](https://thenewstack.io/category/cloud-native/)的采用呈指数级增长。由[容器](https://thenewstack.io/category/containers/)和 [Kubernetes](https://thenewstack.io/category/kubernetes/) 引领的应用程序现代化成为许多企业的一致主题。[基于容器的 CI/CD](https://thenewstack.io/category/ci-cd/) 是创业公司和企业事实上的 [DevOps](https://thenewstack.io/category/devops/) 标准。Kubernetes 是在[边缘](https://thenewstack.io/category/edge-iot/)运行工作负载的首选平台。它还转变为一个混合计算平台，使公共云提供商能够在本地环境中部署的集群中运行他们的[托管服务](https://thenewstack.io/category/cloud-services/)。

随着我们过渡到 2022 年，这里有五个关键的云原生趋势需要考虑:

### 趋势 WebAssembly 在云原生环境中的崛起

[WebAssembly](https://webassembly.org) 已经发展成为一个面向云原生软件组件的高性能、跨平台、多语言的软件沙盒环境。鉴于容器运行时和 WebAssembly (WASM)之间惊人的相似，Kubernetes 可以用于编排 WASM 组件。

[WasmCloud](https://github.com/wasmCloud/wasmCloud) 、 [WasmEdge](https://github.com/WasmEdge/WasmEdge) 、 [KubeEdge](https://github.com/kubeedge/kubeedge) 、 [Krustlet](https://github.com/krustlet/krustlet) 等项目让 WASM 成为了云原生宇宙的一等公民。可以将打包成 WebAssembly 的软件与容器化的软件一起运行。Kubernetes 可以从一个控制平面无缝地协调这两种工作负载。

包括 [SecondState](https://www.secondstate.io/) 、 [Cosmonic](https://cosmonic.com/) 和 [Suborbital](https://suborbital.dev/) 在内的初创公司正在搭建平台和工具，以加速 WASM 的采用。

期待在 2022 年看到云原生 WASM 的崛起。

### 趋势 Kubernetes 的新分布

虽然云原生生态系统充斥着各种 Kubernetes 发行版，但我们可能会看到这个领域的新参与者。

Kubernetes 有三种版本——开源版本、商业版本和托管版本。

开源发行版包括 plain vanilla，upstream [Kubernetes](https://github.com/kubernetes/kubernetes) ，[亚马逊 EKS-D](https://distro.eks.amazonaws.com) ， [K3s](https://k3s.io) ，以及 [RKE2](https://docs.rke2.io) 。商业发行包括[红帽 OpenShift](https://www.redhat.com/en/technologies/cloud-computing/openshift) 、 [VMware Tanzu](https://tanzu.vmware.com/tanzu) 、 [Rafay](https://rafay.co/) 、 [Mirantis Kubernetes 引擎](https://www.mirantis.com/software/mirantis-kubernetes-engine/)、 [D2iQ Kubernetes 平台](https://d2iq.com/kubernetes-platform)。

公共供应商主要推动托管 Kubernetes 产品。诸如 [Amazon Elastic Kubernetes 服务](https://aws.amazon.com/eks/)、 [Azure Kubernetes 服务](https://azure.microsoft.com/en-in/services/kubernetes-service/#overview)、 [Google Kubernetes 引擎](https://cloud.google.com/kubernetes-engine)、 [IBM Kubernetes 服务](https://www.ibm.com/in-en/cloud/kubernetes-service)、[Oracle Container Engine for Kubernetes](https://www.oracle.com/in/cloud-native/container-engine-kubernetes/)和[platform 9 Managed Kubernetes](https://platform9.com/managed-kubernetes/)等产品都是托管 Kubernetes 发行版的例子。客户不能直接获得这些发行版，只能通过由提供商运营和管理的托管环境获得。

2022 年，我预计谷歌和微软会宣布基于他们的托管产品——GKE 和 AKS——的开源 Kubernetes 发行版。这些发行版将被定位为生产级 Kubernetes 环境，提供与托管服务相同的功能。采用这些发行版的客户将能够轻松地转向基于云的服务或混合托管服务。这有助于他们将其产品定位为 AWS 的 EKS-D 和 EKS-A 的替代品。

除了托管提供商，我们可能会看到针对物联网、边缘和人工智能工作负载专门构建和优化的 Kubernetes 发行版。

### 趋势 3:越来越关注云原生安全性

随着对网络安全的重视，我希望看到开源项目和商业产品直接关注云原生安全性。

两个领域将受到关注——软件供应链和 eBPF。

软件供应链密切模仿真实世界商业的供应链，其中资源被消耗，然后通过一系列步骤和过程被转换，最后被提供给客户。现代软件开发是关于将公共领域中的各种组件作为开源项目进行组装和集成。在复杂的软件供应链中，一个受损的软件会对多个部署造成严重损害。

最近涉及 [CodeCov](https://about.codecov.io/security-update/) 、 [Solarwinds](https://www.solarwinds.com/sa-overview/securityadvisory) 、 [Kaseya](https://helpdesk.kaseya.com/hc/en-gb/articles/4403440684689) 和 [ua-parser-js NPM 包](https://hackaday.com/2021/10/22/supply-chain-attack-npm-library-used-by-facebook-and-others-was-compromised/)的事件凸显了保护软件供应链的必要性。

2022 年，将有新的计划、项目，甚至新的创业公司专注于安全软件供应链管理。

另一个令人兴奋的趋势是 [eBPF](https://ebpf.io) ，它使云原生开发者能够构建安全的网络、服务网格和可观察性组件。

我们已经看到，Isovalent 通过 Cilium 、 [Pixie(被 New Relic 收购)](https://docs.px.dev/about-pixie/pixie-ebpf/)利用它来构建可观察性堆栈、 [Falco](https://falco.org/docs/event-sources/drivers/) 和 [Tracee](https://www.aquasec.com/products/tracee/) 使用 eBPF 来监控和发出安全事件和警报，以及为服务网格引入了[无侧架代理](https://isovalent.com/blog/post/2021-12-08-ebpf-servicemesh)。

期待 eBPF 成为云原生安全性和联网的基础。

### 趋势 4: Kubevirt 成为主流

Kubevirt 是一个开源项目，它使 Kubernetes 能够像容器一样编排虚拟机。通过并行运行虚拟机和容器，客户可以轻松地将传统工作负载与基于微服务的现代应用集成。他们还受益于用于管理两种工作负载的简化开发运维工作流。

Kubevirt 已经是 Red Hat OpenShift Virtualization、T2 Rancher ' s Harvester、T4 platform 9 Managed Kubernetes 和谷歌 Anthos 的重要组成部分。

2022 年，我们将看到 Kubevirt 与 Kubernetes 的采用和集成大幅增加，在 Kubernetes 中，虚拟机被视为一等公民。

### 趋势 5: GitOps 成为持续部署的标准

[GitOps](https://www.gitops.tech) 将熟悉的基于 Git 的工作流引入云原生工作负载的发布管理。通过将 Git 视为真实的单一来源并结合快速回滚的能力来协调状态，使得 GitOps 成为一种强大的机制。

[Weaveworks](https://www.weave.works/?utm_content=inline-mention)'[Flux CD](https://fluxcd.io)、 [ArgoCD](https://argo-cd.readthedocs.io/en/stable/) 、 [Google Anthos 配置管理](https://cloud.google.com/anthos/config-management)和 [Rancher Fleet](https://fleet.rancher.io) 是实现 GitOps 的一些可用选择。

2022 年，GitOps 将发展到支持多租户和多集群部署，从而轻松管理运行在边缘或混合环境中的数万个 Kubernetes 集群。

GitOps 将成为持续部署的黄金标准。

[https://www.youtube.com/embed/0XUIHwIf1Ss?feature=oembed](https://www.youtube.com/embed/0XUIHwIf1Ss?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>