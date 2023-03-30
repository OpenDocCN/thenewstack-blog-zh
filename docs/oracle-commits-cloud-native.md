# 甲骨文支持 Kubernetes，致力于云计算原生计算

> 原文：<https://thenewstack.io/oracle-commits-cloud-native/>

[甲骨文](http://www.oracle.com)正在谋划转机。更准确地说，该公司大约在两年前开始转向开放水域，从那以后我们一直看到了结果。

就在那时，[公司收购了 StackEngine](https://thenewstack.io/oracle-settles-docker-ecosystem-stackengine-purchase/) ，这是一家总部位于得克萨斯州奥斯汀的集装箱管理和协调公司。甲骨文容器集团副总裁、前 StackEngine 首席执行官鲍勃·奎尔林说，正是这种 DNA 形成了我们今天看到的基于云的锁定避免甲骨文的核心。

这一方向变化的另一个象征是昨天，甲骨文加入了[云原生计算基金会](https://www.cncf.io/)、监督 [Kubernetes](https://kubernetes.io/) 、 [Containerd](https://containerd.io/) 和其他云原生开源项目的 [Linux 基金会项目](https://www.linuxfoundation.org/)。甲骨文[以白金级别加入该基金会](https://thenewstack.io/cncf-adds-oracle-onboards-envoy-jaeger-projects/)，将甲骨文工程副总裁 [Jon Mittelhauser](https://www.linkedin.com/in/jonmittelhauser/) 安排在 CNCF 管理委员会的投票席位上。

Quillin 说，他希望他的组织能够在迄今为止对 Kubernetes 的贡献之外，扩大与 CNCF 的合作。作为 Kubernetes 分委员会的成员，他希望明年能在这个项目中加入一些跨平台的管理功能。

他说，要做到这一点，CNCF 内部的联邦工作将是关键。“这是我们非常感兴趣的一个领域。我们有机会了解如何扩展 Kubernetes 管理，并使其跨云互操作。我们收到了许多在内部使用 Kubernetes 的客户的请求，他们希望它成为一个跨云的主控制平面。概念验证是有的，但让它成为企业级是我们和我们的客户感兴趣的一个领域，”Quillin 说。

作为最后一家加入云潮流的公司，Oracle 希望致力于跨云兼容性是可以理解的:这将使更受欢迎的云上的工作负载能够轻松转移到他们的云上。但是他们的先行者地位也使他们有权基于新技术而不是旧技术进行建设。Kubernetes 开源容器编排引擎似乎是一项新技术。

因此，Oracle 正在推动其基于 Oracle 云基础设施的高可用性 Kubernetes 集群。这个新产品基于 [Terraform](https://www.hashicorp.com/products/terraform/) 的[打包安装程序](https://github.com/oracle/terraform-kubernetes-installer/)，来自 [HashiCorp](https://www.hashicorp.com/) 的环境设置系统。

Quillin 的团队是这种新的以云为中心的甲骨文的先锋。他说整个团队是由开源老手和前 AWS 成员组成的。他们不是你的老派先知类型，围绕开放项目和标准策划《权力的游戏》级别的阴谋。

Quillin 说:“新的技术和技术专家不断涌现，但推动这一趋势的客户也要求拥有这种开放的云中立解决方案。”

“我们通过在 Kubernetes 项目中投入人力和精力来赢得我们的荣誉。根据我们的经验，我们将推出更多的工具和实用程序。我们也是这项技术的用户，所以与社区分享这项技术对我们内部有利。我们这样做是因为在这个新的容器组中，它存在于我们的 DNA 中。这也是客户开始将传统应用程序迁移到云中时所推动的事情，”Quillin 说。

Kubernetes 也被添加到 Oracle Linux 7 中。这使得 Oracle Linux 用户能够启动 Kubernetes 并在内部管理它。这最终将支持 Quillin 希望带给 Kubernetes 整体的内部和外部功能。

Quillin 说，多个 Kubernetes 集群的跨云管理应该对每个人都有帮助，但他补充说，甲骨文追求这些功能的真正原因是给客户他们想要的东西。

“甲骨文有一件事做得非常好:它倾听客户的声音。我们被市场的需求所驱使。他们希望拥有云中立性，他们希望在本地运行，并在云之间来回移动。我们听到了这一点，我们对此做出了承诺。

虽然神谕船的方向已经改变，但下面的舱底仍然是古老的神谕。当谈到标准团体和开源项目时，读者对 Oracle 保持极度谨慎是可以理解的。在过去，该公司给整个社区造成了浪费，比如它关闭了 OpenSolaris 项目，或者就在上个月，它彻底终止了 Solaris 项目。那是在甲骨文坚持开放容器倡议的标准工作之后，将最终提案推迟了六个月。

为什么？当然要包括 Solaris 支持！

甲骨文的开源之罪可以被列到日落时分。从导致 Hudson/Jenkins fork，到将 [CentOS](https://www.centos.org/) (最初是复制粘贴 Red Hat Linux)复制粘贴到 [Oracle Linux](https://www.oracle.com/linux/index.html) ，到用更多的 copyleft [AGPL](https://opensource.org/licenses/AGPL-3.0) 重新许可 [SleepyCat](https://opensource.org/licenses/Sleepycat) ，但是哦，等等，它只是碰巧扩展到您的 web 应用程序的源代码，使得 SleepyCat，一个内存中的 XML 数据库库，在没有向 Oracle 支付商业许可的情况下，对于商业活动来说基本上是无用的。

更不用说 Oracle proposative 花了几年时间试图通过反对、新提议和其他诡计来减缓 WS*规范的发展。然而，也许我们应该感谢他们:WS*死了，现在我们只是使用 REST。

然而，奎尔林说，甲骨文云摆脱了这个包袱。它被设计成开放的，并整合了 Oracle 贡献回代码的开源项目。这通常是甲骨文的首要问题:它从来不喜欢为开源做贡献。

例如，围绕着 [OpenJDK](http://openjdk.java.net/) ，Oracle 从来没有完全超越 [Java 社区进程](https://www.jcp.org/en/home/index)，它实际上控制了这个进程。它还雇佣了驱动 OpenJDK 的人员。它在 Oracle Linux 上的努力并不是因为它们在重新分发 CentOS 而不受欢迎，而是因为该公司没有向上游贡献其公平份额的补丁。Oracle 一直是一个糟糕的社区成员。

奎尔林说，这一切都已经改变或正在改变。即使在他的团队之外，Oracle 最近也向 Eclipse Foundation 贡献了 Java EE，而不是建立自己的新团队来充当傀儡，或者依赖现有的缓慢的 JCP。

该公司还发布了许多有趣的[集装箱工具](https://thenewstack.io/oracle-opens-oci-container-runtime/) : [轨道车](https://github.com/oracle/railcar)、[史密斯](https://github.com/oracle/smith)和[防撞车](https://github.com/oracle/crashcart)。

最后，奎尔林说，甲骨文正在被比战略或商业学位更大的力量所推动。“这在一定程度上是当今市场的现实。我们的信念推动着我们，但这也符合客户的行为。”

云本地计算基金会和 Linux 基金会分别是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>