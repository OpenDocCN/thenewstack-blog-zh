# Docker 如何加快集装箱游戏的步伐

> 原文：<https://thenewstack.io/shining-historical-lens-containers/>

尽管 Docker 今天如此成功，但很难理解该项目仅仅在两年前从一家名为 dotCloud 的苦苦挣扎的 PaaS 提供商那里开始，该提供商决定开源其编排框架。但 Joyent 首席技术官 Bryan Cantrill 表示，Docker 提供了其他容器技术在此之前所没有的东西，即无缝连接开发和运营世界的能力。是的，德沃普斯。

“这么多年来，我们一直在谈论集装箱的运营效率。Docker 所做的实际上是使用容器来提供开发效率，使开发应用程序变得更容易，而不仅仅是部署它。它允许开发者进行操作性思考，”Cantrill 在今年旧金山举行的[容器峰会](http://containersummit.io/)上说。“这是一件大事。”

在一次热情而广泛的演讲中，Cantrill 不仅谈到了容器背后的历史，还谈到了在一个人的开发堆栈中使用容器的未来将如何继续发展。

随着技术的新进步，有更多的理由来探究容器的概念从何而来，因为现在被称为基于容器的工作流的历史是从软件隔离开始的。总的来说，容器不是一个新概念，在某些方面已经被广泛使用了几十年。但是他们的承诺才刚刚开始展现。

## 从 Chroot 到监狱

尽管 IBM 从 20 世纪 70 年代就开始玩弄这个概念，但今天服务器时代的容器真正开始于比尔·乔伊，当时他在太阳微系统公司，他最初开始使用 Unix [chroot](https://wiki.archlinux.org/index.php/Change_root) 操作作为隔离软件的一种方式，这样它就不会损坏系统。

![“Things reflect their origins.” --  Bryan Cantrill, CTO, Joyent](img/e1318a464ecf721eb265ab556e900d48.png)

“事物反映其起源。”–Joyent 首席技术官 Bryan Cantrill

在 chroot 环境中运行软件是第一个包含独立运行软件的实例，除了能够影响运行它的系统。Chroot 绝不是万无一失的，有很多种方法可以破解它，或者查看它下面的系统。FreeBSD 旨在通过[引入被称为 jails](http://phk.freebsd.dk/pubs/sane2000-jail.pdf) 的概念来解决这些痛点，在 jails 中，不可信的软件可以在不损害系统的情况下在一个环境中独立运行。

Sun Microsystems 看到了 FreeBSD 以监狱为目标的方向，并希望通过引入区域来更进一步。2005 年推出的 Solaris Zone 容器不仅仅用于隔离应用；他们能够整合它们，同时提供更强大的虚拟化来运行应用程序，使应用程序软件隔离在自己的容器中。Sun 将区域与资源管理工具结合起来，允许开发人员在项目需要时与它们进行交互。和区域安全边界，通过这些边界，不同区域中的容器不能与彼此的进程进行交互。

容器通过隔离软件、应用或微服务的片段，然后将它们编排成许多协同工作的小部分来构建这一概念——尽管它们最终保持独立。系统发现工具允许容器相互查看和交互。因此，chroot、Solaris Zones 和 [FreeBSD jails](https://www.freebsd.org/doc/handbook/jails.html) 为如今 Docker 等平台上的容器架构奠定了基础。

Cantrill 还指出，操作系统虚拟化有助于采用不同的应用程序并一起运行，尽管在虚拟化和整合包括操作系统在内的整个技术堆栈时，它存在不足。

[![The Honeywell 200](img/0556baf57fbd07569065f5ea82f6dff9.png)](https://en.wikipedia.org/wiki/Honeywell_200#/media/File:H200c.jpg)

霍尼韦尔 200，使虚拟化成为必要的机器。

IBM 的硬件级虚拟化早在 20 世纪 70 年代就解决了这个问题；不过，作为一项较老的技术，它也有自己的问题。IBM System 360 是历史上最重要的计算硬件之一。IBM 希望 System 360 将成为整合所有现有机器的机器，IBM 360 指令集将成为通用语言。

然而，这种方法要求开发人员用 IBM 360 指令集重新编写他们的应用程序，这被认为是非常无效的，特别是对于那些已经为 IBM 1400 系列编写的程序。

利用这一点，霍尼韦尔推出了霍尼韦尔 200，它可以运行为 IBM 1401 编写的软件。这台机器被称为解放者，它允许用户在 H200 上运行 IBM 1401 代码。由于霍尼韦尔对 1401 平台的虚拟化，IBM 在 360 上增加了 1401 虚拟化。

> “45%的 Y2K 问题来自一个单一的体系结构，IBM 1401。IBM 1401 是一台非常旧的机器，软件仍在上面运行。”布莱恩·坎特里尔，Joyent

如果想无限期地运行软件，硬件虚拟化将允许这种情况毫无问题地发生。随着技术的不断进步，需要进一步的抽象。应用程序并不运行在实际的系统硬件上，而是通过一系列的管道运行，在应用程序看来它们并不是这样。Cantrill 指出，基于操作系统的虚拟化是唯一有意义的发展方向。

## 回到未来

这又把我们带回了 Docker。Cantrill 说，有了 Docker，开发人员可以将“他们所有的依赖项集成到一个有效的静态二进制文件中”，这个文件可以被发布到产品中。开发人员可以在笔记本电脑上创建一个应用程序，然后在生产环境中不加修改地运行它。

[![“Docker is doing to applications what apps did to TAR. We’ve up-leveled our thinking, allowing developers to think operationally” -- Bryan Cantrill, Joyent](img/82198ccc2a575380b602e9feeca028ec.png)](https://thenewstack.io/wp-content/uploads/2015/10/Bryan-Cantrill-02.jpg)

“Docker 对应用程序的作用就像应用程序对 TAR 的作用一样。我们已经提升了我们的思维，允许开发人员从操作的角度考虑问题。”——Bryan can trill，Joyent

Cantrill 指出，许多被称为“Docker”痛点的常见问题根本不是真正的 Docker 问题。在 VM 中部署 Docker 被认为是安全运行容器的关键，尽管这会严重影响容器的性能。仍然需要能够“在金属上”部署容器

Joyent 提供了一个解决方案，旨在通过基于 [Illumos](http://wiki.illumos.org/display/illumos/illumos+Home) 的第一类管理程序 [SmartOS](https://smartos.org/) 推动容器技术的发展。

SmartOS 可以在生产中运行 Docker 容器，能够通过 [Joyent 的智能数据中心](https://www.joyent.com/private-cloud)通过 API 提供新的容器实例。这种虚拟化消除了供应虚拟机的需要，开发人员只需负责容器的分配。因此，Cantrill 指出，随着未来在容器生态系统中引入更多开源产品，软件开发团队必须从分配心态转变为消费心态。

开源软件开发的兴起为每个人引入了竞争框架，使开发团队能够在应用程序生命周期的每个阶段选择最适合他们的解决方案，同时随着更多客户端用例的出现，允许更容易地转换。

Cantrill 说，为了实现容器的全部潜力，开发人员必须改变他们处理问题的方式。要利用基于容器的技术堆栈的真正力量，开发人员必须远离虚拟机和硬件虚拟化。随着 Docker 环境的发展，软件开发人员必须简化、适应和修改他们的技术栈，以确保应用程序开发继续是一个流畅的过程。

Joyent、Docker 和 IBM 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>