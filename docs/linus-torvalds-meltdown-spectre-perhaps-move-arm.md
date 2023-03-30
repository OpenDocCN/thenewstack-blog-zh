# 莱纳斯·托沃兹谈熔毁:也许我们应该转向武装

> 原文：<https://thenewstack.io/linus-torvalds-meltdown-spectre-perhaps-move-arm/>

Linux 创造者 [Linus Torvalds](https://github.com/torvalds) 之前热爱英特尔和 x86 架构。该架构有一个既定的基础设施，程序只是运行，不像 ARM，代码不需要调整到设备上。

但是，关键的 x86 漏洞允许黑客从芯片内存中窃取数据，这让 Torvalds 对英特尔非常恼火，并告诉 Linux 社区认真考虑 ARM 架构。

周三[研究人员披露了英特尔 x86 芯片上的多个漏洞](https://www.kb.cert.org/vuls/id/584653)——称为 Meltdown 和 Spectre，黑客可以访问基于 Windows 或 Linux 操作系统的个人电脑、手机和平板电脑中受保护的内核内存中的敏感信息。

托瓦尔兹说，这一漏洞的发生部分是因为英特尔的芯片设计过程中的不称职。在对英特尔对这些漏洞的糟糕反应进行了一些评论后，他建议或许是时候放弃英特尔，转而关注 ARM 了。

托沃兹说:“也许我们应该开始更多地关注 ARM64。

这些漏洞很大，会影响数百万甚至数十亿台设备。这些漏洞利用了英特尔所谓的指令“推测性执行”,这是一种预测过程的预执行指令，从易受攻击的内核内存空间中窃取个人数据。预执行指令可能会被使用，也可能不会被使用，但准备好它们可以减少执行任务所需的周期数，从而提高芯片速度。

谷歌发现了三种潜在泄露秘密信息的“旁道分析”技术，这些秘密信息可能包括用户名、密码和通常在计算机上受到保护的其他数据。“这些技术可以通过浏览器中运行的 JavaScript 代码来使用，这可能允许攻击者获得攻击者进程中的内存，”微软在[的一篇博客文章](https://blogs.windows.com/msedgedev/2018/01/03/speculative-execution-mitigations-microsoft-edge-internet-explorer/#HLRJH5myXGDGyCjf.97)中说。

 [来自证书漏洞注释

不同的 CPU 受到不同的影响，例如，许多英特尔 CPU 的推测性执行和高速缓存实施允许攻击者在不受保护的操作系统上使用变体 3 读取内核内存。攻击需要能够在目标系统上本地执行代码。通常，这需要目标的有效帐户或独立危害。在 web 浏览器中使用 JavaScript 进行攻击是可能的。多用户和多租户系统(包括虚拟化和云环境)可能面临最大的风险。用于浏览任意网站的系统也面临风险。不容易为攻击者提供本地执行代码的方法的单用户系统面临的风险要低得多。](https://www.kb.cert.org/vuls/id/584653) 

个人电脑可能会因浏览器而面临风险——已经有一组研究人员设计了一个 JavaScript 漏洞。然而，除了浏览器之外，这种利用还会影响广泛的程序和虚拟化软件。也影响到 AMD 和 ARM 的芯片。软件提供商、芯片和云公司正在发布警报和补丁，链接可以在 Meltdown 网站上找到。

这些漏洞的全部冲击尚不清楚，但这些补丁可能会影响芯片性能，并影响云和软件提供商。Phoronix 的一项基准测试显示，Linux 操作系统和 PostgreSQL 数据库的运行速度有所下降。Phoronix 的创始人迈克尔·拉贝尔在文章中写道，这些补丁可能会给 Windows、Linux 和 MacOS 电脑带来 5%至 30%的性能损失。

英特尔[已经发布新闻声明](https://newsroom.intel.com/news-releases/intel-issues-updates-protect-systems-security-exploits/)淡化这些漏洞，称这不是一个架构问题，而是一个行业问题，AMD 对这一事实提出异议。但是，鉴于英特尔 CPU 用于大多数个人电脑和超过 90%的服务器，它们吸引了最多的注意力。

托沃兹[写道](https://lkml.org/lkml/2018/1/3/797)“我认为英特尔内部的一些人需要认真审视他们的 CPU，并实际承认他们有问题，而不是写公关广告说一切都按设计运行。”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>