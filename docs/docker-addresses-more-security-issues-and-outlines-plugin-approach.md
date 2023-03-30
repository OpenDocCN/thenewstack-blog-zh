# Docker 解决了更多的安全问题，并概述了“可插拔”方法

> 原文：<https://thenewstack.io/docker-addresses-more-security-issues-and-outlines-plugin-approach/>

Docker 发布了一个新版本的 Docker 引擎，旨在减少 Docker 可能被恶意图片利用的安全隐患。虽然新的安全功能对容器中的图像进行了更好的验证，以改善信任链，但 Docker，Inc .也发现了新的威胁，现在必须加以管理。

在发布 1.3.2 之后，Docker 写道，他们发现了额外的漏洞，这些漏洞可能被恶意的 Docker 文件、映像或注册表利用来危害 Docker 主机，或伪造官方映像。Docker 引擎 1.3.3 和 Docker 引擎 1.4 都发布了修正。在帖子中，Docker 鼓励用户升级到 Docker 引擎 1.3.3 或更高版本。还引入了一个新的[覆盖文件系统作为实验存储驱动](https://github.com/docker/docker/pull/7619)。该帖子还指出:

请注意，这些漏洞只会影响用户下载或运行恶意图像，或从恶意 docker 文件构建。用户可以通过仅下载、构建或运行来自可信来源的图像来保护自己免受恶意内容的侵害。

这篇文章是由 Marianna Tessel 写的，她是 Docker 的高级工程副总裁，最近从 VMware 加入该公司，她在一定程度上关注安全问题。首席执行官 Ben Golub 在最近的一次采访中表示，Tessel 将有助于使安全性成为其技术发展的一个重要方面。

她写道，Docker 引擎利用了操作系统提供的安全机制和隔离:

这是可插拔的，在 Linux 上支持通过 libcontainer 或 lxc 实现的名称空间、功能和 cgroups。在未来，我们期望新的执行引擎插件为我们关注安全性的用户提供更多的选择和更大的粒度。这些机制是定义容器的一部分，在容器中运行比不在容器中运行更安全。在支持的系统上，Docker 集成了 SELinux 和 AppArmor。Red Hat、Canonical 和其他公司一直是 Docker 社区的活跃成员，帮助我们推动安全性向前发展。

Docker 总是相当坦率地谈到他们的安全限制。在过去的四个月里，Docker 的杰罗姆·佩塔佐尼[已经在全球的几个会议上亮相](http://www.slideshare.net/jpetazzo)，经常开玩笑说 Docker 的安全状况最好用“[它很复杂](http://www.projectatomic.io/blog/2014/08/is-it-safe-a-look-at-docker-and-security-from-linuxcon/)”来形容。

Petazzoni 和 Docker Inc .的官方说法是，因为 Linux 容器不是为了安全而制造的，所以安全问题不是 Docker 制造的。部分问题源于这样一个事实，即当授予容器内的应用程序 root 访问权限时，它将能够访问容器底层操作系统的 root 权限。

安全 IT 领导者和博客作者 Lenny Zeltser 昨天写道，虽然 Docker 通过将底层主机与在没有 root 权限的容器中运行的应用程序隔离来解决 root 访问问题，但“这种隔离不如虚拟机那样强，虚拟机在虚拟机管理程序上运行独立的操作系统实例，而不与底层操作系统共享内核。”

Zeltser 提到了使用容器的四个安全好处，包括在同一主机上隔离应用程序的能力；将应用程序环境视为瞬态的；使用脚本安装说明，以确保更好地控制数据和软件；和更频繁的安全修补。但是他也解决了容器技术的三个主要安全风险:

*   “容器的灵活性使运行应用程序的多个实例变得很容易(容器蔓延),并间接导致 Docker 映像以不同的安全补丁级别存在。
*   Docker 提供的隔离不像管理程序为虚拟机建立的隔离那样健壮。
*   更广泛的 ops、infosec、dev 和 auditors 社区还没有很好地理解应用程序容器的使用和管理。"

Adallom 的营销副总裁 Tal Klein 说，初创公司通常不会谈论安全问题，adal lom 专注于通过监控所有活动、检测未经授权的访问和实时保护用户来发展企业在 SaaS 保护信息的方式。

克莱恩说，像任何初创公司一样，Docker 专注于规模。但和大多数创业公司一样，早期并不经常讨论安全问题。到目前为止，他们真的不需要谈论太多关于安全性的问题，因为这个话题更多的是关于更快的开发和容器方法的不同方面。但是现在随着 Docker 越来越受欢迎，它需要更多地参与到安全社区中来。这是 Docker 把事情做好的机会。

Docker 正在提出一个新的信任系统链，旨在创建更严格的要求，以便 Docker 用户可以对 Docker 图像的来源有更大的信心。

但 Docker 公司的声明也提到了与操作系统的合作伙伴关系:红帽、Canonical(本周发布了 Snappy Ubuntu)和“其他公司”，你可以想象其中可能包括微软。通过指出这些操作系统“一直是 Docker 社区的活跃成员，以帮助我们推动安全性向前发展”，Docker 坚持其立场，即安全性错误不在于 Docker 本身，而是更广泛的 Linux 容器方法的限制。

*特色图片[通过](https://www.flickr.com/photos/genista/5730883/in/photolist-cCN57S-vnAk-7EbFbv-97aq7h-aRjiLH-cYZC9u-NNUB4-fwdhCa-aZbzdX-abxBej-aFkHko-4p2eWL-8gpGwc-4JJxqS-nSwzny-5NsEfa-5NH1cF-fCzrkD-aZbzDF-98qDsy-h7HBJf-8jMz4x-aD9pEC-8xB9n8-8c82JS-e6BWUU-dJMN9x-8dAbem-o2GQzE-dBEkkN-5PEbhF-awukxB-e6wiG6-cYZoTw-bFAh5F-etYQzK-4M7Lsu-6KJ7ND-dLtET3-a4V3Ye-2HHGVS-3pHDVJ-HDcXV-3rP7Z-6YFzTE-aniLJn-5NwVSs-8dx3o4-99fv5L-98jVaz) Flickr 知识共享。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>