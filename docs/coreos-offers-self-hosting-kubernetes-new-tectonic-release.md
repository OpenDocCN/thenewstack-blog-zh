# CoreOS 提供自托管 Kubernetes 与新的构造释放

> 原文：<https://thenewstack.io/coreos-offers-self-hosting-kubernetes-new-tectonic-release/>

利用 Kubernetes 固有的管理容器化应用程序的能力，CoreOS 已经更新了其商业 Kubernetes 发行版，称为“构造”,能够在不停机的情况下进行自我更新。

CoreOS 首席技术官 Brandon Philips 在本周举行的公司[构造峰会](https://tectonic.com/summit/)的主题演讲中表示:“我们能够使用与监控我们的应用程序完全相同的 API 和功能来监控 Kubernetes。”。"我们把这一切都连接到构造控制台，所以你有一个点击按钮部署."

飞利浦在随后的采访中说，迄今为止，与大地构造和 Kubernetes 的安装过程“非常痛苦”。"本质上，人们不得不对分布式系统进行手动升级."

安装通常包括进入多个节点，手动修改文件，或者至少编写一个执行这些任务的脚本，所有这些都需要一套不同于管理 Kubernetes 本身的应用程序的技能。

“理想情况下，掌握 **kubectl** 和其他工具来操作 Kubernetes 应该首先转化为安装 Kubernetes 的诀窍，并随着时间的推移保持其运行，”CoreOS 关于自托管能力的博客文章指出。

“这就是为什么我们如此努力地向上游发展，以使这种自宿主技术成为可能，”飞利浦说。

飞利浦将这种自托管能力比作 Linus Torvalds 现在如何使用 Linux 来编译新版 Linux。对于 Linux 的第一个版本，Torvalds 必须使用 [minix](http://minix.com.hk/) 作为构建平台。但是在 Linux 稳定之后，他将他的编译器移植到 Linux 本身，以便从本质上直接在 Linux 上构建 Linux。

Kubernetes 本身可以确保，如果它管理的一个 pod 发生故障，它可以启动一个替换 pod。在这个新的构造版本中，推出的是新版本的 Kubernetes，它现在包装在一套豆荚中。structural 利用了一个新的 Kubernetes 安装工具，名为 [**kubeadm**](http://kubernetes.io/docs/getting-started-guides/kubeadm/) 。

在典型的 Kubernetes 设置中，所有的控制节点都被设置为来自工作节点的一个想法。对于构造更新，在控制节点上留出一些额外的空间来设置构造的更新版本。一旦新版本开始运行，工作就会从每个组件切换到更新的组件，直到更新完成。Kubernetes 本身[管理](https://coreos.com/blog/self-hosted-kubernetes.html)这个更新过程:

[https://www.youtube.com/embed/tXyV3IQ8-0k?feature=oembed](https://www.youtube.com/embed/tXyV3IQ8-0k?feature=oembed)

视频

该方法类似于 CoreOS 用于更新其 Linux 发行版的方法([最近被重命名为 Container Linux](https://thenewstack.io/self-driving-infrastructure-makes-internet-secure/) )。因为 structural 是一个分布式应用程序，所以组件是按照特定的顺序更新的，通常是按照 API 服务器、调度器、代理，最后是 kubelet 的顺序。

CoreOS 本身通过容器交付更新，通过管理控制台管理。

对于企业来说，CoreOS 将在更新上线前为企业测试提供 alpha 和 beta 通道。如果更新引起混乱，有几种不同的方法可以回滚更新。Kubernetes 数据存储，etcd，可以存储备份信息，可以恢复到以前的版本。该公司也有如何从各种故障状态中恢复的指南，例如当调度失败时。

Philips 说，自动更新应该可以很好地适应大多数企业部署，因为大多数用户都是在 constructive 的基础上构建的，而不是修改 constructive 本身。

飞利浦表示，CoreOS 不会是唯一一家提供自主 Kubernetes 的公司。飞利浦说，这项技术将包含在软件的未来版本中，因此其他发行版无疑也会使用这项技术。

CoreOS 还宣布了 [Dex](https://github.com/coreos/dex) 的 2.0 版本，这是一个基于 [OpenID Connect](http://openid.net/connect/) 的认证提供商，OpenID Connect 是一个广泛使用的认证协议，可用于通过加密令牌管理 Kubernetes 上的用户，将用户帐户链接回企业的轻量级目录访问协议(LDAP)目录。第二版允许 Kubernetes 用户在没有外部数据库的情况下运行 Dex。Dex 使用 Kubernetes APIs 来持久化标识数据。以前的版本需要外部数据库。

“我真的认为自动驾驶是未来的发展方向。这是我们都应该去的地方，”数字海洋工程经理约纳斯·贝吉乌斯在“大地构造峰会”上介绍新发布的“大地构造”时说。

[构造](https://tectonic.com/?_ga=1.162053372.1955225110.1481644180)现在最多 10 个节点免费。

CoreOS 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>