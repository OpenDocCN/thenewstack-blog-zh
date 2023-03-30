# 牧场主里奥:照顾开发者的前半天

> 原文：<https://thenewstack.io/rancher-rio-taking-care-of-the-first-half-of-the-developers-day/>

Rancher Labs 已经公布了一个名为 [Rio](https://github.com/rancher/rio) 的项目，它称之为“微型 PAAS ”,开发者可以使用它来轻松地在 Kubernetes 的应用程序中部署样板服务。

它处理应用程序中通常需要的所有东西。

“它就像一个积木，一个脚手架，”T4 牧场主实验室的现场工程师[威廉·希门尼斯](https://github.com/wjimenez5271)说。

它将帮助您设置 Istio，以实现服务网格或微服务之间的安全和通信。它将帮助设置信息如何进入您的应用程序的路由，为您提供 canary 部署、A/B 部署、监控服务网格内部的 HTTP 流量等等。

Jimenez 说:“所有这些表格都是每个人都要重新发明的应用程序开发的一部分，我们只为你做一次。”

“我们从开发人员开发应用的第一天开始就减轻了他们的负担。它是 CLI，但它也构建了许多 Kubernetes 原语，您可以在其上构建。它就像一个基础。每个人的应用程序中都需要这些东西，所以让我们把它们放到那个地方。微服务怎么说话？他们如何相互认证？他们如何处理交通突发事件？”

CLI 可用于 macOS、Windows 和 Linux。它可以在任何 Kubernetes 集群上运行，并且不需要任何其他的 Rancher 技术。

“Rio 来自 Rancher Labs 项目系列( [k3s](https://k3s.io/) ， [k3OS](https://k3os.io/) )，专注于轻量级、简单和灵活的基于 Kubernetes 的项目，”Rancher Labs 首席架构师 [Darren Shepherd](https://github.com/ibuildthecloud) 在一篇[博客文章](https://rancher.com/blog/2019/introducing-rio/)中写道。

该公司在 2 月份发布了 k3s，这是其为 edge 开发的轻量级 Kubernetes 发行版，随后又推出了 k3s 的操作系统 k3OS。

“所有功能都经过专门设计，提供了一个合理的默认实现，可以让您立即运行，但可以根据您的需要灵活地进行配置、替换或禁用。如果你只想要 Rio 中的一个特性，你可以使用它，忽略其他的。这一切都是可能的，因为力拓与库伯内特斯生态系统非常紧密地结合在一起，并从中大量汲取营养，”谢泼德写道。

据销售副总裁[戴夫·盖兹勒](https://twitter.com/davegetzler?lang=en)称，该公司一直是 Docker 世界中 [Compose](https://docs.docker.com/compose/overview/) 的忠实粉丝，并希望在 Kubernetes 中创造一些东西，以促进开发者的采用。

“如何让开发人员不用理解每一个原语就可以部署应用程序？”他问。

希门尼斯说，这是非常不个性化和灵活的。

“这是一种解释性舞蹈。它非常灵活，你可以按照自己的方式调整它，但它有一种通用的节奏和旋律。它非常适合你自己的情况，”他说。

它还使用 Kubernetes 中的 Istio 和 Knative 入口控制器等同类最佳技术，允许您加密证书管理。

“我们正在利用这些 CNCF(云计算基础)项目。我们不是在制造新东西，我们只是在帮你驾驭它们，”希门尼斯说。

云计算原生计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>