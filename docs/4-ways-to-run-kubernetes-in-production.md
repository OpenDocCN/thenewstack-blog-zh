# 在生产中运行 Kubernetes 的 4 种方法

> 原文：<https://thenewstack.io/4-ways-to-run-kubernetes-in-production/>

Kubernetes 在生产环境中部署为[容器编排引擎](https://thenewstack.io/what-is-container-orchestration/)、平台即服务(PaaS)以及管理云原生应用的核心基础设施。这些用例并不相互排斥。

运营商可以将完整的应用生命周期管理(ALM)委托给基于 Kubernetes 的 PaaS 层。他们还可以使用独立的 Kubernetes 部署来管理使用现有 CI/CD 工具链部署的应用程序。

构建绿地应用的客户可以利用 Kubernetes，通过滚动升级和金丝雀部署等高级场景来管理新一代基于微服务的云原生应用。

评估 Kubernetes 或将其用于生产部署的客户可以从各种发行版和风格中进行选择。

以下是市场上可用的主流 Kubernetes 发行版列表:

## 上游分布

GitHub 中可用的 [Kubernetes 的上游开源发行版可以部署在数据中心、公共云和私有云环境中。代码库包括在 Kubernetes 上运行工作负载所需的核心构建块和基本元素。](https://github.com/kubernetes/kubernetes)

Kubernetes 附带了一个名为 kubeadm 的部署工具，它为基于 [CentOS](https://github.com/CentOS) 、 [Red Hat Enterprise Linux](https://github.com/RedHatOfficial) 、 [SUSE](https://github.com/SUSE) 、 [Ubuntu](https://github.com/ubuntu) 和其他 Linux 发行版配置集群提供了简单的安装体验。

客户还可以使用自动化部署工具，如 [kops](https://github.com/kubernetes/kops) 、 [kubespray](https://github.com/kubernetes-sigs/kubespray) 和[Rancher Kubernetes Engine](https://github.com/rancher/rke)来安装和配置集群。这些工具为配置容器运行时、网络和存储插件提供了从基础到高级的定制。

上游发行版是免费的、透明的和完全可配置的安装 Kubernetes 的方法。然而，它要求计划使用 Kubernetes 的个人和组织具备高水平的专业知识和技能。

## 商业发行

一些供应商提供定制和优化的 Kubernetes，捆绑了专业服务和支持。他们遵循一种通过服务将开源软件商业化的成熟模式。

商业发行版不仅加速了 Kubernetes 集群的配置和部署，还承诺提供补丁、热修复和无缝升级到平台的新版本。

Canonical 、 [D2iQ](https://d2iq.com/solutions/ksphere) 、 [HPE](https://www.hpe.com/us/en/newsroom/press-release/2019/11/Hewlett-Packard-Enterprise-introduces-Kubernetes-based-platform-for-bare-metal-and-edge-to-cloud-deployments.html) 、[米兰蒂斯](https://www.mirantis.com/software/mcp/kubernetes/)、 [Rancher](https://rancher.com/) 和 [VMware](https://tanzu.vmware.com/kubernetes-grid) 是提供商业 Kubernetes 发行版的一些供应商。

## 容器即服务

Kubernetes 也可以以完全托管、管理平台的形式提供。无论是企业数据中心、协同定位的基础设施还是公共云环境，提供容器即服务(CaaS)的供应商都承诺提供由商业服务级别协议(SLA)支持的端到端 Kubernetes 环境。

几乎所有主要的云提供商现在都有 CaaS 产品。[阿里巴巴 Kubernetes 容器服务](https://www.alibabacloud.com/product/kubernetes)、[亚马逊 EKS](https://aws.amazon.com/eks/) 、 [Azure AKS](https://azure.microsoft.com/en-us/services/kubernetes-service/) 、[数字海洋 Kubernetes](https://www.digitalocean.com/products/kubernetes/) 、[谷歌 Kubernetes 引擎](https://cloud.google.com/kubernetes-engine)、[华为云容器引擎](https://www.huaweicloud.com/en-us/product/cce.html)和 [IBM Kubernetes 服务](https://www.ibm.com/cloud/container-service/)都是公有云中 CAA 的例子。

[Mirantis](https://www.mirantis.com/software/mcp/kubernetes/) 、 [NetApp](https://cloud.netapp.com/project-astra) 和 [Platform 9](https://platform9.com/managed-kubernetes/) 为数据中心和私有云环境提供 CaaS。

## 平台即服务

客户部署 PaaS 主要是为了标准化他们的开发和部署环境。通过使用基于 Kubernetes 的 PaaS，他们将能够开发传统的行业应用程序和绿地应用程序。Kubernetes 已被传统的 PaaS 供应商采用，以向企业客户提供端到端的平台功能。

基于 Kubernetes 的 PaaS 产品建立在核心容器编排功能之上，为容器化的应用程序提供完整的生命周期管理。

[Red Hat OpenShift](http://red.ht/2uJGuQo) 和[VMware Tanzu Kubernetes Grid](https://tanzu.vmware.com/kubernetes-grid)就是基于 Kubernetes 的 PaaS 产品的例子。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>