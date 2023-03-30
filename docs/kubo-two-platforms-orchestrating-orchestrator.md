# 久保和两个平台:指挥管弦乐队

> 原文：<https://thenewstack.io/kubo-two-platforms-orchestrating-orchestrator/>

对于 Kubernetes，高可用性的本地策略是设置多个主副本，并设计一个故障转移系统，在主主机出现故障时将控制权转移给副本。当主服务器出现故障时，没有任何东西可以调度工作负载。但是简单的问题——在这里和其他地方——是它让事情变得太复杂了。

有多种方法可以解决这个问题，并提供这些方法的设计者委婉地描述的真正的高可用性(也许我们应该称之为“RHA ”?).有些涉及整个 Kubernetes 环境的一种复制。 [Kubo](https://pivotal.io/partners/kubo) 是 Cloud Foundry 对这个新兴替代群体的贡献。这是一种利用 Cloud Foundry 已经用于负载平衡虚拟机的功能的方式，用于有效地平衡虚拟机内多个并发 Kubernetes 实例的流量。

Pivotal 首席软件工程师 [Konstantin Semenov](https://www.linkedin.com/in/kvsemenov/?ppe=1) 在与 TNS 创始人 Alex Williams 为 [The New Stack Makers](/tag/the-new-stack-makers/) 播客的讨论中承认，“我们用不同的方法遇到了一些问题，但我们让它运行起来了。”

要使负载平衡在高可用性场景中安全地工作，“首先，您必须拥有安全的通信。这意味着你必须安装证书，”谢苗诺夫解释说。“可以说，这些证书应该宣传同一个实体。因此，您必须在所有故障和重启之间进行协调。”

这是为什么不能同时拥有一大堆 Kubernetes 主控器的合理解释:被编排的容器需要看到单个主控器，即使工作正在多个主控器之间积极地分发。

Semenov 与谷歌云平台倡导者 [Casey West](https://twitter.com/caseywest) 和谷歌软件工程师 [Meaghan Kjelland](https://twitter.com/meaghnk) 一起，广泛讨论了 Kubo、 [Cloud Foundry](https://www.cloudfoundry.org/) 和 [Kubernetes](/category/kubernetes/) 在高可用性环境中扮演的角色。现在请收听“Kubo 为 Cloud Foundry 和 Kubernetes 带来了什么”，这是在加利福尼亚州圣克拉拉举行的 2017 年 Cloud Foundry 峰会上录制的一集播客。

[Kubo 给云代工厂和 Kubernetes 带来了什么](https://thenewstack.simplecast.com/episodes/what-kubo-brings-to-cloud-foundry-and-kubernetes)

### 在这个版本中:

[1:39:](https://thenewstack.simplecast.com/episodes/what-kubo-brings-to-cloud-foundry-and-kubernetes?t=1:39) 什么是久保？
[7:38:](https://thenewstack.simplecast.com/episodes/what-kubo-brings-to-cloud-foundry-and-kubernetes?t=7:38) 探索为什么开发 Kubo，以及它在与 Kubernetes 合作时所解决的问题。
[14:38:](https://thenewstack.simplecast.com/episodes/what-kubo-brings-to-cloud-foundry-and-kubernetes?t=14:38)Kubo 和 Kubernetes 如何将开发者从中间件锁定中解放出来。
[17:27:](https://thenewstack.simplecast.com/episodes/what-kubo-brings-to-cloud-foundry-and-kubernetes?t=17:27) 久保的云部署。
[23:37:](https://thenewstack.simplecast.com/episodes/what-kubo-brings-to-cloud-foundry-and-kubernetes?t=23:37) 开放服务代理 API 创新及其现状。
[27:43:](https://thenewstack.simplecast.com/episodes/what-kubo-brings-to-cloud-foundry-and-kubernetes?t=27:43) 久保背后的技术架构。

[https://www.youtube.com/embed/12JfRZmKqx4?feature=oembed](https://www.youtube.com/embed/12JfRZmKqx4?feature=oembed)

视频

云铸造基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>