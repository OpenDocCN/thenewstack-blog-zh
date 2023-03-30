# Kubernetes 安装程序的涌入引发了关于一致性的问题

> 原文：<https://thenewstack.io/kubernetes-installer-explosion-natural-enthusiasm/>

[](http://robhirschfeld.com/digital-rebar/)

 [罗布·希施菲尔德

罗布·希施菲尔德是 RackN 的首席执行官兼联合创始人，该公司为以容器为中心的数据中心提供编排软件。他已经在云计算和基础设施领域工作了近 15 年，从早期的 ESX 测试版开始工作，到在 OpenStack Foundation 董事会任职四届。](http://robhirschfeld.com/digital-rebar/) [](http://robhirschfeld.com/digital-rebar/)

对于上个月的 KubeCon Europe，行业观察家 [Joseph Jacks](https://twitter.com/asynchio) 整理了一份超过 60 家 Kubernetes 安装商和服务商的名单。令人高兴的是，这种丰富的变化使其本身被称为会议，启动了一致性工作，以确保用户获得一致的体验。我坚信清晰的一致性可以构建生态系统，并且从我的 [OpenStack DefCore](https://robhirschfeld.com/tag/defcore/) 工作中获得了丰富的经验。

**简而言之，一致性不是厂商的问题:这是用户体验和生态系统的问题。**

我们需要确保应用程序可以跨安装和 Kubernetes 版本移植。

为了帮助解释我的立场，我整理了一个简短的问答:

**这是怎么回事？**

大量以运营为中心的工具已经成为现实，因为坦率地说，很难在同一个工具中既有简单的第一天开始，又有长期的第二天和异构支持。用例二分法意味着我们将需要多种工具。

像 [kubeadm](https://github.com/holandes22/kube-admin) 这样的官方安装人员呢？

我认为 kubeadm 可以以一种可以共享的方式帮助整合 K8s 配置，我对此表示赞同；然而，我认为真正的问题是帮助 K8s 适应更广泛的操作环境。为此，像 Ansible 这样的工具非常受欢迎，因此可以解决实际问题。这不是一个非此即彼的问题——生产部署将拥有这两层工具。

**有没有使用比较标准的 Ops 工具的工具？**

Kargo 是部署最佳实践的一个非常好的实现，具有可行的高可用性和升级模型。我们的开放式混合自动化项目 Digital Rebar 在许多配置中不加修改地驱动它，以便我们从社区中受益，并可以将改进反馈给上游。我们也可以驾驶 kubeadm、 [Kops](https://github.com/kubernetes/kops) 或者其他的，但是感觉 Kargo 是目前最便携和最完整的。

**这些安装工作应该在项目治理之内还是之外？**

关于项目内外，这是有细微差别的。我宁愿没有；然而，拥有像 Kargo 这样的“in”会传递一个“在此合作”的信息，这可能是有帮助的。挑战在于让供应商放弃他们自己的努力，加入社区版本。这只有在安装脚本对于许多环境都是灵活的情况下才能起作用。

> 我们看到 Kubernetes 社区的发展速度比任何一家供应商都要快。

最终，这意味着安装程序脚本没有区别。对于寻求优势的供应商来说，这可能是一个艰难的处境。我们看到 Kubernetes 社区的发展速度比任何一家供应商都要快。

**Kubernetes 在数据中心中的角色是什么？会成为数据中心操作系统吗？**

我认为 Kubernetes 是数据中心运营环境的一部分，而不是唯一的东西。

在我的公司 [RackN](http://rackn.com) ，我们使用数字钢筋构建底层，然后在上面覆盖 [Helm](https://github.com/kubernetes/helm) package manager、 [Deis](http://deis.io/) 工作流软件或其他工具。我认为社区应该对 1)有“整体的一部分”的心态和 2)鼓励工具方法的共享/重用的努力施加压力。这两个想法是为 Kubernetes 建立良好的站点可靠性工程操作的基石。

你怎么想呢?我很想听听你的立场。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>