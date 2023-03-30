# Juniper 如何通过托管 Kubernetes 加速其云原生转型

> 原文：<https://thenewstack.io/how-juniper-accelerated-its-cloud-native-transformation-with-managed-kubernetes/>

[](https://www.linkedin.com/in/sravicha/)

[Ravi Ravichandran](https://www.linkedin.com/in/sravicha/)

[Ravi Ravichandran 是 Juniper Networks 的工程、云平台和 DevOps 主管。他引领 Juniper Networks 软件产品向云的数字化转型。他开发新兴技术战略，以支持开发运维并实现业务转型，从而加速向全球客户提供产品和云服务。在加入 Juniper 之前，Ravi 是 SaaS/云平台工程的数字 CTO，并在 GE Digital 担任 DevOps，在 GE Digital，他利用了各种领先的新兴云技术，并领导了新技术引进(NTI)的采用，以改善服务成本(CTS)、云工程、云可靠性、安全性和可扩展性。他还领导了服务的全球 IaaS/PaaS/SaaS 战略、执行、支持和交付。](https://www.linkedin.com/in/sravicha/)

[](https://www.linkedin.com/in/sravicha/)[](https://www.linkedin.com/in/sravicha/)

在数字化转型的时代，我们在 Juniper[的工程云基础设施团队面临着越来越多的挑战，他们需要提供现代云原生技术堆栈，以加快开发生命周期，构建自动化以加快软件测试的周转，并提高工程生产力。由于许多团队都面临着类似的挑战，我们认为分享我们在此过程中学到的最佳实践](https://www.juniper.net/us/en/)[会有所帮助。](https://platform9.com/resource/cloud-native-transformation-with-managed-kubernetes/)

能够实现数字化转型的应用越来越多地被容器化，以实现更敏捷的开发、集成和部署，同时保持严格的性能、安全性和成本预期。考虑到这一点，我们很快发现 Kubernetes 是调度、管理和动态编排这些容器的有效方法，它具有向上/向下扩展的功能和高度自动化的环境，但我们也意识到它确实需要深入的管理和调优专业知识才能得到最有效的部署。作为评估流程的第一步，我们确定了许多企业共有的五项关键要求:

1.  **自动化:**团队希望确保他们能够以自动化的方式进行部署，以最大限度地减少人工干预和返工。
2.  **企业级可靠性、可用性和可扩展性**通过全天候全球云运营模式满足严格的 24×7 SLA。
3.  **轻松集成**现有数据中心存储、网络和安全解决方案。我们希望有一个新的解决方案，能够与我们当前的基础架构无缝集成。
4.  **无缝升级:**总的来说，我们担心自己能否跟上 Kubernetes 定期升级的速度。鉴于我们以前在许多其他平台上的经验，我们不想留下难以升级的技术和浪费时间。
5.  **在没有大量员工的情况下利用创新:**此外，我们希望利用开源项目和社区的创新性和灵活性，而无需自己管理软件生命周期。在我们寻求实施 Kubernetes 的规模下，我们将不得不雇佣一个拥有必要技能和专业知识的相当大的团队。而且，我们很快意识到 Kubernetes 的专业知识很难获得和保留。

与许多企业一样，我们研究了几种潜在的方法，包括 DIY、商业 Kubernetes 发行版，以及将 Kubernetes 作为一种服务来管理。经过仔细评估，我们认为只有托管的 Kubernetes 服务才符合我们的要求。我们确定的主要优势包括:

 [Kamesh Pemmaraju

Kamesh Pemmaraju 领导 Platform9 的企业/产品营销。在过去的十年里，Kamesh 一直致力于各种开源私有云和混合云解决方案。他已经帮助多家企业和服务提供商大规模采用云技术。Kamesh 还带来了强大的产品管理、技术联盟和新兴技术的上市经验。](https://www.linkedin.com/in/kpemmaraju/) 

1.  **更快的上市时间:**托管 Kubernetes 通过为 DevOps 和 CI/CD 管道提供灵活、可扩展的按需基础设施，使我们能够推动数字化转型并加快上市时间。
2.  **更平稳的升级和开源创新:**为不间断的 Kubernetes 产品提供维护窗口是非常具有破坏性的。托管 Kubernetes 的滚动升级功能避免了中断和停机时间。这也持续提供了开源创新的所有好处。
3.  **更低的总拥有成本:**与竞争对手的解决方案相比，更低的 Kubernetes 工程人员成本、战略性人员重新部署和增强的操作简单性有助于像我们这样的企业实现显著的总拥有成本节约。
4.  **第 2 天运营简化:**托管 Kubernetes 及其 SLA 支持的服务解决了我们对以高效方式全天候运行托管 Kubernetes 的关注。
5.  **更快的价值实现时间:**如果我们试图单独实施 Kubernetes，则需要 6 到 12 个月才能达到全球部署的生产阶段。一个托管的 Kubernetes 解决方案在短短几周内就实现了这一目标。

许多组织可能仍然自然地回避开源技术。然而，随着下一代 SaaS 管理平面架构的可用性不断提高，现在有一些资源可以提供公共云的操作简单性和易用性，同时使用上游开源云原生堆栈(如 Kubernetes、Prometheus、Istio 和 OpenStack)提供最开放的环境。这使得跨基础架构标准化和扩展操作变得非常容易。

在 SaaS 模式下，我们现在可以访问一个中央操作控制台，并为所有 Kubernetes 集群提供单一控制台，无论它们位于何处。因此，我们不再需要担心正常运行时间/SLA 管理、升级、安全补丁和生产中断的运营负担。对我们来说，托管 Kubernetes 解决方案已被证明是两全其美。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>