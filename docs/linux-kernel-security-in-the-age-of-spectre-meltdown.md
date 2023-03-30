# 幽灵时代的 Linux 内核安全

> 原文：<https://thenewstack.io/linux-kernel-security-in-the-age-of-spectre-meltdown/>

根据 [Greg Kroah-Hartman](https://github.com/gregkh) 、[在今年早些时候于上海举行的最后一次](https://github.com/gregkh/presentation-spectre) [KubeCon+CloudNativeCon](https://www.lfasiallc.com/events/kubecon-cloudnativecon-china-2019/) 活动上的发言，自从 Spectre、Meltdown 和其他基于硬件的攻击激增以来，Linux 的安全格局已经发生了变化。简而言之，在运行 Linux 时，他们迫使 Linux 用户进行一次不幸的选择冒险:性能还是安全。

“糟糕的是，你现在必须做出选择:性能还是安全。这不是任何人想做的好选择，”克罗亚-哈特曼告诉人群。

今年早些时候发现的最新漏洞是 MDS ( [多架构数据采样](https://www.kernel.org/doc/html/latest/admin-guide/hw-vuln/mds.html))，它与去年的 Spectre/Meltdown 攻击如出一辙，利用了英特尔处理器中的推测性执行模式。这种处理器试图预测所采取的下一个动作，以便提高性能，这在无意中暴露数据方面存在问题。这在云计算环境中尤其麻烦，因为一个客户的数据可能会被其他用户访问。

原来 [OpenBSD 社区](https://www.openbsd.org/)，远远领先于 Linux 开发者自己，是第一个理解推测性执行所基于的技术——即英特尔的 SMT(同步多线程)，其中 CPU 将自己分成多个虚拟内核——是有问题的。它呼吁在 2018 年 6 月禁用 SMT，远在僵尸加载、RIDL(流氓飞行数据加载)、辐射尘、MDS 和其他人随后出现之前。它们都是相同基本主题的变体，禁用多线程消除了它们引入的许多问题。

Kroah-Hartman 说，虽然这些是硬件错误，但修复它们是操作系统内核的任务。为了减少这种攻击，用户必须禁用超线程，并更新他们的内核和硬件 BIOS。“如果你只是做一件或另一件事，你就不会安全，”他说。例如，RIDL 和 Zombieload 可以跨应用程序、虚拟机甚至安全区域窃取数据。

[https://www.youtube.com/embed/-hWK8BOfNVQ?feature=oembed](https://www.youtube.com/embed/-hWK8BOfNVQ?feature=oembed)

视频

## 系统调用现在很昂贵

修补这些漏洞的缺点是服务器运行速度变慢，云服务提供商很快就发现了这一点。“传统上，系统调用进出速度很快。现在我们必须刷新这些缓冲区。它会让事情变慢，”他说。

Kroah-Hartman 自己工作的很大一部分，维护旧的 Linux 内核版本，并不奇怪，是构建内核，这是一个非常 CPU 密集型的过程。“我的 CPU 越多，它就越好，”他说。即使超线程保持开启，他也见证了新补丁到位后 CPU 性能下降了约 2%。当他禁用超线程时，这种滞后会增加到 15%。

也就是说，每个最终用户都应该测试他们自己的工作负载，以了解他们获得的性能影响。有些工作负载可能根本不会变慢，有些可能会慢很多。Kroah-Hartman 说，用户也应该看看他们的云提供商做出了什么选择。网站[让 Linux 再次快速运行](https://make-linux-fast-again.com/)提供了全速运行原始 Linux 的所有内核标志，让用户能够估计补丁将对他们的系统产生的影响。

## 经验教训

作为最后一个话题，Kroah-Hartman 深入研究了英特尔因发现漏洞而引发的例行警报。总之:最初，它可以做得更好，但仍有改进的空间。

他说，对于去年的第一批，Spectre 和 Meltdown——英特尔只是在过程的后期通知了 Linux 内核社区。由于漏洞的消息让 Linux 用户容易受到攻击，这些发行版毫无察觉。英特尔通过 NDAs 向发行版核心维护者披露了这些信息，不允许不同的供应商就可能的解决方案进行交流，即使在消息公开后也是如此。“对我们来说，这完全是一场噩梦，”他说。

> “英特尔需要更早引入 Debian”——Linux 内核维护者 Kroah-Hartman。

然而，芯片巨头很快为后续漏洞制定了一个更灵活的流程，在流程的早期——在公开披露之前——提醒社区中的玩家。这使得 Linux 社区能够在研究人员宣布他们的发现时准备好补丁。虽然不是每个人都包括在内——其中最明显的遗漏是最大的发行版之一 Debian，它只是在发布前 48 小时才被通知。值得称赞的是，Debian 团队匆忙准备补丁。

“英特尔需要更早引入 Debian，”Kroah-Hartman 告诉观众。

尽管如此，在最初的补丁发出后，还有很多工作要做。Linux 的多种使用方式导致了许多边缘情况，需要纠正代码。像 Spectre 这样的东西不仅仅需要一个补丁，而是在接下来的几周里需要一系列补丁。Kroah-Hartman 大约每周发布一次内核更新，大约有 22 个补丁。其中至少有一个与安全有关。

一个有趣的问题是，用户不能依赖 CVEs 来跟踪内核漏洞。通常，业界使用[常见漏洞和暴露](https://www.cvedetails.com/cve-help.php)数据库来了解危及安全的漏洞。然而，在 Linux 内核的情况下，CVE 报告只在事后完成——在事后很久以后。Kroah-Hartman 警告说，不应该把它作为 Linux 漏洞的主要来源。

事实上，内核中很少有修复得到 CVE。你不能只是“挑选”Linux 的 CVE，然后期望它被覆盖。你会错过所有的后续补丁。Spectre 和 Meltdown 有几十个后续补丁，其中一小部分被标记为 CVEs。被标记的漏洞平均在首次发现漏洞后 100 天左右被发现。"

Kroah-Hartman 指着一个网页说,[解释了 Linux 安全团队如何工作。](http://kroah.com/log/blog/2018/02/05/linux-kernel-release-model/)

简而言之，当谈到内核安全性时，“你可以确保你正在运行一台安全的机器的唯一方法是，如果你使用最新的 LTS[长期支持]内核，或者使用一个自己做这件事的发行版，”Kroah-Hartman 说。

云计算原生计算基金会和 Linux 基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>