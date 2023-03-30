# VMware 为定制 Kubernetes 部署推出基本 PKS

> 原文：<https://thenewstack.io/vmware-introduces-essential-pks-for-custom-kubernetes-deployments/>

VMware 发布了 Essential PKS，这是一个面向组织的平台，这些组织希望构建 Kubernetes 的自定义部署，但也可以获得专家支持。

它是对之前宣布的两个产品的补充:[企业 PKS](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/datasheet/services/vmware-pks-datasheet.pdf) ，一个使用 Kubernetes 的紧密打包方式，和云 PKS，一个总部位于 SaaS 的仍处于测试阶段的 Kubernetes 服务。两者都为运行 Kubernetes 工作负载提供了生命周期管理、注册和其他组件。

“Essentials 代表了为 VMware 客户带来生机的 Heptio 模式，”VMware 负责云原生应用的产品营销高级总监 [Scott Buchanan](https://www.linkedin.com/in/scottdbuchanan/) 说。

他指的是该公司去年 11 月斥资 5.5 亿美元[收购西雅图的](https://thenewstack.io/vmware-to-acquire-heptio-to-boost-enterprise-kubernetes-expertise/) [Heptio](https://heptio.com/) 。这是 Joe Beda 和 Craig McLuckie 的创业公司，他们和 Brendan Burns 一起在 Google 创立了 Kubernetes。

Heptio 的愿景是让用户更容易接触到 Kubernetes。

基本 PKS 有三个部分:最新的，上游 Kubernetes 的稳定版本；专家支持；以及为设计决策提供信息的参考架构，包括收购带来的技术，如 [Contour](https://github.com/heptio/contour) 、 [Sonobuoy](https://github.com/heptio/sonobuoy) 和 Bolero。

同样来自 Heptio 的 Buchanan 说:“被 Essential PKS 吸引的客户通常是更大、更完整的企业，它们有非常具体的要求、想要使用的非常具体的技术或想要运行的环境。“因为他们是一个更大、更复杂的企业，他们更有可能拥有内部专业知识来参与该足迹的设计，然后继续运营它。”

企业 PKS 是一个更好的交钥匙产品，而云 PKS 更适合不想管理或维护其集群的客户。

[PKS](https://pivotal.io/platform/pivotal-container-service) (Pivotal 容器服务)，是一个企业级 Kubernetes 发行版(Pivotal 和 VMware 都属于戴尔)。然而，Buchanan 说，所有这三个 VMware PKS 产品都是建立在上游 vanilla Kubernetes 的框架之上的。

他说:“我们认为，这为客户提供了跨环境的最佳可移植性，考虑到这个市场变化的速度，这一点非常重要。”。

参考体系结构帮助客户找出许多需要尽早做出的决策。

“我使用什么工具进行监控、记录和跟踪？客户不一定有很多专业知识，因为 Kubernetes 是一项年轻的技术，”他说。

“他们几乎是在寻找一个蓝图:哪些技术可以很好地协同工作？像我这样的其他企业在生产中部署了什么？这就是我们构建并扩展这些参考体系结构库的原因。”

随着收购而来的许多 Heptio 现场工程师现在被称为 Kubernetes 建筑师团队。他说，他们正在注入高度的实践专业知识，这将有助于公司扩大规模，接触更多的 VMware 客户。

Buchanan 说，在过去的 12 个月里，VMware 是整个开源 Kubernetes 项目的第三大贡献者，该公司计划继续这样做。

集装箱化最初被[视为对 VMware 基于虚拟机的业务的威胁](/amid-container-vs-vm-hype-vmware-draws-docker-closer/)。

Cowen &公司当时的高级基础设施软件分析师 Gregg Moskowitz 在收购前的一份[报告](http://videos.cowen.com/detail/videos/recent/video/5789172432001/gregg-moskowitz-%7C-the-container-age:-ready-for-the-next-level---aotc-%7C-5-24-18?autoStart=true)中断言，VMware 正在继续淡化容器运动。

“对 VMware 来说，好消息是我们认为大多数组织最初都会在 vSphere 环境中部署容器。这应该使他们能够在中期内应对集装箱威胁，”他说。“然而，在我们看来，vSphere 存在一些长期风险。”

VMware 声称超过 80%的容器运行在虚拟机上，而且这个数字还在增长。对 Heptio 的收购被视为快速提升其 Kubernetes 能力的一种方式。

虽然许多组织正在将基于虚拟机的应用程序迁移到容器，但虚拟化仍然普遍存在于数据中心和公共云中，Red Hat 的 [Joe Fernandez 最近为新的堆栈写了](https://thenewstack.io/guide-for-2019-what-to-consider-about-vms-and-kubernetes/)。他指出，虚拟机的使用正在跨越 Kubernetes 堆栈的多个层演变成[。](/kubernetes-and-the-return-of-the-virtual-machines/)

在去年八月的一项[调查](https://www.cncf.io/blog/2018/08/29/cncf-survey-use-of-cloud-native-technologies-in-production-has-grown-over-200-percent/)中，云计算原生计算基金会发现 40%的拥有超过 5000 名员工的企业在生产中运行 Kubernetes。它还发现，15%的 Kubernetes 用户使用 VMware 解决方案，15%的 VMware 用户运行 Kubernetes。

云计算原生计算基金会、Pivotal 和 VMware 是新体系的赞助商。,

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>