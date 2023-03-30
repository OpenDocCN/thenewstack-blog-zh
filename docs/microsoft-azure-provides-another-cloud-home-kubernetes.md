# 微软 Azure 为 Kubernetes 提供了另一个云家园

> 原文：<https://thenewstack.io/microsoft-azure-provides-another-cloud-home-kubernetes/>

在一次技术预览中，微软已经开始提供 Kubernetes 开源容器编排工具，作为 T2 Azure 容器服务 T3 的一部分。

“这是使 Kubernetes 成为 Kubernetes 平台易于使用的一部分的重要一步，” [Brendan Burns](https://github.com/brendandburns) 说，他是微软的合作伙伴架构师和 [Kubernetes](/category/kubernetes/) 的联合创始人，周一在西雅图举行的 [OpenShift Commons](https://commons.openshift.org/) 聚会上发言。

随着这个新产品的推出，Azure 成为三个最受欢迎的编排引擎的第一个云服务提供商，Kubernetes 加入了 Docker Swarm 和 Mesosphere 的数据中心操作系统(DC/OS)。微软跟随谷歌提供 Kubernetes 作为托管云服务。

通过这种集成，用户将能够通过 Azure 门户用户或在新的[基于 Python 的 Azure 命令行](https://github.com/Azure/azure-cli)内构建 Kubernetes 集群，该命令行将于本周末正式发布。用户可以通过微软 Kubernetes 命令行界面 [kubectl](http://kubernetes.io/docs/user-guide/kubectl-overview/) 来控制他们的集群，微软为 Mac、Windows 和 Linux 提供了 Azure 就绪的下载。

[https://www.youtube.com/embed/nhY9XdzNbbY?feature=oembed](https://www.youtube.com/embed/nhY9XdzNbbY?feature=oembed)

视频

该服务还将与微软计划在 11 月 14 日公开预览版中推出的新容器注册表配合使用。

该服务利用了 9 月发布的 Kubernetes 1.4 的许多新功能，包括对原生 Azure 网络、第 4 层负载平衡和 Azure 文件(SMB 挂载到 pods)的支持。它还为 Azure 虚拟磁盘提供测试版支持。

为了帮助 Azure 上的 Kubernetes 用户，微软还推出了一个新的开源项目: [ACS Engine](https://github.com/azure/acs-engine) ，它可以用于在 Azure 上生成和共享编排容器的模板。用 Go 编写的模板处理器，可以将不同的配置组合在一起，生成一个模板来运行集群。模板是在用户机器上创建的，可以作为一组部署复杂 Kubernetes 集群的指令传递到 Azure 上。

【T2![k8-book](img/6fec44c9aca417aebc9e45055954f1df.png)

随着这一预览版的发布，微软正在努力将 Kubernetes 与自己的 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/) 服务捆绑在一起，该服务可以为用户和工作提供认证，并将 Kubernetes 集群捆绑到企业的访问控制策略中。该公司还在研究围绕自动供应的功能，这可能是即将发布的 Kubernetes 1.5 版本的一个功能。

微软也在帮助 Apprenda 让 Kubernetes 支持 Windows 容器，这项工作 Apprenda 可能会在 Kubecon 上演示。

对于 DC/OS 用户，微软也将其在 Azure to DC/OS 上支持的版本升级到 1.8.4 版本，该版本包括新的虚拟网络功能。

[英特尔的乔纳森·唐纳森讨论 Kubernetes](https://thenewstack.simplecast.com/episodes/intels-jonathan-donaldson-discusses-kubernetes)

Cloud Native Computing Foundation、Docker 和 Mesosphere 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>