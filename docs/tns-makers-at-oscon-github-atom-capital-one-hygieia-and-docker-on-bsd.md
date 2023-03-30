# OSCON 的 TNS 制造商:GitHub Atom、Capital One Hygieia 和 BSD 的 Docker

> 原文：<https://thenewstack.io/tns-makers-at-oscon-github-atom-capital-one-hygieia-and-docker-on-bsd/>

新的堆栈强调解释和表达开源项目。本着这种精神，我们很高兴能够近距离观察 2015 年 OSCON，我们采访了三位与会者，了解他们的项目、使用案例以及他们如何看待自己的价值。

## 原子

[Atom](https://atom.io/) 被描述为“21 世纪的可破解文本编辑器”，它可以被完全定制为做任何事情，而且还可以高效地使用，“无需接触配置文件”一个内置的包管理器使您能够搜索和安装新的包，或者开始创建自己的包——所有这些都在 Atom 中完成。Atom 允许您在一个窗口中轻松浏览和打开单个文件、整个项目或多个项目，并且可以在 OS X、Windows 或 Linux 上使用。

听听 GitHub 的 [Brandon Keepers](https://github.com/bkeepers) 解释 Atom 的原因和方式:

[布兰登守护者，GitHub:在 OSCON 讨论原子](https://thenewstack.simplecast.com/episodes/brandon-keepers-github-discussing-atom-at-oscon)

“众所周知，GitHub 是社交编码的地方，所有代码都托管在这里，但在 GitHub 上之前，在构建软件的过程中会发生很多事情。布兰登说:“我们希望打造一款工具，让我们能够创造社交编码的未来。"如果我们能在编写代码的时候一起工作会怎么样？"

## 卫生

在 Capital One，平台工程研究员[tapa brata Pal](https://twitter.com/topopal)(人称“Topo”)博士说，他们已经做了四年的 DevOps。在使用多个工具的过程中，每个工具都有自己的仪表板，他们发现需要在一个仪表板中查看整个管道。在商业或开源市场上找不到任何解决方案，他们决定自己构建一个。

“它从每个工具中获取所有信息，将其收集在一个中心位置，并有一个漂亮的用户界面向您显示来自这些工具的实际信息。整个想法是缩短和扩大反馈回路，”Topo 引用 Gene Kim 的三种发展方式中的第二种说。

听 Topo 讨论卫生保健项目和他们的开源计划:

[首都一号塔帕伯拉塔博士:在 OSCON 讨论卫生学](https://thenewstack.simplecast.com/episodes/dr-tapabrata-pal-capital-one-discussing-hygieia-at-oscon)

对于一个用例的主要例子，Topo 指出开发团队同时在独立的项目上工作，如果一个构建失败，一个集中的仪表板将立即向团队中的每个人发出信号，从而缩短确定原因所需的时间。

新堆栈还在“[观察:卫生学、Capital One 进入开源的 Neflix 和 Etsy 领域](https://thenewstack.io/what-stands-out-about-hygieia-capitol-ones-entry-into-the-neflix-and-etsy-land-of-open-source/)”中深入探讨了该项目。

## BSD 上的 Docker

正如长期的 FreeBSD 社区成员 Michael Dexter 在他最近的帖子“ [Docker 做得对](http://www.freenas.org/whats-new/2015/07/docker-done-right.html)”中所建议的，“FreeBSD 可能会被证明是终极的 Docker 平台，这要归功于它 15 年多的遏制经验和无与伦比的 [OpenZFS](http://open-zfs.org/wiki/Main_Page) 文件系统。”Docker 从 2015 年 6 月起在 FreeBSD 上可用。

Michael 将 Docker 视为“系统管理员的软件打包方法”

“系统管理员被束缚住了手脚，不能修改他们上面和下面的东西，”Michael 说。“那你是做什么的？您可以创建一个 shim 环境，在其中轻松移植应用程序。”

“作为一个平台，”他解释说，“一旦 Linux 仿真达到 64 位，像 Docker 这样的东西就只是几周的移植时间，而不是一个巨大的工程壮举。”Michael 对 FreeBSD 充满热情，他说，“这可以直接追溯到 CSRG 和 BSD 项目。”

“当你采用这样一个为(Docker)这样的东西做好准备的平台时，它就自然而然地到位了。”

听迈克尔·德克斯特在 BSD 上讨论 Docker:

[迈克尔·德克斯特，FreeBSD 社区:BSD 上的 Docker](https://thenewstack.simplecast.com/episodes/michael-dexter-freebsd-community-docker-on-bsd)

“我们已经有了一个非常清晰的端口树，以及从这个角度来看的应用程序管理，所以很长一段时间以来，我们一直在监狱中包含来自端口的应用程序，”他说。他认为，那些被 FreeBSD 平台所吸引的用户，以及那些发现 Docker 性能如此之好的用户，将不会再想回去。“一旦你和 ZFS 相处了一段时间，你就不会再想在你的生活中看到另一张硬件价格卡了。一旦你对重要数据进行了 ZFS 发送，你就再也不想使用 rsync 了。”

新堆栈向 Michael 以及 GitHub 和 and Capital One 团队的成员致以深深的“感谢”，感谢他们与我们分享时间和故事。

Docker 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>