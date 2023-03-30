# 问与答:Kubernetes 社区中存储了什么数据

> 原文：<https://thenewstack.io/qa-whats-in-store-for-the-data-on-kubernetes-community/>

[](https://www.linkedin.com/in/bart-farrell/)

 [巴特法雷尔

巴特是 CNCF 大使，是 Kubernetes 社区的数据发动者。在过去的六年里，他一直在组织和领导技术社区，现在他很高兴地让 DoKC 成为所有人的欢迎之家。](https://www.linkedin.com/in/bart-farrell/) [](https://www.linkedin.com/in/bart-farrell/)

去年，MayaData 帮助创建了 Kubernetes Community (DoKC)上的独立[数据，为从业者提供了一个无营销区，以比较他们在 Kubernetes 上运行数据的方法。2020 年 7 月的第一次 meetup 是对 Datastax 开发者关系副总裁 Patrick McFadin 的采访，DoKC 社区现在有 500 多名成员，每周至少举办两次 meetup 讨论，已经扩展到多种语言，最近成为了一个官方的 CNCF 社区。它由 CNCF 大使兼社区经理 Bart Farrell 领导。](https://dok.community/)

现在，将近一年后，任何关于 K8s 已经准备好接受数据的怀疑都将在 5 月 3 日 CEST 时间上午 10 点(美国东部时间上午 4 点/太平洋时间上午 1 点)在一场名为[Kubernetes Day](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/program/colocated-events/#data-on-kubernetes-day)的特别活动中平息，该活动是即将举行的[kube con+CloudNativeCon Europe](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)会议的一部分。亮点包括:

*   超过 10 场讲座，涉及的主题包括可观察性([费曼周](https://www.linkedin.com/in/feynman-zhou-569461178/?originalSubdomain=cn)-库比斯菲尔)、操作者([谢尔盖普罗宁](https://twitter.com/sergeypronin?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)-珀科纳)和持久数据存储([埃里克兹特洛](https://www.linkedin.com/in/ericzietlow/)-马亚达塔)。
*   包括 Flipkart 和 Digital Ocean 在内的 Kubernetes 大型用户对数据的坦诚讨论。
*   社区正在开发和发布的免费培训介绍。
*   由来自 MayaData 和 Datastax 的工程师主持的免费实践研讨会，与会者将学习在 Kubernetes 上快速部署和高效操作公共数据库。

**请[在 KubeCon 2021](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/program/colocated-events/#data-on-kubernetes-day) 上登记 Kubernetes 日的数据。**

我们借此机会询问了 MayaData 的首席执行官和联合创始人 [Evan Powell](https://www.linkedin.com/in/epowell/) ，为什么 [MayaData](https://mayadata.io/?utm_content=inline-mention) 帮助创建了 DoKC，以及 DoKC 的未来(以及更广泛地说，Kubernetes 的数据使用)。

 [埃文·鲍威尔

埃文·鲍威尔是 MayaData 的首席执行官。](https://www.linkedin.com/in/epowell/) 

你认为 DoKC 的使命是什么？

鲍威尔:民主党可以自由地规划自己的道路。也就是说，它已经发布的使命声明和现在正在讨论的原则声明都表明，核心使命是为讨论在 Kubernetes 上运行数据的方法提供一个安全和友好的环境。

**Maya data[和 DoKC](https://mayadata.io/) 是什么关系？**

鲍威尔:在开源领域工作的一大好处是，帮助发展公共资源通常是一件好事。虽然我们创立了 DoKC 并帮助培育它，例如支付它的所有账单，但我们并不控制它。也许最重要的是，虽然许多早期的演讲者自然是 OpenEBS 的用户(如 Arista、Optoro 和其他人)，但从那时起，DoKC 的领导者 Bart Farrell 已经能够通过口口相传建立一个令人难以置信的演讲者名单。通过将 DoKC 贡献给 CNCF，我们更加明确了这种独立治理。

你认为 DoKC 的前景如何？

鲍威尔:也许现在比以往任何时候，那些处于 Kubernetes 和其他技术使用前沿的人的方法都远远领先于大多数人的方法和需求。DoKC 在这些创新者和我们其他人之间提供了一座重要的桥梁。因此，当 Flipkart 谈论如何通过一种创新、高度自动化和高效的方法来为 Flipkart 内数千名高度专注和积极的开发人员和其他工程师动态提供基础设施和服务，从而在一定程度上抵御亚马逊时，我们都可以找到可以采用的模式，以及应该避免的教训。他们是如何在几分钟内从物理部署(即启动并连接系统的机架)转移到工作负载，并在 Kubernetes 和[风格的 OpenEBS](https://openebs.io/) 及其他软件的帮助下获得存储的？这种“零接触”自动化如何让我们更好地利用我们的服务器或云卷，同时避免锁定，更重要的是，为开发人员和数据科学家消除障碍？

今天可能的结果可以提高数据驱动型企业的竞争力。Kubernetes 社区上的数据有可能成为收集、管理和帮助结合技术、工艺和工程师来实现这些成果的地方。我心中永远的理想主义者真的希望它能一直是一个地方，让我们大家一起寻找真理，建设未来。

坚持这些理想需要一个拥有独立治理的强大社区。这关系到大量的资金，每一个与数据有关的 IT 专有供应商都声称要为运行在 Kubernetes 和云上的数据增加价值。我希望 DoKC 可以在抵制拥有大量营销预算和传统技术的供应商的云清洗中发挥核心作用。

**还有其他想法吗？**

鲍威尔:请保持高期望值。是的，在 Kubernetes 上运行数据存在挑战。然而，也有可能通过使用 Kubernetes 本身作为数据的基础来消除“共享一切”的上一代技术的巨大爆炸半径和管理挑战。不要寻求对等——要求优势。Kubernetes 社区上的数据可以为我们所有人找到更好的前进道路。加入我们，尽你所能地参与进来。

*要了解有关 Kubernetes 和存储的所有使用案例、解决方案指南、案例研究、白皮书、网络研讨会和研讨会的更多信息，请关注 [MayaData 博客](https://blog.mayadata.io/)。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>