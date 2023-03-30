# 开放标准，以及 containerd 在 Kubernetes 编排中的作用

> 原文：<https://thenewstack.io/open-standards-and-the-role-of-containerd-in-kubernetes-orchestration/>

[集装箱之前可能出了什么问题](https://thenewstack.simplecast.com/episodes/what-could-have-gone-wrong-before-containerd)

当 Kubernetes 开始采用 Docker 时，Docker 已经是事实上的标准，但是 Docker 支持它自己的替代产品 Swarm orchestrator。显然需要一个容器运行时的行业标准。这导致了[Cloud Native Computing Foundation](https://containerd.io/)内的 [containerd](https://containerd.io/) 的创建和随后的毕业，加入了 Kubernetes、Prometheus、Envoy 和 CoreDNS 的行列。

IBM Watson 和云平台部门负责容器和 Linux OS 架构战略的杰出工程师兼首席技术官 Phil Estes 表示:“Container 不仅仅是被创造出来的，它对 CNCF 的捐赠也是响应这种需求的一部分，这种需求是一种稳定乏味的核心运行时，它将驻留在 Kubernetes 之下，并拥有正确的生命周期支持，不会在 Kubernetes 之间引起那些摩擦，因为 Kubernetes 只是想要一个稳定的层，只运行容器，而不做任何其他事情。

Estes 在最新一集的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中分享了他的想法，该播客由 Alex Williams 主持，他是在[开源领袖峰会](https://events.linuxfoundation.org/events/open-source-leadership-summit-2019/)期间录制的 New Stack 的创始人兼主编。

事实上，导致创建 containerd 的讨论最终是建设性的，而辩论是活跃的。埃斯蒂斯说，这样一来，“争论带来了遏制”。

“来自整个行业的许多聪明人在其中发挥了作用，他们可以说，‘嘿，让我们从这里开始有一个冷静的方向，包括一些东西，一个让 Docker 继续创新的基础，’”Estes 说。“在那些日子里，有很多会议不一定是公开的，但在让合适的人聚在一起达成共识方面非常重要。”

埃斯蒂斯说，我们的想法是“不要在这里失去冷静”。“我们决定最好的前进道路是“开放、覆盖良好，这为许多不同的供应商提供了基础，所以我们不会在我的容器不能在你的产品上运行的世界中结束，因为你知道，我们在 2016 年都朝着不同的方向前进，”埃斯蒂斯说。

“由于开放容器倡议(OCI)的标准化努力，containerd、 [cri-o](https://cri-o.io/) 、Docker 和 Kubernetes“都可以生活在这样一个世界中，我们都可以合作并具有互操作性，”Estes 说否则，我认为，如果所有这些实现之间没有真正的互操作性，这将是容器的丧钟，”Estes 说。

在引擎盖下，OCI“实际上是什么是容器映像、什么是容器运行时的标准化层，而 [runC](https://blog.docker.com/2015/06/runc/) 是多年后现在每个人都真正使用和基于的实现，”Estes 说。Estes 说，通过这种方式， [containerd](https://containerd.io/) 在堆栈上设置一层，并管理 runC 正在运行的容器，以便“开始”、“停止”和“列表”等命令可以对 runC 执行的容器进行操作。

Docker 仍然是容器的事实上的标准，然而，争议仍然存在。“即使在今天，你知道，可能会有一些声音说，‘OCI 似乎只是 Docker 风格的图像格式运行时功能的一个橡皮图章。“但标准往往来自务实的地方。“你知道，‘这是人们正在使用的，让我们围绕它标准化，’”埃斯蒂斯说。“所以你知道，我认为，最终，OCI 是一个务实的好选择，接受正在使用和已经完成的内容，并将其编入标准。”

![](img/ca66a79791feb9b6ce8108d80c7903d9.png)

CNCF 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>