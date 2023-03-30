# KEDA 为 Kubernetes 带来事件驱动的自动缩放

> 原文：<https://thenewstack.io/keda-brings-event-driven-autoscaling-to-kubernetes/>

自从去年五月在[红帽峰会](https://www.redhat.com/en/summit/2019)上[首次亮相以来](https://thenewstack.io/red-hat-microsoft-team-to-offer-event-driven-openshift-on-azure/) [Kubernetes 事件驱动自动缩放(KEDA)](https://keda.sh/) 开源项目已经取得了很大的进展，当时联合创始人微软和红帽首次开源了该项目。去年 11 月，它在 KubeCon+CloudNativeCon 北美看到了 KEDA 1.0 的[发布，现在 KEDA 正在向](https://cloudblogs.microsoft.com/opensource/2019/11/19/keda-1-0-release-kubernetes-based-event-driven-autoscaling/)[云本地计算基金会(CNCF)](https://www.cncf.io/) 捐款的第一步，已经在 1 月份提议[加入作为沙盒级项目。](https://github.com/cncf/toc/issues/335)

KEDA 撰稿人杰夫·霍兰(Jeff Hollan)也是微软无服务器 Azure Functions 的主要项目经理，他称这次发布是一个“为生产做好准备的里程碑”，他说这导致了令人兴奋的几个月的增长和采用，有几个因素可以证明这一点。

“在我们推出 1.0 之前，我们已经做出了一些很好的贡献，但从那以后，就只有一些不同的客户和合作伙伴了。我们的社区电话不断接到十几个人的来电，他们在使用 KEDA，询问关于 KEDA 的问题，还有，让我真正兴奋的是，为 KEDA 做贡献。我们每周都会收到很多添加创新功能的请求，这真的很令人兴奋，”Hollan 告诉 New Stack。“从许多方面来看，这种趋势似乎正在加速。我们真的很期待 CNCF 的捐赠，以保持这一势头。”

KEDA 为 Kubernetes 的标准方法提供了一种替代方法，即查看容器的 CPU 负载和内存消耗等指标。从 KEDA 的角度来看，这种方法是被动的，而不是主动的。KEDA 试图通过根据 Kafka、Azure Service Bus 或 RabbitMQ 等事件源中的消息队列大小等指标来提升主动性，这与无服务器平台非常相似。

Hollan 说，自从达到 1.0 以来，KEDA 已经看到可用事件源的数量增加到近 20 个，其中许多是由社区贡献的，并且继续以每月两到三个的速度增长。社区成员贡献的另一个特性是围绕着缩小而不是扩大。

“Kubernetes 的人们普遍面临着共同的问题，这不一定是 KEDA 独有的问题，但我们在开发的前几个月听到的一个大问题是，KEDA 在 Kubernetes 中为我提供了这种非常快速的无服务器扩展，但有时当你超快速扩展时会有负面影响，然后你可能会很快恢复。如果我不想让你这么快就把它关掉呢？”霍兰说。“如果我正在做一些事情，比如对一些可能需要几个小时才能完成的音频进行转码，该怎么办？”

他说，这项新功能是由社区发起的，使用一种叫做“Kubernetes 作业”的东西来识别在完成之前不应缩减的工作量。从本质上讲，KEDA 只关注领先指标，一旦领先指标消失，它就会开始缩小规模。现在，该功能可以被关闭或打开。Hollan 说，该项目着眼于未来发展的一个特点是，通过使用预测技术，比事件源更早地寻找规模指标。

“如果每周五下午 5 点，考勤卡系统会丢弃一堆需要处理的考勤卡，该怎么办？今天，KEDA，一旦这些时间卡开始进来，它将先发制人地开始扩大 Kubernetes。但如果在此之前，你已经有一些机器学习或人工智能在里面运行，那会怎么样，也许我们可以主动扩展，”霍兰说。“这是一种可能性，我们已经与一些团队合作，开始探索这可能会是什么样子，以及如何才能成为现实。”

至于对 CNCF 的捐赠，Hollan 说这是从去年 10 月就开始讨论的事情，尽管从项目开始就一直在考虑，他认为这是对社区的承诺。

霍兰说:“微软和红帽向 CNCF 捐赠，每个人都在说，我们没有这个代码的所有权，我们没有商标，我们没有这个项目的方向。”。“这是我们真正希望社区帮助领导和推动的事情，这是对社区的信任投票，但我们也认为这是编写这种类型软件的最佳方式。”

目前，KEDA 计划在 2 月 20 日的会议上向[运行时特别利益小组(SIG)](https://github.com/cncf/sig-runtime) 提交，然后希望提交给[技术监督委员会(TOC)](https://github.com/cncf/toc) 进行投票。CNCF 沙盒级别的验收过程是一个新的过程。Hollan 解释说，以前，一个项目只需直接提交给 TOC，然后需要两票通过，现在项目需要提交给 SIG，然后才能被 TOC 考虑。

展望未来，Hollan 表示，KEDA 希望与 CNCF 的许多项目密切合作，包括[虚拟 Kubelet](https://virtual-kubelet.io/) 和[服务网格接口(SMI)](https://smi-spec.io/) ，他说这些项目也正在捐赠给 CNCF 和 Kubernetes 本身。Hollan 建议，也许有一些扩展模式，今天你需要安装 KEDA 来处理，这可以成为 Kubernetes 核心项目的一部分。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>