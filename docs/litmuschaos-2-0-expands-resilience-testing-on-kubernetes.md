# LitmusChaos 2.0 扩展了 Kubernetes 上的弹性测试

> 原文：<https://thenewstack.io/litmuschaos-2-0-expands-resilience-testing-on-kubernetes/>

对于 [ChaosNative](https://www.chaosnative.com/) 的首席执行官、 [chaos 工程平台的联合创建者和维护者](https://thenewstack.io/how-chaos-engineering-can-drive-kubernetes-reliability/) [Umasankar Mukkara](https://twitter.com/Uma_Mukkara) 来说，混沌工程的趋势是能够任意设计故障，并在第一时间确定是否存在问题。

LitmusChaos 是加入[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)的[沙盒程序](https://www.cncf.io/sandbox-projects/)的[第一个混沌工程项目](https://thenewstack.io/litmuschaos-brings-chaos-engineering-to-cncf-sandbox/)，它将可编程的声明性方法应用于混沌测试，具有稳态假设，并在实验的不同阶段使用石蕊探针。

本周， [LitmusChaos](https://litmuschaos.io/) 的 2.0 版本已经发布，正式上市(GA)。

Mukkara 说 1.0 版本是为了给开源世界带来混乱。该公司创建了一个运营商来支持 Kubernetes 和开放混沌实验，以建立一个社区。

版本 2.0 的目的是使混沌工程对个人和团队都更有效，特别是支持可伸缩性。“这从来都不是一个针对很多人的实验。它是关于把许多不同的经历放在一起。“混乱的工作流程，而不是混乱的实验，”Mukkara 告诉新的堆栈。

一旦采用稳定，2.0 就开始扩展平台功能，使其在定义、测试和测量来自[稳态假设](https://thenewstack.io/chaos-carnival-cultivate-a-corporate-culture-for-chaos-engineering/)的输出的基础上大规模自动化——这反过来使自动化混沌实验更加有效。这允许增加一组 [Prometheus](https://www.prometheus.io/) 指标，并添加过滤器，用于检测应用仪表板，以获得更好的可观察性。

提高效率的另一个步骤是，该平台现在允许用户在他们的 Kubernetes 名称空间中部署 Litmus 工作流。Litmus 团队观察到，许多开发人员试图使用相同的 Kubernetes 集群，在其名称空间中管理他们的应用程序，因此第二个 GA 版本必须解决多租户实验中 Litmus 的管理问题。

到目前为止，这些早期用户最感兴趣的是新的 chaos 工作流，它赋予每个开发人员独立性，同时还允许用户和团队一起运行多个实验，包括:

*   依赖性设置的自动化
*   产生具有多个故障的复杂混沌场景，包括顺序故障和并行故障
*   使用混沌注入定义加载和验证作业
*   通过模板、从集成中心以及自定义上传，灵活地以不同方式创建和运行工作流

“我们都知道混乱是文化。Mukkara 说:“现在，人们更加开放地在他们的 DevOps 实践中考虑混沌工程，”这就是为什么它正在成为一项多功能、跨组织的努力。

但这并不意味着开始在生产中测试。只有大约 20%的 LitmusChaos 用于生产——而且是在一段时间之后。他说，大多数混沌实验是在 QA 或测试环境中运行的，至少在开始时是这样，在那里它们可以更自由地在更深的层次上引入错误。达到生产混乱的一个方法是让更多的人参与理解混乱工程的最佳实践，包括游戏日。

LitmusChaos 2.0 的测试版已经发布了大约六个月，允许社区进行彻底的测试并提供反馈。上个月差不多是[更新文档](http://docs.litmuschaos.io)。

这个新版本的早期采用者包括网络自动化 SaaS 平台 [Anuta Networks](https://www.anutanetworks.com/) 、法国电信公司 [Orange](https://www.orange.com/en) 和印度眼镜电子商务巨头 Lenskart。

[https://www.youtube.com/embed/D0t3emVLLko?feature=oembed](https://www.youtube.com/embed/D0t3emVLLko?feature=oembed)

视频

2.0 版支持在集群范围和命名空间范围模式下设置专用控制平面、混沌代理和执行混沌实验，以帮助在具有自助服务模式的共享集群中运行。

最后，Litmus 扩展到 Kubernetes 之外，允许将混乱注入到基础架构中，包括 Amazon Web Services、Google Cloud Platform、Azure 和 VMware 上的虚拟机、实例和云盘，而不管是否托管 Kubernetes 集群。您甚至可以引入混沌实验来关闭提供基于智能平台管理接口(IPMI)的带外访问的裸机节点。

## 石蕊 3.0

Litmus 3.0 的前景如何？如果 1.0 是关于社区的，2.0 是关于发布流行功能的，那么路线图的下一阶段就是在 ChaosHub 上贡献更多的混沌实验。他们目前正在与社区合作，以澄清哪些是最常用的实验，以添加到开源 [Chaos Hub](https://hub.litmuschaos.io) 的应用级别。

未来还会有 GitHub Actions 整合到平台中。

Mukkara 要求你去 [GitHub](https://github.com/litmuschaos/litmus) 试用 Litmus 2.0，并告诉团队你对其 Slack 社区的看法

石蕊背后的组织 ChaosNative 的下一步是什么？像许多公司一样，它仍然试图找到正确的开源商业模式——注意到开源[不能直接成为商业模式](https://thenewstack.io/open-source-licenses-who-holds-the-power/)。该公司为企业提供商业支持。在未来，他们希望遵循一个开放的核心模型，在 Apache License 2.0 版的明确指导方针内，他们将在此基础上构建一些企业 SaaS 工具。

*第二届年度[混沌嘉年华](https://chaoscarnival.io/)，云原生混沌工程免费活动，将于 2022 年 1 月 27 日至 28 日举行。演讲人[征集活动](https://www.papercall.io/chaoscarnival2022)现在开始，截止到 10 月底。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>