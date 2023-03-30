# DigitalOcean 在其云功能组合中增加了一项可扩展的防火墙服务

> 原文：<https://thenewstack.io/digitalocean-adds-scalable-firewall-service-cloud-feature-portfolio/>

仅在 2017 年的前四个月，就有超过 312 起数据泄露事件被报告，安全成为许多系统管理员和开发人员的心头之患。为了帮助其用户加强他们自己的操作， [DigitalOcean](https://www.digitalocean.com/) 在其云服务中增加了免费的防火墙服务，这种服务旨在易于使用和高度可扩展。

“我们希望他们在体验中零摩擦，”数字海洋的联合创始人[米奇·怀纳](https://www.linkedin.com/in/mitchwainer/)说。

继二月份[推出负载平衡器](https://thenewstack.io/digitalocean-upgrades-load-balancing/)和四月份[推出水滴监控](https://thenewstack.io/digitalocean-now-provides-droplet-monitoring/)之后，新的防火墙服务是 DigitalOcean 首席技术官 [Julia Austin](https://twitter.com/austinfish) 扩展 DigitalOcean 功能的又一举措。

## 简单

云防火墙服务不需要安装任何软件，只需在开发人员的基础设施上点击一下即可激活。

该服务可以通过仪表板或命令行进行配置。一次点击就可以选择一个 droplet (DigitalOcean 的基本虚拟机)的所有端口被防火墙的规则覆盖。然后，可以根据需要取消选择单个端口，以便快速设置对不同的入站连接应用不同的规则。

用户可以根据需要创建组、定义和应用访问规则，直至 droplet、负载平衡器、IP 范围或标签级别，从而防止未经授权的流量到达 droplet。规则可以在一个地方更改，并立即应用于每个被标记的 Droplet，允许开发人员轻松地为不同的入站连接编写不同的规则。

Wainer 解释说:“因此，您可以重定向流量来设置您的 SSH 或 HTTP、ICMP，您可以保护入站流量来接受或丢弃它，从而保护内部和外部流量。”。

云防火墙可以自动从一滴扩展到数千滴。

Wainer 解释说，开发人员不必手动在每个单独的微滴上安装安全策略，这允许他们使用标记功能在多个微滴上安装。“如果需要，他们可以无缝地、即时地对数千个液滴应用相同的规则，”他说。

开发人员还可以利用 DigitalOcean 的 API 来自动化任务和构建集成。只需一个调用，您就可以为想要设置的任何端口创建一个规则，然后选择源，并创建一个可以应用于多个 Droplets 的标签。官方客户端库在 Go 和 Ruby 中都有。

## 还会有更多

Wainer 说，这只是数字海洋安全故事的第一步。“当我们推出一款产品时，这不是生产线的终点，而是第一步。”他们将在下一年迭代这个产品并发布更多的高级功能。

Wainer 说，到今年年底，数字海洋平台将更加强大，能够支持任何规模的组织。你可以点击查看发布时间表[。](https://blog.digitalocean.com/2017-whats-shipping-next-on-digitalocean/)

“随着 4 月份宣布的监测服务，我们正在通过在这些免费服务的基础上不断增加社区的价值，”Wainer 说。数字海洋定价模式只对底层基础设施收费。云防火墙是免费的。

“我们相信，我们需要帮助、教育并为更大的社区增加价值。这项免费服务加强了这一方向，”他说。

[数字海洋](https://www.digitalocean.com/)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>