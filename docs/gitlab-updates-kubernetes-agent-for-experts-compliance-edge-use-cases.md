# GitLab 为专家、合规性和边缘使用更新 Kubernetes 代理

> 原文：<https://thenewstack.io/gitlab-updates-kubernetes-agent-for-experts-compliance-edge-use-cases/>

在该公司首次开始提供 Kubernetes 集成三年后， [GitLab](https://gitlab.com/) 已经[发布了](https://about.gitlab.com/blog/2020/09/22/introducing-the-gitlab-kubernetes-agent/)[GitLab Kubernetes Agent(GKA)](https://gitlab.com/gitlab-org/cluster-integration/gitlab-agent)，这是一个用于解决 git lab 和 Kubernetes 集成任务之间的集成任务的主动集群内组件，据该公司称，它将采用与以前软件不同的方法。

“虽然当前的 GitLab 托管集群和 GitLab 内的集群创建可能适用于许多用例，但它主要针对简单的集群设置，不够灵活，无法作为生产集群的基础。我们希望改变这种方式，首先关注 Kubernetes 专业工程师的需求，”GitLab [博客帖子](https://about.gitlab.com/blog/2020/09/22/introducing-the-gitlab-kubernetes-agent/)解释道。

除了额外的用例，该公司还发现了当前集成的一些弱点，希望通过新代理来解决这些问题。现有的集成使用基于推送的操作模型，需要对集群的管理员权限，并且需要对互联网开放，这给一些用户带来了挑战。

“我认为最大的担忧是合规性。我们有很多客户来找我们，希望自己托管 GitLab，因为他们不希望自己的代码在云中，他们有很大的合规性问题。GitLab 开发人员布道者 Brendan O'Leary 说:“还有一些人希望在 GitLab.com 上运行主机，但他们有很多边缘要求。

新的集成解决了这些问题，它作为一个代理运行在集群上，定期检查 GitLab 实例的配置变化。当发生变化时，代理从集群内部(而不是外部)提取新的配置代码并点击 Kubernetes API 来进行更改。

O'Leary 说:“对于那些将自己的群集放在完全断开的网络中，或者放在具有复杂安全要求的网络中的人来说，这将真正帮助他们解决很多问题。

主要用 Go 编写，其部署机制建立在 [gitops-engine](https://github.com/argoproj/gitops-engine) 之上，GKA 已经在 MIT 许可下发布。然而，目前的版本是一个非常早期的版本，提供的功能有限，更多的[还在路上](https://gitlab.com/groups/gitlab-org/-/epics/3329)。奥利里解释说，该代理将充当“Kubernetes API 和 GitLab API 之间的桥梁”，带来各种功能，如 [GitLab 管理的应用程序](https://docs.gitlab.com/ee/user/clusters/applications.html)，它允许 GitLab 轻松安装 Prometheus 和 Knative 等应用程序。GitLab 概述的一些更具体的后续步骤包括[将 GitLab Kubernetes 代理作为官方 Linux 包的一部分发布](https://gitlab.com/groups/gitlab-org/-/epics/3834)和[支持私有库的部署](https://gitlab.com/gitlab-org/gitlab/-/issues/220912)。

关于这最后一点，O'Leary 说“你今天必须使用 Helm 进行部署，这很好，但我们希望能够让任何人都可以使用它，而且只是在 GitLab 附带的 Linux 包中。”

未来的一些计划包括集群端动态容器扫描，使用 GitLab 作为 Kubernetes 集群的身份验证和授权提供者，提供 linters 并检查 Kubernetes 在已部署资源上的最佳实践，以及提供代理集群服务，所有这些都可以在 [GitLab Kubernetes 代理 epic](https://gitlab.com/groups/gitlab-org/-/epics/3329) 中找到。

GitLab 是新堆栈的赞助商。

来自 Pixabay 的 Arek Socha 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>