# io:为什么我们增加了 Kubernetes 的支持

> 原文：<https://thenewstack.io/containership-ceo-phil-dougherty-added-kubernetes-support/>

编者按:周二，容器编排服务提供商

[Containership](http://containership.io/)

宣布推出完全管理的 Kubernetes 服务，为客户提供内置工具。在本文中，Containership 首席执行官 Phil Dougherty 是新堆栈和

[a recent contributor](https://thenewstack.io/wal-mart-kicks-partners-off-amazons-cloud-implications-organizations/)

，讨论了这一举措背后的战略，以及为什么他认为 Kubernetes 本身可能是一个对许多组织来说太难接受的平台——至少在没有帮助的情况下是如此。

我们在 2014 年成立了 Containership，其使命是:打造一种产品，简化令人困惑的云自动化和开发运维世界。构建一个易于安装、易于管理、易于升级的工具，并提供大多数用户需要的最重要的功能。让企业使用统一的工作流程，快速轻松地将容器化的工作负载部署到他们选择的提供商。让这些企业重新开始生产他们的产品。

当我们在开源项目上开始最初的工作时，集群调度器还处于起步阶段。这些选项要么极其沉重和复杂，要么在实施时使用起来很麻烦，而且脆弱到不稳定的程度。Mesos 是当时唯一明确的选择，除非你想和来自 CoreOS 的 [Flynn](https://flynn.io/) 、 [Deis](https://deis.com/) 或 [Fleet 碰碰运气。](https://github.com/coreos/fleet)

我们还希望确保避免走上使用 [systemd](https://thenewstack.io/systemd-vs-linux-kernel/) 来管理服务配置的道路(就像 Fleet 所做的那样)，并且我们希望避免像 Mesos 这样的系统的复杂性，因为它的许多不同的分布式系统都需要维护它们自己的 quorums，升级会让你濒临心脏病发作的边缘。

从那以后，我们通过引入我们的集装箱即服务产品 Containership Cloud，在开源项目上进行了显著扩展。我们添加了日志记录、指标、防火墙、全功能负载平衡以及跨提供商快照和恢复。我们已经从只有几个主要的云提供商发展到支持 14 个。通过所有这些产品迭代，我们仍然设法将关注和保持简单性作为我们的目标。

## 我们读了很多书，和很多人交谈

 [菲尔·多尔蒂

Phil Dougherty 是 ContainerShip 的联合创始人兼首席执行官，container ship 为您在多个云提供商之间编排容器化应用程序和微服务提供了最简单的方法。Phil 从事 web 托管和系统工作已经超过十年，在纽约市的托管公司领导团队，也是零售商的领先移动商务提供商。](https://containership.io) 

有一段时间，气氛很紧张，因为每个人和他们的母亲都在努力尝试在集装箱调度领域获得牵引力。[牧场主养了**牛**](https://github.com/rancher/cattle)； [CoreOS](https://coreos.com/) 拥有也被 Deis 使用的舰队；中间层推动了 Mesos 及其马拉松框架；Docker 收购了 Tutum，并致力于让自己的调度程序 Swarm 深入用户的心灵。然后就像火箭船上的独角兽一样，谷歌的 Kubernetes 项目爆发了，其他人都被甩在了后面。

最终尘埃落定，留下的是一个 Kubernetes 项目，它几乎每次在 DevOps 圈子里被提及时都会引起一场同时的愤怒。Google 在可伸缩性方面的声誉，加上它在发展和培育开源项目方面的经验，导致了发展最快的开源项目，并在许多人的心目中成为编排战的明显赢家。

与 Docker 相比，谷歌相对开放的状态，加上它对社区的更大关注——以将对 Kubernetes 的控制权让给[云本地计算基金会](https://www.cncf.io/)为标志——给了用户信心，他们可以建立在 Kubernetes 提供的基础上，而不用担心它明天会消失，被晾在一边。

## 提高“高水平”的标准

Kubernetes 位于宣传图表的顶端，这是有充分理由的，但如果你没有准备好在深水区游泳，只是用容器沾湿你的脚，你可能会淹没在选项和配置中。带有 Kubernetes 的 Containership Cloud 使入门变得容易，并为今天希望做这种称为 DevOps 的事情的开发团队带来了自助服务。

我们增加了对 Kubernetes 的一流支持，作为集装箱船云完全支持的底层调度程序。

你看，Kubernetes 本身就很强大，但是相当低级。如今，您可以很容易地在您的笔记本电脑上获得并运行环境，但是在生产中运行它仍然需要大量艰苦的工作，集成所需的系统以实现负载平衡、DNS、卷管理和一系列其他事情。

通过将 Kubernetes 集成到我们自己的 CaaS 平台中，我们能够让用户高枕无忧。他们将会知道他们在流程编排上是明显的赢家。他们已经对 Google 交付稳定且可扩展的项目的能力充满信心，但现在他们可以通过我们更简单的界面来获得这种能力，使服务管理和在团队环境中工作变得更容易。

幸运的是，集装箱船不仅仅是一个围绕 Kubernetes API 的用户界面。在 Kubernetes 的支持下，我们将产品中已经存在的所有高级功能和特性带到了桌面上。在我们支持的任何提供商上，在几分钟内启动 Kubernetes 集群。通过 UI/API/或 CLI 管理防火墙规则、负载平衡器、服务发现、数据量等。最重要的是，我们的快照功能完全相同，允许您克隆整个 Kubernetes 集群来创建新环境，实施灾难恢复，或者扩展和迁移到其他可用性区域、地区或云提供商。

## 前进的道路

我们对 Kubernetes 支持的首次发布标志着我们向为开发者提供首要的云计算平台发展的一个里程碑。目前，我们支持我们自己的 scheduler 和 Kubernetes 之间的通用特性，但是我们将继续添加额外的功能，帮助团队充分利用项目提供的选项和特性。

当我们朝着模糊然后消除云提供商和世界私有数据中心之间的界限的目标努力时，Kubernetes 将提供一个稳定的、可扩展的、社区驱动的构建模块，让用户相信他们是在开放的基础上构建的，不会再把自己锁在里面。

云本地计算基金会、T2、CoreOS 和 Containership 是新堆栈的赞助商。

专题图片:加拿大图书馆和档案馆公开的大约 1885 年，加拿大太平洋铁路的[最后一根钉子被钉进了横贯大陆的铁路](https://en.wikipedia.org/wiki/Transcontinental_railroad#/media/File:LastSpike_Craigellachie_BC_Canada.jpg)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>