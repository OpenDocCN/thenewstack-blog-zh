# Shippable 如何以 AWS 虚拟机无法达到的方式扩展 Docker

> 原文：<https://thenewstack.io/how-shippable-has-scaled-docker-in-a-way-it-never-could-with-aws-vms/>

昨天，我在 glue con 上与 Avi Cavale 坐在一起，听取了[shipping able](https://www.shippable.com/)如何为其开发者服务扩展 Docker 来发布代码。

Cavale 解释了 Docker 如何帮助 Shippable 的业务转型，该业务定位于持续集成市场。该公司现在经营着近 4000 个集装箱，而去年 8 月只有 200 个。由于其轻量级功能，Docker 的运行速度比专用的 Amazon EC2 VM 快 40%。因此，商业模式发生了变化。

Shippable 一度决定经营自己的集装箱。但在去年春天的一次 Y Combinator 采访中，卡瓦勒遇到了 Docker 的创始人、平台即服务网站 dotCloud 的时任首席执行官所罗门·海克斯(Solomon Hykes)。Hykes 告诉 Cavale 关于 Docker 的事，Docker 一直在监视它。当它在去年 7 月完全开源时，Cavale 开始使用 Docker，并最终实现了转换。

在采用 Docker 之前，Shippable 使用 Amazon VMs 来管理其客户的工作流。但这不是一项可扩展的业务，Shippable 无法在市场中脱颖而出。他们相信，他们可以用自己制造的容器扩大业务规模。但事实证明 Docker 更好，这在很大程度上是因为它是开源的。

Docker 容器对于开发人员来说更容易使用。它位于操作系统之上。只是代码在更新。现在有了 Docker，公司免费赠送前几个集装箱，之后收费。它现在可以使用 Docker 技术基础开始提供更多的定制服务，如并行处理。

享受表演吧！

通过 Flickr 上的 Creative Commons 获取专题图片

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>