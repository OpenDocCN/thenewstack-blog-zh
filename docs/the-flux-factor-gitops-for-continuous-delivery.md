# 流量系数:连续输送的 GitOps

> 原文：<https://thenewstack.io/the-flux-factor-gitops-for-continuous-delivery/>

[KubeCon + CloudNativeCon](http://bit.ly/2GBO5Dd) 赞助本帖。

GitOps 通常与 Kubernetes 的持续交付同义。更广泛地说，GitOps 采用了 DevOps 的最佳实践——协作和打破孤岛、版本控制、自动化测试和合规性，当然还有持续集成——通常应用于应用层，并将其向下扩展到基础架构层。GitOps，其中代码更改从 git 存储库中自动[推送](https://thenewstack.io/what-is-gitops-and-why-it-might-be-the-next-big-thing-for-devops/)，旨在为运营工作流转换敏捷开发的速度和可伸缩性，并且通常在 Kubernetes 层进行抽象。

在这一集的 [The New Stack Makers](/podcasts/makers) 播客中，我们将与 [Weaveworks](https://www.weave.works/) 团队的三名成员进行对话:创始人兼首席执行官 [Alexis Richardson](https://twitter.com/monadic) 、首席技术官 [Cornelia Davis](https://twitter.com/cdavisafc) 以及开发者体验工程师 [Flux](https://github.com/fluxcd/flux) 和 [Flagger](https://flagger.app/) 的架构师 [Stefan Prodan](https://twitter.com/stefanprodan) 。他们反思了云原生技术社区中的下一代工具。四方还讨论了该工具如何融入 GitOps 工具包，特别是 GitOps 项目的 [Flux 连续交付](https://www.weave.works/oss/flux/?utm_source=thenewstack&utm_medium=website&utm_campaign=platform)的下一个发展。《新书库》的创始人兼发行人亚历克斯·威廉姆斯(Alex Williams)主持了这一集。

[流量系数:GitOps 为连续输送](https://thenewstack.simplecast.com/episodes/the-flux-factor-gitops-for-continuous-delivery)

Flux 允许在环境中自动部署更新，无需外部脚本或工具。与 Kubernetes 的大多数东西一样，它的好处是无需开发人员与它直接交互就能获得 Kubernetes 的好处。正如 Container Solutions 的 Steve Landry Tene 写的那样:“Flux 连接到你的 Git 存储库，监视特定分支和文件夹的所有变化。当提交发生时，Flux 将在集群上操作，以便部署这些更改。”

Davis 把 Flux 看作是一个信号，表明 CI/CD 几乎完全专注于集成方面，代码交付只是在最后发生的事情。

“持续交付是在一个协调循环中发生的事情，”她说。“它在不断变化，不断需要调和。”

Davis 解释说，GitOps 然后将交付流程进一步扩展到持续运营中。

[https://www.youtube.com/embed/_jNYwTKIEJI?feature=oembed](https://www.youtube.com/embed/_jNYwTKIEJI?feature=oembed)

视频

“从运行时的角度来看，这是交付，然后是我的群集中实际发生的事情，以及这与连续交付有什么关系，”Davis 说。“所以他们有点像是在一起跳舞，然后一起合作。”

Prodan 以此为基础，描述了如何扩展安全性，不仅仅是基于角色的访问控制，而是扩展到整个变更管理系统，包括 git 端和集群内部。随着 Flux 的第二个版本开始推出，他们通过在集群内启用多租户来添加第三个安全层，不同的存储库具有不同的访问权限。此外，他们允许来自多个存储库的协调。

“Flux 正在做的是查看 git 而不是 [etcd](https://etcd.io/) ，并将 git 与 etcd 同步。然后本地 Kubernetes 控制器接管并做他们自己的事情。因此，在某种程度上，Flux 就像所有内置或其他运算符之上的一个运算符，”Prodan 解释道。

总的来说，Flux 2.0 希望创建一种 GitOps 工具包，允许团队定制他们自己的 Kubernetes 工作流。

理查森认为这是信息技术民主化的一个明显的下一步——即使是在大公司里。

“我们发现，客户要求最多的是‘我的 CI 已经准备就绪。添加 CD 的最简单方法是什么？我们向他们展示的最简单的方法实际上是使用 GitOps 实现的这一非常酷的协调概念，”理查森谈到 Flux 在持续部署中的受欢迎程度。

Davis 描述了下一步将不会是破坏已经运行了一段时间的持续集成，而是 GitOps 的下一步是确保持续交付方面的现代化。最终结果？纯平台团队赋能。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>