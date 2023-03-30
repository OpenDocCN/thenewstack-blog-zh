# Sysdig 在其云原生安全平台中增加了异常检测和运行时分析功能

> 原文：<https://thenewstack.io/sysdig-adds-anomaly-detection-and-runtime-profiling-to-its-cloud-native-security-platform/>

云原生安全公司 Sysdig 的最新版本是为了应对现代分布式软件架构的复杂性。

Sysdig Secure 的 2.4 版本是该公司的[可见性和安全平台](https://sysdig.com/platform/) (VSP)的一部分，包括运行时配置文件和异常检测，它建立在今年早些时候宣布的 VSP 的先前更新的基础上，该更新基于“来自主机、容器、编制器、网络、进程和文件的丰富和深入的性能和安全数据”提供了[可见性改进](https://thenewstack.io/sysdig-update-provides-security-and-visibility-to-cloud-native-applications/)，这是通过使用[增强的 Berkeley 数据包过滤器](https://thenewstack.io/linux-technology-for-the-new-year-ebpf/) (eBPF)提供的。类似地，此版本添加的机器学习和异常检测也是使用相同的数据构建的。

Sysdig 将 VSP 称为“Kubernetes 环境的风险、健康和性能的第一个也是唯一一个统一视图。”

该公司在一份声明中写道，随着使用微服务的容器化应用程序由数千个不断变化的部分组成，人为配置的错误可能变得“不可避免”。

“我们审计所有衍生和运行的进程、文件系统、网络活动和每一个系统调用。说到文件系统，我们审计每一个读写活动，包括文件和目录，以及其他 Linux 东西，比如管道。对于网络活动，我们正在审核 TCP/UDP 端口以及传入和传出连接。Sysdig 的产品管理总监 Knox Anderson 在一次电子邮件采访中解释道:“它最终会成为大量的数据，然后用于分析运行时行为，并创建一个将预期活动列入白名单的配置文件。“使用自动生成的配置文件，用户可以轻松创建每个容器的安全和预期行为的策略。如果集装箱遵循不同的模式，Sysdig 会将其识别为异常活动。”

Sysdig 现在使用机器学习来分析运行时，并“创建一个可以自动应用于容器映像的策略集，为大规模环境提供可扩展的运行时防御，”根据公司声明。除了这些政策，Sysdig 还自动生成信任级别，它说这提供了“对容器行为的透明度和保证，而不是盲目地应用黑盒自动生成的配置文件。”

除了这些机器学习功能，Sysdig 本周还发布了 Falco Rule Builder，这是一个新的用户界面，扩展了[Falco Container Runtime Monitor](https://sysdig.com/opensource/falco/)，该公司[去年将其捐赠给了云本地计算基金会](https://thenewstack.io/cncf-adopts-sysdigs-falco-container-runtime-monitor/)。声明称，Falco Rule Builder 简化了规则的创建，允许用户“与 Falco 引擎进行可视化交互，以创建新的定制策略，这些策略可以根据主机和容器的安全和治理要求应用于它们，而不必具备 Falco 表达式和过滤命令的深厚技术知识”。

Falco Rule Builder 不仅试图简化规则创建，而且 Sysdig 希望通过托管 Falco 规则库使用户能够相互共享规则，从而使用户更容易找到和采用规则。Anderson 写道，每一个新的 Sysdig 版本都将制定新的规则，包括由 Sysdig 团队策划和支持的规则以及来自 Falco 社区本身的规则。

至于 Sysdig 的下一步是什么，Anderson 说他们计划继续在这些现有功能的基础上进行开发，着眼于秋季的 Kubernetes。

“随着开源 Sysdig 项目增加新的检测，我们将在每个版本中扩展规则库。在分析方面，我们将更容易将分析扩展到 Kubernetes 服务，而不仅仅是容器图像，”Anderson 写道。“众所周知 [Kubecon 将于 11 月](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/)到来，所以期待 Kubernetes 在大会上的一些新功能。”

云原生计算基金会和 KubeCon+CloudNativeCon 是新堆栈的赞助商。

由 Pixabay 的 JamesDeMers 制作的专题图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>