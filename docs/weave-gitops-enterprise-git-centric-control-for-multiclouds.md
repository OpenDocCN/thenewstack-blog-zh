# Weave GitOps Enterprise:以 Git 为中心的多云控制

> 原文：<https://thenewstack.io/weave-gitops-enterprise-git-centric-control-for-multiclouds/>

Weaveworks 的第一个正式发布的 [Weave GitOps Enterprise](https://www.weave.works/product/gitops-enterprise/) 代表了一个雄心勃勃的努力，以支持整个 Kubernetes 环境中 CI/CD 的整个开发和部署过程。它还强调了跨多个 Kubernetes 集群的以 Git 为中心的部署管理，并扩展到内部部署和多个云。

“Weave GitOps Enterprise 的正式发布是为了在支持不同云提供商的同时，从 Git 获得越来越多的多集群管理功能，”除了亚马逊网络服务(AWS)和裸机环境，[Weave works](https://uk.linkedin.com/in/steveww)的技术营销经理 Steve Waterworth 告诉新堆栈。“我们现在可以说这个平台正在走向成熟。更多新的优秀产品即将推出。”

Weave GitOps Enterprise 构建在 Weaveworks 之前发布的开源替代产品 [Weave GitOps Core 之上。](https://www.weave.works/product/gitops-core/) Weave GitOps Core 用于帮助简化和自动化在该公司所说的“任何 Kubernetes 集群”上部署代码的过程。这涉及一个双命令行过程，无需手动配置群集设置。除此之外，Weave GitOps Core 还为集群预先配置了监控和可观察性工具，以便它们在部署过程中继续不间断地运行。

在一篇[博客文章](https://www.weave.works/blog/weave-gitops-enterprise-general-availability)中，Waterworth 描述了 Weave GitOps Enterprise 如何成为“第一个企业 GitOps 平台”，为 Kubernetes 基础设施和应用团队提高软件交付和运营性能。Waterworth 写道，通过支持 GitOps 统一应用开发和运营，该平台实现了“开发过程中的早期协作，同时在整个应用生命周期中提供更高的安全性、可预测性和可见性”。Waterworth 写道:“团队可以通过任何规模和跨部署类型(包括混合云、多云和边缘)的连续应用交付和运营控制来自动化 Kubernetes。”

Weave GitOps Enterprise 公司传达的关键功能包括:

*   **Web 用户界面** : 控制面板提供已配置集群的概述、警报、应用程序目录和集群模板库。使用 GitOps，集群管理和配置文件目录通过 Git pull 请求和合并来管理。

*   **集群管理** : 所有集群:无论是云提供商还是本地环境，都可以在一个存储库中以自助方式访问和管理，Git 充当所谓的“单一事实来源”可以导入现有集群，并定义用于创建新集群的模板。

*   **应用程序配置文件目录** : 应用程序配置文件在目录中定义，提供一组认可的应用程序，可以在集群创建时或以后安装在集群上。软件包可以是单个应用程序，也可以是一套可以安装、更新或删除的应用程序(例如 Prometheus、Grafana、Loki 或 Tempo for monitoring and observability)。

*   **警报选项**:Weave GitOps Enterprise dashboard 链接到 Prometheus Alert Manager，提供所管理的所有集群的警报概览。

Waterworth 告诉新的堆栈，管理多个 Kubernetes 集群的能力对德国电信来说特别方便。“他们管理着数千个 Kubernetes 集群。他们运行在你在德国看到的大量德国电信手机信号塔的边缘，”Waterworth 说。“它们都是以这样的方式管理的，如果他们想进行更改，他们可以在 Git 中进行更改，并且该更改会自动推广到数千个 Kubernetes 集群。”

随着 GitOps 流程的不断发展，GitOps Enterprise 也将随之发展。“我们已经用 Weave GitOps Enterprise 达到了这一点，它的普遍可用性对许多人非常有用，”Waterworth 告诉 New Stack。“但这并不意味着开发已经停止——我们正在努力为更广泛的云平台添加更多功能。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>