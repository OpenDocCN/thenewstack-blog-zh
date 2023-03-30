# MLOps 需要一种更好的方法来管理 GPU

> 原文：<https://thenewstack.io/mlops-needs-a-better-way-to-manage-gpus/>

GPU 是深度学习和其他大规模机器学习形式的必需品，但我们还没有工具来有效地管理它们，就像我们可以管理普通 CPU 一样。尤其是在 GPU 成本如此之高的今天，你需要确保你的钱得到最大的回报。

两个[跑。AI](https://www.run.ai/) 软件工程师——[娜塔莎·罗姆](https://www.linkedin.com/in/natasha-romm-ba4707149/?originalSubdomain=il)和[拉兹·罗滕博格](http://www.razrotenberg.com/about/)(软件团队负责人)——一直在研究提高 GPU 利用率的方法。他们在 Kubernetes AI Day(T7)上展示了他们的发现，这是上周在底特律举行的 KubeCon+CloudNativeCon 会议的一部分。

“GPU 必须以更智能的方式进行配置，”罗滕博格说。

今天，GPU 是静态分配的，没有太多的细微差别，通常由用户或人工智能工作负载来分配。我们需要的是更细粒度的权限，即 GPU 时间的一部分，以便它们可以更好地在任务之间分配。

“GPU 配置不是我们日常使用的术语，”罗滕博格承认道。随着越来越多的部门开始使用 GPU，管理员可能会申请更多的硬件。但是这些现有的 GPU 可能没有得到充分利用。“事实是，你并不总是需要更多的 GPU，”他说。

管理员应该能够超额配置，分配比 GPU 运行更多的工作负载。CPU、内存甚至存储通常都会过度配置。Kubernetes 不能过度配置。

大多数用户不需要整个 GPU 来完成工作。而且，大多数时候，他们可能根本不运行 GPU。研究人员可能去喝咖啡休息，甚至去度假。

Kubernetes 可以做动态分配。但是，它为每个 pod 分配一个 GPU。一旦 GPU 被分配给 pod，它就不能在其他地方使用，即使 GPU 本身没有被使用。

## 更好管理的工具

跑步。AI 工程师已经创建了一个开源实用程序，称为 [genv](https://github.com/run-ai/genv) (GPU 环境管理)，可以用来控制、配置和监控 GPU 资源。该工具适用于直接在裸机上运行的工作负载，或者可以通过 SSH 访问的工作负载。

对于 Kubernetes 部署，看看英伟达的 [DCGM 导出器](https://docs.nvidia.com/datacenter/cloud-native/gpu-telemetry/dcgm-exporter.html)，可以从英伟达的 GPU 中提取运营指标。它可以作为独立容器运行，也可以作为 daemonset 部署在 Kubernetes 集群中的 GPU 节点上。它通常由 Nvidia 的 Kubernetes 运营商部署，因此如果您使用该运营商，您可能已经内置了此功能。

要构建 GPU 监控仪表板，运行。人工智能的人们也在 NVidia exporter 上使用[普罗米修斯和 Grafana](https://thenewstack.io/cncf-prometheus-agent-could-be-a-game-changer-for-edge/) 。该控制面板以百分比形式显示 GPU 使用情况。

有了这些信息，管理员可以联系 GPU 的所有者(可通过 K8s 命名空间识别)并要求他们放弃利用率为 0%的 GPU。

## 沿着这条路走下去

Genv 的创建是为了向人工智能用户介绍更好地管理 GPU 的想法。Romm 说，下一步是智能利用和智能供应。

Run.ai 已经为 ai 资源建立了一个编排层，特别是用于管理 GPU。

“我们使用智能调度算法和深度核心功能，帮助组织从昂贵的硬件中获得更多价值，”罗滕博格在后续的电子邮件中写道。

他写道，公司工程师已经建立了 Linux 级别的功能，“允许更好地管理 GPU，如内存限制、内存交换、分时和优先化、将运行的 pod 重新路由到空闲的 GPU”。Linux 级别的功能被集成到 Kubernetes 级别的层中，该层提供调度和其他关键领域的支持。

跑步。人工智能平台还提供管理功能，通过创建项目和部门来管理人工智能工作负载，以及管理用户和执行更复杂的配额。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>