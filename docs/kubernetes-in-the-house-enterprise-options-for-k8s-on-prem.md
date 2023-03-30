# kubernetes in the House:K8s 内部部署的企业选项

> 原文：<https://thenewstack.io/kubernetes-in-the-house-enterprise-options-for-k8s-on-prem/>

这篇文章是关于在内部使用 Kubernetes 的两部分系列文章的第一部分。下周回来查看第二期。

吐温·泰勒

吐温·泰勒在谷歌开始了他的职业生涯，在那里他为 AdWords 团队提供技术支持。后来，他构建了品牌社交媒体应用程序和自动化脚本，帮助初创公司更好地管理营销运营。今天，他阐述了 DevOps 团队如何改变他们构建和发布应用程序的方式。离开电脑时，他会弹贝斯吉他，或者找个借口骑着摩托车离开。

当您考虑在本地部署 Kubernetes 时，通常首先想到的是“在 AWS 上部署 Kubernetes 已经够难的了，为什么还要在本地部署呢？”事实上，组织寻求在内部部署 [Kubernetes](/category/kubernetes/) 的原因有很多，其中最常见的是合规性，即处理患者记录或信用卡信息等敏感信息的组织有政府限制，阻止他们使用公共云。

其他原因可能包括组织希望获得云计算的基本优势，如可扩展性、按需服务、敏捷性和弹性，而不损害隐私或依赖云供应商提供这些服务。这种方法也有助于未来的云兼容性，因为它大大简化了向云的迁移过程，以防组织希望在未来走这条路。此外，这种设置对于使用混合策略将一些数据保存在现场的组织也是有益的。

## 云复杂性

为了成功部署全功能的 Kubernetes 集群并在内部实现类似云的体验，我们需要能够处理托管服务竭力向我们隐瞒的所有复杂性。这些包括但不限于部署自动化、SDN 管理、存储管理、负载平衡、安全性和身份验证。对于内部部署，记住您对“一切”负责也很重要，因为没有可依赖的云弹性。

Kubernetes 面临的挑战是，一开始很难设置和配置，并且随着您的进展会变得越来越复杂。这可能就是为什么除了像谷歌、网飞和脸书这样的全球 IT 巨头，或者拥有非常大的 IT 部门的组织，组织更喜欢寻求“企业就绪”的 Kubernetes 解决方案。这是因为这需要大量的工作，需要一个熟练的专门团队来开发和维护内部的云原生架构。

## 房子里有 k8

虽然 Kubernetes 的范围相当广泛，但我们可以或多或少地将在本地运行 Kubernetes 的可用解决方案分为三个或四个基本类别。第一个是 PaaS 解决方案，已经被修改或重写以与 Kubernetes 一起工作，因此，使用一种相当固执己见的方法来管理 Kubernetes 层，通常使用预先确定的应用程序生命周期管理工具包。第二类是可以在内部部署的 Kubernetes 发行版。这些解决方案侧重于 Kubernetes 层，而不是应用程序生命周期。

其他可用的选项包括一类工具，它们不完全是 PaaS，而是可以归类为 Kubernetes 的“聚合器”，因为它们通过在 Kubernetes 之上提供各种服务来扩展 Kubernetes 的功能。这些服务的范围可以从更复杂的操作(如管理和监控)到简单的功能(如在集群上构建一个可观察层)。此外，我们还将深入了解内部部署的云托管 Kubernetes 解决方案。

## PaaS 方法

虽然这种方法的优点是很多人已经熟悉这些平台，并且它有助于避免与 Kubernetes 相关的陡峭的学习曲线，但缺点是这些平台不是 Kubernetes 本地的。这主要是因为它们在 Kubernetes 成为国王之前就已经存在了，因此必须重新整合。

Red Hat OpenShift 是一个非常受欢迎的选择，也是 PaaS 重新整合 Kubernetes 的一个很好的例子。最初是为了使用 Heroku 来部署容器，然后经过改造以适应 Docker，然后是 Kubernetes，红帽将其称为混合云，企业 Kubernetes 平台。特别是对于混合云部署，OpenShift 尤其具有吸引力，因为它为网络、负载平衡和服务网格提供了多种选择，包括对 Istio 的支持。

[VMware 企业 PKS](https://cloud.vmware.com/vmware-enterprise-pks) 是这一类别的下一个有力竞争者，不言而喻，如果您已经使用了 VMware，这可能是您的第一选择。PKS 建立在 Cloud Foundry 的名为 Kubo 的容器运行时之上，基本上在 BOSH 上运行 Kubernetes。不像 OpenShift 在云和本地数据中心之间有一个更平衡的方法，PKS 更倾向于后者。除了高可用性数据中心托管和内部虚拟化，PKS 还在其公共云产品和内部混合平台之间提供了大量工具和集成。

## “Kube-Native”方法

原生 Kubernetes 发行版可能是最接近普通 Kubernetes 本地实现的版本，这也是强烈推荐这种方法的原因。这些平台不仅允许您在多个环境中部署 Kubernetes，还为您提供了一个单一的“类似云”的控制平面来管理您的集群。这里的额外优势是，这些平台都不需要与 Kubernetes 集成或“合并”,因此在内部实现 Kubernetes 时绝对不会损失任何性能。

[Rancher 2.0](https://rancher.com/products/rancher/) 是适合几个类别的选项之一，因为它最初是一个容器编排和管理工具，后来被完全重构以采用 Kubernetes。虽然它是以开发为中心的 Kubernetes 平台的一个很好的例子，但它也非常关注应用程序管理。与有付费版本的 OpenShift 和更像是专有产品的 PKS 不同，Rancher 是 100%开源的，采用完全独立于供应商的方法。Rancher 还使用自己的操作系统 RancherOS 来运行容器内的所有服务。

Kublr 是另一个有趣的开源 Kubernetes 发行版，它只关注 Kubernetes 层。 [Kublr](https://kublr.com/) 获得了[云本地计算基金会](https://www.cncf.io/)(管理 Kubernetes 代码库)的认证，除了支持几乎任何环境之外，它还提供了一系列企业功能，如集中式多集群管理、集中式日志记录和监控，甚至自我修复节点。此外，Kublr 支持气隙部署，集成 RBAC 和 IdM/AAA 系统作为标准功能。它还附带了基础设施供应和管理功能，可以跨环境使用，也可以与 Azure ARM 或 Cloudformation 等云提供商工具结合使用。

Canonical 的目标是成为 Kubernetes，就像它的 Ubuntu 发行版对于 Linux 一样，它似乎走在了正确的道路上。如果你正在寻找一个简单、实用、普通的上游 Kubernetes，它已经在云、本地数据中心、裸机和虚拟机上经过了测试，[Kubernetes](https://ubuntu.com/kubernetes)(CDK)的规范发行版是一个非常有吸引力的选择。因为它部署在很多人都熟悉的 Ubuntu Linux 上，所以更是如此。虽然 CDK 声称支持任何云或内部部署，但它也有一个名为 Microk8s 的迷你版本，可以安装在笔记本上。

总之，虽然许多组织无疑认为采用 PaaS 方法在内部部署 Kubernetes 是安全的，但它确实比本地 Kubernetes 方法涉及更多的移动部件。更多的移动部件不仅会增加安全风险，还会增加环境的总体复杂性。纯 Kubernetes 方法也更加灵活，允许团队使用他们选择的工具，同时也保持与未来发展的更好兼容性。

在下一篇文章中，我们将探讨一些在本地部署 Kubernetes 的最佳实践，以及一些目前在本地可用的最新云“托管”解决方案。

*本帖作者曾与 Rancher 和 Kublr 做过咨询工作。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>