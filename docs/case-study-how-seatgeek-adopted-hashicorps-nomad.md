# 案例研究:SeatGeek 如何采用 HashiCorp 的 Nomad

> 原文：<https://thenewstack.io/case-study-how-seatgeek-adopted-hashicorps-nomad/>

洛杉矶——开源容器 orchestrator Kubernetes 可能在云原生世界中有很大的足迹，但一些组织没有它也做得很好。以 SeatGeek 为例，它运行一个移动应用程序，作为活动门票的一级和二级市场。

[案例分析:SeatGeek 如何采用 HashiCorp 的 Nomad](https://thenewstack.simplecast.com/episodes/case-study-how-seatgeek-adopted-hashicorps-nomad)

对于云基础设施，这家有 12 年历史的公司的工作负载——包括非容器化的应用——主要运行在[亚马逊网络服务上。](https://aws.amazon.com/?utm_content=inline-mention)几年前，[seat geek 的员工工程师 Jose Diaz-Gonzalez](https://www.linkedin.com/in/josediazgonzalez)在本期 New Stack Makers 播客中说，他们转向了 [HashiCorp 的](https://www.hashicorp.com/?utm_content=inline-mention) Nomad，一个为应用程序运行而构建的调度程序，无论它们是否被容器化。

[https://www.youtube.com/embed/dv6YXy1tqu0](https://www.youtube.com/embed/dv6YXy1tqu0)

视频

这个关于 seat geek[采用 Nomad](https://thenewstack.io/conductor-why-we-migrated-from-kubernetes-to-nomad/) 和 HashiCorp 云平台的案例研究是创客在路上的一集，在 HashiConf，HashiCorp 的年度用户大会期间录制。对话由 TNS 的特稿编辑希瑟·乔斯林主持。

这一集是由哈希公司赞助的。

## 游牧者与库贝奈特人:权衡

Diaz-Gonzalez 说，SeatGeek 本质上是为其合作伙伴管理票务销售的后台办公室，包括百老汇制作公司和达拉斯牛仔队等 NFL 球队，为他们提供“类似于软件即服务的东西”。

“所有这些安装都是单租户的，但对于每个客户来说，它们的运行方式大致相同。在消费者方面，我们运行大量不同的服务和微服务，诸如此类。”

他说，尽管工作负载运行在不同的语言或不同的框架上，但它们在部署模式上本质上是同质的；SeatGeek 在企业端部署到 Windows 和 Linux 容器，在消费者端部署到 Linux，并部署到美国和欧盟地区。

它开始使用 Nomad 让开发者对他们的应用程序有更多的控制权；Diaz-Gonzalez 说，以前，部署体验非常受限制，导致了他所说的“非常静态的体验”

“要扩展一个应用程序，需要平台团队方面的手工劳动，然后他们可以做一些工作，”他说。“因此，对我们来说，我们希望向工程师展示更多的平台，让他们能够更好地控制他们交付的内容、运行时环境的执行方式以及他们如何扩展自己的应用。”

他说，现在，SeatGeek 使用 Nomad 来为我们的部署提供基本上完整的编排层。

前述 Kubernetes (K8s)确实有其缺点。[云原生生态系统](https://landscape.cncf.io/)很大程度上是围绕旨在与 K8s 而非 Nomad 一起运行的产品构建的。

围绕 HashiCorp 产品建立的生态系统是“一个小得多的社区。如果我们需要支持，我们非常依赖哈希公司。我们愿意在支持团队中回答问题。但是，如果我们需要支持来进行一些特定的改变，或者使用某些特定的功能，我们可能是少数开始使用该功能的人之一。”

“也就是说，对我们来说，管理和支持 Nomad 以及它与我们平台其余部分的集成要容易得多，因为它运行起来非常简单。”

要了解更多关于 SeatGeek 的云之旅及其面临的挑战——如处理安全和政策——请查看完整集。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>