# FreeBSD 现在由 DigitalOcean 支持

> 原文：<https://thenewstack.io/freebsd-now-supported-digital-ocean/>

今天，DigitalOcean 通过为流行的操作系统提供支持，向 FreeBSD 社区致敬。FreeBSD 是 DigitalOcean 支持的第一个非 Linux 发行版。

在一篇博客文章中，他们引用了 FreeBSD 核心团队如何在内核和用户空间工具上协同工作。他们喜欢这个联合的团队如何确保整个项目的一致开发。管理系统和对清晰的技术写作的热爱也有帮助。但是很大一部分支持来自于数字海洋用户，他们使得 FreeBSD 成为数字海洋用户版块上最热门的请求之一。

DigitalOcean 承认他们花了一些时间来支持 FreeBSD。公司的发展和随后的重组促使公司花了一些时间为 FreeBSD 提供支持。一个转折点随着[对](https://thenewstack.io/digital-ocean-now-supports-coreos-the-lightweight-linux-distro-for-hosting-docker-containers/) [CoreOS](https://coreos.com/) 的支持到来，这是一个自动更新的操作系统和容器托管服务。这种采用迫使 DigitalOcean 的工程师们建立了一个元数据服务——“允许一个液滴在它被创建的时候访问关于它自己的信息。”使用元数据服务，droplet 本身会查询可配置项，如主机名、SSH 密钥。然后，它会自行配置，而不是依赖第三方，例如配置管理工具。

如果没有元数据服务，DigitalOcean 将面临后端代码需要知道图像内容时出现的问题。

“我们需要元数据”来提供 FreeBSD，高级软件工程师 Neal Shrader 在今天的采访中说。

以下是 DigitalOcean 在博客中对这一过程的描述:

为了查询元数据，我们需要有一个初始网络配置，以便建立我们的配置，因为数字海洋的水滴使用静态网络。在引导期间，我们在 v4 链路本地地址上启动 droplet，以便对服务进行初始查询。从那里，我们获得真正的网络配置、主机名和 ssh 密钥。然后，cloud-init 项目编写一个与 droplet 的 ID 相关联的配置。将此配置链接到 droplet ID 是一种机制，它允许 it 知道映像是从快照创建的还是新创建的，或者只是已配置的 droplet 的重新启动实例。

FreeBSD 有着深厚的根基。FreeBSD 出现于 20 世纪 90 年代初，紧随比尔和林恩·乔里兹的工作，他们创造了 386BSD。他们的故事非同寻常。蕾切尔·查尔莫斯现在是 Ignition Partners 的负责人，她在 2000 年为沙龙杂志写了一篇关于这对夫妇的[简介](http://www.salon.com/2000/05/17/386bsd/)。他们的工作为 FreeBSD 及其广泛使用铺平了道路。[对当时发生的事件](https://www.freebsd.org/doc/en_US.ISO8859-1/books/handbook/history.html)的叙述提供了一些关于为什么 Linux 而不是 386BSD 成为最流行的基于 Unix 的开源运动的观点。值得一读。

网飞和瞻博网络使用 FreeBSD。WhatsApp 联合创始人[简·库姆](https://en.wikipedia.org/wiki/Jan_Koum "Jan Koum")是 FreeBSD 的热情拥护者。11 月，他向 FreeBSD 基金会捐赠了 100 万美元。库姆认为是 FreeBSD 让他摆脱了贫困。

DigitalOcean 因吸引开发商而得到广泛认可。FreeBSD 符合它的剧本。但一个有趣的故事是关于生态系统以及它如何影响公司技术发展的轨迹。DigitalOcean 花了一些时间来支持 CoreOS。有了元数据服务，第三方配置的复杂方面已经被抽象了。这使得 DigitalOcean 能够支持 FreeBSD，从而拓宽其生态系统，对开发者更具吸引力。通过这种结合，DigitalOcean 只是在做科技公司应该努力去做的事情。构建平台，开发生态系统，并不断寻找新的方法来帮助构建和开发跨分布式基础架构的应用程序。

DigitalOcean 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>