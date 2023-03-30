# Ubuntu 21.04 缩小了 Kubernetes 在 Raspberry Pis、GPU 方面的影响

> 原文：<https://thenewstack.io/ubuntu-21-04-shrinks-kubernetes-footprint-for-pis-gpus/>

虽然不是长期支持(LTS)版本，但周四发布的 Ubuntu 21.04 确实提供了一些重要的功能。而且，对于任何比较过这个版本的服务器和桌面版本的人来说，可能会惊讶地发现服务器版本是两者中更重要的。

在桌面上，Ubuntu 21.04 不包括最新的 GNOME 版本，因为开发人员认为他们需要更多的时间来适应桌面上的新变化。也没有发现 GTK4。你会发现:

*   改进的安装程序。
*   默认为韦兰。
*   主目录现在被设置为私有。
*   改进黑暗主题。
*   更好的活动目录集成。
*   Linux 内核 5.11。

这就是精彩片段。当然没有交易撮合者或破坏者。但是当你转向操作系统的服务器版本时，事情变得更加令人兴奋。

我和 [Canonical](https://canonical.com/) 的产品经理 [Tytus Kurek](https://www.linkedin.com/in/tkurek) 通过电子邮件交流了 Canonical 的最新版本将如何影响云原生和容器开发。让我们开始吧，直接进入我们的 Q & A。

21.04 将在哪些方面帮助改进云原生应用和开发？

我们发布了应用程序图像的新滚动版本([于 2020 年 11 月宣布](https://ubuntu.com/blog/canonical-publishes-lts-docker-image-portfolio-on-docker-hub)，作为“LTS Docker 图像”计划的一部分)。虽然这些版本不会从长期支持中受益，但它们是开发人员快速构建基于 [Ubuntu](https://hub.docker.com/u/ubuntu) 之上的生产级应用程序映像的绝佳选择。

最新的 MicroK8s 1.21 版本[将 Kubernetes 的内存占用量减少了 32.5%](https://ubuntu.com/blog/microk8s-memory-optimisation)，允许用户在小设备上运行 MicroK8s，如 Raspberry Pi 和 NVIDIA Jetson，并仍然为多容器部署留出空间。最新版本还在基于 x86 的系统上提供了 MicroK8s 与最新 NVIDIA GPU 运营商的无缝集成。

**21.04 中有哪些面向容器部署的新特性？**

Ubuntu 21.04 附带了最新发布的 [containerd](https://launchpad.net/ubuntu/+source/containerd) 和 [docker.io](https://launchpad.net/ubuntu/+source/docker.io) 本身具有许多简化容器开发和部署的新特性。

要了解 Docker 20.10 中的新内容，请查看 Dimitris Poulopoulos 的“[Docker 20.10 中的新内容](https://towardsdatascience.com/whats-new-in-docker-20-10-fd1de1216c0?gi=977695ee917a)”或[Docker 官方发布说明](https://docs.docker.com/engine/release-notes/)。

要了解 ContainerD 1.4 中的新特性，请阅读 Akihiro Suda 的“[container d 1.4 中的新特性](https://medium.com/nttlabs/containerd14-70ae3ea29dba)”，或[container d 官方发行说明](https://github.com/containerd/containerd/releases)。

【21.04 如何在以前版本的基础上提高安全性？

Ubuntu 21.04 是第一个在所有支持的版本中使用一个 Grub 的版本；这使我们能够更快地解决安全漏洞，如安全引导旁路。Ubuntu 21.04 附带了最新的 fwupd 版本 1.5.8，其中包括对最新 UEFI 安全引导改进所需的元数据的支持。

Ubuntu 21.04 还引入了[私有主目录](https://ubuntu.com/blog/private-home-directories-for-ubuntu-21-04)，强化了多用户系统的默认设置。

Linux 内核 5.11 带来了几项改进，包括检查点/恢复，将整个进程的状态移动到其他系统，RISC-V 堆栈保护器，以及 ARM64 内存标记，基于硬件的内存损坏漏洞保护。

**默认情况下会启用[硬件支持堆栈](https://askubuntu.com/questions/248914/what-is-hardware-enablement-hwe)吗？管理员将如何使用它？**

目前它是作为 PPA 提供的，但是计划在 22.04 中进一步集成它。

对于那些不了解硬件支持栈的人来说，这是一种让 Ubuntu 在最新发布的硬件上运行的方法。这是通过安装滚动发布的内核来实现的，它包括对更现代硬件的支持。为了实现这一点，Ubuntu 在测试(通过建议的口袋和特殊的 Q/A 方法)并发布后，立即对 HWE 内核进行打包。这确实带来了一些缺点(比如引入了错误和问题，这可能会使这个解决方案对于企业用例不可行)。

硬件支持栈在云托管提供商上工作，比如 AWS、Google Cloud 和 Azure。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>