# 通过 Kubernetes，Mirantis 将 OpenStack 集装箱化，以缓解运营挑战

> 原文：<https://thenewstack.io/mirantis-containerizes-openstack-to-ease-operational-challenges/>

随着美国电话电报公司、威瑞森、宝马、大众和沃尔玛等巨头越来越多地利用 OpenStack，open stack 正迅速成为构建私有云基础架构的公司的核心构建模块。虽然部署 OpenStack 已经变得相对容易，但扩展、管理和运营 open stack 仍然是一个巨大的挑战。

“OpenStack 的问题是，从历史上看，OpenStack 社区没有充分重视解决有关管理 OpenStack 的问题。一旦安装了云，你如何确保它不会崩溃，如何修补它，如何升级？”OpenStack 发行商 [Mirantis](https://www.mirantis.com/) 的联合创始人兼首席营销官 Boris Renski 在接受采访时说。“因此，企业无法以稳定的方式运行 OpenStack。是的，他们可以安装。但是一个月后它就停止工作了，没有人知道如何修理它。

新兴的集装箱技术可能会带来一些缓解。毕竟，谷歌将所有东西都部署在容器中。就连作为基础设施即服务层的谷歌云也作为容器部署在名为[的共享容器管理平台上。](https://thenewstack.io/google-learned-borg-container-management/)

“谷歌运行他们所有的内部系统，包括谷歌云，以非常特殊的方式，他们在多年的过程中完善，”Renski 说。“Kubernetes 是他们发布的一个工具，允许人们使用这种‘谷歌方式’运行大规模分布式系统，”他说。

他说:“我们正在采用这种完全的‘谷歌方式’运行软件，并对 OpenStack 架构进行现代化，以坚持这种方式，使 OpenStack 更加稳定，更易于管理。”

> 通过打包 OpenStack 服务，使其可以由 Kubernetes 管理，Mirantis 正在解决 OpenStack 的许多扩展、管理和运营挑战，从理论上讲，使其与任何微服务一样可扩展。

在最近的 OpenStack 峰会期间， [CoreOS](https://coreos.com/) 推出了一个名为 [Stackanetes](https://thenewstack.io/openstack-gets-self-healing-coreoss-new-kubernetes-based-stackanetes/) 的项目，该项目旨在将 OpenStack 作为一个应用程序在您的基础设施上运行，就像任何其他应用程序一样。实际上，Stackanetes 使用 [Kubernetes](/category/kubernetes/) 编排引擎来管理分布式 OpenStack 部署。

现在，米兰蒂斯正在通过一个名为 [Fuel](https://wiki.openstack.org/wiki/Fuel) 的现有 OpenStack 项目为 OpenStack 带来类似的功能。米兰蒂斯正在与谷歌和[英特尔](https://www.intel.com/content/www/us/en/it-management/intel-it/it-managers.html)合作重写 OpenStack 的生命周期管理工具 Fuel，以使用 Kubernetes 作为其底层编排引擎。

典型的真正开源，Mirantis 正在使用 CoreOS 所做的工作来重构 Fuel。“我们将利用其中一些成果。几个月前，我们与英特尔和 CoreOS 合作开发了 Stackanetes，它是一些类似功能的早期概念验证，构建于任何社区之外，针对 CoreOS 而设计，”Renski 说。“我们希望继续与 CoreOS 合作，实施我们今天与谷歌和英特尔宣布的计划，并将纳入 Stackanetes 中展示的一些内容。”

在今年早些时候的一次采访中，CoreOS 首席执行官 Alex Polvi 表示， [Stackanetes](https://github.com/stackanetes/stackanetes) 不是 CoreOS 的产品，它是一个类似于 [Kubernetes](http://kubernetes.io/) 的开源项目。

“我们一直在与包括 Mirantis 在内的普通 OpenStack 社区合作开发 Stackanetes。Stackanetes 是 OpenStack Nova 和相关组件在 Kubernetes 上的端到端部署。我们计划继续与上游 OpenStack 合作，”他说。

通过打包 OpenStack 服务，使其可以由 Kubernetes 管理，Mirantis 正在解决 OpenStack 的许多扩展、管理和运营挑战，从理论上讲，使其与任何微服务一样可扩展。

“随着 Docker 作为标准容器映像格式和 Kubernetes 作为容器编排标准的出现，我们终于看到了人们处理分布式应用程序操作的连续性。将 Kubernetes 和 Fuel 相结合将开放 OpenStack，形成一种新的交付模式，允许更快地消费更新，帮助客户更快地获得结果，”Renski 说。

据该公司称，最终的解决方案将是虚拟机、容器和裸机系统的单一平台，可以动态控制 OpenStack 操作和生命周期管理。

“这在技术上是有意义的，我们很高兴看到 OpenStack 社区的更多成员支持 Kubernetes 部署和管理 OpenStack，”Polvi 说。

通过该包，用户将对服务进行细粒度控制，使他们能够对 OpenStack 进行滚动更新，使 OpenStack 控制平面能够自我修复，更具弹性。它还将使在 OpenStack 上创建基于微服务的应用变得更加容易。他们还将获得能够运行虚拟机和本地容器工作负载的单一开放结构。

集装箱化的形式还将允许 Mirantis 将更新的集装箱不断地运送到客户的暂存环境中，他们可以将其提升到生产环境中。

“Mirantis OpenStack 将成为一个单一的、持续滚动的版本，”Renski 说。Mirantis 还将在 OpenStack Fuel 项目下启动一个新的持续集成/持续交付(CI/CD)管道，用于围绕集装箱化 OpenStack 部署和运营建立能力。

随着 Kubernetes 成为 Mirantis 战略的基石，该公司正计划增加对 Kubernetes 的贡献。

英特尔软件定义基础设施事业部副总裁兼总经理 Jonathan Donaldson 表示:“英特尔和 Mirantis 在开源领域的联合领导地位将有助于搭建 OpenStack 和 Kubernetes 社区的桥梁。“我们的共同努力将使两个互补且强大的开源社区联姻，让企业管理私有云变得更加简单。

特写图片[通过](https://www.flickr.com/photos/nasacommons/18767975800/)美国宇航局。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>