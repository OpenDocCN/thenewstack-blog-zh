# LogicMonitor 转向 Kubernetes 监控

> 原文：<https://thenewstack.io/logicmonitor-shifts-to-kubernetes-monitoring/>

如果 2018 年真的是“库伯内特之年”，那么 2019 年很可能成为完善库伯内特生态系统的一年。

虽然 Kubernetes 可能已经开始走向成熟，并提供容器化和微服务的所有好处，但随之而来的是对我们已经习惯于遗留应用程序的所有装备的需求——管理、监控、打包等等。所有这些需求都通过 Istio、Helm 等产品逐一得到了满足。传统应用可以通过传统方式监控，而新的应用架构意味着新的监控方式和要求，这就是性能监控软件提供商 [LogicMonitor 的](https://www.logicmonitor.com/)两款最新产品发挥作用的地方。

LogicMonitor 于 2016 年首次提供了针对集装箱的[监控解决方案，并于 2017 年](https://thenewstack.io/logicmonitor-brings-visibility-needed/)扩展至 AWS 等[云服务。根据云本地计算基金会的调查](https://thenewstack.io/logicmonitor-adds-cloud-agnostic-monitoring/)，40%的企业正在生产中运行 Kubernetes，该公司本周发布了两个新的软件包“帮助工程师监控他们的动态微服务和容器化应用程序:Kubernetes 容器监控和 LM 服务洞察，”根据一份声明。

这两个服务各自处理 Kubernetes 监控的不同方面，尽管它们被绑定在一个单一的集成解决方案中。Kubernetes 容器监控功能允许组织深入到短暂的 Kubernetes 容器的本质细节，而 LM Service Insight 后退一步，查看服务性能的更广泛情况，提供现成的警报和长期数据保留。

LogicMonitor 基于事件的 Kubernetes 监控通过 Kubernetes 包管理器 [Helm](https://helm.sh/) 安装为[应用程序](https://github.com/logicmonitor/k8s-argus)，并在您的集群中作为一个 pod 运行，这意味着它可以访问否则无法访问的信息，消除了每个节点上的代理需求，并提供集群和应用程序级别的性能和健康指标。然后，LogicMonitor Service Insight 能够提供“面向服务的监控，支持将支持通用应用程序、服务或集群的资源动态分组到一个逻辑组中，同时仍然提供对底层资源的可见性。”

与该公司的其他监控解决方案非常相似，有一千多个预配置的指标和警报，因此用户不需要花费太多时间进行设置，就可以开始监控工作。

“如果您想将单一服务分解为由 Kubernetes 协调的微服务，您不必停下来确保您的监控解决方案能够跟上。你永远不应该因为基础设施的挑战而牺牲商业愿景，”LogicMonitor 创始人兼首席传道者[史蒂夫·佛朗西斯](https://www.linkedin.com/in/francissteve/)在一份公司声明中说。

在讨论这些新特性时，LogicMonitor 的产品经理 Sarah Terry 提供了几个用例。托管服务提供商可能会在客户层面监控服务和 SLA 合规性，而大型企业可能会从更广的角度监控大型网络中设备的统计数据。与此同时，一家 SaaS 公司可能会关注 web 服务的整体健康和性能，将负载平衡器、数据库和 web 服务器等组合在一起，以便了解请求和延迟。

LogicMonitor 的 Kubernetes monitoring 和 Service Insight 还提供了许多集成，包括用于 IT 服务管理的 ServiceNow、Autotask 和 ConnectWise，用于基础设施自动化的 Anisble、Terraform 和 Puppet，以及用于通知的 Slack、HipChat 和 PagerDuty。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>