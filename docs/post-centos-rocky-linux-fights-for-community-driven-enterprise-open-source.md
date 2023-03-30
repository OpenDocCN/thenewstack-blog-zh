# 后 CentOS 时代，Rocky Linux 为社区驱动的企业开源而战

> 原文：<https://thenewstack.io/post-centos-rocky-linux-fights-for-community-driven-enterprise-open-source/>

本月早些时候，当[红帽](https://www.openshift.com/try?utm_content=inline-mention)突然[终止对](https://thenewstack.io/red-hat-deprecates-linux-centos-in-favor-of-a-streaming-edition/)CentOS Linux 发行版的支持时，世界各地的大量用户突然失去了企业级 Linux 的选择。现在，CentOS 的最初创造者 [Gregory Kurtzer](https://gmkurtzer.github.io/) ，已经开始了一个新的发行版 [Rocky Linux](https://rockylinux.org/) ，以取代 CentOS，甚至介绍一些 Kurtzer 在 CentOS 工作期间学到的痛苦教训。

Kurtzer 在 Changelog 播客的一次精彩采访中说，Rocky Linux 将代表“一个开源项目应该如何运行，应该如何维护，以及我们如何采取预防措施，以确保它不仅是包容性管理和稳定的，而且有必要的适当社区承诺，以确保 CentOS 发生的事情不会再次发生。

CentOS 最初是本世纪初开始的一个项目的分支，该项目旨在创建一个基于社区的 RPM Linux 发行版，名为 [CAOS Linux](https://archiveos.org/caos/) 。当时，该项目的构建系统是在 Red Hat Linux 上构建的，Red Hat Linux 是今天的 Red Hat Enterprise Linux 的前身。Red Hat 在 2003 年关闭了这个非常流行的发行版，让混乱的 Linux 用户没有了构建系统。该项目的志愿者之一 Rocky McGaugh 自愿建立一个基于 RHEL 的新发行版。他们将它命名为 CentOS，意为“面向社区的企业操作系统”，它立即起飞，使用户群中的 Chaos Linux 项目相形见绌。(Rocky Linux 的名字来自 McGaugh，他已经去世了。)

Kurtzer 在谈到 CentOS 时表示:“看到这一点非常了不起，获得了如此高的可见性，然后看到它在企业生态系统和云生态系统中的定位有多好。”。

几年后，在受到 Red Hat 商标侵权诉讼的威胁后，Kurtzer 离开了这个项目。但是今天，根据 W3Techs 的数据，CentOS 是互联网上第三个使用最广泛的发行版，占所有服务器的 17.3%。它仅次于 Ubuntu (47.6%)和 Debian (18.8%)，甚至远远超过 RHEL 本身，仅占所有网站的 1.7%。

许多[认为](https://thenewstack.io/wherefore-art-thou-centos-rocky-linux-cloudlinux-and-centos-stream/)红帽撤出 CentOS 的原因是它与 RHEL 自身竞争过于激烈。Kurtzer 对红帽没有任何恶感，红帽为开源生态系统做出了巨大贡献。作为一家企业，该公司需要做出正确的财政决策，从这一优势来看，它不能让其旗舰产品 RHEL 服务被免费产品侵占，自该公司 2014 年控制 CentOS 以来，该产品主要由红帽工程师在内部维护(主要是通过接管其董事会，如 Kurtzer 所述)。

然而，在某种意义上，红帽背叛了 CentOS 的“社区企业”方面的根源，Kurtzer 认为。它的替代品 CentOS Streams 是基于一种未来的计算模式，在这种模式下，操作系统会不断更新。他说，今天只有一小部分企业在使用这种模式，并指出这种方法对于需要验证和评估进入其系统的新软件的企业来说是有问题的。

Red Hat 还承诺在 Red Hat Enterprise Linux (RHEL)的两个免费版本中为小型生产工作负载和客户开发团队提供 CentOS 的替代品。但是这些需求可能无法满足大部分用户对低成本稳定 Linux 发行版的需求。例如，超级计算实验室和资金紧张的初创企业需要可扩展的基础设施。

## 现在要飞了

去年年底，当听到 CentOS 即将消亡的消息时，Kurtzer 第一次提出了用 CentOS 替代他自己的客户的想法(他现在经营着高性能计算初创公司 [Ctrl IQ](https://ctrliq.com/) )。

反应非常热烈。他为这个项目提供的空闲频道很快就被信息淹没了，许多信息来自希望做出贡献的人。现在有数百人在开发 Rocky Linux。围绕发行版的特定用例，包括笔记本电脑/台式机版本和 HPC 工作负载的最小安装版本，已经形成了许多特殊兴趣小组。

Rocky Linux 将于今年年中发布，并承诺“100% bug-for-bug 兼容 Enterprise Linux”这个想法是，一个简单的命令就可以将 CentOS 实例化迁移到 Rocky Linux 实例化，而所有的底层库和实用程序保持不变。一个专门的团队可以确保未来的工作将特别有利于用户的企业需求，例如实现联邦信息处理标准(FIPS)合规性，这需要一个安全的构建系统。

理想情况下，Rocky 将保持对社区的关注，并由一个小型核心团队领导。这类似于 CentOS 采用的方法，但是 Kurtzer 在如何管理/支持社区驱动的软件项目方面学到了更多。与早期的 CentOS 相比，围绕构建过程的工具变得更加复杂和自动化。

“因为人太多了，我们玩得很开心。感觉就像一场地下运动，现在刚刚兴起，”库尔策说。“一切都在成形，想要参与其中并想做类似事情的人有机会做一些真正与众不同的事情。”

在这里听完整个采访:

[变更日志 427:洛基 Linux 的崛起](https://changelog.com/podcast/427)——收听[Changelog.com](https://changelog.com/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>