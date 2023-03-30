# NodeSource 为 Kubernetes 集群打包了它的商业 Node.js 软件

> 原文：<https://thenewstack.io/nodesource-offers-one-click-deployment-node-js-across-kubernetes/>

NodeSource 已经配置了其商业 Node.js 实现的一个版本，以在 Kubernetes 集群上运行，这有可能加快容器化 Node.js 应用程序的部署和 N|Solid 部署本身。

“我们看到 Kubernetes 精心策划的集装箱背后有大量的牵引力，”[的首席执行官和](https://twitter.com/joemccann) [NodeSource](https://nodesource.com/) 的联合创始人乔·麦肯说。“对我们来说，在 Kubernetes 编排的 [Docker](https://www.mirantis.com/software/docker/kubernetes/) 容器中专门化 N|Solid 产品是有意义的。”

Node.js 与容器结合使用可以加快部署速度，NodeSource 技术产品经理 Ross Kukulinski 解释道。大约 45%使用 Node.js 的开发者已经将它们与 Docker 等容器技术结合使用。

“Kubernetes 提供的东西之一是微服务分布式架构的有效扩展，”Kukulinski 说。“这与 Node 擅长的工作负载类型相同。我们看到了倍增效应。您可以使用 Node.js 构建一个非常可扩展的应用程序，然后使用 Kubernetes 对其进行扩展和管理。”

N|Solid 已经在 Linux 和 Mac 原生包中可用，并打包在 Docker 映像中。这个[新的 N |固体 SKU](http://content.nodesource.com/nsolidkubernetes) 提供了在 Kubernetes 集群中部署软件的多个副本的指令。

[Kubernetes](/category/kubernetes/) 是市场上众多容器编排工具之一，还有 Apache Mesos、HashiCorp 的 [Nomad](https://github.com/hashicorp/nomad) 和 [Docker 引擎本身的内置编排功能](https://thenewstack.io/docker-engine-1-12-will-come-built-orchestration-capabilities/)。编排工具提供了一种自动化容器化工作负载的部署和扩展的方法。

该软件包假设客户已经有一个由 Kubernetes 控制的集群，通过软件包中包含的 Kubernetes 清单，在内部或在 Google Container Engine (GCE)等云服务上运行。它包括一个预配置为在 Kubernetes 上运行的 N|Solid 副本，以及一个快速入门指南。

N|Solid 监控软件可用于在 Kubernetes 集群中启动并监控软件的多个副本。它还包括用于将基于一般 Node.js 的工作负载转换为 N|Solid 工作负载的软件。

例如，管理员可以使用该软件在三个可用性区域中分布 N |个可靠的运行时，从单点故障中加强应用程序。Kubernetes 还可以帮助快速更新 N|Solid 本身的多个副本，或者在升级没有按预期进行的情况下，快速将它们回滚到以前的版本。

NodeSource 专注于提供 Node.js 服务器端 JavaScript 运行时引擎的商业级版本，包装了增强的安全性和性能监控工具。迄今为止，该公司已经签署了美国宇航局，康泰纳仕，赛门铁克和贝宝等客户。

该公司在本周于旧金山举行的节点峰会上宣布了这一新产品。

[码头工人](https://www.mirantis.com/software/docker/kubernetes/)是新栈的赞助商。

特写:德鲁·柯林斯的《北极光》。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>