# DigitalOcean 现在支持 CoreOS，这是一个用于托管 Docker 容器的轻量级 Linux 发行版

> 原文：<https://thenewstack.io/digital-ocean-now-supports-coreos-the-lightweight-linux-distro-for-hosting-docker-containers/>

DigitalOcean 已经正式采用了自动更新操作系统和 Docker 容器托管服务的 CoreOS，该服务已经受到开发人员的广泛欢迎。

通过合作，开发者现在可以在他们的 [DigitalOcean](http://digitalocean.com) droplets 中使用 CoreOS，为网络和移动开发者提供一种的方式来部署应用程序和试验 Docker 容器。DigitalOcean 的客户可以立即获得这项服务。它类似于 Ubuntu 和 CentOS 等其他操作系统。用户在 Droplet 创建页面上选择 CoreOS 映像，然后立即启动 CoreOS 服务器。随着今天早上的新闻，DigitalOcean 发布了如何使用 CoreOS 的教程。

“数字海洋的 CoreOS 在我们的社区和开发人员中引起了很大的轰动，”CMO 和数字海洋的联合创始人 Mitch Wainer 说。“这是开发人员开始使用和试验 Docker 容器，并开始构建更具弹性的架构的最简单方式。”

CoreOs 是一个轻量级操作系统，模仿 ChromeOS 浏览器。像 Chrome 一样，CoreOS 会自动更新，这意味着开发者拥有一个不需要手动升级的操作系统。该公司将其描述为大规模部署 Linux 服务器的操作系统。

与 DigitalOcean 和 CoreOS 有天然的搭配。这两项服务对开发者都很有吸引力。DigitalOcean 以简单易用、价格实惠的服务著称。CoreOS 的配置和管理系统构建在分布式键值存储 etcd 上，使得部署 Docker 容器变得非常简单。

CoreOS 在集群级别进行管理。它不需要像传统虚拟化环境那样运行主机。它也不能在软件包上运行，这降低了让它正常运行的复杂性。相反，软件运行在 CoreOS 之上的容器中。码头工人是这里的关键。它允许开发人员专注于应用程序，而不是底层基础架构和一些虚拟化主机。没有虚拟机管理程序，消除了大量开销。通过 etcd，CoreOS 协调集群，管理大规模扩展服务带来的复杂性。

“我们已经有了 Docker，它是一个一键安装的应用程序，用户可以从任何应用程序创建轻量级、可移植、自给自足的容器。Wainer 在电子邮件采访中说道。“但 CoreOS 是开始 Docker 实验的理想操作系统，所以这引起了很多关注。”

CoreOS 也可用于其他服务，如谷歌计算引擎和 Rackspace。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>