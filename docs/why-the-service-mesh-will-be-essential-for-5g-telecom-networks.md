# 为什么服务网格对 5G 电信网络至关重要

> 原文：<https://thenewstack.io/why-the-service-mesh-will-be-essential-for-5g-telecom-networks/>

[](https://twitter.com/sagarnangare)

[Sagar Nangare](https://twitter.com/sagarnangare)

[Sagar Nangare 是科技博客作者，专注于数据中心技术(网络、电信、云、存储)和边缘计算、物联网、机器学习、人工智能等新兴领域。他目前在浦那担任 Coredge.io 的产品营销总监。](https://twitter.com/sagarnangare)

[](https://twitter.com/sagarnangare)[](https://twitter.com/sagarnangare)

尽管[服务网格](https://thenewstack.io/category/service-mesh/)与其他云原生技术相比是一项相当新的技术，但 2020 年 3 月[云原生计算基金会](https://cncf.io/?utm_content=inline-mention)的一份报告[表明](https://www.cncf.io/wp-content/uploads/2020/11/CNCF_Survey_Report_2020.pdf)42%的受访者正在评估其在云中的使用，27%的受访者正在生产中使用。考虑到微服务和分布式云在企业和电信领域的增长，服务网格将很快在生产中得到广泛应用。服务网格可以解决电信(telecom)和 5G 网络的关键可扩展性挑战，以解决大规模带来的关键挑战。

5G 网络是一个基于软件的网络，其中大多数基础设施元素都被转化为运行在商用现成硬件上的虚拟化软件。 [WIFI 网状网络](https://thenewstack.io/category/service-mesh/)可以使用单一控制台控制资源/设备，为服务交付带来灵活性。此外，云原生技术(containers、Kubernetes)可以与微服务架构一起使用，并通过 DevOps 方法加速虚拟化或容器化的服务和软件组件的交付。

今天的电信网络和即将到来的 5G 网络是基于服务的网络，其中网络运营中心专注于通过网络传递服务。现在，我们有一个服务运营中心(SOC)来管理现代电信网络。

微服务架构与 Kubernetes 一起支持自动化、服务集中管理以及跨所有软件层的端到端生命周期管理和服务编排。这也有助于基础架构随时做好自我扩展和修复的准备。

但是，我们从分布式特性中获得的这些好处也为电信云带来了挑战。这种网络包含来自不同供应商的不同的基于软件的组件和应用、边缘云的分布式部署、不同云环境下的服务性能、服务的可扩展性、大型云网络的集中管理、VM 或容器的服务控制和协调等。面对这样的挑战，电信运营商要满足 SLA 并确保服务的可用性并不容易。

服务网格通过从微服务中抽象出网络组件来控制网络，从而帮助解决这些问题。这使得软件开发者只关注服务的开发，而不是与每项服务相关的网络部分。通过这种方式，服务网格可以使用单个管理网络层来管理大规模的分布式云或边缘。

详细说明:

*   电信和边缘云包含目前使用虚拟机(VM)和少量容器部署的工作负载。服务网格有助于管理容器和虚拟机。
*   使用 sidecar 代理，可以监控虚拟机和容器中部署的每个服务的性能，并控制网络流量。这进一步有助于实现 5G 网络的动态网络切片。
*   服务网格通过启用基于策略的通信和加密在不同服务内移动的数据来提高传输数据的安全性。服务网格使用 [mTLS 协议](https://thenewstack.io/mutual-tls-microservices-encryption-for-service-mesh/)来自动保护云本地应用的通信。服务网格支持微服务之间的[零信任](https://thenewstack.io/zero-trust-security-with-service-mesh/)安全策略，实现从中央数据中心到边缘节点的动态网络策略和端到端授权。
*   使用服务网格获得的控制有助于获得高水平的可观察性，这可用于监控部署在大型电信网络集群上的服务的健康状况，快速解决问题，并在新软件发布或升级期间提高服务的可用性(VNFs、 [Open RAN 软件](https://www.calsoftinc.com/resources/ebriefs/open-ran-cloud-native-software-aspects-for-end-to-end-orchestration-automation/)等)。

在 12 月的 ServiceMeshCon 大会上，Prajakta Joshi 和 Kunal Shukla [展示了](https://smcna20.sched.com/event/fDB9/service-mesh-use-cases-for-telco-and-edge-kunal-shukla-prajakta-joshi-google)服务网格如何为大规模 5G 和电信云环境提供业务和技术价值。此外，他们还展示了如何在多云和边缘环境中维护安全性以及使用案例。

值得一提的是，Istio、Linkerd、Aspen Mesh、Consul Connect 等服务网格技术在确保更好地控制具有动态交付需求的异构环境方面发挥着关键作用。其他云原生技术为新服务和电信运营商带来了灵活性，但服务网格对于保持服务的可用性、可观察性和弹性等特性非常重要。

蒂姆·J 在 [Unsplash](https://unsplash.com/s/photos/services?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>