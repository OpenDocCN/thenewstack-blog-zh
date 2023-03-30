# 微软红帽团队将在 Azure 上提供事件驱动的 OpenShift

> 原文：<https://thenewstack.io/red-hat-microsoft-team-to-offer-event-driven-openshift-on-azure/>

本周在波士顿举行的[红帽峰会](https://www.redhat.com/en/summit/2019)上，[红帽](https://www.redhat.com/en)宣布 [Azure 红帽 OpenShift](https://azure.microsoft.com/en-us/blog/generally-available-azure-red-hat-openshift/) 全面上市，将红帽 [OpenShift 容器平台](https://www.openshift.com/)的第一个联合管理版本带到微软的公共云 [Microsoft Azure](https://azure.microsoft.com/en-us/) 。根据红帽在发布会上的声明，Azure 红帽 OpenShift“结合了可信企业 Kubernetes 的创新和世界领先的企业 Linux 平台红帽企业 Linux，在 Azure 的规模和功能上运行。”

在接受新堆栈采访时，Red Hat 的产品战略总监 Brian Gracely 解释说，微软已经注意到其客户正在 Azure 上运行 OpenShift，它希望获得这一过程的所有权，以提供更好的体验。

“大约一年前，微软找到我们，说他们看到了这一趋势，并问我们是否愿意共同建立一个托管服务，”格雷斯利说。“我们在 AWS 上提供一个版本的 OpenShift，在 Google 上提供一个版本，我们完全有意向在 Azure 上以红帽服务的形式提供它。随着您越来越多地与云提供商合作，他们都有自己的个性，都有自己喜欢的走向市场的方式。Azure 最终找到我们，并说微软的做事方式是一种更加集成的体验。Azure 只是想建立一种不同的业务关系，最终为他们的客户带来不同的体验。”

这种不同的体验以与现有 Azure 客户界面更紧密集成的形式出现，其中包括统一的注册流程、入职、服务管理和技术支持，以及集成的计费。根据 Red Hat 的一份声明，合作伙伴关系并未就此结束，因为“微软和 Red Hat 还在合作，为客户带来基于 Azure 的 Red Hat Enterprise Linux 8、Red Hat Ansible Engine 2.8 和 Ansible Certified modules 的容器化解决方案”，并共同努力“提供具有 Red Hat Enterprise Linux 8 支持和性能增强的 SQL Server 2019。”

虽然这些是 Red Hat 公告中提供的要点，但微软和 Red Hat 迅速发展的合作的进一步证明也可以在 OpenShift 4 的发布中找到，其中包括另一个联合开发的功能，称为 [Kubernetes 基于事件驱动的自动缩放(KEDA)](https://github.com/kedacore/keda) 。

在一篇[宣布 KEDA 的博客文章](https://cloudblogs.microsoft.com/opensource/2019/05/06/announcing-keda-kubernetes-event-driven-autoscaling-containers/)中，Azure Functions 的高级项目经理[杰夫·霍兰](https://www.linkedin.com/in/jeffhollan)解释了 KEDA 如何给 Kubernetes 带来“事件驱动的容器和功能”。

“像 Azure Functions 这样的完全托管的无服务器产品是由设计驱动的事件，但是我们已经从客户那里听说了基于 Kubernetes 的解决方案在这些功能上的差距。Kubernetes 中的扩展是反应式的，基于容器的 CPU 和内存消耗。“相比之下，像 Azure Functions 这样的服务能够敏锐地感知事件源，因此能够基于直接来自事件源的信号进行扩展，甚至在 CPU 或内存受到影响之前。我们开始将事件驱动架构的优势和功能的生产力带给 Kubernetes。”

微软和红帽一起着手建立一个解决方案，因此 KEDA 诞生了，霍兰写道，“使任何容器能够根据事件度量标准，如 Kafka 流或 Azure 队列的长度，从零扩展到潜在的数千个实例。”

优雅地将 KEDA 的功能与大多数公共云已经提供的功能联系起来，为用户抽象出基础架构的复杂性。

“以前，Kubernetes 只负责处理应用程序。它不一定知道如何将其扩展到底层基础架构。因此，如果应用程序说，‘我真的可以再使用 10 个节点来处理这个工作负载’，那么您必须离开平台，运行 Ansible 之类的程序来构建 10 个以上的节点，”Gracely 说。“现在，Kubernetes 能够说‘您将达到您的工作负载阈值’,并告诉底层云，‘为我再横向扩展 10 个节点。’公共云提供商正在提供“不要担心基础设施”的服务，这为 Kubernetes 和 OpenShift 带来了这种能力。"

只有时间能证明一切，但随着微软最近对开源软件的推动，以及红帽对意识形态的长期投入，这两家公司之间的友谊似乎正在萌芽。

红帽是新堆栈的赞助商。

图片由来自 Pixabay 的布里吉特·沃纳拍摄

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>