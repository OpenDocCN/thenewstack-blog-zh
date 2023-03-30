# 存储和数据库如何赶上 Kubernetes

> 原文：<https://thenewstack.io/how-storage-and-databases-can-catch-up-with-kubernetes/>

谷歌和其他科技巨头可能是难以效仿的例子。随着组织急于在内部和云环境的混合环境中扩展其基础架构，尤其是在 Kubernetes 上，他们在尝试存储和分析来自无状态来源的数据时往往会遇到困难。许多传统的存储数据库没有达到所需的规模，而早期的云服务，如 AWS 和 Google，在内部开发了自己的存储环境。

华为 [Futurewei Technologies](http://www.huawei.com) 的技术副总裁[昆顿·霍尔](https://www.linkedin.com/in/quintonhoole)说:“Kubernetes 最初非常专注于无状态工作负载，老实说，在提供任何类型的存储支持方面都做得不太好，除了你可以连接到现有的公共云提供商。“我认为这在过去几年里发生了很大的变化，因为有许多不同的云原生数据库[选项]。人们开始在云中，尤其是在 Kubernetes 中执行大量有状态的工作负载。”

本期 New Stack Makers 播客在[kube con+CloudNativeCon North America 2019、](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/)[planet scale](https://www.linkedin.com/in/sugu-sougoumarane-b9bb25)的联合创始人兼首席技术官 Sugu Sougoumarane 以及 Hoole 现场录制，讨论组织可以采取哪些工具和方法来存储和管理来自 Kubernetes 和容器的数据。

他们还讲述了存储和数据库管理工具如何满足组织通常复杂的基础架构需求。然而，找到正确的工具组合并不容易。

[存储和数据库如何赶上 Kubernetes](https://thenewstack.simplecast.com/episodes/how-storage-and-databases-can-catch-up-with-kubernetes)

收听更多剧集，订阅[simple cast](https://thenewstack.simplecast.com/)|[fireside . FM](https://thenewstackmakers.fireside.fm/)|[Pocket Casts](https://pca.st:443/6Ltf)|[Stitcher](https://www.stitcher.com/podcast/the-new-stack-makers)|[苹果播客](https://apple.co/2Dj1tv8) | [阴天](https://overcast.fm/itunes915443155/the-new-stack-makers)|[Spotify](https://spoti.fi/2DYrLEf)|[tune in](https://tunein.com/podcasts/Technology-Podcasts/The-New-Stack-Makers-p989517/)

“当你进入存储，特别是数据库类型的存储时，有大量的配置选项，一个编排系统很难支持所有这些组合，”Sougoumarane 说。“通常情况下，更容易有一种自以为是的方式说，‘这是我们认为应该如何运行的’，但当这种情况发生时，就会有一大堆事情被忽略，所以这是一个很难解决的问题。”

在可用的解决方案中， [PlanetScale CNDb](https://planetscale.com/) ，一个由 CNCF 开源项目 [Vitess](https://github.com/vitessio/vitess) 支持的云原生数据库，为 MySQL 的扩展提供数据库集群。CNCF SIG Storage 也是一种资源。

一个关键要点是，没有一个适合所有组织采用的通用解决方案。如上所述，这在很大程度上取决于组织的复杂性以及它对数据库的要求可能会有哪些具体的限制。

“当你构建小而相对简单的应用程序时，你可以使用任何东西，”Hoole 说。“对于其他事情，当你达到很多人开始使用 Kubernetes 的规模时，我们已经看到了一些非常有趣的例子，说明在非常大的规模上什么是可能的，例如 Zoom 和 Slack 已经开发了什么。

最终，您的组织可能会有非常特殊的存储和数据库需求。

“我认为你最终需要更加专业化的解决方案来解决你试图解决的特定问题，”胡尔说。

[https://www.youtube.com/embed/IM4_jBcpHMU?feature=oembed](https://www.youtube.com/embed/IM4_jBcpHMU?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>