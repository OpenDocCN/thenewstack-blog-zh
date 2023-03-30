# Yelp 发布了 Docker 容器的初始化系统

> 原文：<https://thenewstack.io/yelp-releases-initialization-system-docker-containers/>

Yelp，[是 Linux 容器](https://thenewstack.io/docker-helped-yelp-leave-monolith-behind/)的早期采用者，发布了一个运行在 Docker 容器内部的初始化系统，称为 dumb-init，旨在消除可能滋生僵尸进程的信号问题。

该公司正在将单个命令转移到容器中，以便他们可以在不中断当前工作流的情况下慢慢迁移工具和基础架构。这要求它们的进程在用户输入、响应信号和终止时，就像在遗留系统中运行一样。

【Yelp 软件工程师 Chris Kuehl 在一篇宣布发布的博客文章中解释道:“我们可以将单个命令移入容器，而不必强迫开发人员放弃他们现有的工作流程，开发人员甚至不会意识到他们在每次调用时都会生成一个 Docker 容器。”。“它还让我们在开发 Docker 时采取了一种实用的方法:我们可以选择在从业务或技术角度看有意义的时候使用容器，而不是要求所有东西都存在于容器中。”

当在容器中运行测试他们的应用程序时，程序员遇到了意想不到的行为，包括孤立的僵尸进程，这与来回发送的信号有关。轻量级 Docker 容器仍然运行完整的 Linux 系统，使 shell 充当 PID 1。原来这中断了信号传递过程。

“发送到 shell 的信号不会被转发到子进程，shell 也不会退出，直到您的进程退出。杀死容器的唯一方法是向它发送 SIGKILL(或者如果你的进程碰巧死了)，”Kuehl 写道。

事实证明，当 init 进程过早终止时，所有子进程都会被内核不干净地终止，留下孤立的僵尸进程。没有人喜欢僵尸在他们的过程中。

进入 dumb-init，一个解决这些问题的简单方法。添加到任何容器命令前面的代码充当 PID 1 的角色。这使得进程作为 PID ~2 进入容器，从而避免了特定于 PID 1 的特殊内核行为，并解决了信号问题(例如，孤立的僵尸进程)。

[One Thing Well](http://onethingwell.org/post/137085423925/dumb-init) 技术博客总结了 dumb-init:“dumb-init 是一个简单的进程管理器和 init 系统，设计为在最小容器环境中作为 PID 1 运行(比如 [Docker](https://www.docker.com/) )。它是一个用 c 语言编写的小型静态链接二进制文件。

虽然有一些现成的产品( [runit](http://smarden.org/runit/) 或 [systemd](http://www.freedesktop.org/wiki/Software/systemd/) )，但它们运行在 Python 上，需要一些设置工作和更多的资源来运行。Kuehl 说，dumb-init 是“一种更简单的正确做事的方法:它将你的进程作为它的独生子，并将信号代理给它。dumb-init 实际上不会死亡，直到您的进程死亡，允许您进行适当的清理。”

简单、干净、易于安装。听起来很优雅。最棒的是，你可以亲自去看看。Yelp 在 [GetHub](https://github.com/Yelp/dumb-init) 上给了 dumb-init 自己的页面。Dumb-init 是社交推荐服务[作为开源](https://yelp.github.io/)发布的众多内部构建工具之一。

Docker 是新堆栈的赞助商。

专题图片:美国国家档案馆的[拖拉机卡在中间点](https://www.flickr.com/photos/usnationalarchives/24355535415/)，途经[新老库存](http://nos.twnsnd.co/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>