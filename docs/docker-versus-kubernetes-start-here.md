# Docker 对 Kubernetes:从这里开始

> 原文：<https://thenewstack.io/docker-versus-kubernetes-start-here/>

Kubernetes 赢得很好，在 Kubernetes 与 Docker 之间的战斗。今天的 Kubernetes 给所有生产级 IT 蒙上了可怕的阴影；Docker 的位分散在不同的开源代码库和高级订阅计划中。

这很遗憾，因为开发商喜欢💕docker——许多人仍然如此——尽管他们对 Kubernetes 基本上没有什么好感。

根据谷歌搜索查询，关于“Kubernetes 对 Docker”的辩论仍然是一个热门话题。这可能就是你现在正在读这篇文章的原因。为什么有人会在搜索引擎中输入“Kubernetes vs. Docker”这样的内容？但许多人确实如此。

所以我们都在这里，这是我们的荣幸教育你所有的事情 Kubernetes，Docker，和他们的联盟。

[https://www.youtube.com/embed/XfBrtNZ2OCw](https://www.youtube.com/embed/XfBrtNZ2OCw)

视频

## Kubernetes 需要 Docker 吗？

传统上，行业创新巨头们对开发人员的活动并不感兴趣。“Devs”没有太多的购买权限，只是坐在那里，一直编码。当史蒂夫·鲍尔默在 2008 年高呼“开发者，开发者，开发者”时，这是一个绝望的请求，要求开发者跳到 Windows 平台上，永远陷入与互联网的地盘争夺战(这是在 it 行业认识到开发者自己将成为[的热门商品](https://thenewstack.io/2022-forecast-whats-next-for-tech-workers/)之前)。

但是开发人员的数量非常多，当 Docker 挠痒痒的时候，开发人员会热情地回应，就像一只巨大的狮子从它巨大的爪子上拔掉刺一样。

棘手的问题是，一旦他们的代码完全开发出来，就很难在生产环境中运行。所有这些配置更改都必须满足生产中的要求。这是一场争论。

使用 Docker，开发人员可以将整个应用程序及其附件[放入一个容器](https://thenewstack.io/how-to-deploy-a-container-with-docker/)中，并让其他系统运行该容器，而不是应用程序，而不是将应用程序及其库复制到一个变化的环境中。

伊兹·佩兹。欢乐随之而来。

## 码头工人和集装箱

2015 年，Docker 是房间里最酷的孩子，这让年龄更大、更强壮的孩子有点不安。

比如说操作人员，他们可能被 Docker 的管理员的一些任性的做法吓到了，他的口头禅是“[包含电池但可更换](https://thenewstack.io/orchestration-toolkit-release-aims-prove-dockers-commitment-flexibility-community-ecosystem/)”运营是指那些在“开发运维”中扮演关键角色的 IT 专业人员他们认为 Docker 的编码实践有点不可预测。

此外，他们抱怨说，容器只是 Unix 命令集的[。Sun Microsystems 在自己的产品目录中有容器已经有十年了，IBM 从 20 世纪 70 年代开始在大型机中使用容器。甚至开源企业软件巨头](https://earthly.dev/blog/chroot?joabj.com) [Red Hat](https://www.openshift.com/try?utm_content=inline-mention) 的仓库中也有 LLVM。

一些公司，完全独立地，甚至[大力游说](https://thenewstack.io/docker-fork-talk-split-now-table/)开源社区，已经开源的 Docker 代码应该移交给一个标准机构。感觉到阻力的力量，码头工人被迫。

## Kubernetes 比 Docker 好吗？

Atlassian 在自己对 Docker 与 Kubernetes 争议的看法中，[将两者之间的差异](https://www.atlassian.com/microservices/microservices-architecture/kubernetes-vs-docker#:~:text=Kubernetes%20vs.-,Docker,CRI%20(Container%20Runtime%20Interface).)描述为 Docker 只是一个容器运行时，而 Kubernetes 是一个用于运行容器运行时的*完整平台*:

*Docker 是一个容器运行时，Kubernetes 是一个运行和管理来自许多容器运行时的容器的平台。Kubernetes 支持许多容器运行时，包括 Docker、containerd、CRI-O 和 Kubernetes CRI(容器运行时接口)的任何实现*

从 1.24 版本开始，Kubernetes 不再支持 Docker 运行时，尽管 Docker 容器本身在 Kubernetes 上运行良好。

可观察性提供者 [Dynatrace](https://www.dynatrace.com/?utm_content=inline-mention) 进一步[解释了 Docker 和 Kubernetes 之间的区别](https://www.dynatrace.com/news/blog/kubernetes-vs-docker/):

就像人们使用施乐作为纸质副本的速记，说“谷歌”而不是互联网搜索一样，Docker 已经成为容器的代名词。然而，Docker 不仅仅是容器。Docker 是一套工具，供开发者构建、共享、运行和编排容器化的应用程序。

## Kubernetes 能取代 Docker 吗？

回到 2015 年:在谷歌总部，一些谷歌工程师认为，如果世界上的每个人都以谷歌的方式组织他们的大规模数据中心，这将是一个好主意。这体现在一个叫做 [Kubernetes](https://thenewstack.io/primer-how-kubernetes-came-to-be-what-it-is-and-why-you-should-care/) 的东西上，它是一个内部资源调度器的仿制品，叫做——我们不骗你——博格。

幸运的是，谷歌雇佣了一个来自*我们自己的*星球的人——总是才华横溢的[凯尔西·海塔尔](https://thenewstack.io/kelsey-hightower-on-his-very-personal-kubernetes-journey/)——向容器用户解释这种“Kubernetes”，这些用户对他们手头越来越多的容器越来越感到困惑。海托华让这看起来很容易，他在舞台上旋转一个集群，通过手机上的语音命令*，同时在数千名持怀疑态度的旁观者面前开玩笑。*

[https://www.youtube.com/embed/07jq-5VbBVQ?feature=oembed](https://www.youtube.com/embed/07jq-5VbBVQ?feature=oembed)

视频

于是各方一致同意:[牛不是宠物](https://thenewstack.io/how-to-treat-servers-and-software-as-cattle-not-pets/)。云原生计算诞生了。

## 最后

Kubernetes 和 Docker 是两个不同的软件包，服务于不同的目的。如今，Docker 公司为开发人员提供了大量桌面工具来构建容器。它甚至有自己的竞争对手 Kubernetes，名为 [Docker Swarm](https://docs.docker.com/engine/swarm/) ，因其易用性而受到[好评。](https://thenewstack.io/docker-swarm-wins-scaling-benchmark-dont-take-gospel/)

2019 年，Docker [将其一部分](https://thenewstack.io/mirantis-acquires-docker-enterprise/)资产出售给 [Mirantis](https://www.mirantis.com/?utm_content=inline-mention) ，后者继续提供 Docker 企业平台。另一方面，Kubernetes 是所有最大的云提供商提供的服务。亚马逊网络服务’[亚马逊 Kubernetes 服务](https://aws.amazon.com/)就是这样一个例子。

从某种意义上说，Docker 和 Kubernetes 分别像农夫和牧场主。每个人在农场都有不同的角色，每个人都用农场的土地做不同的用途。但这不是他们不能成为朋友的理由。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>