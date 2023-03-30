# CoreOS 的 rkt 容器现在可以用于生产工作负载了

> 原文：<https://thenewstack.io/coreos-container-runtime-rkt-reaches-1-0/>

该公司周四宣布，CoreOS 的[容器运行时 rkt](https://coreos.com/blog/rkt-hits-1.0.html) (发音为“火箭”)已经准备好生产。CoreOS 将 rkt 吹捧为广泛使用的 Docker 容器环境的更安全的替代方案，这要归功于 rkt 的设计是如何基于 Unix 最佳实践的。

[CoreOS](https://coreos.com/) 的首席执行官[亚历克斯·波尔维](https://twitter.com/polvi)说:“随着 rkt 1.0 的推出，从应用层一直到硬件的分布式信任链对于那些认真考虑在安全和超大规模环境中运行应用程序的企业来说唾手可得。”他补充说，“开发人员可以尝试一下。”

该公司还宣布了附带的生态系统支持的可用性，包括注册，监控和网络。

“CoreOS 通过开发和增强 rkt 容器运行时，为应用程序容器增加了一个关键的安全元素，”451 Research 的研究经理 Jay Lyman 说。

生产就绪型 rkt 具有以下特性:

*   **稳定的** **命令行 UX 和向后兼容的磁盘格式**。
*   **高级安全功能**，如基于 KVM 的容器隔离、SELinux 支持、图像签名验证和基本权限分离。
*   **运行现有 Docker 映像和基于标准的应用程序容器映像的能力。**

今天，rkt 运行在所有现代的 Linux 发行版上。

公司还公布了来自 Sysdig 的 rkt 监测；集装箱注册通过其[码头企业](https://quay.io/tour/enterprise)产品；使用容器网络接口( [CNI](https://github.com/appc/cni) )标准和来自项目 Calico、Weaveworks 和 Kubernetes 的集成进行联网。

8 月，当 CoreOS 发布 0.8.0 版本时，它宣布支持英特尔的 VT-x in-silicon virtualization 或[“透明容器”技术](https://thenewstack.io/securing-containers-intels-clear-containers/)，该技术将容器映像作为完整的 KVM 虚拟机启动，以提供硬件辅助的安全性。

两个月前，该公司推出了一个[可信计算平台](https://thenewstack.io/coreos-offers-a-trusted-computing-platform-for-distributed-containers/)来运行被称为分布式可信计算的安全容器，它使用可信平台模块( [TPM](https://www.trustedcomputinggroup.org/developers/) )，这是一种生成基于处理器的加密密钥的标准。

## **Unix 方式**

Polvi 于 2014 年 12 月在一篇煽动性的博客文章中介绍了 rkt，他在文章中称 Docker 的安全模型“存在根本缺陷”此后，他的立场有所软化，但仍坚定不移地关注集装箱安全。

他说 CoreOS 从头开始构建 rkt 是为了利用 Unix 的最佳实践。他这样解释了建筑与 Docker 的区别:

“Docker 引擎是 Docker 守护程序，它以 root 用户身份在您的服务器上运行。它执行许多不同的功能:图像上传，下载…它有所有这些功能来运行一个容器，这意味着你做的一切都必须在该应用程序内。那个东西在你的机器上以最高特权用户的身份运行。当您键入命令“Docker run”时，该命令会与守护进程中启动容器的 API 进行对话。因此在建筑上产生了约束。

“rkt 模型是完全无守护进程的。所有用于下载映像、验证映像和运行容器引擎的命令都是模块化的，您可以以正常的 Unix 方式运行它们，也就是说，您可以使用您拥有容器之前的正常系统。它给你同样的效果，但它是以最佳实践方式实现的。”

与此同时，他说，用户不必放弃他们的 Docker 容器或 Docker 工具，就可以通过 rkt 获得安全性的好处，rkt 可以动态转换 Docker 图像。

## **稳定与安全**

Engine Yard 的首席技术官和被 Engine Yard 收购的[平台即服务 Deis](https://thenewstack.io/engine-yard-buys-opdemand-maker-of-deis-a-paas-built-on-containers/) 的创建者 Gabriel Monroy 说，尽管它还没有在生产中为客户的集装箱运行 rkt，但它已经在广泛测试 rkt。

“对我们来说，这关乎稳定和安全。安全性与代码库中的代码量成正比。当您添加代码时，存在漏洞的风险。Rkt 是一个紧凑的小型代码库，”他说。

“此外，它处理容器图像 API 的散列和签名的方式更有吸引力，因为它是联合的，它不以一家公司拥有城堡的根密钥为前提，”Monroy 说，他说 CoreOS 强调了一种去中心化的方法。

“我们注意到的一件事是，坦率地说，现在的容器运行时有很多不稳定性，尤其是 Docker 比如内存泄漏、系统快速启动和关闭时的错误，您可能会失去一台服务器，而当服务器恢复时。你可以得到 Docker 引擎内部的腐败。他说:“有一大类问题，只有在你运行了几个月之后，你才会了解到。

“我们面临的一个挑战是，我们一直在与 Docker 的人合作，他们是非常想解决这个问题的人，我看到的问题是，Docker 引擎的代码库增长如此之快，有如此多的新东西被添加到 Docker 想要做的其他事情的代码库中，以至于运行容器的核心工作有点像是事后想起的。如果你追溯一下，我们在生产中发现的许多错误，都与项目中增加的一些表面积有关。”

他说，当 Kubernetes 1.3 可能在第三季度推出时，他的公司可能会转向 rkt。

“所以对我们来说，rkt 就是做一件事，并且做得非常好。它只是专注于成为一个真正伟大的容器运行时，而不是，例如，专注于围绕注册表的一些 Docker 特定的功能，Docker Hub 在代码库中有某种优惠待遇。…"

Docker 是新堆栈的赞助商。

专题图片: [Greg Westfall](https://www.flickr.com/photos/imagesbywestfall/) 的[火箭](https://www.flickr.com/photos/imagesbywestfall/3490098688/in/dateposted/)，在 **CC BY-SA 2.0** 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>