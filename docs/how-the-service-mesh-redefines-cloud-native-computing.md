# 服务网格如何重新定义云本地计算

> 原文：<https://thenewstack.io/how-the-service-mesh-redefines-cloud-native-computing/>

[服务网格如何在云中提供反思——原生转变](https://thenewstack.simplecast.com/episodes/how-service-meshes-offer-a-rethink-in-the-cloud-native-shift)

即将到来的向云原生计算的迁移为 DevOps 管理应用部署的方式带来了明显的变化和转变。挑战中的关键是可观察性和监控、日志记录、路由，当然还有安全性。作为控制这一切的一种方式，服务网格不仅被越来越多地视为非常有用的额外层，而且被视为在微服务和 Kubernetes 上运行的生产管道、部署和操作的必需品。

这是本周 [The New Stack Analysts](https://thenewstack.io/podcasts/analysts) 播客的主题，该播客由 New Stack 创始人兼主编亚历克斯·威廉姆斯(Alex Williams)主持，并由 CloudDon 创始人兼负责人 [Sriram Subramanian](https://www.linkedin.com/in/sriramhere) 共同主持。加入他们的还有 [Instana](https://www.instana.com/) 的[首席执行官兼联合创始人 Mirko Novakovic](https://twitter.com/mirko_novakovic) 和[高级技术产品经理 Michele Mancioppi](https://de.linkedin.com/in/michelemancioppi) 。Instana 提供以微服务为中心的应用性能管理软件和服务。

当然，管理和监控 Kubernetes 的能力是对话的核心部分。Novakovic 说，最初，在 2015 年出现对作为应用程序的微服务和容器的 APM 监控解决方案的需求时，“像 Kubernetes 这样的东西还没有那么受欢迎”。

“我想说的是，发生的事情是人们提高了规格，他们看到像 Kubernetes 这样的编排工具对他们来说非常重要。如今，250 名客户中有 70%在使用 Kubernetes，”Novakovic 说。“因此，他们中的大多数正在转向一个编排层，在这个层中，您已经有了像 Envoy 或 Nginx 这样的代理，我认为我们现在还看到的是具有其他服务网格的下一层。”

Novakovic 说，组织也在“向更高的一层移动，并提取他们需要的服务，如将流量路由到编排层之上的一层，这就是服务网格，如 Istio。

Novakovic 说，服务网格也越来越多地用于多种任务，例如支持 AB 测试的部署策略或仅在服务之间部分路由流量。“这就是为什么我们通过这些代理实施追踪，因为我们得到了客户的需求，他们需要端到端的可见性，”诺瓦科维奇说。“不仅要了解微服务，还要了解服务网格和 Kubernetes 流程编排层等复杂基础设施在做什么，如果出现问题，他们可以在一个完整的跟踪中看到。”

当然，支持广泛的代理是至关重要的。Mancioppi 描述了 Instana 如何支持“已建立的代理”，如 Apache 的代理，它在很大程度上被理解和采用，Mancioppi 说。我们从 Envoy 和 Nginx 开始，”Mancioppi 说。的确，Mancioppi 说 Envoy 是“反向代理复兴的典型代表”。虽然 Instana 支持的“到目前为止不是唯一的”代理，但 Mancioppi 表示，还支持一系列其他替代方式，如流量。未来还可能会有更多，”曼乔皮说。

考虑到增加计算负载的可能性，监控当然是至关重要的。诺瓦科维奇说:“我们今天看到的是，你需要一种额外资源非常少的技术，并且基本上零延迟地进行观察和追踪。”

### 在这个版本中:

[3:24:](https://thenewstack.simplecast.com/episodes/how-service-meshes-offer-a-rethink-in-the-cloud-native-shift?t=3:24)Instana 刚刚宣布了针对 NGINX 和 Envoy 应用程序代理的监控和跟踪功能，这与这些快速增长的复杂性有什么关系呢？
[5:55:](https://thenewstack.simplecast.com/episodes/how-service-meshes-offer-a-rethink-in-the-cloud-native-shift?t=5:55) 探索延迟、数据平面以及 Instana 如何处理这些问题
[10:48:](https://thenewstack.simplecast.com/episodes/how-service-meshes-offer-a-rethink-in-the-cloud-native-shift?t=10:48) 这是您现在服务的两个代理吗？或者你也以某种方式包括了 HAProxy？
[18:46:](https://thenewstack.simplecast.com/episodes/how-service-meshes-offer-a-rethink-in-the-cloud-native-shift?t=18:46) 在这个已知与未知的交汇点，你在这里找到了什么？
[22:41:](https://thenewstack.simplecast.com/episodes/how-service-meshes-offer-a-rethink-in-the-cloud-native-shift?t=22:41) 作为一名应用程序开发人员，当我试图启用跟踪时，我可以使用哪些钩子？
[27:40:](https://thenewstack.simplecast.com/episodes/how-service-meshes-offer-a-rethink-in-the-cloud-native-shift?t=27:40) 在这部作品中，你开始看到了哪些模式？

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>