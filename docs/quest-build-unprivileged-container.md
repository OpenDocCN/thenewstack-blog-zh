# 构建无特权容器的探索

> 原文：<https://thenewstack.io/quest-build-unprivileged-container/>

Docker 容器长期困扰安全专家的一个方面是，它们以 root 用户身份运行，即使它们自己运行的进程没有特权。

现在，Docker 的维护者 [Jessie Frazelle](https://twitter.com/jessfraz) ，以前是 Docker 的员工，现在在谷歌工作，正在和一些来自社区的 Docker 用户，包括许多来自 [Gnome](https://www.gnome.org/) 开源桌面项目的用户，一起寻找解决这个问题的方法。

确切地说，容器享有的根用户状态比机器所有者的完全根用户特权要有限得多。默认情况下，通过 Linux kerenel，Docker [放弃了超过一半的根功能](https://docs.docker.com/engine/security/security/#docker-daemon-attack-surface)。此外，Docker 阻止危险的系统调用，并使用许多其他方法限制容器。

但是要运行每个 Docker **run** 命令，最终用户必须[运行 **sudo** 命令](http://askubuntu.com/questions/477551/how-can-i-use-docker-without-sudo)——该命令授予用户管理权限。为了消除所有这些额外的输入，管理员可能会想把他们的用户添加到系统 Docker 用户组中，这样会给用户系统的根访问权限，从而使系统容易受到特权提升攻击。

Frazelle 和他的公司正在开发一种叫做无特权容器的东西，它完全取消了 sudo 的要求，取而代之的是一组更好的控件。她在最近的 QCON 纽约开发者大会上解释了这项工作。

除了减轻安全担忧，非特权容器更适合支持多租户环境，因为许多商店限制他们的开发者将他们的应用程序作为基本的安全措施在 root 中运行。

Frazelle 说，即使使用默认设置，容器仍然比在服务器上本地运行应用程序更安全。Frazelle 自己在容器中运行她所有的桌面应用程序(这是 Gnome 人感兴趣的想法)。

Docker 有充分的理由以 root 用户身份运行容器。Docker 安全工程师 [David Lawrence](https://github.com/endophage) 在上个月 Dockercon 2016 的一次简短采访中表示:“要让一个典型的网络应用启动并运行，你需要以 root 用户身份执行很多操作。

## 铬灵感

Frazelle 在一次技术会议上解释说，无特权容器的想法是受谷歌开源 [Chromium 浏览器](https://www.chromium.org/getting-involved/download-chromium)的启发。Chromium 浏览器使用 Linux 内核中的 **[名称空间](https://lwn.net/Articles/531114/)** 和 **[seccomp](https://lwn.net/Articles/656307/)** 将每个浏览器标签限制在其沙盒进程中。

你猜怎么着？Docker 容器也使用 Linux seccomp 和名称空间。Seccomp 限制了进程可以进行的调用，名称空间限制了用户(即容器)可以看到的资源。Linux 内核(版本 3.8)的最新进展使每个容器都能够[创建自己的通用名称空间集](https://integratedcode.us/2015/10/13/user-namespaces-have-arrived-in-docker/)。

这个项目的困难部分是处理控制组，即所谓的 **[cgroups](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Resource_Management_Guide/ch01.html)** 。Cgroups 可用于限制资源，如用户可以消耗的 CPU 时间、系统内存和网络带宽。例如，对 cgroups 更严格的控制可以防止容器叉炸弹攻击服务器。

Frazelle 指出，迄今为止，无特权用户创建 cgroup 控件是非常棘手的，他在最近的一篇博客文章中将这项工作比作“巨大的轮胎火灾”。

尽管如此，Frazelle 还是开发了一个概念验证的无特权容器，名为 **[binctrl](https://github.com/jfrazelle/binctr)** ，没有 cgroup 控件。SUSE 软件开发商 [Aleksa Sarai](https://twitter.com/lordcyphar) 已经[向 Linux 内核团队](https://twitter.com/jessfraz/status/755849554759675904)提交了补丁，以使 cgroups 更加友好地支持非特权容器。工作[也正在进行中](https://groups.google.com/a/opencontainers.org/forum/#!topic/dev/yutVaSLcqWI)在 runc 通用容器运行时[中添加对无特权容器的支持，Docker 容器现在可以在其上运行](https://medium.com/@tiffanyfayj/docker-1-11-et-plus-engine-is-now-built-on-runc-and-containerd-a6d06d7e80ef#.du2lzsu4y)。

## 最低特权微服务

弗雷泽勒并不是唯一一个攻击这个问题的人。Docker 的安全团队正在努力实现一个叫做“最低特权微服务”的概念，Docker 的 Lawrence 说。“想法是你的微服务应该运行尽可能少的权限，”他说。

劳伦斯说，理想情况下，容器应该有点像移动应用程序，因为它们预先配置了安全设置，当它们被下载时，它们让管理员确切知道它们需要什么权限。

另外， [BubbleWrap](https://github.com/projectatomic/bubblewrap) ，来自构建 [Project Atomic](http://www.projectatomic.io/) 下一代基于容器的操作系统的人，是另一个致力于类似工作的工具。根据该项目的 GitHub 页面，它创建了一个新的名称空间，允许用户“在沙盒中运行应用程序，在沙盒中，它限制对操作系统或用户数据(如主目录)的访问”。

Docker 是新堆栈的赞助商。

专题图片:[@ sined _ NYC](https://www.instagram.com/sinned_nyc/)画的一个“[箱式货车卫士](https://www.instagram.com/p/BFC5YXgQ81B/?taken-by=joabjack)”。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>