# 认识一下 Alpine Linux，Docker 的容器选择发行版

> 原文：<https://thenewstack.io/alpine-linux-heart-docker/>

Alpine Linux 发行版是作为 T2 LEAF T3(Linux 嵌入式设备框架)项目的一个分支而诞生的，这个项目本身是一个非常小的发行版的一个分支，这个发行版就是现在已经不存在的 T4 Linux 路由器项目 T5(LRP)。

Alpine 背后的概念是创建一个可以在 RAM 中运行的轻量级和简单的防火墙/代理/VPN 发行版。Alpine Linux 的创造者 Natanael Copa 在一次采访中解释说:“这个想法是，系统在从只读介质启动时安装在内存中，一旦启动，你可以删除启动介质。

真正意义上的 Alpine Linux 是技术人为技术人创造的。它的目标一直是技术人员，他们可以自己修理东西，并有技术技能来做出贡献。

2016 年当 [Docker](http://www.docker.io) 决定将 Docker 官方图片库从 [Ubuntu](https://www.ubuntu.com/) 切换到 Alpine 时，Copa 加入了公司。Docker 是科技行业最热门的词汇，这种关注改变了 Alpine Linux，因为它现在吸引了更多的初学者。

“用户范围相当广泛。Docker 将 Alpine 用于生产和运输产品。还有其他非营利组织使用 Alpine，包括电话公司、托管公司，”Copa 说。

除了 Docker，Alpine 也被许多安全相关的项目使用，但是这些人不想公开谈论他们正在使用什么，所以 Alpine 仍然在媒体的雷达之外。

被技术先进的项目利用的一个好处是，作为回报，Alpine 从开发和维护 Alpine 的技术先进的人那里获益。“我们中的一些人得到赞助在阿尔卑斯山工作，一些人利用我们的空闲时间在上面工作，”科帕说。“我们大多数人对编码更感兴趣，而不是告诉世界 Alpine 有多好。”

这些人为使用 Alpine 的公司和组织工作。所以有一个非常强的共生关系，这也创造了项目的稳定性和可持续性。“有各种组织和公司正在帮助提供资金。有些人赞助开发人员开发 Alpine，例如 Docker，有些人提供硬件和基础设施。例如，Docker 支持开发， [Scaleway](https://www.scaleway.com/) 提供托管， [Fastly](https://www.fastly.com/) 提供内容交付网络，许多其他公司以不同的方式提供支持，”他说。

## 规模确实很重要

阿尔卑斯山的独特之处在于它的规模。较小的尺寸使它非常安全和高效。当我问及 Alpine Linux 与 Linux 世界的大公司如 [Red Hat Enterprise Linux](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux) 和[SUSE Enterprise Linux Server](https://www.suse.com/de-de/products/server/)在效率方面的主要区别时，Copa 说:“它们可能比 Alpine 更完善，而且(在许多事情上)更容易使用，但我仍然要说，与 Alpine 相比，它们都很大，而且速度很慢。我的意思是，‘apt-get update’更新软件包索引缓存的时间几乎与 Alpine 执行整个系统安装或升级的时间相同。”

他不只是提供一个假设。他提供了一个真实的对比:

```
$  time docker run  --rm  -it ubuntu sh  -c  "apt-get  update &amp;&amp; apt-get install -y gcc"
...
real  0m  12.66s
user  0m  0.03s
sys  0m  0.01s

$  time docker run  --rm  -it alpine sh  -c  "apk add --no-cache gcc"
...
real  0m  4.68s
user  0m  0.03s
sys  0m  0.00s

```

它们都有自己的用例。

## 阿尔卑斯山和集装箱:天作之合

Alpine，尽管它早于 Linux 容器的流行，却很好地补充了容器的概念。“最初的目标是从 RAM 运行，这是一种一次性系统，每次重新启动时都会重新安装。这非常符合一次性容器的概念，”科帕说。

早在名称空间进入主线内核之前，Alpine 就支持 [vserver 容器](http://linux-vserver.org/Welcome_to_Linux-VServer.org)。“我们有一种 alpine-vserver 风格，并将其用于我们自己的基础架构。我们后来用不需要任何特殊内核补丁的 [LXC](https://linuxcontainers.org/) 替换了它。所以我们长期以来一直支持和使用容器，”他说。

当 Docker 社区在寻找一个发行版时，他们发现如果使用 Alpine，他们可以使他们的容器变得更小，并且与其他发行版相比，构建 Alpine 容器只需要很少的时间。

“这使得阿尔卑斯山社区在过去两年里发展非常迅速。就连 Docker Inc .也盯上了 Alpine，所以现在 Docker 赞助了 Alpine 的开发，”Copa 补充道。“所以 Alpine Linux 非常适合容器，并且从一开始就参与了容器游戏。”

## 阿尔卑斯山的内脏

Alpine 最初是用 [Gentoo](https://gentoo.org/) 构建的，但现在是独立自主的。它使用了 [Linux 内核](https://www.kernel.org/)(带有 [grsecurity 补丁](https://grsecurity.net/)的非官方端口) [musl](https://www.musl-libc.org/) C 库、 [BusyBox](https://busybox.net/) 、 [LibreSSL](https://www.libressl.org/) 和 [OpenRC](https://wiki.gentoo.org/wiki/OpenRC) 。

“我们最初使用的是 Gentoo 强化工具链，因此我们可以使用 Gentoo 强化的安全特性。Copa 说:“我们需要额外的强化，因为典型的使用案例是针对 VPN 和防火墙等安全设备。后来，我们增加了对磁盘安装的支持，但我们仍然支持并使用从 RAM 运行的安装方式

Alpine 使用自己的包管理器，名为 [apk-tools](https://wiki.alpinelinux.org/wiki/Alpine_Linux_package_management) 。不要和安卓的混淆。apk 格式。在这里，APK 代表阿尔卑斯山包保管员。Alpine 一直在使用“apk-tools”和“apk”在谷歌收购安卓公司之前。

因为 Alpine Linux 需要非常小，所以它的开发者希望所有的东西都能放在内存中，所以他们必须把东西做得尽可能小。除此之外，“由于系统每次重启都是从头开始安装的，所以我们需要一个速度也很快的包管理器，”Copa 说。

Alpine 社区在编写他们自己的包管理器之前做了大量的研究。“我们评估了来自 Arch Linux 的 pacman。deb，ipkg，。rpm 等，”科帕说。“我们最终使用自己的产品的主要原因是我们的‘从内存中运行’要求。我们需要一个能够从 initfs 设置 tmpfs rootfs 的快速管理器。”

Alpine 开发人员还希望已安装的软件包数据库开销低。Copa 补充说:“我们的主要要求是，它应该只有几个文件作为完整状态——所有其他文件通常每个安装包都有一个或多个文件。

为了向用户交付软件包，Alpine 使用“aports”，这是发行版的移植应用程序树，少数 Alpine 软件包维护者与上游保持同步。他们从这个树中构建一个包存储库，并将它同步到主镜像。然后有一个镜像站点列表，它将镜像存储库，最终用户将使用“apk add”通过 HTTP 获取所需的包。为了确保安全性和完整性，包被签名，apk add 验证它们没有被意外或故意修改。

## 安全不是一个指向和拍摄相机

最近，我们开始听到很多关于 Linux 的安全漏洞。这并不是说 Linux 变得越来越不安全，只是现在它在关键领域被大量使用，以至于它得到了它一直需要的额外关注。

然而，Copa 和许多其他公司一样，并不黑白分明地看待安全问题。Copa 认为，如何衡量安全性因你询问的对象而异。“我认为业内的一个误解是，安全就是尽可能快地推出安全修补程序，我认为这是因为跟踪 CVE 和检测到并解决它们的时间是最容易衡量的事情。但是安全远不止这些，”Copa 说。

虽然及时修补补丁很重要，但这并不是保护软件的唯一方法。Copa 表示:“我们会跟踪安全漏洞，并努力发布最新的软件。“我没有这方面的统计数据，但我相信我们能够相对较快地提供修复，如果我们比其他发行版平均更快，我不会感到惊讶。但及时修复 CVEs 远不是我们维护安全所做的唯一事情。”

修复 bug 是一种反动的方法。除此之外，Alpine 团队还采取主动措施，通过设计来确保安全。第一步是让核心系统尽可能小。

Alpine 从不安装很多用户永远不会使用但可能会很方便的东西。一个例子是 [Bash shell](https://www.gnu.org/software/bash/) 。默认情况下没有安装 BashAlpine 使用 BusyBox Bash 作为默认 shell。因此，没有任何阿尔卑斯系统受到 2014 年 [ShellShock](https://www.symantec.com/connect/blogs/shellshock-all-you-need-know-about-bash-bug-vulnerability) Bash 漏洞的影响。

除了保持预装组件的数量较低之外，Alpine 还通过默认不启用来增加另一层安全性。Alpine 所做的只是提供构建模块，让经验丰富的系统管理员来实现他们需要的功能。这与许多发行版的做法相反:它们不仅默认安装了很多东西，还默认启用了很多东西。在这些情况下，为了保证系统的安全，系统管理员必须首先禁用一些东西。

Alpine 在为核心系统选择安全库时也非常保守。如果需要的话，如果他们发现更安全的东西，他们也会替换图书馆。“我们最近用 LibreSSL 替换了 OpenSSL，因为我们认为这是一个更安全的库，”Copa 告诉我。“我们使用 musl libc 作为标准的 C 库，这是一个现代的 C 库，可以避免许多你在 GNU libc 中发现的会给你带来麻烦的糟糕设计决策。”

默认情况下，Alpine 还为系统管理员提供了一个强化的工具链。Copa 说:“这意味着堆栈粉碎保护(-fstack-protector)、位置独立可执行文件和带有 bind-now 链接的完整[RELRO](http://tk-blog.blogspot.de/2009/02/relro-not-so-well-known-memory.html)[内存损坏缓解技术]都是默认启用的，如果您无法使用它们，您必须显式禁用它们。”“虽然许多其他发行版已经为他们的许多或大部分软件包启用了这些功能，但我们总是为每个单独的软件包启用这些功能，因为 Alpine 的第一个版本就已经启用了。”

Alpine 团队从第一个版本开始做的另一个聪明的举动是为内核使用 grsecurity 补丁。这些天他们使用了一个非官方的版本，因为稳定内核的补丁还没有公开。这个内核，加上强化的工具链，使得利用安全漏洞变得更加困难。

“所有这些因素加在一起，使得 Alpine 成为那些关心真正安全，而不仅仅是关心上面有许多绿色“OKs”的漂亮图形的人的好选择，”他说。

最近另一个流行词是自动更新。但是阿尔卑斯山没有。“我们不提供自动更新，但对于那些对此感兴趣的人来说，用 Cron 工作来做应该是微不足道的，”他说。

他认为安全性最终是系统管理员的责任，因为大部分是在配置中，但 Alpine 社区希望提供良好的默认设置和工具来实现这一点。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>