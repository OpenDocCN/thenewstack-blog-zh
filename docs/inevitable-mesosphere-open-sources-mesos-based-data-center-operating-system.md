# 不可避免的:Mesosphere 开源了基于 Mesos 的数据中心操作系统

> 原文：<https://thenewstack.io/inevitable-mesosphere-open-sources-mesos-based-data-center-operating-system/>

在竞争激烈的新兴容器编排工具市场上，Mesosphere 周二采取了备受期待但至关重要的步骤，在 Apache v2 许可下，将基于 Apache Mesos 的[数据中心操作系统](https://dcos.io/) (DC/OS)发布为开源。

“Mesosphere 将 DC/OS 视为一个关键的开源项目，并致力于建立一个活跃和参与的社区，”Mesosphere 的首席营销官马特·特里费罗在给新堆栈的一份说明中说。“我们在运行成功的开源项目(如 Apache Mesos)方面有着悠久的历史，我们也将利用这些专业知识来丰富这个社区。”

作为开源软件，DC 操作系统现在与主要竞争对手之一谷歌的 Kubernetes(T7)在数据中心的布局上不相上下。

也许你已经注意到了， [Mesosphere](https://mesosphere.com/) 也给其平台的缩写加了一个斜杠——或者，正如我的一位前编辑所纠正的，加了一个 [virgule](http://englishplus.com/grammar/00000140.htm) 。从今以后，数据中心操作系统将被称为 DC 操作系统，而不是 DCOS。这是一个可以追溯到 PL/I、CP/M 和 OS/2 的辉煌时代的人工制品。这也是让人们停止说“dee kos”的一种方法

## 逻辑补语

[在周二](https://mesosphere.com/blog/2016/04/19/hindman-mesos-dcos/)的一篇博客文章中，Mesosphere 创始人 [Ben Hindman](https://twitter.com/benh) 提醒客户，他在短短三年前创建该公司的目的是围绕 Apache Mesos 构建一个核心数据中心操作系统。但在追求这一愿景的过程中，他意识到 Mesos 最终可能只是其中的一部分。

“DC/操作系统是像 Mesos 这样的项目不可避免的下一步，”Hindman 写道。“Mesos 是必要的，但还不够，DC/OS 是利用 Mesos 的最佳方式，同时提供组织运行其软件所需的所有其他功能。不是 DC/OS 对 MesosDC/操作系统是 Mesos 的逻辑补充…虽然 Mesos 将继续添加和改进其类似操作系统的原语(例如，即将推出的对外部存储卷和通用容器的支持)，但 DC/操作系统将继续专注于补充功能，如服务发现、负载平衡、隐私和易于安装。”

Trifiro 告诉我们，超过 60 个合作伙伴将以某种实质性的方式为该项目做出贡献，并提到了 Autodesk 和 Yelp 等从业者；系统咨询公司，如埃森哲(最近的一个新的 Stack @Scale 播客)和集装箱解决方案；独立软件厂商如 [MemSQL](http://www.memsql.com/) 和[Crate](https://thenewstack.io/crate-addresses-database-speed-scaling-standard-sql/)；Canonical 和 Cisco 等网络集成商。微软也给予了支持；微软 Azure，[，其新推出的容器服务](https://azure.microsoft.com/en-us/blog/azure-container-service-is-now-generally-available/)提供 DC/操作系统作为 Docker Swarm 大规模部署的两个选项之一。

微软发言人周二向新堆栈证实，它打算继续为 DC/OS 和 Apache Mesos 做出贡献，着眼于完成 Mesos 到 Windows Server 的移植。“这将确保客户可以运行混合的 Linux 和 Windows 容器工作负载，”该发言人说。

> “我们的观点是，容器编排只是一种赌注，只能解决现代企业应用程序所面临的一小部分挑战。”—马特·特里费罗

虚拟化提供商 Citrix 周二也加入了这一名单，称计划将 DC/操作系统集成到其 NetScaler CPX 中，这是一种通过容器部署的应用交付控制器版本，目前作为技术预览版提供。

“NetScaler CPX 显然不是孤立运行的，而是作为运行和扩展基于容器的部署结构的一个组成部分，”思杰市场开发副总裁 Nand Mulchandani 在周二的一篇博客中写道。“我们最大的客户之一刚刚帮助整合了一个集成堆栈，其中包括 Mesosphere Marathon、Nuage Networks、Infoblox 和 NetScaler CPX。这是通过 Citrix 与 Mesos Marathon 的集成实现的。”

思科也加入进来，宣布它一直在与 Mesosphere 合作——并将继续这样做——与其快速分布式服务平台 Mantl 合作。

“Mantl 是一个包含电池的端到端微服务基础设施解决方案，”[周二](http://blogs.cisco.com/cloud/batteries-included-not-crippleware)思科云基础设施服务首席技术官 Ken Owens 写道。“Mantl 的精神是围绕一个端到端的解决方案来聚焦一个社区，而不是围绕一个单独的组件；旨在解决业务和团队挑战的 one glue，由社区改进，到处测试。我们与 Mesosphere 进行了非常密切的合作，因为 Apache Mesos 是现代应用程序开发模型的一个关键组件，具有在社区中开发的大型框架生态系统。”

## 宣布胜利还为时过早

随着容器工作负载部署和编排空间的成熟，[企业的不同选择正在形成](https://thenewstack.io/parity-check-container-orchestration-mean/)。

公有云方面，有 [AWS EC2 容器服务](https://aws.amazon.com/ecs/)、 [Joyent Triton](https://www.joyent.com/) ，还有最近推出的[微软 Azure 服务](https://azure.microsoft.com/en-us/services/container-service/)。对于内部 Docker 环境， [Docker Swarm](https://docs.docker.com/swarm/) 和 Docker Datacenter 将资源汇集到集群中，用于部署在 Docker 环境中作为 Docker 映像本地创建的工作负载。

但 Docker 的合作伙伴，包括微软，正在证明容器工作负载与现有工作负载的集成可能需要一个不以容器为中心的编排和部署系统。Mesos 是为了共存而设计的。正如 CoreOS 与英特尔的合作所表明的那样，Kubernetes 正在有必要共存的环境中成功部署。

对于最近的一些评论，包括 CoreOS 首席执行官 Alex Polvi 的评论，他宣称编排市场需要一个“赢家”，Mesosphere 的 Trifiro 告诉新堆栈，“坦率地说，Kubernetes 的炒作让我感到惊讶。现在宣布这个领域的赢家还为时过早。

“让我坦率地说:Kubernetes 是一个容器管弦乐队，类似于我们的 DC/OS 马拉松，”Trifiro 继续说。“DC/OS 是一个完整的数据中心操作系统，其中包括容器协调，但容器协调只是拼图的一小部分。

“我们的观点是，容器编排只是一种赌注，只能解决现代企业应用程序所面临的一小部分挑战。我们还相信，我们拥有最成熟、最适合生产的容器协调器 Marathon，”Trifiro 说。

Trifiro 继续表达了他的观点，即现代应用程序远远大于简单的容器化微服务，需要像 Cassandra 分布式数据库这样的复杂资源。他断言，在多租户环境中，只有 DC 操作系统能够在同一个集群上运行所有必要的组件。通过 Mesos 的两级调度，DC/OS 可以同时运行 Kubernetes 和其他 orchestrators 如果有必要的话。

有些人说是的，认为 Kubernetes 是开发人员在进行工作时的选择，而 Marathon 可能更适合生产环境。

英特尔也是 Mesosphere 的众多合作伙伴之一，这意味着它在这两个领域都有优势。事实上，[英特尔投资是 Mesosphere](http://www.redherring.com/internet/mesosphere-raises-10-5m-investment-round-up/) 的早期投资者，就像商业 OpenStack 提供商 Mirantis 一样。去年二月，当 [Linux 基金会宣布其 FD.io 计划](https://thenewstack.io/linux-foundation-takes-networking-fd-io/)致力于一个开放的 I/O 服务框架时，英特尔和 Mesosphere 作为合作伙伴同样受到关注。

在英特尔发布其云计算计划后不久发布的一篇 Mesosphere 博客文章中，英特尔首席工程师兼 SDI 架构师 [Das Kamhout 告诉该公司](https://d2iq.com/blog/intel-explains-its-new-program-to-accelerate-cloud-computing-for-all/)“我们与 Mesosphere 合作，并且我们也直接在 Apache Mesos 上工作。我们坚信有几种解决方案是打入大规模数据中心运营人员的广阔市场所必需的。我们喜欢 Mesosphere 的地方是它的双层调度，这允许许多事情在一个巨大的资源池之上运行。”

在新的堆栈制造商播客的[讨论中，Kamhout 吹捧最近对 Kubernetes 在英特尔客户中的成功的观察，认为这是](https://thenewstack.io/intel-engineer-das-kamhout-kubernetes-lock-developers/)[选择 CoreOS 作为通用资源调度器](https://thenewstack.io/intel-coalesce-coreos-mirantis-universal-resource-scheduler/)的原因，并在英特尔云日宣布。

Kamhout 说:“Kubernetes 作为容器的应用程序编排层获得了巨大的吸引力。“我们出去和人们交谈，很常见的是，至少在应用程序层，它得到了很多关注。现在任何人都在构建应用——也许他们正在使用 Docker 作为他们的容器运行时。但最理想的是，当你看到他们是如何编排的，很容易发现 Kubernetes API 已经就位，他们正在学习“pod”概念，并基本上建立在 Kubernetes 之上。”

当 Kamhout 说，“至少在应用程序层”时，他肯定会将资源编排(Kubernetes 和 Mesosphere 都擅长的地方)与服务编排区分开来，例如电信公司和其他上游提供商通过下一代基于 IP 的网络提供的服务类型。

Docker Swarm 在这幅图中处于什么位置？(你还记得 Docker 吗，这家公司在几个月前首次推广了容器格式？)Swarm 仍然是开发者空间的现实。但在去年 3 月 30 日的微软 Build 2016 大会上，在展示其 Azure 容器服务(周二向 g a 发布)时，容器服务高级项目经理罗斯·加德勒(Ross Gardler)明确表示，它选择的编排平台——Swarm 和 meso sphere——分别面向开发人员和生产经理。

“我们与 Docker 合作的目的是确保具有 Docker Swarm 风格的 Azure Container 服务是一个能够运行他们工具的好地方，”Gardler 说，并列举了 Docker Inc .的可信注册表和通用控制平面组件，“当你大规模使用 Docker 生态系统时，这很有用。

“与 Docker-native 环境相比，Mesosphere 的 DC/操作系统产品在某些类型的工作负载方面有一些额外的优势，”他继续说道他之前解释过 Mesos 是如何在容器出现之前的某个时间和地点开发出来的。“因此，您可以运行混合容器工作负载。如果你想运行 Spark 或 HDFS (Hadoop)或 Cassandra，或任何其他技术，[*它们也已经在这些环境中得到验证。”*

虽然 Docker Inc .继续在将这些其他类别的工作负载移植到 Docker 原生技术方面取得进展，但 Mesosphere 显然将自己呈现为一个不需要进行所有移植的领域。容器、虚拟机、“大数据”和 NoSQL 工作负载可以简单地共存。

## 桌面木桩

任何离开 3 月中旬在旧金山举行的开放网络峰会的人都会认为，在资源编排领域取得最大进展的是 Mesosphere，而不是 Kubernetes，至少在通信工程师方面是如此。虽然这些工程师指出，工作负载扩展原则并不能转化为服务扩展，但至少目前，我们看到的许多现场演示都称赞 Mesosphere 是一种非常明智的扩展和分布工作负载的方法。

如果这些演示在技术上还不足以说明问题，安德森·霍洛维茨基金的普通合伙人彼得·莱文(Peter Levine)提出了商业意义方面的理由。在称赞 Red Hat 已经实现了使开源软件在企业中取得成功所必需的业务规模的同时，Levine 说，“我相信开源的未来也将需要业务创新，而不仅仅是认为，我们将建立另一个开源公司，它将免费提供软件，并建立一个支持和服务组织。”这一评论是在与 ONS 创始人 Guru Parulkar 的一次讨论中提出的，当时提到中间层是安德森·霍洛维茨的关键投资之一

下周的 OpenStack 峰会将考验美国电话电报公司等电信公司、英特尔等建筑公司以及思科、瞻博和 Brocade 等网络公司的忠诚度。在大规模协调工作负载时，Kubernetes 和 Mesos 及其商业选择都有明显的优势。借用 Matt Trifiro 的话来说，虽然 Mesosphere 将是“桌面赌注”的一部分，但对于下周关于如何在巨大规模上编排容器的几个小组讨论来说，有趣的是他如何将 OpenStack 塑造成可能不是桌面上最大的玩家。

“我们看到许多 OpenStack 部署，特别是在较小的云提供商(四大之外的提供商)和许多企业中，但 OpenStack 主要是关于配置虚拟机的，”Trifiro 写道。“DC/操作系统是对 OpenStack 部署的一个很好的补充，因为您可以使用 OpenStack 来配置底层机器，然后将 DC/操作系统置于其上，创建一个容器驱动的结构来部署现代应用程序。”

思科、CoreOS、Docker、英特尔和 Mesosphere 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>