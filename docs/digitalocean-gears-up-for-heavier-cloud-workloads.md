# 数字海洋为更重的云工作负载做好准备

> 原文：<https://thenewstack.io/digitalocean-gears-up-for-heavier-cloud-workloads/>

DigitalOcean 于 2012 年成立，主要面向开发者提供易于部署的低成本云服务。然而，随着托管服务越来越受欢迎，它已经开始构建用于管理更大规模的开发项目甚至生产工作负载的服务。

周二，该公司推出了一项名为浮动 IPs 的新功能，旨在提高网络应用程序的可靠性。Floating IPs 加入了另一个最近推出的功能，团队帐户管理，顾名思义，它允许开发人员小组在单个虚拟映像上进行协作。

DigitalOcean 的产品总监 Brooke McKim 解释说，这些新功能反映了 DigitalOcean 客户使用方式的自然演变。一个开发者可能会在这个服务上开始一个项目，但是如果这个应用成功了，它将需要更多的控制和更多的贡献者来保持它的运行。

使用 DigitalOcean，用户主要通过 dropletss 与服务进行交互，droplet 是运行许多 Linux 发行版(Ubuntu、Fedora、Debian、CentOS)之一或 FreeBSD 副本的虚拟机。该公司还提供许多流行的开源应用程序的虚拟实例，如 WordPress、Docker、Django Python 框架和许多其他应用程序。

这些虚拟机可以在几分钟内启动，并有多种不同的大小，单个 CPU 和 20GB 固态存储每月 5 美元起。

这种简单的云计算方法已经被证明是[非常受欢迎的](http://trends.netcraft.com/www.digitalocean.com)；据该公司称，迄今为止，已有超过 70 万人安装了超过 800 万台云服务器。许多人用它来快速拼凑一个原型应用程序，而不需要购买服务器，甚至不需要经历其他云提供商更复杂的设置过程。

McKim 说，浮动 IP 旨在保持 web 应用程序运行，即使运行该应用程序的主映像出现故障。实际上，它可以消除单点故障。

当然，IP 代表互联网协议。通常每个数字海洋水滴都有一个专用的 IP 号码，因此可以通过互联网联系到它。

DigitalOcean 注意到它的一些客户使用 droplet 作为负载平衡器，这实际上将流量导向许多应用服务器中的任何一个，每个服务器都运行在自己的 droplet 中。这种方法可以很好地处理大量的流量，但是如果前端负载平衡器本身由于某种原因停止运行，就会出现严重的故障。

浮动 IP then [提供了一种解决这个问题的方法](https://www.digitalocean.com/community/tutorials/how-to-create-a-high-availability-setup-with-heartbeat-and-floating-ips-on-ubuntu-14-04),它允许用户设置一个备用负载平衡器，在主负载平衡器出现故障时发挥作用。McKim 说，浮动 IP 号码被分配给主负载平衡器，但如果需要，可以转移到备用负载平衡器，从而“对生产流量造成非常小的中断”。“最终客户不应该看到差异。”

浮动 IP 可以通过 web 控制台手动分配给不同的 droplets，也可以通过 API 来分配。第三方服务器监控产品可以配置为自动向 DigitalOcean 发送命令，以便在主实例无响应时将 IP 号码切换到辅助实例。

这项服务是免费的，尽管用户将为每个保留但未使用的浮动 IP 每月支付 1 美元。McKim 说,[IP v4 地址的严重短缺](https://www.arin.net/resources/request/ipv4_countdown.html)迫使数字海洋公司收取这项费用。“我们不希望客户收集他们没有使用的知识产权，”他说。

McKim 说，浮动 IPs 是为了应对 DigitalOcean 的客户运行的更复杂的工作负载而出现的。除了业余爱好者和独自开发新作品的人之外，软件开发团队也开始使用这项服务来构建甚至运行更复杂的应用程序。

这也是该公司今年 6 月发布团队账户的原因。使用团队帐户，droplet 的主要帐户持有人可以指定其他开发人员访问相同的 droplet，只需提供他们的电子邮件地址。可以访问 droplet 的其他用户数量没有限制。

DigitalOcean 和 Docker 是新堆栈的赞助商。

图片:[国王海王星](http://joabj.com/Photos/2014/1406-PL-VABeach-Neptune.html)，眺望大西洋，弗吉尼亚州弗吉尼亚海滩。照片由约阿布杰克逊。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>