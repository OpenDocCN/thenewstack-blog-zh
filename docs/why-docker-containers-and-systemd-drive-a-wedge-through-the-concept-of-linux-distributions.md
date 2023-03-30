# 为什么 Docker、Containers 和 systemd 打破了 Linux 发行版的概念

> 原文：<https://thenewstack.io/why-docker-containers-and-systemd-drive-a-wedge-through-the-concept-of-linux-distributions/>

由 [CoreOS](https://coreos.com/) 发布的火箭被许多人认为是对 Docker 的直接挑战，尤其是它发生在 [DockerCon Europe](http://europe.dockercon.com/) 的前夕，并有可能盖过在该活动中发布的新闻。Docker，Inc .的首席执行官 Ben Golub 很快以他对火箭公告的[初步想法进行了回击。这篇文章不是关于生态系统和风投资助的初创公司的政治，我将把这个问题留给](http://blog.docker.com/2014/12/initial-thoughts-on-the-rocket-announcement/)[科林·汉弗莱斯](http://blog.hatofmonkeys.com/blog/2014/12/03/docker)(注意 Docker 创始人兼首席技术官所罗门·海克斯的[精彩回应)。这也不是关于管理开源社区，我将把这个问题留给 Matt Asay。这里我想看一下 systemd，它是技术争论的核心。](http://blog.hatofmonkeys.com/blog/2014/12/03/docker/#comment-1723725845)

一段时间以来，围绕 systemd 的邪恶战争一直在 Linux 世界肆虐。几乎系统上的所有东西都会被选择作为系统上的第一个进程，以及它是如何影响所有东西的启动的。人们非常关心这些东西，争论也很激烈。然而，马克·舒托沃尔斯代表 Ubuntu 承认失败标志着 systemd 的最后一次大发行。除非像 [Devuan](https://devuan.org/) 这样的分支取得成功，否则在几年时间内，如果没有 systemd 的参与，很难获得 Linux。

由于 CoreOS 是一个全新的发行版，他们从一开始就选择了 systemd。这是一个显而易见的举动，坦率地说，其他任何事情都会显得非常可笑。然而，多克是另一代人的孩子。Docker 无法与 systemd 结盟，然后坐等它流行起来。Docker 不得不使用已经存在的东西，这些东西现在大多不是基于 systemd 的安装。这就是 Docker 作为守护进程安装的原因，它很不舒服地位于 CoreOS 和其他基于 systemd 的发行版的进程管理范围内。达伦·谢泼德在他的文章《Docker 有根本缺陷吗？》中很好地解释了血淋淋的细节。，他的结论是，真的没有根本性的缺陷:

“这并不是说 Rocket 没有一个独立的守护进程，只是这个守护进程恰好是 systemd，PID 1，它作为 root 运行。那么 Docker 是否存在根本性缺陷？我无法想象你怎么能这么说，因为 Rocket 遵循一个非常相似的范例，它只是碰巧被内置到 systemd 中。根本问题是 Docker 和 systemd 都想成为管理容器的守护进程。”

具有讽刺意味的是，总体上向容器的转移，尤其是 Docker，正在打破 Linux 发行版的概念。CoreOS、RedHat 的 [Project Atomic](http://www.projectatomic.io/) 和 Ubuntu 的[‘Snappy’Core](http://www.ubuntu.com/cloud/tools/snappy)都被定位为运行 Docker 的发行版。与此同时，新的发行版在 Docker 中运行的领域是敞开的(目前 Docker 通过让开发人员坚持他们所知道的并继续使用他们选择的发行版而取得了巨大的成功)。非常清楚的是，在容器中根本不需要 systemd 一个 init 系统并不是单个进程(甚至是支持一个给定服务的几个进程)所必需的。对于启动 Docker 来说，systemd 似乎也是大材小用，并且与过程控制方法不匹配。因此，也许 systemd 拒绝派是对的——它似乎在集装箱服务的世界里没有任何合适的位置。

Docker 方法和 Rocket 方法的选择可以归结为用户体验，或者缺乏用户体验。Docker 在开发人员中一炮而红，因为它的用户体验简单而熟悉。谢博德认为这是火箭的劣势所在，火箭缺少什么？用户体验。但也许这才是重点——运营不应该有用户体验；它只是变成了在幕后自动运行的东西。开发和运营二分法是错误的，是由过于简单的组织结构造成的，并由开发运维运动解决。Docker vs Rocket 也可能是一个错误的选择，因为 Docker 的开发人员友好的 CLI、API 和 Dockerfile 完全有可能通过一个有助于大规模操作的可移植容器规范结合在一起。systemd 在这一领域是否有一席之地还有待观察。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>