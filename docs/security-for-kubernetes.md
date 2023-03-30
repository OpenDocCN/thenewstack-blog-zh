# Kubernetes 的安全性

> 原文：<https://thenewstack.io/security-for-kubernetes/>

[保安为库伯](https://thenewstack.simplecast.com/episodes/security-for-kubernetes)

随着容器和 Kubernetes 的出现，人们很容易忘记这些系统仍然需要旧的虚拟机和基于硬件的系统所需要的相同类型的帮助。其中最主要的需求是安全。我们最近在哥本哈根的 [KubeCon+CloudNativeCon](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2018/) 与 [Aqua Security](https://www.aquasec.com/) 的技术布道者 [Liz Rice](https://www.linkedin.com/in/lizrice/) 以及[纽约大学](https://scholar.google.com/citations?user=COE6KUgAAAAJ&hl=en)[坦顿工程学院](https://www.nyu.edu/)计算机科学与工程副教授 Justin cap pos 一起讨论这个话题。Cappos 是 TUF(更新框架)项目背后的驱动力之一。

现在由[云本地计算基金会](https://www.cncf.io/) (CNCF)管理，TUF 是一个软件更新规范，专门设计来假设你的基础设施在某个时候会受到损害。Cappos 表示，该框架对这些妥协具有弹性，并且能够在这样的入侵后恢复密钥和安全性。“TUF 是一种解决方案，从一开始就将撤销作为首要考虑因素，这对于安全系统来说是非常不典型的，”Cappos 说。

赖斯说，TUF 旨在允许管理员跟踪在云环境中运行的应用程序的来源和完整性。TUF 可以提供网络中运行的所有东西的来源确认，确认二进制文件是否被外部的人修改过。她补充说，CNCF 的其他安全项目，如 [SPIFFE](https://github.com/spiffe/spiffe) ，正在为服务做类似的事情，确保整个平台的完整性和信任。

不过，Rice 说，Kubernetes 的安全是一个不断发展的领域，充满了不断发展的项目之间的差距。“它们是安全难题中完全不同的部分。安全是一件大事。我们可能会看到更多的项目和更多与安全相关的举措，”赖斯说。这并不是说 CNCF 要等到项目完成后才确保安全。

卡波斯说，CNCF 已经支付了 TUF 和公证人的安全审计费用，SPIFFE 和其他项目也将很快跟进。赖斯补充说， [CoreDNS](https://gist.github.com/rothgar/bdc0cb8f7c2bad2a56627457bebb152f) 也通过了类似的安全审计，发现并修复了一个缓存中毒漏洞。从即将发布的 1.11 版本开始，CoreDNS 已经成为核心 Kubernetes 平台的一部分。

[https://www.youtube.com/embed/mNFoqxnuecg?feature=oembed](https://www.youtube.com/embed/mNFoqxnuecg?feature=oembed)

视频

### 在这个版本中:

[1:10:](https://thenewstack.simplecast.com/episodes/security-for-kubernetes?t=1:10) 给我们介绍一下 TUF 项目。
[3:58:](https://thenewstack.simplecast.com/episodes/security-for-kubernetes?t=3:58)Kubernetes 的其他安全项目是如何整合在一起的？
[10:10:](https://thenewstack.simplecast.com/episodes/security-for-kubernetes?t=10:10) 如何使用 Kubernetes 管理微服务部署中的安全复杂性？
[13:37:](https://thenewstack.simplecast.com/episodes/security-for-kubernetes?t=13:37) 在未来六个月内，Kubernetes 会面临哪些明显的安全问题？
[15:05:](https://thenewstack.simplecast.com/episodes/security-for-kubernetes?t=15:05) 您认为开源项目正在哪些领域崭露头角？
[17:00:](https://thenewstack.simplecast.com/episodes/security-for-kubernetes?t=17:00)[格拉夫阿斯](https://grafeas.io/)此刻的状态。

云原生计算基金会、KubeCon+CloudNativeCon 和 Aqua Security 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>