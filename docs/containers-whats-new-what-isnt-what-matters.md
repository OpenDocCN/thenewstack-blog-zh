# 容器:什么是新的，什么不是，什么是重要的？

> 原文：<https://thenewstack.io/containers-whats-new-what-isnt-what-matters/>

我记得第一次有人兴奋地向我解释太阳系区域时，我对自己说，“Neato，你为什么要这么做？”当时我是一名软件开发人员，对系统和操作有基本的了解。我理解“什么”,但“为什么”并不明显。

那是十年前的事了，从那以后发生了很多事。

虽然已经有一些高调的项目和服务使用了容器(谷歌在 2007 年为 Linux 内核贡献了[cgroups](https://www.google.com/url?q=http%3A%2F%2Fen.wikipedia.org%2Fwiki%2FCgroups&sa=D&sntz=1&usg=AFQjCNF7NaPa3wfFqNFZTNFDnPLWBcOmeA)，特别是 [Heroku](https://www.heroku.com/) 、 [Cloud Foundry](https://www.cloudfoundry.org/) 和 [dotCloud](http://www.crunchbase.com/organization/dotcloud) 至少从 2011 年就开始基于容器)，但主流 IT 直到最近才开始对 Linux 容器的潜力感到兴奋。so什么变了？ 直截了当地说，主要的区别是引入了[【Docker】](https://www.google.com/url?q=https%3A%2F%2Fdocker.com%2F&sa=D&sntz=1&usg=AFQjCNGN_4SG8M9o-W8tb3scDMnzSJ9r5g)(最初是作为 dotCloud 的一个项目产生的) 。

Linux [操作系统虚拟化](https://www.google.com/url?q=http%3A%2F%2Fen.wikipedia.org%2Fwiki%2FOperating_system%25E2%2580%2593level_virtualization&sa=D&sntz=1&usg=AFQjCNESVydMkMh3hpokY6mvnmBW6JcfHw) 或“容器”一直是谷歌开发的管理和利用基础设施的主要工具之一。已经有许多项目提供了管理容器的工具，但是 Docker 提供了一个“如何”来使这项技术变得易于使用并吸引大量采用。，[OpenVZ](https://www.google.com/url?q=http%3A%2F%2Fopenvz.org%2FMain_Page&sa=D&sntz=1&usg=AFQjCNFd4h7PvcS0Sc0temhcPsZepl5tdg)，Google 的[lmctfy](https://www.google.com/url?q=https%3A%2F%2Fgithub.com%2Fgoogle%2Flmctfy&sa=D&sntz=1&usg=AFQjCNH2qgEEbdeIP7kF_tvRBNNRfDpa7g)，Cloud Foundry 的[warden](http://blog.pivotal.io/cloud-foundry-pivotal/features/cloud-foundry-container-technology-a-garden-overview)以及 now Docker 的 [libcontainer](https://github.com/docker/libcontainer) 都是管理 Linux 容器不同方面的项目。(Docker 一直在包装 LXC，直到 libcontainer 被创建出来，将接口统一到 cgroups、名称空间和任何其他底层的复杂部分。)这些项目有些已经有很多年了，那么 Docker 改变了什么呢？在我看来，有两件大事， 便利的缺省值和图像管理 ，这两件事都将容器的使用从一种为具有专业知识的人提供支持的技术转变为一种实际上普通开发人员在一两个小时内就能轻松安装并运行的技术。我参与的项目从 LXC/OpenVZ 和/或手工制作的写入时复制映像管理解决方案中获益匪浅。我们从未将这些点连接在一起，最终几乎没有在这些项目之外通用或可重用的东西。Docker 将图像版本控制和 Linux 容器结合在一起，打包用于大众消费。

> …至少，Docker 的繁荣正迫使组织重新审视阻碍他们的流程和架构

## 历史背景

在过去，服务器相对昂贵，充分利用一台服务器通常意味着在同一硬件上运行多个不相关的服务，这通常会导致软件依赖性冲突，以及争用资源的进程之间的操作混乱。运行虚拟机的虚拟机管理程序允许将服务拆分为更易于管理的部署，但在大规模部署时，虚拟化的开销会变得非常明显。容器提供了服务隔离，但不会比启动任何其他进程多多少开销。考虑容器的最好方式是一个内核空间支持多个用户空间，这些用户空间彼此不知道对方的存在(尽管实际上这并不完全正确)。为了完整性，像 OpenMirage 和 [OSv](http://osv.io/) 这样的项目更进了一步，在没有完全多用户操作系统开销的情况下运行应用程序，人们甚至可以想象未来一些服务可能会在硅片上实现。(这主要是考虑服务器，但像 [ZeroVM](http://www.zerovm.org/) 、 [Qubes OS](https://qubes-os.org/) 和 [Bromium](http://www.bromium.com/) 这样的项目在这些虚拟化堆栈的发展中也值得注意，尽管这些项目在实践中的侧重点略有不同。此外，网络和存储也在经历类似的演变。)

这些技术遵循相似的采用曲线，都是基于相对便宜、相对可用和更快的商用硬件的扩散。发行版促进了 Linux 的广泛采用，因为打包低级驱动程序、用户工具和软件降低了成功所需的专业知识水平，并提供了更好的用户体验。虚拟机管理程序是 IBM 在 20 世纪 60 年代首创的，但直到 20 世纪 90 年代末，随着实施和工具的出现，虚拟化技术变得触手可及，虚拟机管理程序的采用才出现爆炸式增长。Docker 有效地降低了使用容器的门槛，同时支持灵活的新工作流，生成可部署和索引的图像，可以私下或公开地共享和社交。

## 潜得更深一点

Docker 用一个统一的界面将映像管理和 Linux 容器进程管理结合在一起。图像是部署的标准化工件，使“运输容器”的比喻起作用。“容器”的另一个概念，根据 LXC (LinuX Containers)项目名称(与监狱、区域、分区或其他东西相对)，可能被认为是历史的偶然事件，是在 cgroups 和 namespaces 中运行的 Docker 进程。从这个意义上来说，容器更多的是“包容”，而不是标准化单元。描述 cgroups 和名称空间如何工作的最简单的方法是，cgroups 限制对资源的访问，而名称空间限制可见性。更具体地说，通过组合名称空间、cgroups 和映像，进程使用映像作为根文件系统，对 CPU、内存、挂载、用户、进程和网络等具有有限的访问和可见性，使它们看起来像是独立的机器。尝试查找文档，阅读关于 cgroups 和[名称空间](http://lwn.net/Articles/531114/)的资料，会很快让大多数人相信直接操作这些是复杂而麻烦的。LXC 用命令行工具包装了这一点，许多人都很好地利用了 LXC，包括在 libcontainer 之前的 Docker。B y 约束选项并提供默认值，Docker 意味着一般开发人员可以在安装一些包后几分钟内运行一个容器，更重要的是，对映像的任何修改都成为可部署的工件。从某种意义上来说，这并不新鲜，但以一种新颖的方式将现有的东西放在一起，可以成为一种倍增创新的力量。从来不知道 LXC 存在的人，以及在某些情况下从来没有使用过 Linux 的人正在使用 [boot2docker](https://github.com/boot2docker/boot2docker) 作为他们软件开发和部署过程的一部分。

> Docker 用一个统一的界面将图像管理和 Linux 容器进程管理结合在一起。

## 我们现在去哪里

容器最终将被主流 IT 所采用(所有 Solaris 和 BSD 管理员都点头称是“最终”)，但我个人打赌，在可预见的未来，容器的优势将在虚拟机中运行，如果不是永远。在云计算环境中尤其如此，但即使在防火墙后面，大多数组织也会乐意支付“虚拟化税”来换取虚拟机当前提供的成熟工具和安全性。虽然虚拟机具有更强的资源和安全隔离，但使用容器在虚拟机内分割容量可提供更灵活的资源粒度控制(这对于比较不同配置和规模的每 GB 公共云价格尤其有益)。还有一个可移植性的问题。一个 hypervisor 可以运行任何可以在现有机器架构上工作的操作系统，但是容器将依赖于特定的内核。适用于每个平台的 Docker 风格的映像管理和工作流会很棒，但这不会让 Linux 容器在 Windows(或 Solaris，或 BSD 等)上运行。)或反之亦然，这样做的尝试将不可避免地看起来可疑地像一个管理程序(或者更糟)。

当工作的主要产品变成可直接投入生产或作为进一步合作的基准的可部署图像时，使用 Docker 尤其会改变工作流程。能够在几秒钟内从单个映像部署完整容器的运营优势将改变应用程序的管理方式。Docker 的采用还将推动对 Linux 容器的更多了解，这可能会推动 cgroups 和名称空间功能的内核创新，以及一个工具生态系统，用于管理网络、存储和所有其他需要围绕容器处理的事情，以做有用的工作。这已经在发生了。如果 Docker 和微软之间最近的声明有任何指示，Linux 容器的采用也将有助于激励微软为他们的生态系统带来更好的进程隔离和资源限制。这些都是很棒的事情。

我们正在寻找更好的方法来创作软件，并把软件安装到电脑上。Docker 整合在一起的部分在技术上可能不是新的，但是这种新的技术组合是可行的，如果没有别的，Docker 的繁荣正迫使组织重新审视阻碍他们的流程和架构。我很喜欢电脑，但电脑的用处取决于运行在电脑上的软件。运行软件的计算机不是零和游戏。各种形状和大小的计算机将会越来越多；硬件、虚拟机管理程序和容器。大多数解决方案揭示(或创造)新的问题(机会？).容器不能解决我们所有的问题，但是容器的采用代表了由对速度和规模的需求驱动的技术发展中的一个转折点。

这应该足以让我们暂时消化，也是我希望下次讨论的一个很好的继续，解决大规模快速安全行驶的问题。

研究生毕业后，fate 将 Andrew Clay Shafer 带到了风险投资创业公司，在那里他迷上了在人与技术的交叉点上创造价值，同时优化工具和流程。他目前在 Pivotal 担任高级技术总监，但一路走来，Andrew 共同创立了 Puppet Labs，是 Cloudscaling 的第一位工程副总裁，作为 devopsdays 的核心组织者帮助了许多活动，并在从 OpenStack 到组织学习的各种会议上做了很多演讲。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>