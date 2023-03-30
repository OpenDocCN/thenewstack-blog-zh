# KubeCon 2017 Pancake 播客:关于服务网格的一切

> 原文：<https://thenewstack.io/kubecon-2017-pancake-podcast-service-mesh/>

[#152: KubeCon 2017 煎饼播客:关于服务网的一切](https://thenewstack.simplecast.com/episodes/152-kubecon-2017-pancake-podcast-all-about-the-service-mesh)

上周，在[云原生计算基金会](https://www.cncf.io/)的 KubeCon+CloudNativeCon 2017 上，大部分讨论似乎都围绕着[服务网格](/tag/service-mesh/)，每个人都很好奇，既然他们已经安装了 [Kubernetes](/category/kubernetes/) 开源容器编排引擎，为什么他们还需要一个。这个话题为我们的 pancake 播客小组讨论带来了一名 SRO 观众，我们在最新一集的 [The New Stack Analysts](https://thenewstack.io/podcasts/analysts) 播客中捕捉到了这个话题，以供您欣赏。

这一活动证明是受欢迎的。人们挤满了房间，以便从我们的小组中听到更多关于技术的信息，小组由 TNS 创始人[亚历克斯·威廉姆斯](https://twitter.com/alexwilliams?lang=en)主持:

就在那天早上，浮力公司推出了 Conduit，这是它专门为 Kubernetes 开发的下一代服务网。它立即加入了这个新兴市场的新兴服务网格竞争者的行列，与 Lyft 的 Envoy、Istio 和 bubbly 自己的 Linkerd 并列。

简而言之，服务网格是一组用于服务到服务通信的网络软件。它遵循面向服务的体系结构(SOA)的原则，但是它没有使用集中式企业服务总线(ESB)，而是使用一组轻量级网络代理，作为“附属设备”附加到每个服务上。这使得开发人员不用考虑支持基础设施，只需用他或她喜欢的语言开发服务。对于管理员来说，服务网格带来了许多内置功能，如速率限制、负载平衡、服务发现机制和断路功能。

专家组一致认为，随着基于微服务的应用程序越来越多地由 Kubernetes 处理，显然需要某种类型的服务网络。Pierov 讲述了他的组织 NCBI 是如何使用服务发现工具的，但是随着服务数量的急剧增加，他们在扩展时遇到了困难。

例如，虽然 Kubernetes 在 L4 负载平衡方面提供了一些灵活性，但它只能对整个连接进行负载平衡，而不能对单个请求进行负载平衡。摩根指出，虽然 Kubernetes 可能需要一个服务网格，但一个好的服务网格并不局限于只与 Kubernetes 一起运行。事实上，服务网格还可以与虚拟机、无服务器部署甚至裸机部署进行应用程序级通信。沉浸在虚拟机中的组织可以使用服务来构建 SOA，然后，随着时间的推移，跳过容器，直接进入无服务器模式。

Nova 指出，服务网格本身的出现在很大程度上归功于 Kubernetes 开创性的可扩展架构。

“最终,(服务网格)是我们正在解决的一个高级问题的软件封装。这正是 Kubernetes 所擅长的:允许用户将自定义业务逻辑，或者在这种情况下，自定义网络逻辑，封装到软件中，并以非常灵活的方式运行它，”Nova 说。“因此，当我听到人们谈论服务网格时，我的脑海中总是这样想，“耶，Kubernetes 正在做我们从第一天起就设计它要做的事情。"

[https://www.youtube.com/embed/el6fWr689t0?feature=oembed](https://www.youtube.com/embed/el6fWr689t0?feature=oembed)

视频

### 在这个版本中:

[4:16:](https://thenewstack.simplecast.com/episodes/152-kubecon-2017-pancake-podcast-all-about-the-service-mesh?t=4:16) 什么是服务网格？
[12:21:](https://thenewstack.simplecast.com/episodes/152-kubecon-2017-pancake-podcast-all-about-the-service-mesh?t=12:21)Kubernetes 背景下的服务网状演进。
[14:14:](https://thenewstack.simplecast.com/episodes/152-kubecon-2017-pancake-podcast-all-about-the-service-mesh?t=14:14) 服务网格可以帮助捕获哪些信息。
[20:24:](https://thenewstack.simplecast.com/episodes/152-kubecon-2017-pancake-podcast-all-about-the-service-mesh?t=20:24) 服务网格如何帮助仍处于传统环境中的组织。
[25:39:](https://thenewstack.simplecast.com/episodes/152-kubecon-2017-pancake-podcast-all-about-the-service-mesh?t=25:39) Conduit 使用 Rust 实现数据平面安全。
[36:12:](https://thenewstack.simplecast.com/episodes/152-kubecon-2017-pancake-podcast-all-about-the-service-mesh?t=36:12) 导管和分布式跟踪。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>