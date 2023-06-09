# 在 Kubernetes 迁移过程中关注可靠性

> 原文：<https://thenewstack.io/looking-around-reliability-corners-during-a-kubernetes-migration/>

[云计算原生计算基金会](http://cncf.io/)和 [Gremlin](https://www.gremlin.com/) 赞助了这篇文章，期待虚拟 [KubeCon + CloudNativeCon 北美 2020–虚拟](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)，11 月 17-20 日。

 [泰勒·史密斯

泰勒是 Gremlin 的技术产品营销经理，帮助客户开发更可靠的系统。他对现代应用和基础设施充满热情。此前，他为思科和 NetApp 制定了有机和无机战略。](https://www.linkedin.com/in/taylorbsmith/) 

Kubernetes 对开发人员的生产力和我们应用程序的可伸缩性有很大的好处。容器化应用为我们提供了适合微服务应用的可扩展架构，容器的数量迅速增长，编排变得无法控制。Kubernetes 是 Google 对容器被部署、操作和维护的组合爆炸的开源响应。它简化了许多操作任务，抽象出了各个容器的编排细节。结果，集装箱化环境的采用率飙升至 45%。

然而，就像科技领域的所有事情一样，细节决定成败。Kubernetes 是一个非常强大的工具，具有足够的可调性，可以很好地处理大多数工作负载，但也足够复杂，难以正确处理，并且会以不可预测的方式中断。在单块只有一个代码库需要单步执行的地方，微服务增加了难以调试的复杂的相互关系。再加上新的、独特的问题，如处理延迟、依赖性故障、服务快速扩展和扩展以及 pod 故障，需要测试和修复的内容很多。对于 Kubernetes 的新公司来说，这可能令人望而生畏；对于拥有多年经验的公司来说，复杂性只会继续增加。

在 Gremlin，我们与处于云原生采用早期的公司合作，一直到那些处于前沿的公司，在这些公司中，普通配置和核心组件不再适用。对于那些刚刚踏上旅程的人来说，一种树立正确部署 Kubernetes 的信心的方法可以大大加快迁移和开发过程。

当安德玛的工程师应用混沌工程时，他们迁移到 Kubernetes 的速度提高了四倍。与此同时，多年来，Workiva 的编排需求超过了 Kubernetes 的本地能力，因此该公司手工推出了自己的功能。当 Kubernetes 赶上时，他们将其系统换成 Kubernetes，以便获得 Kubernetes 路线图的好处，然后在转换之前，应用混沌工程来确认新平台与以前的 orchestrator 一样可靠。

## 消除对失败的恐惧

混沌工程是一种有系统的实践，以可控的方式给系统增加少量的伤害，以学习和改进系统处理故障的方式。通过将少量的失败注入到系统中，我们的团队可以确信他们的可靠性机制将从失败中恢复，并且他们的操作手册将工作。这确保了当不可避免的失败在现实世界中发生时，客户永远不会知道。

Kubernetes 带来新范式；以前我们必须将系统作为一个整体纵向扩展或横向扩展，现在我们可以独立地横向扩展单个服务。更简单的是，有管理 Kubernetes 的工具——如云提供商的托管产品或 OpenShift。然而，即使在这些托管环境中，您也不能将应用程序提升和转移到 Kubernetes 中。它们必须被重新架构成无状态的和可伸缩的。您正在构建一个复杂的分布式系统，有些事情您必须进行测试，否则您将遭受中断。

借助流程编排，我们获得了更高的资源利用率——只扩展所需的资源——这意味着节省了资金。然而，应用程序的设计必须能够处理 pod 的短暂特性，包括需求的高峰和低谷。单线程、单路径服务无法扩展，也无法处理相关服务的中断。如果一项服务收到过量的需求，请确保该服务不会过于庞大且启动缓慢，从而降低向外扩展的能力。一旦重写，不要把它留给意外收获或假设 Kubernetes 管理掉对深思熟虑的架构的需求。为了确保应用程序能够处理缩放，添加自动缩放时产生的资源约束，并观察我们的系统如何运行。通过增加单个 pod 中的资源消耗，确保共享同一主机的 pod 不受嘈杂邻居的影响。

容器化我们的应用程序可能增加的另一件事是以前没有的网络。微服务架构开放了多语言编程——根据开发或性能的难易程度为每种服务选择最佳语言，但警告是现在这些服务必须通过网络相互交流。这意味着我们的系统需要准备好应对以前没有发现的网络问题，比如延迟和数据包丢失。测试我们的服务是否为延迟和丢包做好了准备的最佳方法是什么？尽早并经常使用注入延迟和丢包来测试它们。

## 超越我们的盲点

将开发人员暴露于他们代码中的真实失败会改变他们编写代码的方式。他们能够从一个新的角度来审视自己，如果他们的服务面临资源限制，或者如果大厅里的团队出现故障，会发生什么。独立开发服务意味着服务必须真正解耦；换句话说，一个服务启动不应该要求其他服务启动。否则，我们将失去转换到容器化、协调的环境的好处。将失败添加到开发人员的应用程序中，作为游戏日的一部分，或者作为开发管道中的一个步骤，有助于他们建立处理失败的直觉，并建立弹性机制。

同样，我们的运营团队也将从中受益。随着我们迁移到 Kubernetes，我们的运营团队将会不熟悉如何在这个新环境中解决问题。不要等待影响客户的问题来培训我们的团队。阻止关键服务的流量，并训练我们的团队建立肌肉记忆，以快速找到并修复问题。确保警报和仪表板是可操作的，然后重新测试以观察改进。如果我们的团队花了太长时间才发现问题，那么是时候重新审视我们的监控指标选择了。一旦开发人员和运营团队磨练了他们的适应性和反应时间，我们就可以拔掉旧系统的插头，满怀信心地启动新的微服务系统。

## 下一关

我们已经看到我们的许多客户经历了 Kubernetes 的采用过程。一旦他们达到一定的规模，他们就需要根据他们的应用和使用模式定制 Kubernetes。调整设置和添加或替换组件增加了管理和测试由 Kubernetes 编排的应用程序的难度，但是对于达到某些组织的规模和性能要求是必要的。更重要的是，这些组织要进行失败测试。当他们试图通过添加新的功能和性能来使他们的产品与众不同时，如果客户不能访问他们的应用程序，这些优势就失去了。

这些客户在对 Kubernetes 进行更改时应用了混沌工程，确保他们在调整架构时不会失去通过调整传统设置获得的可靠性。例如，当 pods 与新的负载平衡器发生故障时，或者当添加了由服务网格运行的代理时，应用程序可能会做出完全不同的反应。知道的唯一方法是实际关闭 pod 并观察系统反应，调整新组件，然后确认修复。

## 满怀信心地向前迈进

如果做得好，整个企业都能感受到 Kubernetes 的好处。公司正在达到前所未有的应用规模，功能速度超过了旧模型。有了混沌工程，这些缩放应用的可靠性就能跟上；事实上，在设置新环境的同时执行这一测试将会加快这一过程，因为将会减少对要调优的拨号盘的猜测，并留出更多的时间来构建客户需要的产品。

*要了解更多关于 Kubernetes 和其他云原生技术的信息，请考虑参加于 11 月 17 日至 20 日在举行的 [KubeCon + CloudNativeCon 北美 2020 大会。](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/)*

云计算原生计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>