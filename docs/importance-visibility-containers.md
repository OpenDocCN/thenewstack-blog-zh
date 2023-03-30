# Sysdig:容器可见性的重要性

> 原文：<https://thenewstack.io/importance-visibility-containers/>

在今天的[新堆栈分析师](https://thenewstack.io/podcasts/Analysts)播客中，TNS 编辑[本杰明·鲍尔](https://twitter.com/benballjr)采访了 [Sysdig](http://www.sysdig.org/) 创始人[洛里斯·德吉奥安尼](https://www.linkedin.com/in/degio)，为我们的第五本电子书做准备，刚刚发布的[用 Docker &容器](https://thenewstack.io/ebookseries/)监控&管理。Sysdig 的 [ContainerVision](https://sysdig.com/press-releases/sysdig-announces-container-monitoring-software/) 技术为开发人员提供了对其容器化应用程序的可见性，而无需在容器中放置单独的代理。Ball 和 Degioanni 探讨了容器编排的未来、企业目前面临的遥测问题，以及在更新传统监控基础设施时需要考虑的问题。

[#124:容器可见性的重要性](https://thenewstack.simplecast.com/episodes/124-the-importance-of-having-visibility-into-containers)

[https://www.youtube.com/embed/VggD3lBoi3c?feature=oembed](https://www.youtube.com/embed/VggD3lBoi3c?feature=oembed)

视频

Degioanni 建议开发人员在使用 Docker 和 Kubernetes 时，首先利用他们可用的各种工具，而不是将容器视为较小版本的 VMs。其中包括利用 Docker statistics API 来帮助获取系统指标，这对于那些只需要了解系统在大规模运行时如何受到其容器负载影响的人来说非常有用。

ContainerVision 的工作方式与许多监控解决方案中的传统方式大相径庭，它选择在操作系统本身中安装一个模块，而不是在每个单独运行的容器中安装一个代理。“因此，你不必把东西放在容器里面，而是把东西放在容器下面，这样做的好处是安装起来既完整又简单，既完整又水平。所以你永远不会忘记任何事情，因为这个模块可以看到每一个容器，包括正在运行的容器，也包括未来将运行的容器，”Degioanni 说。

通过利用 Linux 内核系统调用， [ContainerVision](https://thenewstack.io/no-agents-needed-to-monitor-containers-says-sysdig-just-linux-kernel-changes/) 可以在数据导出到数据库时拦截数据。“另一种方法是对每个容器进行大量检测，以便能够从中收集数据。从本质上说，这样做意味着向容器添加流程和依赖关系，这些容器实际上是在实现你的实际服务，并向外部世界暴露表面，”Degioanni 说。

最终，随着监控的未来继续发展和变化，开发人员和企业从端到端的角度进行监控的方式也必须发展。

[cyclone slider id = " ebook-5-赞助商"]

“您的工具确实需要从头开始构建。你需要从一张白纸开始。这就是一批新的供应商在过去几年中获得显著地位的原因。那么，我是否尊重现有的遗留系统供应商和监控工具供应商？是的。我认为他们能进化他们的工具以某种方式到达那里吗？是的。”

Sysdig 赞助了这个播客。

由[奥内拉·宾尼](https://unsplash.com/@ornellabinni)通过 [Unsplash](https://unsplash.com/?photo=ZoCwTGO8bJI) 拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>