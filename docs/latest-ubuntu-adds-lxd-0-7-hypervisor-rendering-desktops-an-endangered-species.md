# 最新的 Ubuntu 增加了 LXD 0.7 管理程序，使桌面成为濒危物种

> 原文：<https://thenewstack.io/latest-ubuntu-adds-lxd-0-7-hypervisor-rendering-desktops-an-endangered-species/>

在 Linux 客户机系统上的服务器环境中运行 Linux 容器的能力本身听起来并不令人兴奋，除非你是一名退休的英语教师，渴望校对句子。让我们试试这个:假设一个管理程序层可以允许桌面操作系统像服务器一样托管容器。这包括实时迁移，即在处理器之间传递活动工作负载的能力。

客户端系统可以通过 HTTPS 连接直接从网络集线器获取一个活动的、甚至可能正在运行的工作负载，并开始运行它，而无需安装。如果 Canonical 专注于推广这一理念，使用除了 Linux 变体之外的地球上人类通用的任何语言，它可能会破坏一些东西。

Canonical 去年 11 月宣布的用于实时工作负载分配的 Ubuntu 项目被称为 LXD，从那以后一直全速运行。它成为 Ubuntu Linux 15.04 版本的正式组成部分，该版本于今天正式上线。

## 戴着钻石的露西

“LXD”是有史以来附在一个软件上的最不幸的名字，这就是为什么 Ubuntu 不像它看起来那样发音。尽管它的前身和同胞 LXC 的发音很清楚是“el-eks-see”，但 LXD 的发音是“lex-dee”

抛开对蒂莫西·利瑞的所有回忆，LXD 是一个客户端虚拟机管理程序，旨在运行 Linux 容器，包括那些用于服务器的容器，具有通常与典型的虚拟机管理程序相关的安全限制和内核隔离类型。它的目标是使基于容器的工作负载可以跨服务器和客户机移植，同时增加一些 VM 用户所期望的灵活性:例如，拍摄正在运行的容器的快照。

“这个概念相对简单，”领先的 Ubuntu 建筑师和 LXC/LXD 的联合创作者斯蒂芬妮·格拉伯宣布，然后介绍了一个最终复杂的概念。“它是一个守护进程，通过 Unix 套接字本地导出经过验证的 REST API，并使用 HTTPS 通过网络导出。这个守护进程有两个客户端:一个是 OpenStack 插件，另一个是独立的命令行工具。”

事实证明，LXC 将是命令行工具，对于许多 Linux 爱好者宣称的第一个 Linux 容器虚拟化环境来说，这将是一个重大的升级。(事实上，在 Docker [在 0.9](https://blog.docker.com/2014/03/docker-0-9-introducing-execution-drivers-and-libcontainer/) 版本中放弃对 LXC 的依赖之前，第一个 Docker 版本使用 LXC 作为他们的执行环境。)但是早期版本的 LXC 让[用户为创建根文件系统的容器](https://help.ubuntu.com/lts/serverguide/lxc.html)创建模板，而 LXD 则依赖于这样一个事实，即现代容器是由图像组成的，因此不再使用模板。

“LXD 是我们重新开始的机会，”格雷勃周二在他的个人博客的[帖子中写道。“我们将继续让 LXC 保持其低层次集装箱管理公司的地位。并在此基础上构建 LXD，使用 LXC 的 API 完成所有底层工作。这实现了两全其美:我们保留了低级别的容器管理器及其 API 和绑定，但跳过了使用其工具和模板，而是用 LXD 提供的新体验来取代它们。”](https://www.stgraber.org/2015/04/21/lxd-getting-started/)

## 翻译矩阵

LXD 集装箱的分配机制是这个故事中最重要的部分。我先用 Linux 语言给你解释，然后翻译成英语。(如果我成功了，一个光明的未来可能会在英国广播公司国际部等着我。)

您可以从 LXC 命令行启动 LXD 守护进程。从那里，您使用 **remote** 命令来声明各种 Linux 容器的位置，这些容器可以被列为一种基本的目录。有了这个目录，您可以使用 **launch** 命令选择一个映像并在本地运行它。要启动本地 shell 来执行容器内部的命令，就像在网络上发布远程命令一样，可以使用熟悉的 **exec** 命令。

现在，再次用英语播报新闻要点。

你记得台式机吗？桌面的全部意义在于让你能够访问你已经安装在本地的东西——你的程序和你的文档。好吧，假设你需要运行的一切都可以从容器中运行，你需要存储的一切都可以存储在云中，谁还需要桌面呢？

真正的头条新闻是:LXD 可以将桌面客户端操作系统完全转变成某种更像定制控制的集装箱起重机的东西，将集装箱从存储中心吊起，放到合适的位置，然后运行它们。“安装”变得无关紧要。此外，使用网络协议对个人存储进行寻址实际上比使用本地地址更加方便。

也许“D”代表“颠覆”

尽管 Ubuntu 挂着鲜艳的蓝鲸旗帜，但“D”并不代表——至少现在还不是——Docker。正如 Ubuntu 在 LXD 的营销页面上写的那样，“为了以最有效的方式将你的二进制文件交付给一个平台来执行，Docker 是我们的舞蹈。”

显然，这种舞蹈是一种失败，可能类似于史蒂夫·沃兹尼亚克在《与星共舞》中尝试的

斯蒂芬·格雷伯明确表示，尽管 Docker 最初可能是为 LXC 建造的，但 LXD 与 Docker 有些不同。“LXD 的重点是系统容器，”他写道。也就是说，运行 Linux 发行版的干净副本或完整设备的容器。从设计的角度来看，LXD 并不关心容器中运行的是什么。这与 Docker 或 Rocket 非常不同，它们是应用程序容器管理器(相对于系统容器管理器)，所以专注于将应用程序作为容器分发，所以非常关心容器内部运行的内容。”

如果 Canonical 能够超越这个小差异，学会说其他人的语言，它有可能为 Linux 客户端操作系统注入通用的、常识性的相关性，这可能是十年来的第一次。

通过 Flickr Creative Commons 的特色图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>