# NGINX 承诺开源和 Kubernetes Ingress

> 原文：<https://thenewstack.io/nginx-commits-to-open-source-kubernetes-ingress-involvement/>

在今年的 [NGINX Sprint 2.0](https://www.nginx.com/nginx-sprint-registration/) 虚拟会议上， [NGINX](https://www.nginx.com?utm_content=inline-mention) ，流行的开源 web 服务器/负载均衡器和同名反向代理[背后的](https://www.nginx.com/resources/glossary/nginx/) [F5](https://www.f5.com/) 的分支[就其关于开源软件、未定义的即将到来的开源版本以及参与](https://www.nginx.com/blog/nginx-sprint-2-0-clear-vision-fresh-code-new-commitments-to-open-source/) [Kubernetes Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/) 项目的意图发表了[几份声明](https://www.nginx.com/blog/nginx-sprint-2-0-clear-vision-fresh-code-new-commitments-to-open-source/)。

第一点，NGINX 对开源的承诺，部分是为了抵御[NGINX 2019 年被 F5](https://thenewstack.io/f5-to-buy-nginx-to-enhance-cloud-native-and-multicloud-capabilities/) 收购后任何感知或担心的变化。在一篇[博客文章](https://www.nginx.com/blog/nginx-sprint-2-0-clear-vision-fresh-code-new-commitments-to-open-source/)和他在 Sprint 2.0 的主题演讲中，[F5 NGINX 产品组总经理 Rob Whiteley](https://www.linkedin.com/in/rwhiteley/) 讨论了该公司希望如何清晰地定义其开源软件前进的方法，以及在未来几个月进一步致力于开源参与。

“当 F5 收购 NGINX 时，我认为人们担心我们会放弃我们的开源根基，我们在开源领域做的任何事情都只是为了收益。作为 F5 的一部分，我们的体验正好相反。Whiteley 在接受采访时表示:“F5 拥有额外的资源和能力，这是我们作为一个独立的 NGINX 所无法承受的。“F5 了解到，与大多数现代大型企业一样，如果您没有开源战略，您将无法在现代应用环境中保持相关性。我想向大家保证的是，我们没有秘密议程。这并不是要为商用 F5 或 NGINX 软件植入特洛伊木马。坦率地说，这是我们在应用领域保持相关性，并确保现在我们有能力进行更多投资，我们会这样做。”

关于 NGINX 的开源软件向前发展，Whiteley 说，该公司的高管已经承诺了一种模式，在这种模式下，开源将用于生产，而不是更少。Whiteley 甚至说，如果他们能够回到过去，某些目前只在 NGINX Plus 中可用的功能将在开源版本中可用。

“一种模式是‘开源’等于‘测试/开发’，‘商业’等于‘生产’，所以当你进入生产阶段时，你就遇到了使用权的问题，然后你就必须开始许可这项技术。我们不想走那条路，因为它不利于开发人员将应用程序投入生产，”Whiteley 说。“我们想要做的是，随着应用程序的扩展——它提供更多的流量，产生更多的收入，无论它作为应用程序的目标是什么——投资要与成功和增长保持同步。”

这第一点，NGINX 对开源的承诺，在一定程度上作为上述最后一点的背景，NGINX 表示将向 Kubernetes 社区投入额外的资源，这一举动部分是由以下事实驱动的: [ingress-nginx 项目](https://github.com/kubernetes/ingress-nginx)的创始人[亚历杭德罗·德·布里托·丰泰](https://github.com/aledbf)，已经决定退出。这些资源将以全职员工的形式提供，以帮助管理社区入口项目，还有几名员工致力于 [Kubernetes 网关 API 特别兴趣小组(SIG](https://gateway-api.sigs.k8s.io/) )的工作，以帮助推进 Kubernetes 入口和出口功能。

作为进一步的背景，Whiteley 解释说，大约五年前，NGINX 开源被改编为默认 Kubernetes 部署的正式包含的入口控制器。这种改编需要在标准开源 NGINX 的基础上增加许多额外的功能，NGINX 是使用 Lua 模块构建的。随后，NGINX 看到了客户对一种不需要 Lua 的 NGINX 形式的兴趣，因此他们构建了另一种开源 NGINX 入口控制器。最后，他们发布了一个额外的商业版本，具有基于 NGINX Plus 的功能。怀特利说，所有这些都导致了用户的困惑，他们投入资源的部分原因是希望消除这种困惑。

“我们认为这是一个向该项目捐款的机会，首先，也是最重要的，以确保我们继续管理该项目，继续确保它活着，并接受捐款，”他说。“我们想做的是与社区合作，看看是否有机会改进 Kubernetes Ingress，重写一些 Lua 模块，也许可以移植它们。我们希望通过努力开始重写和合并，这样我们就不会有两个开源入口控制器在做同样的事情。现在，我们必须小心，因为我们不想出现在社区中，感觉我们在强行进入并创建任何形式的议程。”

虽然任何入口控制器的整合都有待更大社区的决定，但 Whiteley 表示，他们也希望将他们的专业知识带到其他领域，例如参与 [SIG 网络](https://github.com/kubernetes/community/tree/master/sig-network)，在那里他们将致力于[网关 API](https://gateway-api.sigs.k8s.io/) 。Whiteley 解释说，网关 API“本质上是一个新项目，旨在研究我们如何发展入口控制器，使其能够同时处理入口和出口。”他进一步解释说，nginx 已经使用自定义资源定义(CRD)来扩展其开源入口控制器，而不是默认入口 NGINX 使用的注释，并且网关 API 团队对使用这种方法感兴趣。

“[他们]很早就找到我们说，‘嘿，我们喜欢你用 CRDs 做的事情；Whiteley 说:“我们想创造一种具有内在可扩展性的下一代网关设备，所以我们一直在就这个项目进行咨询。”。“当网关 API 的一个版本在 NGINX 上发布时，我们将提供本地支持。我们的希望是消除我们在 Ingress 中制造的混乱，即有一个社区版本和一个 NGINX 支持的单独版本。我们将从第一天开始确保我们是支持该标准的几家供应商之一，并且它将只是它的一个开源版本，因此我们可以消除一些混乱。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>