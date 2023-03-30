# 洛克波特:是时候从头再来，回到 LXC 集装箱公司了

> 原文：<https://thenewstack.io/flockport-time-to-start-all-over-again-and-return-to-lxc-containers/>

几乎可以接受的是，Docker 已经为容器设定了标准，而 Kubernetes 则在编排方面游刃有余。但是一家总部位于孟买的初创公司认为，我们需要把事情带回起点，从头再来——这一次用 Linux containers (LXC)而不是 Docker。

Flockport 在 2013 年开始时是一个服务器端应用程序的应用程序商店，后来它转移了重心，成为 Kubernetes 等更复杂解决方案的替代方案，Flockport 创始人 [Indrajit Banerjee](https://www.linkedin.com/in/indrajitb/?originalSubdomain=in) 说，Kubernetes 引入了更多的复杂性，需要更多的专业知识，超出了大多数公司的能力。班纳吉说，这个问题来自于远离 LXC 和 Docker 做出的三个具体设计决定。

“LXC 项目给了你标准的多进程容器。它们就像轻量级虚拟机。Docker 采用了这种方法，并对其进行了修改，为您提供了‘单进程容器’，”Banerjee 在一封电子邮件中写道。"在复杂性和管理开销方面，这些都有显著的下游影响."

指着他写的一篇关于为什么你应该“[对容器说是，对复杂性说不](https://www.flockport.com/guides/say-yes-to-containers)”的博客文章，Banerjee 解释说，他指责 Docker 强制实施单进程容器，通过使用 **aufs** 和 **overlayfs** virtaul 文件系统使用层，以及使容器化的应用程序“通过法令无状态化”——他认为这三个决定导致了难以管理的复杂性水平。

今年早些时候，经过几年的努力，Flockport 发布了新的混合和多云部署容器平台，旨在简化应用程序迁移和部署。

[https://www.youtube.com/embed/fEmxPHbbfR4?feature=oembed](https://www.youtube.com/embed/fEmxPHbbfR4?feature=oembed)

视频

Banerjee 在一份公司声明中写道:“企业越来越多地采用混合和多云策略，容器是解决这种用例的完美工具。”“虽然 DevOps 的目标是开发人员，但容器的真正故事是在部署中，而 Flockport 提供了一个全面的平台，展示了容器的真正力量和灵活性。”

Flockport 提供了 Banerjee 所说的“标准操作系统环境”，这意味着它不需要无状态应用程序、层的使用或对容器的单个进程的限制，从而提供了“从虚拟机无缝迁移应用程序，而不需要任何定制或昂贵的重新设计”，并允许应用程序“按原样”迁移

在接受 New Stack 的采访时，Banerjee 表示，Docker 和 Kubernetes 提供的这种“非标准操作系统环境”对于寻求从遗留应用程序迁移到容器的公司来说意味着困难。

“当我们开始时，我们发现 Docker 存在许多问题。这造成了一点管理开销，一点复杂性。它给你一个非标准的操作系统环境。在堆栈的基础上，您有一个非标准的操作系统环境，这增加了复杂性。当你想移民时，这就成了一个障碍。“对于容器来说，这是一个巨大的机会，一切都部署在虚拟机中，您可以使用所有工具无缝地从虚拟机过渡到 LXC 容器，而无需管理单进程容器和 Docker 的工作方式。我认为这在某种程度上阻碍了转型。”

Banerjee 认为，容器复杂性的现状所带来的威胁甚至超出了迁移的复杂性，而是威胁到整个行业。他将当前的氛围与 OpenStack 的氛围进行了比较。

“整个生态系统目前是关于 Docker 和 Kubernetes 以及所有其他服务，所有其他公司都在围绕这些服务构建解决方案。同样的事情也发生在 OpenStack 上，但人们不断抱怨它的复杂性，在某一点上，它就这样消失了，”Banerjee 说。“这也是我所担心的，因为这可能会让人们离开容器，他们会继续使用 AWS 和虚拟机，而不会打扰。如果要这么复杂，这么贵，有什么好处？”

Flockport 首次向公众发布其软件，并提供容器管理、服务器供应、网络、存储和服务发现的[演示](https://www.flockport.com/demos)。Banerjee 说，Flockport 是用 Python 编写的，并在 GPL 许可下开源，尽管这个五人小组还没有把它放到 GitHub 上。Flockport 目前可用于[下载](https://www.flockport.com/demos)，既可以安装，也可以作为虚拟机运行。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>