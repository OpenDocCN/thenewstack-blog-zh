# 微软如何将重心转移到开源上

> 原文：<https://thenewstack.io/microsoft-shifting-emphasis-open-source/>

开源正在成为事实上的软件开发模型。今天，每个软件公司，尤其是在企业领域，都在处理大量的开源软件。微软也不例外。

事实上，微软似乎正在加速这项工作，赶上传统上与开源生态系统联系更紧密的竞争对手。根据来自[云本地计算基金会](https://www.cncf.io/)的汇编，该公司拥有任何一个实体[最多的 500 强开源项目。微软有 24 个项目，远远领先于谷歌和 Pivotal(各有 7 个)和红帽(有 6 个)。](https://www.cncf.io/blog/2017/06/05/30-highest-velocity-open-source-projects)

拥有自己的开源项目，比如[。Net Core](https://www.microsoft.com/net/core#windowsvs2017) 、Visual Studio 代码和 TypeScript，微软从外部开源社区获得了相当大的帮助。CoreFX 中超过 60%的贡献。Net 核心库和 [CoreCLR](https://github.com/dotnet/CoreCLR) 。Net 核心运行时来自微软之外。该公司正在为外部开源项目做出重大贡献，如 Linux、Docker 和 Kubernetes。

## 新文化

微软的第一个开源软件可以追溯到 2004 年，当时该公司发布了一个名为 [WiX](http://wixtoolset.org/) 的 Windows 开发工具集，它带有一个编译器、一个链接器、一个 lib 工具和一个反编译程序。从那以后，该公司一直在发布开源软件。

2012 年，微软成为 Linux 内核的最大贡献者。 [Ky Srinivasan](https://www.linkedin.com/in/ky-srinivasan-590b5a3/) 现在是微软 Windows 服务器部门的软件架构师，他是推动许多贡献的工程师，最关心的是促进 Hyper-V 对 Linux 的支持。“从那以后，我一直在努力让 Linux 运行得和其他平台一样好，如果不是更好的话，”他说。

Srinivasan 的工作也使他成为了 Linux 的第一贡献者。他的第二个优先任务是将这些代码放入主线树中，这样其他发行版就可以开箱即用地将 Linux 支持移植到 Hyper-V 上。今天，所有主要的 Linux 供应商都在这么做。

通过这项工作，微软真正看到了开源的第一手好处。Srinivasan 说，Linux 在微软平台上如此成功，以至于微软对 Hyper-V 相关补丁的贡献已经下降到略低于 60%。其余的补丁来自社区，许多来自 Linux 发行商，如 SUSE、Red Hat 和 Canonical。

在 Azure 方面，微软正在与所有主要的商业 Linux 供应商合作——包括红帽、SUSE、Canonical、T2、CoreOS 等。—和其他社区，以确保客户可以在 Azure 上运行他们喜欢的 Linux 工作负载。

对于开发人员来说，微软现在正在将 Linux 工具原生引入 Windows。微软一直在与 Canonical 密切合作，为 Linux 构建 [Windows 子系统](https://thenewstack.io/windows-10-creators-update-means-windows-subsystem-linux/) (WSL)，使开发人员、系统管理员和运营团队能够在 Windows 上原生使用所有*NIX 功能，允许他们管理在 Azure 或任何其他云上运行的 Linux 工作负载。

Linux 发行商 [Canonical](https://www.canonical.com/) 的首席执行官马克·舒托沃尔斯认为这是一件非常好的事情:“我认为这将意味着更多的用户。更多错误报告。更多的参与。更多眼球。更多的参与。更多的用法。我认为这一切都很好。”

## 前方的路

当微软在 Linux 世界中艰难前行时，它面临着一些严峻的挑战。Linux 不是为在 Windows 上运行而设计的，而 Windows 也不是为运行 Linux 而设计的。这就是“一起工作”部分发挥作用的地方。

![](img/0c82bea14ac9c6693e3cf924bd3c917d.png)

特征图片:Docker 技术人员 Patrick Chanezon 在 Dockercon EU 2015 上，两侧是微软 Azure 架构师 John Gossman(左)和微软首席编程经理 Taylor Brown。

“我们试图将这两个不同的世界融合在一起，并且一直以来我们都能够让它们很好地合作。这是一个技术上的挑战，我们已经或多或少地解决了这个问题，并且知道该怎么做，因为双方现在都愿意对话。他们能够影响 Windows 的设计，以更好地支持 Linux，我们也能够与 Linux 社区交流，并确保事情以不妨碍运行 Windows 的方式进行，”Srinivasan 说。

微软也一直在与 Docker 合作，为 Windows 和 Azure 创建 Docker 的特别版本。这两家公司在过去几年的共同努力导致了另一个叫做 LinuxKit 的开源项目。

Windows Server 和 Hyper-V Containers 的首席项目经理[泰勒布朗](https://www.linkedin.com/in/taylorbro/)指出，LinuxKit 是基于微软在 [boot2docker](http://boot2docker.io/) 项目上所做的工作。微软还致力于将 Linux 容器引入 Windows 服务器，为运行在 Windows 上的 Linux 容器增加了对 Hyper-V 隔离的支持。这意味着 DockerHub 上托管的超过 900，000 个 Docker 容器可以在 Windows 服务器上运行，将这些容器带给用户。

今年，[微软还收购了 Deis](https://techcrunch.com/2017/04/10/microsoft-acquires-container-platform-deis/) 来引入内部的容器专业技术。通过这次收购，微软也成为了 [Kubernetes](/category/kubernetes/) 生态系统的主要贡献者，其项目包括[工作流](https://deis.com/workflow)、[掌舵人](https://helm.sh/)和[管家](https://github.com/deis/steward)。

## 帮助生态系统

开源是关于社区和生态系统的。没有健康的生态系统，任何公司都无法生存，微软对此非常清楚。该公司一直在开源社区投入巨资。它加入了 Linux 基金会，微软 Azure 的首席架构师 John Gossman 成为了董事会成员。该公司[最近](https://azure.microsoft.com/en-us/blog/microsoft-joins-cloud-foundry-foundation/?v=17.23h)也作为顶级成员加入了云铸造基金会。

该公司在 GitHub 上有超过 15，000 名贡献者。该公司表示，超过 6000 名员工为开源项目做出了贡献，并发布了超过 3000 个开源项目。微软的开源程序办公室跟踪近 10，000 个开源组件，从 NPM 软件包到微软团队使用的 Linux 发行版。

该公司最近为 Azure Networking switch 编写了一个名为 [SONiC](https://azure.microsoft.com/en-us/blog/sonic-the-networking-switch-software-that-powers-the-microsoft-global-cloud/) 的操作系统，它由 Linux 驱动。是的，微软正在自己的基础设施中使用 Linux。该公司最近还将 Windows 开发转移到了 Git 。

SONiC 并不是该公司开源消费的孤立案例。微软是开源软件的忠实消费者。“我们有一个超过 10，000 种不同开源组件的列表，我实际上是该列表的批准者之一，”Gossman 说。

以下是微软内部使用和维护的一些开源技术:

*   Kafka: LinkedIn 和 Bing 是 Kafka 最大的两个用户。
*   Linux:Azure 上大约三分之一的虚拟机运行 Linux。
*   [LightGBM](https://github.com/Microsoft/LightGBM) 和[微软认知工具包](https://github.com/Microsoft/CNTK) (CNTK)机器学习框架。
*   Azure 上基于 Linux 的 Hadoop 和 Spark 服务。
*   Azure 上的 Postgres 和 MySQL 托管服务。
*   [Azure Functions](https://azure.microsoft.com/en-us/services/functions/) ，一款开源的无服务器功能即服务。
*   [Chef](https://www.chef.io/) 用于管理 Azure、Office 365 和 Bing 内部的数千个节点。

该公司投入巨资雇佣最优秀的开源人才。微软现在是一些开源技术的创始人和顶级开发者的家园，包括:

*   [布伦丹·伯恩斯](https://www.linkedin.com/in/brendan-burns-487aa590/):伯恩斯是 Kubernetes 的联合创始人，现在是微软的一名架构师，领导着为上游 Kubernetes 做出贡献的团队。
*   Gabe Monroy : Monroy 创建了 Deis，现在是微软容器的首席项目经理。
*   约翰·霍华德:霍华德是 Azure 的软件工程师，也是过去 12 个月 Docker 的主要撰稿人。
*   [安德斯·海尔斯伯格](https://github.com/ahejlsberg):Hejlsberg 是 C#和 Turbo Pascal 的创造者，他是一名领导 Typescript 开发的技术人员。
*   [Erich Gamma](https://github.com/egamma) :一位杰出的工程师，是 Eclipse 项目的创始人之一，也是软件工程教科书《[设计模式:可重用面向对象软件的元素](https://www.amazon.com/gp/product/0201633612/ref=as_li_qf_sp_asin_il_tl?ie=UTF8&tag=the0757-20&camp=1789&creative=9325&linkCode=as2&creativeASIN=0201633612&linkId=7ddc75bdb1ef5efb1a28a46a559a9b59)》的“四人帮”的作者，Gamma 领导着 Visual Studio 代码团队。
*   罗斯·加德勒:前 Apache 软件基金会主席，加德勒现在是 Azure 容器服务和开源项目的项目经理。
*   Maggie Pint : Pint 是 Azure Site Reliability Engineering(SRE)的软件工程师主管，也是一个名为 [Moment.js](https://momentjs.com/) 的流行开源库的维护者，也是 JavaScript 基金会对 [TC39](https://www.ecma-international.org/memento/TC39.htm) 的代表。

## 文化冲击

所有这些工作意味着微软内部文化的重大转变，微软长期以来一直是一家专有公司。Srinivasan 开玩笑地回忆说，当他在 2011 年加入微软时，作为一名铁杆 Linux 工程师，没有太多人愿意和他交谈，他一直在对 Windows 进行逆向工程。

但是随着时间的推移，事情发生了变化。“现在我几乎参与了 Windows 内核团队的所有设计讨论，我的团队和 Windows 内核开发架构团队之间的关系非常密切，”他说。

通过收购 Deis 进入微软的软件工程师 Michelle Noorali 也讲述了同样的故事。她现在是微软 Azure 的高级软件工程师。诺拉莉以前从未在大公司工作过，她只和初创公司合作过，所以很明显，当她跳槽到微软时，她非常犹豫。“我对未来非常谨慎，但老实说，我印象深刻。人们真的很欣赏我们正在做的事情，Deis 团队在开源社区正在做的事情，希望这成为文化的一部分，并张开双臂欢迎它，”她说。

斯里尼瓦桑将这一变化归功于微软的最高领导层。

“正如我们所说，微软内部的文化正在发生变化。Linux 专业知识正在整个公司传播。如你所知，微软内部有许多嵌入式 Linux 部署，所以这是一个对 Linux 更友好的地方，每天都比以前更友好。现在真的很好，”斯里尼瓦桑说。

微软将于 6 月 21 日星期三在 Azure OpenDev 虚拟会议上讨论开源的所有问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>