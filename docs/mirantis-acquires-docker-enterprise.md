# 米兰蒂斯收购 Docker 企业

> 原文：<https://thenewstack.io/mirantis-acquires-docker-enterprise/>

*TNS founder and publisher [Alex Williams](https://thenewstack.io/author/alex/) contributed to this article.*

[云咨询公司 Mirantis](https://www.mirantis.com/) 以 OpenStack 为根基，最近专注于 Kubernetes，已经收购了 Docker 的企业业务，该业务由 [Docker 企业技术平台](https://www.docker.com/solutions/docker-enterprise-solutions)和所有相关知识产权、大约 400 名员工中的 300 人、750 家企业客户以及所有企业合作伙伴组成。Docker 企业技术平台本身包括 [Docker 容器引擎](https://docs.docker.com/engine/)、 [Docker 可信注册中心](https://docs.docker.com/ee/dtr/)、 [Docker Kubernetes 服务](https://www.docker.com/products/kubernetes)、[通用控制平面](https://docs.docker.com/ee/ucp/)和 [Docker 边缘技术](https://www.docker.com/solutions/docker-edge)。为 Docker 企业业务支付的金额尚未披露。

Mirantis 首席执行官兼联合创始人 Adrian Ionel 表示，此次收购“可能占 Docker 业务的 90%”，还将包括与微软和其他公司的合作，所有这些都旨在加速 Kubernetes 在 Mirantis 中的努力。

“我们收购 Docker Enterprise 有几个原因。一是加快我们向全球提供面向多云和混合用例的 Kubernetes 即服务的进程，许多 Docker 企业客户实际上都在内部使用 Kubernetes。我们还收购了 Docker Enterprise，因为我们认为集装箱化是大势所趋。这是现代应用程序构建的方式，也是现有应用程序重新现代化的方式。“这是我们已经实现的愿景的巨大加速器。我们还收购了 Docker Enterprise，因为我们对技术人才的水平感到兴奋。我们相信，Docker Enterprise 拥有当今世界上最优秀的云原生基础架构人员——出色的工程师——他们将非常适合我们在 Mirantis 的工程文化。”

Ionel 还指出，他不能忽视 Docker“巨大的客户群”的重要性，他说这部分客户约占财富 100 强的三分之一，全球 500 强中约有 20%已经在使用 Docker Enterprise。值得注意的是，此次收购不包括 [Docker Desktop](https://www.docker.com/products/docker-desktop) ，尽管 [Docker Enterprise 3.0 据说](https://thenewstack.io/docker-enterprise-3-0-simplifies-kubernetes-management/)整合了该接口，以成为“唯一能够无缝管理从开发者桌面到 Kubernetes 管理的基于云或内部的生产环境的容器的商业软件”，Docker 产品营销总监 [Jenny Fong](https://www.linkedin.com/in/jcfong/) 当时如是说。Ionel 解释道，Docker Desktop 顾名思义是一款面向开发者的桌面产品。

“99%左右的企业将[Docker 桌面]作为社区版本与 Docker Enterprise 结合使用，”他说。“我们和 Docker 致力于确保持续的无缝集成。”

在未来的其他努力方面，该公司在一份声明中提供了“与 Docker，Inc .开源和合作的承诺”，写道“Mirantis 和 Docker 将在核心上游技术上合作，为开源开发做出贡献。此外，Mirantis 和 Docker 将继续确保其产品与 Docker 桌面和 Docker Hub 上的 Docker 以及 Docker 企业容器平台上的 Mirantis 之间的集成。”根据 Ionel 的说法，这些特定的核心技术还包括容器引擎、莫比、Compose，以及“其他一些与世界范围内使用和采用的容器相关的技术”

一篇宣布收购的博客文章暗示 Docker Swarm 将被淘汰，Ionel 写道“未来的主要指挥者是 Kubernetes。Mirantis 致力于为所有 Docker 企业平台客户提供出色的体验，目前预计支持 Swarm 至少两年，具体取决于客户对路线图的投入。米兰蒂斯还在评估让 Swarm 用户更容易过渡到 Kubernetes 的选项。

## Docker 让开发人员的工作流程重回正轨

Docker 于 2013 年首次推出，将核心 Linux 技术带入主流，并通过其对 Linux 容器技术(LXC)的独特扩展成为无处不在的容器化工具，该技术[提供了可移植性、以应用程序为中心的方法、自动构建、版本控制、重用、共享，以及当时强大的工具生态系统](https://docs.docker.com/v17.12/engine/faq/#what-does-docker-technology-add-to-just-plain-lxc)。从那时起，Docker 就一直是基于容器的架构的象征。在 Kubernetes 之前，Docker 获得了传奇般的追随者，以相当快的速度增长，获得了 2.79 亿美元的资金。随着公司越来越深入到企业中，这种势头逐渐消失，不知何故失去了当它对开发人员具有如此内在的吸引力时如此明显的兴奋感。他们希望被认为是乏味的，在这方面，他们肯定没有让人失望。

随着[新栈首次报道](https://thenewstack.io/docker-fork-talk-split-now-table/)，随着 Docker 1.12 中包含 Docker Swarm，挫败感达到顶峰，并最终导致分叉的威胁。通过 Swarm，Docker Engine 允许用户管理复杂的容器化应用程序，而不需要额外的软件，使用与开发人员熟悉的 Docker 容器相同的命令行结构和语法。Docker 编排功能被选择加入；它们必须由用户激活。尽管不选择可能会导致向后兼容问题。

这一举动让它上了 Kubernetes 的速成班，Kubernetes 是由谷歌开源的，其编排能力已经开始在市场上崛起。

Swarm 的问题变得如此激烈，以至于导致了分叉的威胁。但是 Docker 继续把精力投入到企业中，尽管他们处于劣势，与 Kubernetes 社区隔离。

Docker 对公司和开源项目采用了相同的名字，这加剧了问题，造成了固有的混乱。然后，该公司放弃了它的开发合作伙伴，他们搬到了 Kubernetes，正如我们现在所知，赢得了这场战斗。两年前，Docker 试图纠正路线，先是[将 Kubernetes 添加到 Docker Swarm](https://thenewstack.io/docker-fully-embraces-kubernetes/) 中，六个月后[将其添加到 Docker Enterprise](https://thenewstack.io/docker-enterprise-edition-2-0-embraces-kubernetes/) 中，但现在该公司表示，它已经决定转而关注其根源。回到开发者社区？这当然会是一个不错的转变，甚至可能带回一些当年让该公司如此引人注目的活力。

“Docker 通过专注于推进开发人员在构建、共享和运行现代应用程序时的工作流程，开创了一个回归本源的新时代。“作为这一调整的一部分，米兰蒂斯宣布收购了 Docker 企业平台业务，”Docker 发言人在一封电子邮件中写道。展望未来，我们将扩大 Docker Desktop 和 Docker Hub 在现代应用开发人员工作流程中的角色。具体来说，我们正在投资扩展我们的云服务，以使开发人员能够快速发现构建应用程序时使用的技术，轻松地与队友和社区共享这些应用程序，并在任何 Kubernetes 端点上流畅地运行应用程序，无论是在本地还是在云中。"

New Stack 的分析师劳伦斯·赫克特(Lawrence Hecht)称，这次收购与其说是重新聚焦，不如说是未能实现其潜力。

“这标志着一项失败努力的结束，即创造一种能够证明其获得的所有风险投资(根据 Crunchbase 的数据，通过 9 轮融资获得 2.729 亿美元)是合理的产品。愿景是利用 Docker 庞大的用户群赚钱，并驾驭容器浪潮。Hecht 写道:“他们认为可以把 Docker Enterprise 作为一个平台出售。“Docker 试图将运行时与映像注册表、开发工具和专业服务捆绑在一起，但从未获得成功，因为 Docker Enterprise 只有 750 个付费客户。”

尽管如此，Hecht 指出， [Docker 引擎](https://www.docker.com/products/container-runtime)的采用仍然“非常强劲”，根据[牧场主调查](https://info.rancher.com/kubernetes-industry-survey-key-findings)，96%的容器用户使用它，32%的用户也使用 containerd，Docker [在 2016 年底将](https://thenewstack.io/docker-spins-containerd-independent-open-source-project/)作为独立的开源项目推出

Hecht 继续称 Docker 对 Docker Enterprise 的关注是“硅谷过度行为的警示故事”，并假设“如果它保持早期对开发人员宣传的关注，例如通过 [Meetups](https://thenewstack.io/focused-enterprise-docker-doesnt-fear-kubernetes/) ，它可能会有一个庞大的客户群，他们支付相对较少的费用来许可其软件。”

## 米兰蒂斯以专业服务支持 Docker Enterprise

至于 Docker Enterprise 的未来，Mirantis 首席执行官 Adrian Ionel 表示，该公司将保留其名称，并计划“继续全力发展”，尽管增加了他们自己的“更强大、更强大、功能更丰富的 Kubernetes 堆栈”，最终目标是“消除整个平台升级和运营管理的任何管理开销。”

“对于现有的 Docker 企业客户，他们将有机会获得更多的白手套体验，为那些想要它的客户，”Ionel 说。“他们将拥有更丰富的功能和更强大的 Kubernetes 功能，他们还可以访问 Mirantis deep professional service bench，帮助他们更快地将应用程序容器化，并将其部署在公共云和本地基础设施上。”

为了进一步了解 Mirantis 如何看待 Docker Enterprise 在其指导下的发展，该公司将于 2019 年 11 月 21 日星期四上午 9 点(太平洋标准时间)举办一场网络研讨会，Mirantis 营销高级副总裁 Dave Van Everen 将出席。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>