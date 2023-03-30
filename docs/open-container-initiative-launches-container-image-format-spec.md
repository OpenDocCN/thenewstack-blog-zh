# 开放集装箱倡议发起了集装箱图像格式规范

> 原文：<https://thenewstack.io/open-container-initiative-launches-container-image-format-spec/>

[开放容器倡议](https://thenewstack.io/oci-reveals-governance-structure-amid-debate-focus/) (OCI)在建立新兴容器生态系统的标准基础方面迈出了下一步。该组织已经启动了一个项目，以建立一个集装箱图像格式规范。

CoreOS 首席执行官 Alex Polvi 说，作为 OCI 正在研究的容器运行时标准的后续，容器映像的开放规范是“整个讨论的关键部分”。CoreOS 提供了 [rkt 容器软件](https://coreos.com/rkt/)，这是广泛使用的 Docker 容器图像格式的一种替代方案。

“我喜欢网络浏览器的类比。就像 Firefox 和 Chrome 一样，”他说。“那些就像 Docker 和 rkt 就像他们两个共享 HTML5 一样。这是开发人员开发的目标，web 应该在浏览器中也是一样的。

我认为，最终这对于客户和最终用户来说是一个巨大的胜利，因为他们有了选择和互操作性。有了通用格式，用户可以打包应用程序，然后让它在 Docker 或 rkt 中交替运行。"

该项目的目标是允许开发人员对应用程序容器进行打包和签名，然后使用最符合他们需求的构建工具和执行方案在各种容器引擎中运行它们。然后，容器可以在各种运行时不加修改地运行，从 rkt 和 Docker 到 Kubernetes 和 Amazon ECS。

OCI 图像格式规范的最初维护者是来自 Red Hat 的 Vincent BattsJonathan Boulle 和 Brandon Philips，CoreOS 码头工人斯蒂芬·戴；贾森·布赞恩和布伦丹·伯恩斯，谷歌和约翰·斯塔克斯，微软。

该项目将基于 Docker v2.2，并借鉴 CoreOS 的 [appc 规范](https://thenewstack.io/coreoss-rkt-blazes-secure-trail-appc-containers/)。Apcera、Google、Red Hat 和 VMware 都是支持 appc 的行业联盟的成员。

当 OCI 四个月前宣布其路线图和治理结构时，Polvi [指责](https://coreos.com/blog/oci-image-specification.html)该项目过于狭隘地关注运行时规范。Polvi 当时写道，为了实现真正的互操作性，在图像格式方面还有更多工作要做。

“OCI 背后的想法是从 Docker 获得广泛部署的运行时和图像格式实现，并本着 appc 的精神建立一个开放标准。我们欣然接受了这一前景，因为拥有一个共享标准是一个独特的机会，可以促进容器的广泛扩散和采用，以及竞争实现的健康生态系统，”他当时写道。“虽然最初看起来 OCI 和 appc 之间有一些重叠，但 OCI 只专注于运行时，这比我们对项目的预期更加狭隘。”

同样在 OCI 相关的新闻中，Docker 已经发布了 Docker Engine 1.11，这是第一个完全符合 OCI 的运行时引擎版本，通过 [runC](http://runc.io/) OCI 规范和 Docker 的 containerd 。

“随着这个版本的发布，Docker 引擎现在是基于 containerd 构建的，所以每个使用 Docker 的人现在都在使用 OCI，”Docker 引擎技术负责人 [Arnaud Porterie](https://twitter.com/icecrime) ，[在宣布发布](https://blog.docker.com/2016/04/docker-engine-1-11-runc/)的博客帖子中写道。

“这是我们努力将 Docker 分解成小的可重用组件的一部分，”Porterie 补充道。

451 Research 的云计算管理和容器研究经理 Jay Lyman 表示，简单性一直是现代应用程序容器的核心驱动力，这种向图像格式规范的转变反映了人们对继续保持简单性的兴趣和需求。

“尽管我们看到容器中的许多关注、活动和竞争都集中在容器管理和编排的堆栈上；重要的是容器背后的社区尽可能保持简单性。一个以可分发容器图像为中心的新项目应该会有所帮助，”他说。

特征图片:[巴塞罗那集装箱港口](https://www.flickr.com/photos/davies/3842826974/in/photolist-6Rzuzu-rRNFjd-rcAUyX-89BrKS-8mTFNu-6uo4X7-rRQ8Ab-hD7EEi-4X2Pm7-hD9dcx-6PcBHz-4UUC3M-hD7Yfu-hD91V4-4mKEv3-4U8yUp-piD2pu-bmF8ew-82coQc-oZqQPS-82cqTr-hD81qb-hD7HeX-7eWEYB-7SAL5L-hD7QJ7-hD8nSN-4mKFGf-ct5SK9-rbygvx-8bRNk1-8bRP93-8bNtNM-8bRN1L-8bNuxT-hYpVJY-8bNuaB-8ABe7k-8AFdUC-82crT8-4aSGdf-f2zFam-hD99sZ-74R6zq-9semb-4Lrsav-keiysf-hD8mof-hD9aak-aoaoiD)由[戴维·戴维斯](https://www.flickr.com/photos/davies/)提供，在 **CC BY-SA 2.0** 下获得许可。

Apcera、CoreOS 和 Docker 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>