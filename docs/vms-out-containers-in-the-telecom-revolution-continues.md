# 虚拟机退出，容器进入:电信革命仍在继续

> 原文：<https://thenewstack.io/vms-out-containers-in-the-telecom-revolution-continues/>

长期以来，电信领域的创新轨迹被认为是渐进式的，而非革命性的。

 [穆尔利·蒂鲁马勒

Murli 是 Pure Storage 的云原生业务部门 Portworx 的总经理，负责为 Kubernetes 提供多云数据服务的战略、运营和解决方案。他拥有西北大学凯洛格管理研究生院的 MBA 学位，是 F.C .奥斯汀杰出学者。](https://www.linkedin.com/in/murlithirumale/) 

从 1914 年最早的海岸到海岸的通话开始，到接下来的 60 年，从基础设施的角度来看，变化并不大。随着光纤技术的引入，以及最近网络功能虚拟化(NFV)的出现，这一步伐加快了。网络功能虚拟化旨在将在专用硬件上运行的网络功能转移到虚拟机(VM)上。

现在，5G 服务的推出给运营商带来了巨大转型的挑战和机遇。

新的服务产品将有可能开辟全新的业务领域。挑战将是满足这种需求，并灵活地快速推出新服务，以超越竞争对手。拥有合适的基础设施将是电信从“管道”转向“平台”的关键推动因素，有助于为成为创新、数据驱动服务的首选平台奠定基础。

虽然虚拟化仍然是 5G 部署的重要组成部分，但对于这一新挑战，云原生和容器是一种革命性的方式。

## **虚拟机时代**

NFV 过去和现在都是一个变革性的想法:本质上，任何可以在专用机器上完成的事情，也可以通过商用数据中心套件(服务器、存储和网络设备)上的虚拟机来完成。

由于 VMware 和其他虚拟机管理程序的兴起，NFV 的潜在优势包括降低成本和功耗、轻松共享资源和快速扩展或缩减服务的能力，以及硬件便携性。

所有这些都有助于电信提供商建设新的 5G 网络。但是，为在太大而无法手动运行的网络上有效完成一件事情而设计的专用设备仍然存在挑战，包括性能、迁移和共存、管理和自动化，当然还有安全性和弹性。

并非所有这些挑战都与存储相关，许多挑战正在解决中。运营商继续将更多 5G 功能转移到虚拟化网络功能(VNFs)中，但网络部署需要时间，并且仍在进行中。

作为这一转型的一部分，他们需要高性能、可靠的基础架构，而不是专门构建的。但是“商品硬件”并不意味着“都一样”。它是指支持开放标准的硬件。事实上，存储供应商之间非常真实的差异对于 NFV 项目的成败至关重要。电信公司应该寻找满足他们对可靠性、性能、自动化和效率的关键要求的存储解决方案。

## **云原生未来**

虽然虚拟化网络功能(vnf)目前正在改变电信行业，但该行业正在通过云原生网络功能(CNF)向前迈出又一步。

CNF 使用容器，这就是为什么您有时会看到 CNF 被称为容器化的网络功能。在 Pure，我们更喜欢云原生网络功能这一术语，因为云原生并不真正涉及应用程序部署的位置；关键是如何部署。云原生应用可以在数据中心、公共云中或任何其他地方的裸机上运行。正如 VNFs 为电信运营商提供了许多好处一样，CNFs 整合了所有这些好处，甚至更多。

CNFs 有助于解决使用虚拟化和 VNFs 时仍然存在的一些挑战。CNFs 优惠:

*   **自动伸缩** —容器可以不费吹灰之力产生更多的自己。每当某个进程需要一个新容器时，您可以旋转它，当它完成时，旋转它。Kubernetes 只是通过代码来处理这一切，所以不需要操作员干预。对于大型电信网络来说，这是一个巨大的胜利。
*   **支持 DevOps** — DevOps 彻底改变了编程，允许持续集成/持续交付(CI/CD)。这意味着运营商可以更快地提供新功能、产品和产品更新。
*   **难以置信的容错和快速重启** — CNFs 基于微服务，可以大大降低大规模故障的运营和安全风险。容器几乎可以立即重启，并且可以在不停机的情况下执行升级，允许在需要时自动快速回滚。如果一个容器出现故障，系统会自动生成一个新容器。
*   **监控和报告** —鉴于电信网络的规模，它们高度依赖于良好的监控和报告。幸运的是，从 Kubernetes 本身开始，Kubernetes 世界中有许多工具可以做到这一点。其他工具包括用于监控的 Prometheus 和用于报告和警报的 Grafana。

迁移到 CNFs 有很多好处，但是尽管应用程序开发人员喜欢 Kubernetes 和 containers，但它们对不习惯它们的基础设施团队来说是一个挑战。

需要的数据管理任务范围很广:容量管理、数据备份、灾难恢复、安全性、数据迁移等等。传统方法不起作用，因为这种方法不是容器感知的(例如，传统备份工具将无法成功地重建容器环境)。需要一个容器本地解决方案来为基于容器的应用程序提供这些预期的企业数据服务。

## 您的基础架构团队准备好应对这一转变了吗？

KPN 是荷兰最大的电信公司之一，也是我们 Portworx 部门的客户，对于它来说，最佳平台是一个能够实现两个世界最佳效果的平台:简化和优化流程的软件，同时留出足够的空间来配置和优化各个集群，以满足您自己客户的特定需求。

在与不同行业的决策者交谈时，这是一个优势。无论是服务于物流客户、医疗保健还是运输，当涉及到他们的信息系统的性能时，每个人都说相同的语言。

对于电信行业来说，前方的路通向云。CNF 是升级运营商网络的下一步——为运营商创新铺平道路，这也使他们的客户生活更轻松，每个人的业务更有弹性，更成功。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>