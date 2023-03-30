# Instana 监控现在支持 CRI-O Kubernetes 运行时

> 原文：<https://thenewstack.io/instana-monitoring-now-supports-the-cri-o-kubernetes-runtime/>

微服务监控公司 [Instana](https://www.instana.com/) 现在支持 CRI-O，替代 Docker 的运行时。

据该公司称，这一增加为希望选择他们首选的编排引擎和运行时容器的客户提供了更多的灵活性。

[CRI-O](https://cri-o.io/) 是 Kubernetes CRI(容器运行时接口)的一个实现。除了促进 OCI(开放容器倡议)兼容的运行时，除了依赖 Docker 作为 Kubernetes 的运行时之外，它还为人们提供了另一种选择。CRI-O 还允许 Kubernetes 在运行 pods 时使用任何符合 OCI 标准的运行时。

作为 Docker 的替代品， [CRI-O](https://cri-o.io/) 具有潜在的众多吸引人的特性。例如，CRI-O 是稳定的，与 Kubernetes 相关的主要和次要版本一起开发和测试。此外，开发人员在使用 CRI-O 时不需要参与太多的直接命令行接触，但是，在监控期间，如果需要，可以使用特定的命令。那些工具[取代并增强了 Docker 的](https://docs.openshift.com/container-platform/3.11/crio/crio_runtime.html)命令和服务。

### Instana 的 CRI-O 支持将如何帮助开发者？

这种对 CRI-O 的新支持将大大减少 DevOps 团队在故障诊断问题上花费的时间。Instana 发现、部署、监控和[分析来自 CRI-O](https://containerjournal.com/news/news-releases/instana-adds-support-for-crio-infrastructure-and-application-monitoring/) 的数据，自动处理所有必要的事情。它还将有关基础设施和数据的信息与其他监控相关的详细信息关联起来。

Kubernetes 是一个多功能系统，适合在几乎任何环境中部署，无论是内部部署还是云中部署。它让 DevOps 专业人员能够大规模解决他们的容器管理需求。Kubernetes 中的多个组件在连续的循环中运行，观察当前状态并进行任何必要的调整以保持在期望的状态。

Instana 最近宣布支持 CRI-O 并不是该公司第一次采用非 Docker 容器技术。然而，这一发展是实质性的，因为它标志着该品牌首次提供关于编排、容器和应用程序监控环境中的 CRI-O 的详细信息。

Instana 花了两年时间构建其初始监控平台。这一最新产品展示了公司不断发展以满足客户需求和期望的承诺。

### Instana 的应用性能管理是如何工作的？

Instana 自动化了整个应用程序监控生命周期，这意味着开发人员可以使用全方位的产品来满足他们的应用程序监控需求。它解决了从应用程序基础架构健康到应用程序发现和映射的一系列问题。

作为第一步，Instana 构建应用程序结构和依赖关系的正确描述。但是，初始表示不是静态的。这是因为 Instana 可以识别动态应用程序的更新。在检测到一个之后，它会自动进行必要的调整，包括将更改或调整映射到监控阈值和健康仪表板。

此外，由于 Instana 允许用户在一个仪表板上看到他们的所有应用程序，只需几秒钟就可以验证一切正常，或者意识到有什么需要进一步关注。Instana [每秒](https://www.instana.com/blog/monitoring-needs-immediate-accurate/)发送数据并立即处理。

因此，关于系统何时开始分析数据并将其提供给用户，实际上没有延迟。更具体地说，从 Instana 处理信息到它出现在用户屏幕上，只有三秒钟的时间。

Instana 还拥有先进的内置技术，可以在问题发生前预测问题。例如，机器学习可以进行模式检测，而神经网络可以预测未来事件。该公司的产品也可以智能地发现异常。

当开发运维团队的工作负载不断增加时，他们尤其会从能够简化工作流程和减少问题的产品中受益。由于 Instana 现在提供了对 CRI-O 的支持，用户可以有更多的选择来定制他们的容器管理流程，并将可预防的问题降至最低。

来自 Pixabay 的 Alexas_Fotos 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>