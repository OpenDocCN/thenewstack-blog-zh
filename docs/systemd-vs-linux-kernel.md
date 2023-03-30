# Systemd 与 Linux 内核

> 原文：<https://thenewstack.io/systemd-vs-linux-kernel/>

[事件](https://lkml.org/lkml/2017/7/6/615)始于 Linux 内核的一个补丁，该补丁旨在限制以另一个用户的权限运行的二进制文件的行为，特别是 root。不同的策略和时机被集思广益，就像在 [Linux 内核邮件列表](https://lkml.org/)上经常发生的那样。然后，在讨论过程中，Linux 创建者 [Linus Torvalds](https://github.com/torvalds) 发表了一个评论，显然是关于 systemd 如何使寻找最佳解决方案的努力复杂化，表明 Linux 内核和 systemd 开发人员之间的宿怨在达到顶峰几年后仍然非常活跃。

托沃兹写道:“想必你们都知道为什么，”也许大多数内核的定期贡献者都知道。然而，对其他人来说，解释并不完全清楚——尤其是因为这不是许多人所假设或希望的。

您可能还记得， [systemd](https://www.freedesktop.org/wiki/Software/systemd/) ，现在由 Red Hat 维护，在过去几年中已经成为大多数主流 Linux 发行版的标准。它取代了系统启动时运行的第一个进程 [init](http://www.tldp.org/LDP/intro-linux/html/sect_04_02.html) ，也是所有其他进程的父进程。由于各种各样的技术和个人原因，它似乎也是许多核心内核开发人员烦恼的来源。

不像 init 或 upstart，Ubuntu 的内部 init 替代品，systemd 也是一个管理系统资源和记录活动的通用工具。虽然许多人支持 systemd 的效率，但其他人认为它打破了非官方的 Unix 哲学，即保持程序简单并仅限于单一功能。一些人甚至谴责 systemd 是其赞助商 Red Hat 试图夺取对 Linux 内核的控制权。

然而，自从其实施以来，对 systemd 的反对已经基本平息。包括 [Slackware](http://www.slackware.com/) 在内的少数发行版还没有切换到它，新发行版如 [Devuan](https://devuan.org/) 和最新发布的 [antiX](http://antix.mepis.org/index.php?title=Main_Page) 开始提供使用 init 的系统。

而且，有一段时间，systemd 威胁要接替 [Mono 跨平台。Net framework](http://www.mono-project.com/) 作为阴谋论者的主要目标，[抵制 Systemd 网站](http://ww1.boycottsystemd.org/?subid1=5dd193d8-69a3-11e7-b2f6-49eac2000a00)借用了臭名昭著的反 Mono 抵制 Novell 网站的名字。然而对于大多数用户来说，这个问题已经解决了，毫无疑问，因为普通用户看不到这种变化。

在这种背景下，托瓦尔兹的评论似乎出乎许多人的意料。在概述了他对补丁的首选策略后，托瓦尔兹补充说，他可以看到几种方法，“绝对没有一种方法涉及随机‘从 init 中取一些值’。”是的，这很大一部分可能是因为我不再相信‘init’会做同样的事情。"

提到“init”显然是指 systemd，而且，由于补丁的效果在以 root 用户身份运行时尤其重要，所以它如何与 systemd 交互是一个自然的问题。然而，除了这些显而易见的事实之外，这种解释在很大程度上取决于先前的预期。一些人想知道托瓦尔兹的参考是否是最近在 systemd 中发现的一个[越界错误](https://thenewstack.io/systemd-flaw-leaves-linux-distributions-scrambling-patch/)，以及对 systemd 代码质量的一个[评论。](http://openwall.com/lists/oss-security/2017/06/27/8)

其他博客作者认为托瓦尔兹是独立的，因为红帽是他的雇主 Linux 基金会的主要捐助者。许多人将此评论视为托瓦尔兹反对 systemd 的证据。当被直接问到时，托瓦尔兹言简意赅:“我不认为我曾经批评过 systemd。我一直对开发人员非常不满，他们弄坏了东西，然后就不管了，或者责怪别人。”

换句话说，他指的是 systemd 开发人员的行为，而不是 systemd 本身——这种解释既符合 Torvalds 的通用标准，也符合许多 Linux 内核和 systemd 开发人员之间过去的互动。

## 背景故事

尽管托瓦尔兹本人经常被指责无礼，但他很少进行人身攻击。例如，2014 年，当 systemd 的联合创始人 Lennart Poettering 指责 Torvalds 在开源开发中的许多无礼行为时，Torvalds 没有做出任何回应。到目前为止，对于其他类似的指控，他大多只是简单地说他就是这样。

相反，托沃兹把他最尖锐的批评留给了那些忽视他的基本规则的内核贡献者，比如用补丁破坏用户应用程序，提供一个考虑不周的解决方案，或者拒绝承担修复 bug 的责任。2012 年，当内核贡献者[毛罗·卡瓦略·切哈布](https://www.linkedin.com/in/mchehab/?ppe=1)指责 Poettering 早期项目之一 Pulse Audio 的一个漏洞时，[托瓦尔兹回复](https://www.theregister.co.uk/2013/01/04/torvalds_kernel_bug_rage/):

毛罗，闭上你的臭嘴！这是内核中的一个错误。你做维修工多久了？你还没有学会内核维护的第一条规则吗？如果一个变化导致用户程序中断，这是内核中的一个错误。我们从不责怪用户程序。这能有多难理解？

尽管托瓦尔兹向记者承认，“我认为[systemd]中的一些设计细节是疯狂的(例如，我不喜欢二进制日志)，但这些都是细节，不是大问题。”然而，他正确地断言，他并没有谴责 systemd 作为一个整体的想法。

托瓦尔兹对 systemd 的保留在 2014 年达到了顶点，当时他拒绝接受 systemd 的另一位联合创始人凯·西弗斯(Kay Sievers)的进一步贡献。在 Linux 内核邮件列表上，Torvalds 告诉 Sievers，他“厌倦了这样一个事实，即你不修复你写的代码中的问题，这样内核就必须解决你引起的问题[……]。这种情况已经持续了*年，而且似乎没有任何好转。]我不愿意合并那些维护者不关心 bug 和回归的东西，然后强迫其他项目的人修复他们的项目。”

## 那个系统虽然…

然而，这种批评大多是合理的。例如，Poettering 没有使用 Linux 现有的挂载系统，而是向 systemd 添加了一个新的挂载命令。类似地，内核开发人员 [Theodore T'so](http://web.mit.edu/tytso/www/home.html) 在 [GooglePlus](https://plus.google.com/+TheodoreTso/posts/K7ijdmxJ8PF) 上抱怨说，systemd 没有写入自己的日志系统，而是写入内核的 [dmesg](http://www.linfo.org/dmesg.html) 缓冲区。T'so 抱怨说“dmesg 缓冲区不属于 systemd。该界面最初是为少量信息设计的。] Dmesg 从未被设计为 Syslog 的替代品，这似乎是 Syslog 滥用它的方式。”

在评论 T'so 的帖子时，托沃兹详细阐述道，“让我(和其他人)不安的是，当报告了一个错误，并给出了解释和如何修复它的建议时，凯只是关闭了错误报告，声称这不是一个错误……。而且]这不是一个孤立的事件。这就是凯过去对待其他虫子的方式。几个月的拖延，关闭错误报告，指责其他人和项目是他造成的问题，告诉其他人他们应该如何改变他们的项目，因为他打破了一些东西，显然这不是他的错。”

显然，托瓦尔兹在 systemd 开发人员的行为中看到了一种持久的模式，这种模式使他们不值得他的信任。

并不是每个内核开发人员对 systemd 的反应都和 Torvalds 和 T'so 一样。例如，Chebab 作为一个驱动程序的作者，定期贡献一些垫片来帮助 systemd 与内核的集成。同样，托瓦尔兹的副手格雷格·克罗亚·哈特曼也参加了 systemd 黑客节，在那里他戴着傻帽与诗人、西弗斯和其他 systemd 开发者一起狂欢。

但是对于托沃兹来说，systemd 开发人员不断违反使交互开发成为可能的不成文的代码，如此多次不负责任的行为，以至于他对他们下一步可能做的事情保持警惕。如果他态度激烈，谁能怪他呢？毕竟，这关系到他一生的工作——如果有人对此没有热情，他们还能捍卫什么呢？

[Linux 基金会](https://www.linuxfoundation.org/)和[红帽](https://www.openshift.com/)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>