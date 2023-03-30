# 回到未来:CentOS Streams 一览

> 原文：<https://thenewstack.io/back-to-the-future-a-look-at-centos-streams/>

多年来，CentOS 一直是企业 IT 行业的宠儿。作为一个开源操作系统，它在稳定性方面接近于 Red Hat Enterprise Linux，这是 Linux 发行版无需支付 RHEL 许可证即可获得的稳定性。对一些人来说，CentOS 是一个远远优于大多数竞争对手的平台。多亏了极其缓慢的发布周期，操作系统总是很稳定，很少遇到经常绊倒运行速度更快的平台的问题。

CentOS 也非常安全。随着 SELinux 成为 Linux 的标准基础，安全性成为企业选择 CentOS 的主要驱动力之一。

12 月， [Red Hat 停止了对 CentOS 的进一步支持](https://thenewstack.io/wherefore-art-thou-centos-rocky-linux-cloudlinux-and-centos-stream/)，这让大量管理员不知如何是好。代替可靠的发行版，将部署滚动发布版本。

滚动发布是 CentOS 流，它不像原来的。

虽然这听起来不像是一个剧烈的变化，但确实如此。但事实确实如此。事实上，从标准 CentOS 到 CentOS 流的转变已经让像 [cPanel](https://cpanel.net/) 这样的主要参与者转向别处。任何提供主机服务的人，都非常熟悉 CentOS/cPanel 的组合，并被 Red Hat 的决定抛在了一边。

## 什么是 CentOS 流？

首先，让我们看看 CentOS 流到底是什么。需要说明的是，CentOS Stream 并不像你所理解的那样是一个滚动发行版。

什么是滚动发布？简单:一个滚动发布版本摆脱了标准的主要发布版本和次要发布版本的束缚。比如 Ubuntu 即将发布 21.04，随后会有 21.10 跟进。这就是每年 Ubuntu 发布的方式，就像时钟一样。每年四月都会发布一个 0.04 主版本，十月会发布一个 0.10 次版本。每一个的更新一旦可用，就会发布到存储库中。

通过滚动发布，主要版本可用，更新在准备就绪时发布。因此，滚动发布不是小的点发布，而是只要包准备好了就更新包。

许多人认为滚动发布是一种在系统中始终拥有最新软件包的方式。然而，其他人认为这是给分布带来不稳定性的一种方式。也就是说，一般来说，不是这样。在滚动发布版本中，软件在发布之前会经过测试。点版本和滚动版本之间最大的区别是，更新在滚动版本中不断推出，而软件被推迟到点版本候选中的下一个次要版本。

然而，CentOS 并不完全是一个滚动版本。嗯，确实是。但事实并非如此。你得到的答案取决于你问谁。根据 Red Hat 的说法，CentOS 是一个“持续交付的发行版，跟踪 Red Hat Enterprise Linux (RHEL)的开发，定位为 Fedora Linux 和 RHEL 之间的中游”

因此，如果你从红帽的市场角度来看，CentOS 是一种混合体。但是这在实时应用中很难应用。任何了解 Linux 版本如何工作的管理员都会告诉你 CentOS Stream 是一个滚动版本。事实上，如果你回到最初的红帽 CentOS Stream 公告，它清楚地表明 CentOS Stream 项目位于 RHEL 开发过程中的 [Fedora 项目](https://getfedora.org/)和 RHEL 之间，提供了未来 RHEL 内核和功能的“滚动预览”。

滚动预览有点泄露了。

了解 CentOS Stream 在 Red Hat 开发生命周期中的位置也很重要。正如 Red Hat 所说，CentOS 刚好在 RHEL 前面，所以这条河流看起来像:

软呢帽> > CentOS >> RHEL

所以 CentOS Stream 实际上是 RHEL 的发展分支。这是一个重大转变，因为绝大多数 CentOS 用户部署了该操作系统，因为它跟踪了 RHEL，这意味着 CentOS 受益于 RHEL 的大量开发工作。很难看出这种情况是否会继续下去。现在看来，RHEL 将受益于 Fedora 和 CentOS Stream 的发展。

## 一点 CentOS 的历史

CentOS 的出现在 Linux 领域非常典型。它开始于 Gregory Kurtzer 为维护一个围绕他当时参与的项目的构建系统所做的努力 [CAOS Linux](https://archiveos.org/caos/) 。最终，CentOS 这个名字被采用了，大卫·欧芹加入了 Kurtzer，并把他自己的项目(Tao Linux)加入了新的发行版。事情进展顺利，直到 2009 年 7 月，联合开发者兰斯·戴维斯带着 CentOS 域名失踪。直到 8 月份，CentOS 团队才联系了 Davis，并成功夺回了对 centos.info 和 centos.org 域名的控制权。

回到 2014 年，Red Hat 宣布将正式赞助 CentOS 项目，以帮助建立一个“非常适合开源开发者需求的平台”。CentOS 商标的所有权被转移到了 Red Hat，这看起来像是开源和商业的完美结合。

但随后 2020 年的到来对发行造成了特殊的破坏，红帽开始向 CentOS Stream 转移。

许多人认为基于流的分发不能提供与旧模式相同的弹性。企业 Linux 支持公司 OpenLogic [指出](https://www.openlogic.com/p/centos-8):

*针对公共 CentOS 流运行软件包升级将导致每天多次软件包更新，并可能向用户开放支持 Linux 软件包的不稳定版本。依赖 CentOS 社区来策划稳定的软件包版本的企业需要在他们的测试计划中考虑这一点。*

*如果您选择继续采用 CentOS Stream，一般来说，您当前交付软件的持续时间越短，您在发布时将面临的风险就越大。*

CentOS 的最新版本 CentOS 8 将在整个 12 月得到支持。它应该支持到 2029 年 12 月底。

## 一点 CentOS 未来

这是浑浊的水开始变清的地方。即使在开源和商业社区对 Red Hat 的举动做出了一些相当强烈的反应之后，这个世界上最大的开源企业也没有任何迹象表明它打算放弃这一举动。

那么会发生什么呢？

分叉发生了。

事实上，有两个项目肯定会吸引大多数 CentOS 用户离开红帽流。这些项目中的第一个是 [Rocky Linux](https://rockylinux.org/) ，它是 RHEL 的一个新的替代产品，具有 1:1 的二进制兼容性。

Rocky Linux 真正重要的是，它是由 Kurtzer 创建的[(正如你现在所知道的，他首先开发了 CentOS)。事实上，根据 Rocky Linux 网站，Rocky Linux 是一个社区企业操作系统，旨在与美国顶级企业 Linux 发行版 100%兼容，因为其下游合作伙伴已经转移了方向。](https://thenewstack.io/post-centos-rocky-linux-fights-for-community-driven-enterprise-open-source/)

Rocky Linux 将是一个下游版本，就像 CentOS 以前一样。这意味着第三方应用程序，如 cPanel，将很可能支持这一新的发行版，CentOS Stream 将不再对不断增长的用户群产生影响。

CentOS 的下一个分支来自 [CloudLinux](https://www.cloudlinux.com/) ，它在构建基于 Linux 的强化平台和基础设施方面拥有超过十年的经验。他们提供的将是另一个 1:1 的 RHEL 二进制兼容发行版，并且将是免费的、开源的、由社区驱动的。这个名为 [AlmaLinux](https://almalinux.org/) 的新发行版将于 2021 年在 Q1 发布——所以请继续关注。

## 你用 CentOS 8 做什么？

如果滚动发布的想法对你来说没有那么糟糕，并且你担心你当前的 CentOS 8 部署会发生什么，请不要担心。只需几个快速命令，您就可以将 CentOS 8 分期付款迁移到 CentOS 8 Stream，甚至无需重启。以下是方法。

登录您的 CentOS 8 服务器。您会发现必须使用以下命令安装 CentOS 流存储库:

`sudo dnf install centos-release-stream -y`

接下来，交换出原始的存储库，这样您的版本默认使用以下命令进行流式传输:

`sudo dnf swap centos-{linux,stream}-repos`

接下来，使用以下命令将当前版本与 CentOS Stream 同步:

`sudo dnf distro-sync`

完成后，您可以使用以下命令验证转换是否成功:

`cat /etc/centos-release`

您应该在输出中看到 CentOS Stream release 8。

如果你不同意在生产中使用滚动版本，你的另一个选择是继续使用 CentOS 8，直到 Rocky Linux 或 [AlmaLinux](https://almalinux.org/) 发布。当这种情况发生时，Rocky Linux 和 AlmaLinux 都计划通过一个用户友好的脚本(适用于 Rocky Linux)和一个命令(适用于 AlmaLinux)，使从 CentOS 迁移到 Rocky Linux 成为可能。

最终，CentOS 管理员和用户不必担心他们平台的未来。由于分流中的分叉，一点回到未来行动将他们的 CentOS 部署到红帽做出改变之前的时间，但这显然是面向一个开放的未来。

特征图片由[瑞安·哈飞](https://unsplash.com/@ryanhafey?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/s/photos/caboose?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>