# 对 Linux 通用软件包有什么期望(和不期望)

> 原文：<https://thenewstack.io/expect-not-expect-linux-universal-packages/>

去年六月， [Canonical Software 推出了](https://insights.ubuntu.com/2016/06/14/universal-snap-packages-launch-on-multiple-linux-distros/)开发的 [Snap](https://snapcraft.io/) 软件包，旨在用于任何 Linux 发行版。一周后，红帽宣布了自己的通用软件包版本，名为 [Flatpak](http://flatpak.org) 。几个月以来，Flatpak 和 Snap 都被宣传为传统封装格式问题的解决方案。然而，这些解决方案并不像宣传的那样完整，并且要求重新安排安全责任，而自由软件根本没有为此做好准备。

传统上，Linux 依赖于两种主要的包格式。deb (Debian)和。rpm(红帽)。虽然结构不同，但两者。黛比和。rpm 软件包包括为特定发行版定制的上游软件，以及安装任何依赖项的脚本，即所需的库、实用程序和其他软件包，这些软件包尚未安装在系统上。这种安排将所需的硬盘空间限制到最小，这两种格式在近二十年来都很好地服务于 Linux。

然而，近年来，这些传统形式受到越来越多的批评。Canonical 物联网营销主管 Thibaut Rouffineau 表示:“Linux 用户越来越期待应用程序的消费者体验——例如，更像智能手机上的应用程序体验。Rouffineau 批评使用。黛比或者。rpm 具有“严格而复杂”的需求，这减缓了新版本的推出，并通过要求几乎每个发行版都有单独的软件包版本而使 Linux 支持复杂化。

通过让上游开发者创建包并将所有依赖项作为每个包的一部分，Snap 和 Flatpak 旨在简化和加速向用户交付最新软件，同时为上游开发者提供更及时的反馈。

> 容器没有检测更新需求或自动更新的机制，因此本身就是漏洞的来源。

Red Hat desktop group 的 Alexander Larsson 是 Flatpak 的最初开发者，他指出，通用软件包可以通过安装在与系统其余部分隔离的容器中来增加另一层安全性。Larsson 说:“在单个桌面中分离安全域的方法使得以更好的方式防止(入侵和隐私丢失)成为可能。”

这些优势已经在 Snap 和 Flatpak 的主页上广泛公布和陈述，这一事实掩盖了许多人的现实，即这些优势仍在开发中，有时希望大于现实。例如，Larsson 提到容器对于 Flatpak 来说是可选的，沙盒的级别各不相同，因此“目前很少有 Linux 应用程序可以完全包含。”此外，Rouffineau 和 Larsson 都认为传统和普遍的一揽子计划是共存的，而不是一个最终取代另一个。

然而，即便如此，通用软件包仍受到发行商的密切关注。例如，OpenSUSE 董事长理查德·布朗在最近的一次[福斯登](https://fosdem.org/2017/)演讲中推测，通用软件包可以减少[维护发行版](https://www.youtube.com/watch?v=mkXseJLxFkY)所需的工作量。出于这个原因，尽管有时会听到夸张的随意声明，但通用格式仍然可以成为 Linux 打包的游戏规则改变者。

## 集装箱的局限性

观察家们普遍注意到，Canonical 开发的 Snap 构建了广受欢迎的 Debian 衍生产品 Ubuntu 和 Red Hat 开发的 Flatpak，最终结果可能只是。黛比和。rpm 格式。然而，这种观察除了讽刺之外，没有什么更有用的了。其他的考虑要重要得多。

首先，容器并不是人们有时认为的通用安全解决方案。2017 年 4 月，北卡罗来纳州立大学的程序员[在 Docker Hub 上发布了一项关于安全漏洞的研究](http://dance.csc.ncsu.edu/papers/codaspy17.pdf)。在 356，218 个社区贡献的图像和 3，802 个官方图像中，该研究在社区图像中发现了平均 153 个漏洞，在官方图像中发现了 76 个漏洞，其中大多数漏洞的严重性很高。在另一项研究中，Banyan 博客的作者发现 Docker Hub 中超过 30%的官方图片包含高优先级的安全漏洞。

换句话说，虽然容器可以提供抵御入侵的安全性，但是没有什么可以保护用户免受容器中实际内容的侵害。正如 Debian 开发人员 John Goerzen 指出的那样，容器没有检测更新需求或自动更新的机制，因此本身就是漏洞的来源。

正如行业观察家 [Adrian Coyler](https://twitter.com/adriancolyer) 所指出的，他[总结了北卡罗来纳州立大学的研究](https://blog.acolyer.org/2017/04/03/a-study-of-security-vulnerabilities-on-docker-hub/)，问题的很大一部分似乎是为了方便起见，新的软件包经常借用旧软件包的依赖关系，使得漏洞的永久存在变得非常可能。事实上，即使一个容器化的包在创建时是最新的，以后也可能被证明有漏洞，但仍会被继续使用。随着自动化工具的引入，如 [Docker 安全扫描服务](https://docs.docker.com/docker-cloud/builds/image-scan/)，这些问题可能会得到缓解，但是，即使如此，很大程度上仍然取决于软件包维护者的责任心。

## 政策与技术

所有这些都带来了另一个问题:尽管技术社区本能地在新技术中寻找解决方案，正如 Debian 的长期维护者 Josh Triplett 所观察到的，“技术并不能取代对政策的需求。”

要求在邮件列表上比较。deb 格式有了通用包，Triplett 根本不为技术格式辩护。“这个。孤立的 deb 格式仅仅代表了文件的存档；他说，真正成为 Debian 软件包的是 Debian 政策。Debian 没有。deb 格式仍然是 Debian 没有 Debian 政策的 Debian 将只是 SourceForge 或 Rpmfind”——也就是说，没有全面质量控制的软件包和源代码的集合。

Triplett 指的是 [Debian Policy Guideline](https://www.debian.org/doc/debian-policy/) ，这是一份冗长的文件，详细说明了 Debian 发行版的软件包必须包含和不能包含的所有内容，以及它必须如何与其他软件包交互。文件应该放在哪里，日志应该如何运行，xservers 和终端的格式，如何在桌面环境中添加一个菜单项——所有这些都在 Debian 策略中指定。

在一个 Debian 包从不稳定的仓库转移到测试和稳定的仓库之前，它已经被反复检查过是否符合 Debian 政策。Triplett 指出，正是这种审查使 Debian 成为了 Linux 中的标准，也是三分之二的活跃发行版的来源，尤其是那些与安全有关的发行版。

该政策也不会以符合 Debian 政策而告终。正如约翰·戈森 [博客](http://changelog.complete.org/archives/date/2017/04/29)所言:

*如果你运行的是 debian 系统，无人值守更新、needrestart、debsecan 和 Debian 安全支持的组合将有助于保证 Debian 系统的安全并验证其安全性。[……]Debian 的安全团队通常会反馈修复，而不只是说“这是新版本”，这使得自动应用补丁非常安全。只要我使用 Debian stable 中的东西，上面提到的所有层(所有东西)都将通过这个方案得到保护。*

到目前为止，Snap 和 Flatpak 都没有像 Debian 那样完善的政策。在目前的发展阶段，任何人都不应该指望它。然而最终，Flatpak 和 Snap 能否兑现它们的所有承诺将取决于构建软件包的政策，而不仅仅取决于它们的技术特性。

## 上游与发行版

出现的其他问题是:谁来执行通用包装的质量控制？与此密切相关的是，在发布过程中的哪一点将会强制执行？

正如 Triplett 和 Goerzen 所说，传统上，质量控制发生在分销层面。在许多情况下，上游开发人员传统上只提供源代码，将打包完全留给发行版。最多，他们为一些流行的发行版提供不同质量的包——通常是 Ubuntu。

这种安排就是为什么当如此多的 Linux 发行版存在时，对编写应用程序的困难的抱怨是无效的——在当前的安排下，上游开发者不负责为发行版裁剪他们的代码；发行版为自己做了这些。例如，当 Steam 移植到 Linux 时，最初的开发工作是为 Ubuntu 开发的，几周之内其他发行版就为自己的发行版改编了 Ubuntu 版本。

然而，如果通用软件包在没有发行版维护者介入的情况下发布，这意味着上游开发者将自己测试软件包并执行策略。正如 Richard Brown 在他的[fosdem 演讲](https://www.youtube.com/watch?v=mkXseJLxFkY)中所说，“有了这些工具，Flatpak 和 Snappy，唯一真正的解决方案就是开始像发行版一样思考。你将不得不承担与我们在分销领域相同的责任。”自动化测试可能会简化这个过程，就像它对 openSUSE 所做的那样，但是在某些时候，它仍然需要被完成。

此外，布朗警告说，所有的分布并不是以同样的方式构成的。他们将文件放在不同的位置，有时使用不同的应用程序来协调他们的 Linux 版本。“你仍然需要在每一个可能的发行版上开发和测试所有的东西，”Brown 说。“除非你把所有你需要的东西都捆绑在一起，否则你最终会哭的。”

Brown 总结道，正如通用软件包的早期成果, [AppImage](http://appimage.org/) 的经历所示，通用软件包可以在任何 Linux 发行版上运行的想法目前是不可能的。他认为通用软件包能够实现其承诺的唯一方式是，像 [Linux 标准库](https://wiki.linuxfoundation.org/lsb/start)这样的标准被用在每个发行版上——这种努力在过去已经失败了。

布朗对通用软件包承诺的快速发布感兴趣。然而，基于 [openSUSE 对其](https://www.opensuse.org/) [Tumbleweed 版本](https://en.opensuse.org/Portal:Tumbleweed)的经验，Brown 建议[滚动版本](https://en.wikipedia.org/wiki/Rolling_release)——持续更新而不是整个发行版的完整正式版本——可能是比通用软件包更实用的快速发布新版本的解决方案。否则，将包准备工作转移给上游开发人员会让他觉得这是一项额外的责任，很少有人愿意承担。责任的转移也是不必要的，因为基于发行版的开发者已经在扮演这个角色，并且拥有做好它所需要的经验。

## 一旦尘埃落定

出于这些考虑，那些期待通用软件包取代传统格式的人几乎肯定会失望。平心而论，那些最大程度地参与通用方案开发的人也没有任何这样的期望。

“我们看到了 Snap 和传统包装管理系统之间的共存，”Rouffineau 说。“例如，deb 包提供了灵活性，而 Snaps 提供了易用性。传统的软件包是构建操作系统的最佳解决方案，在这种情况下，一小组人管理大量的深度互连的软件包。另一方面，快照是分发独立、单机应用程序的更好解决方案，无论是在台式机上还是在无头服务器/设备上。”

同样，Larsson 说，“Flatpak 确实只适用于桌面应用程序，并不适合核心操作系统本身。我希望将应用程序从核心操作系统中分离出来，形成一种模式，让发行版能够专注于改进核心，而不是在它们能够打包多少不同的应用程序方面进行竞争。”

随着通用包的应用越来越广泛，其用途也会逐渐变得更加明显。发行商已经通过准备所有格式的发行来对冲他们的赌注。例如，openSUSE 目前支持 Snap、AppImage、Docker 的构建，但不支持 Flatpak，OpenSUSE 的构建基础架构经理 Adrian Schrö ter 称 flat pak 仍然存在“可重复构建的未解决问题”。

与此同时，尽管通用的一揽子计划仍在开发中，但了解它们能做什么和不能做什么，对于应对不切实际的期望的上升非常重要。

[红帽](https://www.openshift.com/)是新栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>