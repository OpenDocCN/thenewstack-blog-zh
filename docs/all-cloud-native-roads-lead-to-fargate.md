# 所有云族的道路都通向法盖特

> 原文：<https://thenewstack.io/all-cloud-native-roads-lead-to-fargate/>

在过去的几个月里，我们目睹了一个特别有趣的趋势，那就是越来越多的云原生应用最终运行在亚马逊 Web 服务上。Fargate 是一个专注于容器的无服务器计算平台。就计算范式的抽象而言，法盖特位于[λ](https://aws.amazon.com/lambda/)和 [EC2](https://aws.amazon.com/ec2/) 之间。Fargate 的抽象程度比 Lambda 低，用户只需提供相当纯的代码即可运行。但是对容器的关注使得 Fargate 比 EC2 更高级，在 EC2 中你管理虚拟机。已经发生的事情是，由于许多原因，但有一个共同的主题，即与运营成本相关，许多用户最终选择 Fargate 作为他们最喜欢的计算平台。

## Fargate 权衡

 [托尔斯滕·霍格

Thorsten Hö ger 是 Taimos 的首席执行官兼云顾问，他为客户提供如何使用 AWS 的建议。作为一名开发人员，他专注于改进开发流程和自动化一切，以便为各种规模的客户构建高效的部署管道。在成为自由职业者之前，Thorsten 是德国第一家运行在 AWS 上的私人银行的开发人员和 CTO。2013 年，他和同事一起将核心银行系统迁移到了 AWS 平台。此后，他在斯图加特组织了 AWS 用户组，并经常在 Meetups、BarCamps 和其他社区活动中发言。他是 2017 年以来的 AWS 社区英雄。作为开源软件的支持者，Thorsten 正在维护或参与 GitHub 上的几个项目，如 AWS Lambda、亚马逊 Alexa 的测试框架，或 AWS CloudFormation 和 AWS CDK 的开发工具。](https://www.linkedin.com/in/thorsten-h%C3%B6ger-38b77195/) 

AWS Fargate 是弹性容器服务之上的一层，位于 Fargate 最近发布的弹性 Kubernetes 服务之下。Fargate 协调基于容器的工作负载。简而言之，Fargate 允许您运行容器，而不必管理运行这些集群的主机或驱动它们的容器引擎(即 Docker)。

ECS 上的 Fargate 允许您在 AWS 运行的 ECS 基础设施上调度 ECS 任务:您可以利用 ECS 的大多数功能，同时放弃对其基础设施的控制和责任。ECS 任务是一组共享资源(如卷和网络)的容器，与 Kubernetes 中的 pod 没有什么不同。

ECS 任务可以一次性运行，但更多情况下，它们被分组到 ECS 服务中，这些服务为云原生应用程序提供基本功能，如[自动扩展](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-auto-scaling.html)、[负载平衡](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-load-balancing.html)、[服务发现](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-discovery.html)和[节流](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-throttle-logic.html)。也就是说，Fargate 为云原生应用提供了大量的基础功能，这些功能已经嵌入到平台中。

在操作方面，Fargate 用户负责容器的内容、将容器分组为 ECS 任务、ECS 服务和 ECS 集群的定义及其联网。Fargate 的联网，以及在公共互联网上为每个容器获取 IP 地址是如此容易的事实，意味着 Fargate 的采用者需要更多地考虑网络设计。此外，更细粒度的安全组也是可能的，它们是基于每个容器定义的，而不是由主机定义的。

## 可观察性

 [米歇尔·曼乔皮

Michele Mancioppi 担任 Instana 的高级技术产品经理，领导与代理、分布式跟踪、Cloud Foundry 和 VMware Tanzu 相关的所有产品开发。在加入 Instana 之前，他是 SAP 云平台性能团队的开发专家和技术主管。Michele 拥有特伦托大学的计算机科学学士和硕士学位，以及荷兰蒂尔堡大学的信息系统博士学位。](https://www.linkedin.com/in/michelemancioppi/) 

Fargate 的可观察性需求类似于其他微服务环境的需求:需要端到端的可见性来了解请求是如何被服务的(例如，通过分布式跟踪)，以及关于 ECS 任务和 ECS 服务的健康状态的可操作信息。随着应用程序分布在多个 ECS 服务上，任务通过服务发现相互查找，并与过载平衡器(VPC)进行通信，如果没有非常准确的分布式跟踪和它所提供的深度洞察力，就几乎不可能准确了解地图的实际架构并对问题进行故障排除。

就指标而言，与 AWS Fargate 运行时相关的指标在某种程度上可以在容器本身中获得，容器本身提供了一个 Docker 指标端点，内置于 [ECS 任务元数据 API](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-metadata-endpoint.html) 中。这些指标，还有更多，也可以从[cloud watch Container Insights](https://aws.amazon.com/blogs/mt/introducing-container-insights-for-amazon-ecs/)获得。就自定义指标而言，他们可以将它们推送到选择的指标存储中。

在日志方面，可以将日志推送到 CloudWatch 或 FireLens、[以及其他一些受支持的日志驱动程序](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html)，或者运行 sidecar(这在 CPU 和内存方面需要额外的成本)将日志推送到其他地方。

## Fargate 能做好什么？

那么，你应该什么时候使用 Fargate？答案相对简单:当你有几乎所有可以放入容器的东西时，除非你真的想管理基础设施。相比之下，AWS Lambda 就不一样了，由于运行时的特性和限制，人们大多在其上部署设计为在 Lambda 上运行的软件。但是有了 Fargate，如果你的软件现在可以在 Docker 上运行，那么 Fargate 的移植将会非常顺利。

## 何时不使用 Fargate

我们目睹了 IT 或安全策略阻止迁移到 Fargate 的案例。这种情况似乎主要发生在几年内没有修改的安全策略中，并且仍然假设虚拟机是计算单位。(郑重声明，虽然理论上防病毒软件在容器中运行时有可能感染病毒，但这从未发生在我们或我们认识的任何人身上。)

我们还从一些客户那里了解到，与 Fargate 等特定于供应商的计算平台提供的便利性和集成相比，他们更看重独立于特定的云提供商。在许多这样的情况下，最终用户现在倾向于使用托管的 Kubernetes 产品，这减少了供应商锁定。(附注:这似乎正是 EKS 在 Fargate 上存在的原因:提供一个类似 Kubernetes 的 API，尽管有局限性，但也有较小的锁定因素，并且仍然提供对基础设施的管理。)

在我们目睹的一个案例中，应用程序可以在 Docker 容器中运行，但只有在内核以非常特定的方式进行了调整的情况下才能运行，这阻止了应用程序被移植到 Fargate 上，因为内核是不允许的。对内核同样缺乏控制也适用于 Docker 引擎，例如，它阻止您使用跳过 CloudWatch 的任意日志转发器，除非您运行另一个容器(并为其计算资源付费)将您的日志推送到其他地方。

值得一提的是，可能会阻止迁移到 Fargate 的因素，尤其是从 EC2 迁移到 Fargate 的因素，实际上与技术的关系更小，而与人员、组织以及开始云原生之旅的组织中既定角色和职责的危险关系更大。詹姆·多布森的[“第二天的问题”](https://blog.container-solutions.com/structure-day-2-problems)博客文章对此做了比我们更好的解释:

> “许多现有的心理模型不再适用，因此内讧变得猖獗。随着回归旧的工作方式的诱惑出现，调整变得困难。当那些工作面临风险的人意识到即将到来的危险时，恐惧就会增加。”

云原生之旅确实充满了挑战。

## 从 Lambda 迁移到 Fargate 的动机是什么

可以在 Lambda 上运行的软件，只需稍加调整，也可以在 Fargate 上运行(反之则不然:软件需要以特定的方式开发，才能在 Lambda 上运行)。从技术角度来看，放弃 Lambda 的原因基本如下:

*   **对运行时环境的控制:**在 Fargate 中，您提供一个完整的容器映像，包括一个 OS 内核和一个用户空间。这比 Lambda 所能提供的对你的应用程序及其运行环境的控制要多得多，至少没有编写一个[定制的 Lambda 运行时](https://docs.aws.amazon.com/lambda/latest/dg/runtimes-custom.html)，而且我们还没有遇到任何人创建了一个定制的运行时来运行 Lambda 函数，因为这是一项相当于在 Heroku 或 Cloud Foundry 上编写你自己的 buildpack 的任务。
*   **长时间运行的作业:** Lambda 不是为长时间运行的函数设计的(或定价的)。如果您预计批处理作业需要几分钟或几小时才能完成，那么您最好在 Fargate 上使用[计划任务。](https://docs.aws.amazon.com/AmazonECS/latest/userguide/scheduled_tasks.html)
*   **更容易避免冷启动:**虽然在平台层面上，Lambda 中的冷启动似乎是一个大部分已解决的问题，但避免函数本身的大量启动时间仍然需要小心，有时会限制您可以采用的依赖项和框架的种类。
*   **减少锁定:**如果你可以在 Docker 容器中运行你的应用程序，那么你很容易就可以让它在 Fargate 上运行。相反，Lambda 是特定于 AWS 的环境，据报道，将您的功能移植到不同的无服务器产品需要一些不平凡的工作，特别是因为 Lambda 功能倾向于耦合到特定于 AWS 的服务；但是公平地说，云提供商提供的几乎所有当前的无服务器平台都是如此。

有时候在比较 Lambda 和 Fargate 时会提到计费方面。然而，Lambda 和 Fargate 的计费模式以及在这两个平台上运行的软件有着天壤之别，任何比较都需要基于对实际工作负载的实际测量。然而，有可能在大范围内(就请求而言)，您可以使用在负载下伸缩良好的运行时在 Fargate 上节省资金，例如 Node.js 或我们长期以来最喜欢的 Java 反应式编程。

## 从 EC2 迁移到 Fargate 的动机是什么

设定期望值:如果您可以使用 Fargate 而不是 EC2，您可能应该这样做。与容器的灵活性相比，管理和更新虚拟机的人工成本是非常大的，即使是在运行根据您的需求定制的 ami 时也是如此。

安全也是一个因素。虽然 Fargate 上的容器基本上也包含一个操作系统，但事实上，与启动和拆除虚拟机相比，旋转容器版本非常容易和快速，这意味着在出现安全问题时，您可以比虚拟机更快地使用容器。此外，你可以让你的容器不可变，并通过像[发行版](https://github.com/GoogleContainerTools/distroless)和容器优化操作系统这样的方法最小化攻击面。我们与一些客户合作，他们告诉我们，他们的安全团队有非常长的流程来允许在虚拟机上部署，但是大多数实践(例如 antiviruses)在容器中是不需要的，这是不遗余力的。

换句话说，当没有其他计算平台满足您的需求时，您可能应该使用 EC2。其中一个原因可能是您可以在 EC2 机器上施加的控制量。如果你必须运行你自己的操作系统，那么 EC2 就是你要走的路。或者，也许你自己正在运行一些“奇异的”数据库，这通常是将应用程序提升和转移到云的一个必要的缺点，至少在最初的步骤中是这样。涉及数据库的其他情况是，虽然不是特别奇特，但在某些配置中具有极高的资源需求，在一台主机上需要数百千兆字节甚至太字节的内存。另一个常见的用例是在 AWS 上运行自己的平台即服务，如 Cloud Foundry 或 VMware Tanzu。

## 结论

在本文中，我们讨论了 Fargate 及其容器即服务方法如何在许多组织的权衡中找到最佳平衡点。我们讨论了 Fargate 的优势，以及让您选择 Lambda 或 EC2 的原因。总结一下我们的立场:你应该使用你所能承受的最高层次的抽象。如果你的代码可以在 Lambda 中运行，你可能就应该这么做(但是无论如何，你有可能编写了在 Lambda 上运行的软件)。而且，在仔细考虑之后，你可能会考虑搬到法盖特。否则，如果您的应用程序可以在 Docker 容器中运行，请使用 Fargate。除非你真的真的必须用 EC2。

亚马逊网络服务、Cloud Foundry 和 VMware 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>