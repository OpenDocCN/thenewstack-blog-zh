# Docker on Diego，Cloud Foundry 的新弹性运行时

> 原文：<https://thenewstack.io/docker-on-diego-cloud-foundrys-new-elastic-runtime/>

Cloud Foundry 有一个新的弹性运行时，用 Go 编写，现在作为 Diego 的一部分支持 Docker，这是一个新的编排管理器，用于分发任务和应用程序流程。

Pivotal 的高级技术总监安德鲁·谢弗(Andrew Shafer)说，迭戈是一个应用执行、基于容器的可插拔调度器和健康检查管理器。IBM、SAP 和 Cloud Credo 也在帮助开发开源项目。这个项目对任何人开放。查看更多关于 [Github 的信息。](https://github.com/cloudfoundry-incubator/diego-release)

Diego 与 Docker 的契合展示了使 Cloud Foundry 更易访问和简化的努力。Diego 还帮助 Warden 带来了更干净的容器抽象，这是最初为[云铸造厂](http://cloudfoundry.org)开发的容器技术。

演示内容包括:

*   部署 Docker
*   在不到一分钟的时间内从 1 个实例扩展到 300 个实例
*   分布式拍卖的均衡布局
*   日志聚合
*   健康检查
*   当 20%的基础架构消失时，不良请求为零
*   重新显示丢失的实例

“你可以将一个 Docker 镜像放到 Diego 中，它会使用 Docker 库安装所有的层，”Active State 的 Phil Whelan 说。“它将在 Warden 容器中运行。迭戈不经营码头集装箱。它有一个在 Warden 容器中运行兼容图像的接口。对于最终用户来说，差别很小。你可以把一个码头工人的形象推进监狱长。迭戈被设计来运行不同的后端。”

## 更简单的管理

Diego 允许 Cloud Foundry 团队简化平台即服务(PaaS)。惠兰说，droplet 执行管理器(DEA)、健康管理器和一些云控制器现在由迭戈负责。云控制器不是 Diego 的一部分，仍然在 Cloud Foundry 中。对于开发人员来说，Cloud Foundry 将运行应用程序流程并将它们分发到 Diego，然后 Diego 管理其蜂窝网络中的任务和更长的流程。它让 Diego 更像它自己的微服务环境，当然还有很多需要开发的地方。Shafer 说，不希望或不需要 Cloud Foundry 所有功能的开发人员仍然可以使用 Diego 作为核心组件来构建他们需要的 PaaS。

“云控制器以前负责一切，必须管理整个部署的放置元数据，”谢弗在一次在线聊天中说。

用 Diego 创建 PaaS 的能力是随着 Docker 生态系统中的一个快速发展的运动而来的。例如，New Relic 以前从未使用过 PaaS。但是通过 Docker，他们构建了自己的本土服务，用于部署。诚然，用 Docker 构建 PaaS 确实需要一个支持性的生态系统，其中包括对健壮编排的需求。

Whelan 说，Cloud Foundry 与 Docker 的集成显示了新容器技术被接受的速度有多快。

> Docker 对 PaaS 的未来很重要。每个新的 PaaS 都与 Docker 有着紧密的联系。忽视 PaaS 中的码头集装箱无异于自杀。

那么云代工厂 Docker technology Warden 会怎么样呢？很简单，它将接受 Docker 图像在 Warden 中运行。

分布式架构绝不是容易构建的系统。编排所有不相连的组件以形成一个一致的服务是复杂的，在假设会发生故障的情况下更是如此。服务器可能会停机或网络变慢。从历史上看，公司会提前设计网络。但是更现代的实践使用具有短周期和反馈循环的协作方法，而不是通常与现实“脱节”的预先计划，迭戈的产品经理 Onsi Fakhouri 上周在 Whelan 在 Active State 网站上的一篇帖子中说。

Diego 开发的前几个星期花在了理解领域的范围和手头的问题上。他们为迭戈的建筑勾勒出了一个简单的愿景，法库里写道。该团队还构建了一个全面的测试套件，以验证其组件能够协同工作。编排是通过定义协调的集中式脚本进行的。

就迭戈所提供的而言，这是最相关的编排。Fakhouri 说，调度算法协调容器的去向，从而协调应用程序实例进程的运行。

Diego 解决的编排问题使它可以与 Google Kubernetes 和 Mesos 等平台相媲美。Kubernetes 和 Diego 都运行在 etcd 上，这种配置技术也是 CoreOS 用来管理其服务器部署操作系统的技术:

Mesos 只是一个通信基础设施和协议，用于支持跨分布式资源的调度。Diego 做到了这一点(不可否认更具体)以及更多:容器化、日志聚合、路由、健康管理等等。构建在 Mesos 之上的框架，比如 Marathon，更能直接与 Diego 相提并论。

梅索斯现在把多克尔当成一等公民。

至于 Kubernetes，它解决了一般协调容器的问题。相比之下，Diego 特别支持应用部署，但也在朝着类似的方向前进，“而不会牺牲其迎合 CF 的能力和使命，”Fakhouri 在采访中说。

但是为什么叫迭戈呢？

Shafer 说:“Cloud Foundry 版本 1 和版本 2 的容器运行在最初被称为 DEA 的服务中。"所以他们重写了围棋的棋谱."

明白了吗？

缉毒局变成了迭戈。

啊，那些聪明的家伙。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>