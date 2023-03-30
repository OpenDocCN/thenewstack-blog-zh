# 现在是 CoreOS 的测试时间，CoreOS 是用于大规模服务器部署的 Linux 发行版

> 原文：<https://thenewstack.io/its-beta-time-for-coreos-the-linux-distro-for-massive-server-deployments/>

在过去九个月发布了 150 个版本之后， [CoreOS，](https://coreos.com/)一个新的 Linux 发行版，现在处于测试阶段。作为背景，传统的基于服务器的操作系统最多每几个月更新一次。相比之下，CoreOS 是一个轻量级的操作系统，模仿 ChromeOS 浏览器，不断更新。按照谷歌的思路，该公司将[的 CoreOS 技术](https://thenewstack.io/say-goodbye-to-coreos/)描述为“用于大规模服务器部署的 Linux”

通过不断升级，CoreOS 无需用户手动操作即可管理安全性。CoreOS 也类似于自行更新的新一代 app。CoreOS 创始人兼首席执行官 Alex Polvi 在本周的一次电话采访中表示，这使得 CoreOS 本质上是一个被设计成类似于应用程序或现代浏览器的服务器。

使用 Amazon Web Services (AWS)的公司通常必须了解在分布式基础设施上开发工具所带来的复杂性。这意味着理解如何管理与数据中心中的服务大不相同的新概念。在数据中心，虚拟化技术位于操作系统之下。正如我在 [TechCrunch 的一篇文章](http://techcrunch.com/2014/01/21/docker-raises-15m-for-popular-open-source-platform-designed-for-developers-to-build-apps-in-the-cloud/)中提到的，领先的虚拟机管理程序，如 VMware 和 Xen，虚拟化的是服务器，而不是应用程序。正因为如此，操作系统必须移动，以便在应用程序可能被转移到的任何地方运行它。交付后，虚拟机必须启动并配置为与数据库和它所依赖的堆栈的其余部分一起运行。

在 AWS 等平台环境中开发、测试和管理虚拟机可能会很麻烦，因为这些虚拟机非常庞大。

轻量级容器技术 Docker 是这些新的轻量级服务的象征，CoreOS 专门与 Docker 技术合作。使用 Docker，容器位于操作系统之上。唯一会动的是代码。开发人员不必启动和配置。相反，容器与云服务同步。它很轻，便于运输。

但是 CoreOS 也带来了挑战。操作系统的更新可能是自动的，但这是一个全新的概念，不同于像传统软件一样更新的 Ubuntu 或 Red Hat。Polvi 表示，他们认识到了这个问题，并正在努力让人们了解操作系统带来的新概念，即在没有用户参与的情况下作为服务进行管理和更新。

### CoreOS 基础知识

CoreOS 设计用于在数据中心或云服务中运行。它的后端是用谷歌主导的系统语言 Go T1 编写的，这种语言在过去两年里越来越受欢迎。它不在软件包上运行，这降低了让它正常运行的复杂性。相反，软件运行在 CoreOS 之上的容器中。码头工人是这里的关键。它允许开发人员专注于应用程序，而不是底层基础架构和一些虚拟化主机。没有虚拟机管理程序，消除了大量开销。CoreOS 还协调集群，管理大规模扩展服务带来的复杂性。

CoreOS 团队面临来自 Red Hat 的一些竞争，Red Hat 也采用了这种营销方法。该公司已经推出了自己的轻量级操作系统来托管名为[项目原子](http://www.projectatomic.io/)的 Docker 容器。产品和商业战略高级主管 Lars Hermann 在今天上午的电话采访中说，预计它将与每六个月更新一次的 Red Hat Fedora 同步更新。

Red Hat 发布更新的方法是有据可查的。红帽企业(RHEL) Linux 6.0 于 2010 年推出。12 月，红帽推出了 RHEL 7.0 的测试版。RHEL 7.0 的正式上市日期尚未确定。RHEL 的 7.0 候选版本现已面向战略合作伙伴和相关方开放。

原子项目对公司来说是一个真正的开始，也是一个颠覆性的开始。它让 Red Hat 进入了一个更快的循环，但 Herrmann 说，这种速度可以形成一个巨大的生态系统。

CoreOS 引起了理解该技术提供的“通道”方法的开发人员的极大关注和兴趣。有一个阿尔法频道经常更新。测试版的功能已经完成，但仍在测试中。

“如果某样东西能达到那个阶段，那么它就已经通过了很好的测试，”波尔维说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>