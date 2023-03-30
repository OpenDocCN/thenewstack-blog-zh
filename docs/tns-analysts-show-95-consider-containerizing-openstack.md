# 为什么您应该考虑将 OpenStack 容器化

> 原文：<https://thenewstack.io/tns-analysts-show-95-consider-containerizing-openstack/>

OpenStack 不仅改变了开发人员与其基础设施的交互方式，还改变了他们部署和开发软件的方式。许多组织已经开始将他们的 [OpenStack](https://www.openstack.org/) 组件容器化，这揭示了诸如 [Kubernetes](http://kubernetes.io/) 等编排工具的各种用例。OpenStack 充分利用了这一点，创建了一个开源云平台，旨在将公司从通常与云开发相关的标准束缚中解放出来。

在下面嵌入的[新堆栈分析师](https://thenewstack.io/podcasts/)的第 95 集，您可以了解更多关于 GoDaddy 如何利用 OpenStack 和 [Kubernetes](/category/kubernetes/) 为其开发者带来好处，OpenStack 的 [Oslo](http://docs.openstack.org/project-team-guide/oslo.html) 如何标准化库以缓解开发 OpenStack 软件的挑战，并讨论在某些情况下 Kubernetes 并不适合所有人的事实。New Stack 创始人 [Alex Williams](https://twitter.com/alexwilliams) 和联合主持人执行主编 [Joab Jackson](https://twitter.com/Joab_Jackson) 与 GoDaddy 高级工程总监 [Shaheeda Nizar](https://www.linkedin.com/in/shaheeda-nizar-6674532) 和 GoDaddy OpenStack 技术负责人 Josh Harlow[进行了交谈。](https://github.com/harlowja)

虽然一些企业级组织可能不愿意支持开源项目，但 GoDaddy 并非如此。“两年前，GoDaddy 决定全押 OpenStack。我们在私有云上部署了 OpenStack，我们的开发人员可以在不到一分钟的时间内获得一台虚拟机。他们可以将它用于生产工作、CI/CD 或其他工作负载，”Nizar 说。

[#95:为什么应该考虑容器化 OpenStack](https://thenewstack.simplecast.com/episodes/95-why-you-should-consider-containerizing-openstack)

Nizar 提到，对于许多组织来说，自然的发展趋势是关注容器，尤其是将 OpenStack 组件容器化。她称对容器的兴趣之大“令人震惊”，并继续强调 GoDaddy 如何做出将其 OpenStack 部署容器化的决定，“这更像是最近的趋势。我们知道这将是有用的，尤其是对于降低升级成本。随着我们部署的升级，容器化 OpenStack 本身也带来了一些效率。”

哈洛指出，对于许多开发人员来说，[容器意味着简单](https://thenewstack.io/containers-microservices-and-the-multi-cloud/)。它们代表了将任务划分、分解和组织成更小的、易于部署的部分的能力，还代表了将自己抽象成不必担心整个基础设施的能力。哈洛指出，这一点在转换时显而易见。他指出，最小化开销是开发人员继续关注的问题。容器化 OpenStack 是帮助实现这一目标的一部分。

“以前解决方案的开销需要花费大量时间来过渡到较新的代码库。一个人真的要花一个月的时间，这取决于他们的知识水平，从一个版本到另一个版本或者更多。这种进入壁垒是我们需要减少的一件事，而将 OpenStack 放在容器中有助于实现这一点，”Harlow 说。

GoDaddy 正在密切关注 OpenStack API 的容器化版本，特别是将 Kubernetes 与 OpenStack 集成在一起的 [Magnum](https://wiki.openstack.org/wiki/Magnum) 和 [Zun](https://wiki.openstack.org/wiki/Zun) 。Harlow 指出，GoDaddy 希望能够在这两种工具之间“两全其美”，其他许多开发人员无疑也是如此。

Nizar 指出，最终，Kubernetes 并不适合每一种工作负载或每一种业务。对于其他人来说，Zun 和 Magnum 等工具使入职 Kubernetes 和 OpenStack 变得简单。

“Kubernetes 本身对于每个人的工作量来说可能都不是必须的。原因是，学习曲线不是微不足道的。对于简单的用例，需要一个像 Zun 这样的 API，可以使运行 Kubernetes 变得简单。”

[https://www.youtube.com/embed/lEieobGbqjw?feature=oembed](https://www.youtube.com/embed/lEieobGbqjw?feature=oembed)

视频

GoDaddy 是新堆栈的赞助商。

通过像素的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>