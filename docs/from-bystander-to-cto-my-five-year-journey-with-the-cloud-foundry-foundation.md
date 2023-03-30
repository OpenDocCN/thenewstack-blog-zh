# Cloud Foundry 如何感受到 Kubernetes 效应

> 原文：<https://thenewstack.io/from-bystander-to-cto-my-five-year-journey-with-the-cloud-foundry-foundation/>

[云代工厂](https://www.cloudfoundry.org/)赞助本帖。

 [Chip Childers

Chip 在大规模计算和开源软件方面已经花了超过 18 年的时间。2015 年，他成为云铸造基金会的联合创始人，担任技术参谋长。他是 Apache CloudStack 的第一任副总裁，在 SunGard 领导企业云服务时，他帮助推动了该平台的发展，后来又担任 Cumulogic 的产品战略副总裁。在 SunGard 之前，他领导了包括 IRS.gov、USMint.gov、美林和 SEI Investments 在内的组织的任务关键型应用程序的重建工作。](https://www.cloudfoundry.org/) 

我最近一直在反思，Cloud Foundry 项目在短短五年内发生了多大的变化。

我的一个观察是，自 2015 年以来，开源生态系统和企业计算市场变得有多么不同。因此，Cloud Foundry 和围绕它的更广泛的生态系统的共同发展导致了在不同的方向上相互拉动和推动。

这同时也是我职业生涯中最快也是最长的五年。这是因为这种快速变化的持续推/拉的双重性，以及这一切背后的缓慢转变。

现在称为 Cloud Foundry 的最初想法是在 2009 年 VMware 内部产生的。直到 2011 年 4 月，该项目才正式宣布。我记得在观看公告视频流时，我清楚地想到，他们所做的正是市场需要的。此次发布完全是关于一个专注于简化应用程序开发和部署的平台。在接下来的几年里，我观察了这个产品的发展(以及转手)。2014 年，当我编写第一个集成到平台中的 service broker 时，我离社区更近了一点。(对于那些不熟悉的人来说，服务代理是如何将数据库等功能集成到平台中的。)

到 2015 年，围绕现在开源的 Cloud Foundry 项目，一个年轻的开源社区已经形成。Cloud Foundry 基金会成立于 2015 年 1 月下旬。这是我从观察者转变为服务社区的角色的时候。

## 底层架构的变化

自 2015 年以来，该平台发生了巨大变化，无论是内部架构还是向使用它的开发人员公开的功能。

当 Cloud Foundry Foundation 成立时，社区正在对平台的底层架构进行重大重写。这种转变是从最初的(主要是)Ruby 代码库(称为 DEA 架构)到基于 Go 的新架构，称为 Diego。这是一个很难正确解决的重大架构转变。挑战从来不是关于新架构本身(不是减少社区在构建它时的工作)，而是在过渡中:对现有架构中的新功能的竞争需求，以及对新架构具有更少移动目标的期望。在我的职业生涯中，我经历过许多这样的转变，Cloud Foundry 社区给我留下最深刻印象的一件事是它如何处理这种变化。

当然，开放协作可能会很混乱，但结果是一个有序的过渡，给了下游发行版的生态系统和最终用户足够的时间进行转换。从 DEA 架构到 Diego(及其所有子系统)的正式过渡始于 2016 年 11 月，当时 Diego 发布了 1.0 版本。这个发布里程碑向社区表明了两件关键的事情:它达到了与 DEAs 同等的目标特性水平，并且它已经达到了一些下游发行版所希望的 250，000 容器规模的目标。

## 看守人和花园

在开发 Diego 本身的同时，Cloud Foundry 负责节点级容器管理的组件也经历了重大变化。在 DEA 体系结构中，这部分体系结构是一个名为 Warden 的组件。Warden 比 Docker 至少早了两年，但它从未向最终用户公开过。当迭戈被创造出来的时候，对《典狱长》的平行和互补的改写也在进行。这种努力被称为花园。

Garden 的设计是经过深思熟虑的，因为它预见到需要轻松地更改其代码的最底层细节，以支持新兴的操作系统级容器功能。早在 2015 年，Cloud Foundry 社区就在构建 Garden 的实现，以支持基于 Linux 的主机和基于 Microsoft Windows 的主机。改变底层操作系统级容器技术的能力同样允许 Cloud Foundry 平台采用 Docker 向[开放容器倡议](https://www.opencontainers.org/)捐赠的 runC 库。事实上，Cloud Foundry 项目是第二个采用 runC 并在整个生态系统的生产集群中大规模运行的项目(仅次于 [Docker](https://www.docker.com/) 本身)。

## 为什么迭戈如此重要

迭戈的引入开启了新功能的可能性。集装箱到集装箱的联网和批量服务是迪戈号建成后首批增加的两项主要功能。这两组特性都可以看作是内部优化(例如:减少南北交通)，但更重要的是增强了开发者的体验。借助 C2C 网络功能，可以实现更复杂的应用到应用逻辑。这也是 Cloud Foundry 拥抱更广阔的开源网络世界的开始(稍后会详细介绍)。卷服务扩展了平台中可以托管的应用类型的范围，允许运营商向应用开发者提供到网络可寻址存储设备的文件系统装载。

## 集装箱联网

回到网络世界，容器到容器的网络工作确实为开发人员增加了许多有价值的功能。它也代表了一个转折点，云铸造社区开始利用服务网格空间中的开发标准和项目。这项工作从采用[容器网络接口(CNI)](https://github.com/containernetworking/cni) 开始，这是一个基于容器的平台与底层网络层交互以简化配置的规范。下一阶段是在 2017 年采用特使代理。最近，整个 Cloud Foundry 网络堆栈都将 [Istio + Envoy](https://istio.io/docs/ops/configuration/telemetry/envoy-stats/) 作为默认组件，以支持集群入口/出口和跨容器网络功能。

## Kubernetes +云代工厂

最近，Cloud Foundry 社区接受了另一个开源项目:Kubernetes。这始于 Kubo 的捐赠，这是一个由 Pivotal、Google 和 VMware 联合开发的项目。Kubo 很快成为了 Cloud Foundry 容器运行时(而 Elastic Runtime，更广为人知的是传统的 Cloud Foundry PaaS，被重命名为 Application Runtime)。这让我们的社区有信心采取进一步措施，将 Kubernetes 作为底层容器编排层。

项目 Eirini 致力于让 Cloud Foundry 集群在其架构中使用 Kubernetes，并最终(仍在进行中)取代 Diego 代码库。

在过去的五年中，社区已经创建了如此多的其他变化和扩展项目，以至于很难保持跟踪。一些项目已经发展成为大多数云铸造安装的关键组件。其他人已经完成了他们的使命，现在退休到基金会的阁楼。

## 什么没变？

在过去的五年中，有两件事没有改变，值得强调:我们的社区专注于提供世界一流的企业开发人员体验，社区致力于平台的持续发展。这些不变量都不是“技术”他们是社区的核心精神。我们已经带领成千上万使用 Cloud Foundry 的组织和成千上万部署软件到平台的开发人员踏上了征程。我们不断学习如何更好地为企业开发者服务，并不断迭代和扩展这种体验。我们还不断发展架构，从更广阔的开源世界中收获精华。诚然，我们深思熟虑、小心翼翼地做出这些改变。我们允许演进在频繁发布的同时逐渐引入新的功能。

变化很大，但不变的是 Cloud Foundry 社区致力于将我们的生态系统带入一个旅程。我很期待看到我们的未来。

访问我们的[生日时间线](https://www.cloudfoundry.org/cloud-foundry-foundation-turns-5)，观看我们的[生日视频](https://youtu.be/0SCvLBOgIpE)。

[https://www.youtube.com/embed/0SCvLBOgIpE?feature=oembed](https://www.youtube.com/embed/0SCvLBOgIpE?feature=oembed)

视频

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>