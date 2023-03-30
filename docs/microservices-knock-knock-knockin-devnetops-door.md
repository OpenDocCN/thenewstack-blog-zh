# DevNetOps:微服务如何为网络管理带来 DevOps 速度

> 原文：<https://thenewstack.io/microservices-knock-knock-knockin-devnetops-door/>

[](http://jameskelly.net/work/)

 [詹姆斯·凯利

James 是 Juniper Networks 市场部的首席云计算和软件定义网络架构师。此前，他在加拿大渥太华创办了一家资本管理公司，并担任私人瑜伽教练。](http://jameskelly.net/work/) [](http://jameskelly.net/work/)

想象在两个技术轴上进行:时间和空间。如果相对于时间线或管道，自动化更快、更小的步骤显然更健康，那么考虑空间或架构。当优化架构设计和编排来招募敏捷的管道输出时，在今天的角色阵容中，什么是突出的？[微服务](/category/microservices/)。

[DevOps](/category/devops/) 的原则已经存在了一段时间，并在十多年的实践中不断涌现，但彻底破解 DevOps 的关键技术是容器和微服务编排系统，如 [Kubernetes](https://thenewstack.io/ebooks/kubernetes/state-of-kubernetes-ecosystem/) 。回过头来看，更小的边界和来自开发人员的强制打包，通过持续集成和交付管道保留下来，使得部署更加可靠，这并不令人惊讶。

微服务架构并非万无一失，但对于频繁或持续部署的速度和敏捷性而言，它是当今的最佳合作伙伴。

这些趋势对网络空间意味着什么？

## 微服务网络和作为微服务的网络

在服务网格与软件定义的网络的技术试验中，网络在当今的微服务领域占据三个关键位置:

1.  在微服务设计中，各个部分变得更小，而细胞间空间(网络)变得更大、更繁忙，因此变得至关重要。此外，除了微服务本身的零信任式保护，锁定这个网络也很重要。
2.  服务发现、服务/API 网关、使用 DNS 的服务广告以及使用负载平衡的服务向外扩展或向内扩展都是网络领域的参与者。
3.  除了微服务，通过 API、卷或磁盘进行的任何状态复制、备份或分析也依赖于网络。

鉴于网络对微服务成功的重要性，具有讽刺意味的是，网络组件大多是单片的。更糟糕的是，部署焦虑是一种流行病:网络运营商有冗长的变更控制，不频繁的维护窗口，新代码版本被保留 6-18 个月以供询问，并在可用后进行多次修订。

## DevNetOps 的小步骤

如今，借助 [Spinnaker](https://www.spinnaker.io/) 风格的操作阶段编排，开始进入“DevNetOps”是可能的:网络即代码模型和存储库将为所有配置、模板、代码和软件映像工件提供 CI/CD 管道。通过对网络团队进行新的流程和技能培训——如编码和审核物流以及测试和进行模拟——我们可以挫败小规模的 CLI-push-to-production 游戏，并修复严重自动化混乱的“主脑”,这些主脑可能会犯下更大的错误。

技术时间轴上的修正和信心之路始于将 ops 时间线自动化为一个包含微小修改步骤的流水线。

在厂商和开源工具的帮助下，用户社区可以重新发明旧的 ops 实践，但是当涉及到架构时，厂商需要领先。供应商是 DevNetOps 力量中的主要“开发”伙伴，并且比以往任何时候都更有动机来构建追求微服务的案例。

## DevNetOps 的小件产品:微服务

多年来，网络设备越来越大，越来越差——产生了一些庞大到无法通过门的单片比例——供应商不能忽视云、容器和微服务的闪光灯和警报器。

很明显，对 DevNetOps 来说，就像对 DevOps 一样，微型工件是敏捷管道中完美的子弹。但是，尽管有证据表明网络行业取得了进步，但还有很长的路要走。

一些好的解决方案包括 Arista [支持](https://www.arista.com/en/products/eos/resiliency)补丁包，独立于其[可扩展操作系统](https://www.arista.com/en/products/eos) (EOS)交付；[开放计算项目](http://www.opencompute.org/)在其[网络项目](http://www.opencompute.org/projects/networking/)中推广软硬件分解；Juniper Networks [通过支持节点拼接和通用机箱实现更细粒度的模块化和管理边界，在分解的基础上构建](https://www.juniper.net/us/en/dm/cloud-grade-networking/)。此外，具有披萨盒大小设备的弹性横向扩展 [Clos 网络结构](https://www.networkworld.com/article/2226122/cisco-subnet/clos-networks--what-s-old-is-new-again.html)的数据中心网络设计逐渐受到大型聚合设备的青睐。在软件定义的网络中，像 OpenContrail 这样的项目现在被作为容器分发。

在 DevOps 的世界里，我们知道没有什么能像开发人员在凌晨 2 点面对页面的前景那样对部署质量产生奇迹。但对于 DevNetOps 来说，诗意的公正正在消失，供应商-客户墙之间的 24/7 支持很难消除运营商在提交部署变更时的焦虑。此外，有缺陷的供应商代码更改和被发现之间的时间越长，就会变得越混乱，也越难被发现。

应对这些挑战的最佳防线是更小、更频繁的供应商交付、用户测试和部署。从微服务如何支持 DevOps 的成功中汲取灵感，想象一下，如果我们今天向 DevNetOps 持续和敏捷的运营致敬，我们迫使供应商和架构专员支持更细粒度的幸福微服务、设备和网络的设计，以实现更幸运的明天。

来自 Pxhere 的特征图像[，许可证](https://pxhere.com/en/photo/779821) [cc0](https://creativecommons.org/publicdomain/zero/1.0/) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>