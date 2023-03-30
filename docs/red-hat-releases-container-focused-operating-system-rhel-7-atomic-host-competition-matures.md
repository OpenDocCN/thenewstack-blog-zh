# Red Hat 发布以容器为中心的操作系统，集成 Docker、Kubernetes

> 原文：<https://thenewstack.io/red-hat-releases-container-focused-operating-system-rhel-7-atomic-host-competition-matures/>

Red Hat 今天发布了其[Red Hat Enterprise Linux 7(RHEL 7)](http://www.redhat.com/en/technologies/linux-platforms/enterprise-linux)以原子主机容器为中心的产品，同时发布了其主要企业产品 Red Hat Enterprise Linux 的首次更新，现在升级到 7.1 版本。RHEL 7 Atomic Host 从公开测试版正式发布是对容器优化、极简操作系统市场竞争加剧的认可。随着越来越多的企业寻求利用分布式、容器化应用架构环境的微服务和多主机优势，Red Hat 希望复制其主要企业 RHEL 产品中的这种应用。

新版本集成了核心 Docker 工具，包括支持 Docker 格式的容器图像。RHEL 7 原子主机也依靠 Kubernetes 框架来实现大规模的编排。

“原子主机完全是关于如何在企业中设计容器应用程序，”Red Hat 产品营销高级主管 Mark Coggin 说。“优化意味着我们将 RHEL 7 的核心部分转化为一个主机平台。管理应用程序和容器所需的关键部分运行在该主机之上。”

虽然创造了一个在该领域独一无二的大焦点，但 RHEL 7 原子主机中包含的几个功能在其他操作系统中也可用，这些操作系统也是专门为容器使用而设计的。Red Hat 认为，它们提供原子升级是独一无二的，也就是说，这种功能可以用最新的安全补丁自动升级操作系统，同时使系统管理员能够灵活地回滚任何升级。

但是竞争对手 [CoreOS](https://coreos.com/) 的首席技术官 Brandon Philips 说，这是 CoreOS 最初创立时的核心原则:

> "基本的想法是，我们有一个可以自我更新的操作系统."

飞利浦指出，自动更新是一项重要的安全功能，它仍然允许 IT 经理进行控制。过去，补丁、更新和安全修复通常需要由 IT 经理手动安装。最近对病毒 [Shellshock 的安全响应显示了让全球 IT 经理定期了解新的安全问题](https://thenewstack.io/responding-to-shellshocks-chaotic-impact-on-new-stack-ecosystems/)的困难。例如，当时 Digital Ocean 写信给他们的客户，告知其安全风险:52.1%的人打开了电子邮件，这对于这类电子邮件来说是一个很高的回复率，但这意味着不到一半的客户可能没有意识到安全问题。“软件永远不会是 100%安全的，因此您必须设计支持基础架构的软件。更新机器以及以何种顺序更新的认知负荷是一个真正令人头疼的问题。”自动安全更新的想法是减少这种认知负荷。

像 Red Hat 的 Atomic Host 版本一样，CoreOS 仍然使 IT 经理能够继续负责并从任何自动更新中回滚:“这导致了一些好的特性，”Philips 说。

> “我们可以用密码验证磁盘上的系统。这是 CoreOS 独有的。”

Red Hat 将希望 Atomic Host 能够在容器环境中模仿他们的企业产品——Red Hat Enterprise Linux 7——在更广泛的企业环境中占据的市场份额。根据【Top500 强项目的测量，十大超级计算机中有四个使用的是红帽企业版 Linux 操作系统，红帽自己也说财富 500 强公司中有 90%使用该操作系统。

然而，争夺容器操作系统市场可能需要一些追赶。Canonical 的 Ubuntu 的云解决方案产品经理 Dustin Kirkland 认为他们占了上风。

“我对我们在 Docker 生态系统中的地位感到非常自豪，”Kirkland 说。“我们为我们的领先系统感到自豪。Ubuntu 的速度与容器生态系统的速度相匹配。容器化应用的整个概念正在以云与闪电的速度发展，并与我们的 Ubuntu 步伐一致。

“如果你去 Docker Hub，几乎有 200 万张 Ubuntu 图片已经在 Docker 中发布。这是第二常见的五倍多。这是因为 Ubuntu 的速度，我们也很小。速度和安全性至关重要，拥有一个小的图像对此至关重要。”

虽然 Ubuntu 和 CoreOS 等竞争对手热衷于争夺他们的容器权利，但 Red Hat 系统设计和工程高级总监 Lars Herrmann 认为，内置于 RHEL 7 原子主机的技术使他们的产品更安全、更灵活、更便携。其中两个特性是包含 SELinux 和创建超级特权容器。此功能创建了附加的安全条款，可以设置这些条款来通知容器如何访问主机和其他容器。

“容器不包含。RHEL 7 和 RHEL 7 原子主机是唯一与 SELinux 集成的产品，它将容器创建并锁定在一个隔离的环境中。此外，超级特权环境是 RHEL 7 原子主机所独有的。您可以对在容器中运行的内容给予明确的许可。它非常灵活，可以轻松地封装到前端的命令行中，因此功能丰富但简单易用，而且最终是安全的。”

今年，容器的讨论已经扩展到了 Docker 之外，随着 Red Hat Enterprise Linux 7 Atomic Host 的新发布，成为容器环境首选操作系统的最前沿的热潮已经开始。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>