# 从 Fedora 到 CentOS:开源的一致性和透明性

> 原文：<https://thenewstack.io/fedora-centos-consistency-transparency-open-source/>

随着开放源码的发展，开发人员已经能够将他们最喜欢的堆栈或配置的各个方面带到几乎任何设置中。虽然分布式团队并不是一个新概念，但是不管使用什么样的栈或架构，都能够在一个项目上工作意味着在每个团队成员的机器上运行代码所花费的时间更少。在 [Fedora](https://getfedora.org/) 和 [CentOS](https://www.centos.org/) ，这种对环境一致性的强调已经成为提高开发人员生活质量的某种咒语。

在这一集的[中，New Stack Makers](/tag/the-new-stack-makers/)embedded below，New Stack 创始人 Alex Williams 与 CentOS 项目开发人员 Jim Perrin 和 Fedora 社区成员 Adam Miller[在 OSCON 奥斯丁分校进行了交谈，以了解更多关于这两个 Red Hat Linux 项目在它们的配方和发行版中使用开源、与社区合作以及它们的计划的方式。](https://twitter.com/themaxamillion)

[TNS 采访:CentOS 的亚当·米勒和 Fedora 的吉姆·佩兰在 OSCON 奥斯丁](https://thenewstack.simplecast.com/episodes/tns-interviews-centoss-adam-miller-and-fedoras-jim-perrin-at-oscon-austin)

对话[也可能在 YouTube 上听到](https://youtu.be/xcYruTBxBZI)。

尽管围绕环境一致性的嗡嗡声，佩兰很快指出，这并不都是有趣的游戏。创建一致的开发人员体验需要持续的努力，CentOS 通过利用容器实现了这一点。“无论开发人员是使用裸机、虚拟机，还是进入容器领域，我们都希望这种体验在每个平台上都尽可能一致。对我来说，这是关于在所有方面获得一致性，实现这一点的方法之一是容器管道。我们必须努力做到始终如一，”佩兰说。

Miller 继续解释说 Fedora 的核心概念依赖于环，这带来了项目开发方式的最新转变。其中包括 ring zero——它包含了开发人员习惯使用的所有 Fedora 操作系统工具，定义了操作系统和应用程序的起始点。

Fedora 希望通过其对原子项目的贡献来改变现状，该项目是 Flatpak(前 XDF)受 T2 OSTree 文件系统工具的启发而建立的。Project Atomic 专注于使用 Docker 容器创建和开发 Linux 应用程序。Flatpak 还创造了新技术，如 [Bubblewrap](https://github.com/projectatomic/bubblewrap) ，这是 Project Atomic 和 Flatpak 共同创造的。

“Flatpak 允许应用程序在没有核心发行版要求的沙盒中运行，它们可以跨多个版本和 Linux 发行版运行。我们希望用[容器构建管道](https://thenewstack.io/hello-world-ebook-container-orchestration-automation-now-available/)为贡献者创建一个环境，用通用的构建方法创建和构建内容。构建过程是可重复的、可重复的、可审计的和一致的，”Miller 说。

通过他们在开源中的共享工作，Fedora 和 CentOS 为使用他们平台的开发者提供了透明性。简单地说，如果开发人员不信任他们，这两个组织都不认为他们应该为了使用 Linux 及其许多附加产品而信任他们。

“在 Fedora 和 CentOS 中，系统是公开的，因为你可以看到我们制作它们的方法。关于如何部署的一切都是公开的；这些工具都是开源的。我们唯一要做的就是努力控制它，确保构建根不能从互联网上抓取可能有害的东西，”米勒解释道。

Red Hat 的 OpenShift 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>