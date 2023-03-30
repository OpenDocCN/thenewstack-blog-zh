# OpenWhisk 无服务器毕业生 Apache，展望 Knative，Envoy 和更多

> 原文：<https://thenewstack.io/the-openwhisk-serverless-platform-now-an-apache-top-level-project-builds-on-kubernetes-mesos/>

本周，开源无服务器项目 [Apache OpenWhisk](http://openwhisk.apache.org/) 已经从 Apache 软件基金会(ASF)的孵化项目中毕业，成为顶级项目。[三年多前，IBM 首次创建了](https://thenewstack.io/ibm-launches-bluemix-openwhisk-event-driven-program-service/)这个项目，同年晚些时候，IBM 将该项目捐赠给 ASF 作为孵化项目。

自从加入 ASF 以来，OpenWhisk 已经扩展了它的功能，并满足了许多严格的要求，最终成为一个完全自治的成员，正如 OpenWhisk Wiki 上的[项目成熟度矩阵](https://cwiki.apache.org/confluence/display/OPENWHISK/Project+Maturity+Model)中所详述的，显示了该项目满足 [Apache 项目成熟度模型](http://community.apache.org/apache-way/apache-project-maturity-model.html)及其编码框架的要求的方式。在接受 New Stack 采访时，IBM 的无服务器技术和宣传首席技术官 Matt Rutkowski 解释说，这些要求使得公司信任那些从 ASF 孵化出来的项目。

“当公司向 Apache 寻求软件和开源时，他们知道他们已有的过程和政策保证代码的出处是没有问题的。就孵化而言，我们必须证明我们可以通过项目管理委员会来管理项目，我们可以公开地与我们的社区合作，邀请并开放所有想法，并接受来自任何地方的贡献。所有这些事情都受到孵化委员会的审查，”他说。

自从第一次加入 ASF 以来，Rutkowski 在一篇宣布毕业的博客文章中展示了众多的进步。现在它运行在[集装箱](https://containerd.io/)和[库伯内特](https://kubernetes.io/)带[舵轮](https://helm.sh/)的海图上。还支持 [Apache Mesos](http://mesos.apache.org/) 框架。OpenWhisk 平台也可以作为 [GoLang](https://github.com/apache/incubator-openwhisk-runtime-go) 、 [Java](https://github.com/apache/incubator-openwhisk-runtime-java) 、[的运行时。NET](https://github.com/apache/incubator-openwhisk-runtime-dotnet/) 、 [PHP](https://github.com/apache/incubator-openwhisk-runtime-php) 、 [Ruby](https://github.com/apache/incubator-openwhisk-runtime-ruby/) 、 [Rust](https://github.com/apache/incubator-openwhisk-runtime-rust/) 、[ballerine](https://github.com/apache/incubator-openwhisk-runtime-ballerina/)甚至还有一个人工智能(AI)专用的 Python3。

当然，这些语言是基于最新版本的 [NodeJS](https://github.com/apache/incubator-openwhisk-runtime-nodejs) 、 [Python](https://github.com/apache/incubator-openwhisk-runtime-python) 和 [Swift](https://github.com/apache/incubator-openwhisk-runtime-swift) 之上的，OpenWhisk 从一开始就支持这些语言。Rutkowski 还强调了 OpenWhisk“大量服务提供商接口(SPI)的重要性，这些接口允许运营商‘插入’他们最喜欢的日志记录、监控或数据存储”，“提供您自己的调度程序，允许提供商优化他们的云工作负载。”Rutkowski 说，OpenWhisk 已经成为那些希望在不依赖托管服务的情况下运行无服务器的公司的首选项目。

“它高度可用—我们后端体系结构的所有部分都高度可用。如果你想成为无服务器、通用服务计算的提供商，这是你的首选代码。其他所有东西都想成为 OpenWhisk，”Rutkowski 说。“您可以用许多不同的方式实现无服务器，但就高可用性、大规模无服务器而言，OpenWhisk 是开源软件的首选。OpenWhisk 提供了一些独特的东西，因为我们为想要托管无服务器平台的人提供了端到端的解决方案。”

根据 Rutkowski 的说法，OpenWhisk 在不同环境和用例中的暴露已经使它超越了其他开源的无服务器解决方案。

Rutkowski 说:“OpenWhisk 的优势之一是，作为 Apache 下的一个开源项目，并接触到不同的公司和用例，我们可以处理一切事情。“我们将容器作为工作负载来处理，并将功能作为工作负载。我们已经对不同的功能、不同的内存大小、不同的连接数做出了响应。我们已经在多家公司的生产环境中接触了很多东西，这使我们有别于许多其他开源项目。”

现在，在 ASF 上周投票决定让 OpenWhisk 毕业后，Rutkowski 说该项目终于可以开始以更快的速度前进，并解决它到目前为止只试验过的所有问题——例如“集成最新的开放无服务器技术，如 [Knative](https://knative.dev/) 、 [Tekton CI/CD pipelines](https://tekton.dev/) 和 [Kubernetes 事件驱动自动缩放(KEDA)](https://github.com/kedacore/keda) ，并探索用例以允许使用边缘服务代理(如 [Envoy](https://www.envoyproxy.io/) 对功能进行更细粒度的访问控制的新协议

“在想要开发新的软件版本之间有很多时间延迟。在发布之前，我们会受到多层次的审查。我认为[毕业]将增加我们发布新版本的能力。Rutkowski 说:“我们要做的很多事情是大量的整合和清理，以尝试简化我们的一些发布。“当我们开始这个项目时，我想我们可能有几十个存储库，我们不知道主要的用例是什么。现在，我们已经更好地了解了我们所处的位置、我们的使用情况以及我们的发展方向，我认为我们将把许多曾经是试验性的回购整合到我们的主存储库中，并准备再次进行扩展，以利用 Knative 和其他技术进行一些探索性工作。”

来自 Pixabay 的 Steve Buissinne 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>