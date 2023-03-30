# 微软，Windows 容器红帽团队，OpenShift 上的 SQL Server

> 原文：<https://thenewstack.io/microsoft-red-hat-team-combo-hybrid-tech-windows-containers-sql-server/>

尽管对容器的推动主要意味着 Linux 容器，微软和 Red Hat 也在解决构建 Windows 容器的挑战。

他们的计划是在 [Red Hat OpenShift](https://www.openshift.com/) 、 [Red Hat OpenShift 专用于微软 Azure](https://www.openshift.com/dedicated/index.html) 和 [SQL Server 上提供对 Windows Server 容器的原生支持，作为在 Red Hat OpenShift](https://thenewstack.io/sql-server-2017-brings-microsofts-database-linux-container-worlds/) 上使用的容器。

Red Hat 负责技术业务发展和业务架构的副总裁 Mike Ferris 将其描述为两家公司 2015 年[合作协议](https://thenewstack.io/microsoft-red-hat-partnership-signifies-rapidly-evolving-ecosystem/)的扩展，在该协议中，他们承诺支持混合 it 环境。这一最新举措将简化和推动容器在那里的采用。

微软 Azure 团队首席架构师 John Gossman 表示:“如果你进入任何一家大型企业，你都会发现他们混合使用 Windows 和 RHEL(Red Hat Enterprise Linux)。

“当我开始研究这个问题时，我发现一个有趣的事情，不是营销部门在使用 Windows，而是(另一个)部门在使用 RHEL。有许多部门混合了这些成分。…他们可能使用 LAMP 堆栈，并为 web 服务器本身运行 RHEL，但 SQL Server 可能是该公司使用的数据库。”

两家公司联合计划提供:

**Windows Server containers on Red Hat open shift**，这是 Red Hat 的企业级、 [Kubernetes](/category/kubernetes/) 为基础的容器应用平台。Red Hat 将其吹捧为第一个从开源 Kubernetes 项目构建的容器应用程序平台，以在混合云的多个环境中的单个平台上支持 Linux 和 Windows 容器工作负载。

这是 Kubernetes 内部正在进行的一些工作组的扩展。

“但通过这种结盟——将其与平台的产品化版本配对并获得这种集成支持——这些是重点关注的关键领域，以确保企业客户可以在这两个不同的平台都转向集装箱化时采用它们，”Ferris 说。

这在去年 5 月的红帽峰会上进行了演示，预计将在 2018 年春天作为技术预览推出。

**微软 Azure 上的 Red Hat OpenShift 和微软 Azure Stack 上的 Red Hat Enterprise Linux。** OpenShift Dedicated 是红帽的容器平台即托管云服务。T2 已经在亚马逊网络服务和谷歌云平台上为 Linux 容器提供服务。

微软和红帽工程师将致力于提供标准化的企业性能和对运行在 Azure 上的 OpenShift 的支持。2015 年交易的一部分是为他们的联合技术提供共址工程支持。

Azure 上专用的 OpenShift 预计 2018 年初上市。

他们还将致力于优化运行在 Microsoft Azure Stack 上的 RHEL 工作负载，这是一种针对内部环境的扩展。

**红帽企业版 Linux 上的 SQL Server 和红帽 OpenShift** 红帽最近做了更新[。NET Core 2.0](https://blogs.msdn.microsoft.com/dotnet/2017/08/14/announcing-net-core-2-0/) 开发平台在 OpenShift 中作为容器提供。这两家公司计划在今年秋天晚些时候将微软的 SQL Server for Linux 引入 Red Hat Enterprise Linux 和 Red Hat OpenShift。

7 月，微软发布了 Azure Container Instances(T8),它让你在几秒钟内用你选择的内存和 CPU 内核旋转一个容器，使用按秒计费。到目前为止，ACI 仅作为技术预览版用于 Linux，但它也计划添加 Windows 支持。

根据 451 Research 分析师 Jay Lyman 的说法，红帽和微软在容器上的合作是由两种主要力量推动的。

首先，两家公司都从他们的合作中受益匪浅，共同支持红帽在微软的 Azure 云和微软的。红帽 OpenShift 上的 NET Core。其次，这两家公司都是将容器集成到他们的软件和策略中的最积极的成熟供应商。

“这也进一步证明了容器在企业中继续变得越来越主流，并超越了 Linux 上的容器，达到了 Windows 容器独树一帜的地步，”他说。“最后，它还强调了 Linux 和 Windows 的混合环境仍然是企业 it 的标准。”

451 Research 预测应用容器市场到 2020 年将增长到 27 亿美元。

分析师克里斯·赖利也认为这对两家公司都有好处，也许对红帽公司更有利，但也可能造成混乱。

“他们现有的 OpenShift 基础和 REHL 用户可能会大吃一惊，试图理解这对他们的云战略意味着什么，”他说。

“如果你正在考虑将 OpenShift 迁移到 Azure，你为什么不考虑将 OpenShift 一起抛弃呢？我对 Windows 容器持怀疑态度，因为它们几乎和虚拟机一样重，而且我认为 SQL Server 的采用已经不如以前了。所以在 OpenShift 中运行这些似乎和在 Azure 上运行专用的 OpenShift 没有相同的价值。对于现有的 OpenShift 企业用户来说，这实际上是一个非常有趣的产品。”

[红帽](https://www.openshift.com/)是新栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>