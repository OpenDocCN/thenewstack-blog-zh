# CRI-O 如何将 Kubernetes 置于容器生态系统的中心

> 原文：<https://thenewstack.io/cri-o-make-kubernetes-center-container-ecosystem/>

开源项目 [CRI-O](https://github.com/kubernetes-incubator/cri-o) ，原名 OCID，旨在使开源 [Kubernetes](/category/kubernetes/) orchestrator 能够在不依赖传统容器引擎的情况下管理和启动容器化的工作负载。

该软件可以通过与 Kubernetes 或 Kubernetes 的商业实现(如 CoreOS structural)进行接口，借助于由谷歌领导的 Kubernetes 工程师开发的容器运行时接口(CRI)，帮助开发人员管理整个“容器生命周期”。

开发人员需要容器引擎来创建和构建容器映像，并且可能更喜欢使用他们自己的临时环境来进行本地测试。然而，管理员和运营团队可能会发现新兴的 Kubernetes 堆栈——orchestrator、CRI 和 CRI-O——比 orchestrator 和标准容器引擎更适合管理更复杂的生产环境。

这个项目将容器编排工具，而不是容器引擎，放在容器栈的主要组件上。它的贡献者告诉我们，CRI 将允许 Kubernetes 使用任何符合[开放容器倡议](https://www.opencontainers.org/)规范的容器引擎，包括 OCI 自己的 [runc](https://thenewstack.io/ready-docker-containers-runc-runtime-riddler/) 引擎，它可以做像 Docker 或 CoreOS 的 **rkt** 这样的品牌容器引擎可以做的许多事情，包括从注册表中提取图像，只是它不会从 makefile 中构建图像。

## 今天的 CRI-O 是什么

虽然开放容器倡议，就其本身而言，已经远离了对 CRI-O 的责任(尽管其成员和 CRI-O 的贡献者在许多情况下是相同的供应商和相同的人)，该项目是“OCI 的自然发展”，这是为容器运行时和图像开发标准接口，谷歌员工开发倡导者和首席 Kubernetes 工程师 [Kelsey Hightower](https://twitter.com/kelseyhightower) 在接受新堆栈采访时说。

CRI-O 项目的主要主张是，用户不应该依赖创建工作负载的引擎来暂存工作负载。按照最初的设想，该项目将为 Kubernetes 提供作为容器的完整生命周期管理器所需的工具，而不需要 Docker、 **rkt** 、OpenShift、Photon 或任何品牌的容器引擎。

Hightower 说:“我们真的不需要任何容器运行时——无论是 Docker 还是 **rkt** ,它们只需要做很少的事情。“主要是，给我们一个内核的 API。所以这不仅仅是关于 Linux，对吗？我们可以使用 Windows 系统。如果这是社区想要的方向，我们需要 Kubernetes 来支持这些想法——因为在这一点上，它比 Docker Inc .更大。”

这个断言的基础是这样一个假设，即 orchestrator 位于容器生态系统的中心，我们所知道的“引擎”实际上是一个开发工具。

另一方面，CRI(由 Kubernetes 开发并为 Kubernetes 开发的 API)将为容器引擎制造商提供实现 Kubernetes 开放接口的机会，以便包含容器引擎的环境可以建立适当的连接。一位关键的 Google 工程师说，这些连接可能不需要容器引擎供应商“重构”引擎来实现 Kubernetes 兼容性。

相反，可以在容器引擎和编排器之间插入一个称为*垫片*的抽象层。供应商如何实现这样一个垫片将取决于他们。

完成后，CRI API(与 Kubernetes 连接的部分)将把更多的容器生命周期控制委托给*kube let*——一个 pod 的管理者，这是 Kubernetes 的独家概念——并且必须被容器生态系统采用。

Kubernetes 的下一个版本 1.5 的目标是包含一个最终确定的 CRI，使 kubelet 能够与 Docker、 **rkt** 、中国的容器供应平台 Hyper.sh 和 CRI-O(其开发由 Red Hat 领导)进行通信。

“有许多不同的容器运行时，都对与 Kubernetes 通信感兴趣，”Philips 说。“因此，我们没有试图将每个容器运行时的每个接口都构建到 kubelet 本身中，而是创建了一个其他人可以插入的更抽象的接口，而无需直接参与 Kubernetes 的上游工作。”

## 谁重构什么

Hightower 将容器运行时接口(在“-O”之前的“CRI”)描述为一种抽象，它代表了容器引擎应该支持的基本特性，Kubernetes 可以证明这一点。一旦 CRI 完成，他说 Kubernetes 计划重构自己的代码库来实现 CRI。

他解释说，如果 CRI-O 成功了，任何一个容器引擎的生产者都不需要修改引擎的代码库，只需要与 Kubernetes 交互操作。

“现在，如果你想与 Kubernetes 友好相处，你将不得不建立一堆东西，并可能以一种非常不明确的方式修改你今天的做事方式，”Hightower 承认。“你今天必须去看看代码库，弄清楚，这就是我们为 Docker 所做的，你如何为你的运行时引擎修改它，以一种对你很好的方式，也能与 Kubernetes 很好地配合。”

正如 CoreOS 的 Philips 解释的那样，每个容器引擎都将利用一个*shim*——一个将来自引擎本地词典的 API 请求翻译成 Kubernetes 可以消化的形式的组件。

“由于 CRI 是如何工作的，你需要[一个 GRPC 守护进程](https://thenewstack.io/grpc-lean-mean-communication-protocol-microservices/)来监听请求，”Philips 说，“它可以与 kubelet 通信。”他说，反过来，kubelet 将通过套接字向任何实现 CRI 的引擎发送远程过程调用。

“现有的 Docker 和 **rkt** 支持正在被拉进 CRI 接口，”飞利浦解释道。CoreOS 对 CRI 的 rkt 实现目前在 GitHub 上以 **rktlet** 的形式提供。他希望 rktlet 和 Docker 的实现最终被调用，在内部被重构为 CRI。

谷歌的 Hightower 告诉我们，虽然 Docker 已经需要一个 shim 来与 Kubernetes 一起工作，但是是 Kubernetes 的工程师生产了这个 shim，而不是 Docker 的。飞利浦说，无论谁将实施 CRI shim，Docker 都将被改造，与其他所有人合作。

> “为了与 CRI 集成，Docker 引擎和 **rkt** 引擎的集成都发生了变化”——CoreOS Brandon Philips

OCI 图像格式的最终标准仍在确定中，尽管 OCI 发言人已经通知新堆栈，在 OCI 图像格式可以作为版本 1.0 正式发布之前，还有两个发布候选迭代。

与此同时，Docker 继续增强其容器引擎，捆绑了一些功能，如自己的 Swarm orchestrator 和服务发现。

“我认为这很好，”他说。“当然，人们可能不喜欢这样——没关系，每个人都可以有自己的看法。kubernetes——我们也提供很多东西。但是我们倾向于相信我们只是要在我们认为是商品的基础上做这件事。

## Kubernetes 和超越

“为了正确地实现我们所说的 pod，您需要知道很多事情，”Hightower 解释道。“将这种负担推给每个容器运行时，对于所有容器运行时来说是不公平的，必须实现那么多代码才能享受 Kubernetes 的乐趣。想想看:他们将不得不为 Mesos 做一些不同的事情，为 Swarm 做一些不同的事情——无论什么。为了使这更容易，我们将引入特定于 Kubernetes 的逻辑，并将它留在 kubelet 的内部。在外部，我们将只使用对原生容器运行时已经做的事情友好的东西。”

假设确实发生了这种情况，一个对现有的容器化术语友好的接口可以抽象出面向 pod 的、基于 kubelet 的逻辑，这样同一个 API 就可以与 Kubernetes 之外的东西接口，以不同的方式抽象出自己的逻辑。

我们和中间层创始人本·亨德曼一起探索了这种可能性。

“我认为业界真正寻找的是可以组合的组件，”Hindman 向新堆栈解释道。“我认为，在 Kubernetes 的案例中，这一点非常关键。Kubernetes 依靠 Docker 来进行容器管理，他们试图构建流程编排。当 Docker 合并 Swarm 时，现在他们有了一个容器管理器，同时也在进行编排。因此，仅仅从架构的角度来看，戴上我的工程帽子一秒钟，我认为很有理由想说，“嘿，如果我们只是有一个做容器管理的组件，多个人都有可能利用它，那不是很好吗？”"

Hindman 认为 Docker 公司率先将 **runc** 变成了一个开放标准。但是完整的编排需要的不仅仅是与运行时的互操作，他说。

> “还有更多。有下载图像，解包图像-有更多的事情必须实际完成。对我来说，我认为业内的一个大争论是，这些东西是否也应该被分解和组件化？它不是关于一个分叉，而是关于什么在架构上有意义。”[ *本·辛德曼，中间层*

Hindman 解释说，Mesosphere 的 DC/操作系统环境也有这些组件，已经不需要依赖于 **runc** 或任何 Docker 组件。正如他所说，容器社区的真正目标应该是指定组件之间的架构边界，并在它们之间建立适当的接口。

这是否意味着中间层支持 CRI-O，正如凯尔西·海塔尔向我们解释的那样，CRI-O 的目标似乎与辛德曼的预测完全一致？

虽然 Hindman 不代表 OCI，但在这里需要注意的是，中间层是 OCI 的创始成员之一。正如 Hindman 所回应的，OCI 最初的目的是开发一种通用的运行时格式，以便 runc 可以将其作为一个容器来启动。容器化社区还关心图像格式，这涉及到容器静止时的文件系统和元数据。因此，OCI 也开始了这项事业。“这实际上比运行时格式更让我们感兴趣，”Hindman 说。

[Mesosphere 着手开发所谓的“通用集装箱”的原因，](https://thenewstack.io/six-years-later-mesos-makes-version-1-0-now-real-fun-begins/) Hindman 继续说道，是为了能够生产所有开放格式的集装箱，包括 OCI。

但他说，在这样一个最佳架构中，可能没有办法标准化工作负载的调度。时间表的特征彼此之间差别太大了。因此，到目前为止，寻找单个配置文件、元数据文件或清单来描述工作负载，以便任何调度程序都可以充分利用它来进行部署和启动的努力，最终以 Hindman 所谓的“最低公分母规范”而告终，这使得具有更广泛功能集的调度程序无法使用它。

然而，他说，决定一种通用的图像格式要简单得多。归结起来就是 Linux 是否支持该格式。“如果 Linux 支持，我们可以公开它。我不认为对于图像格式应该是什么样子有太多的争论；所以，把它当成一个标准，完全没问题。”

Hindman 总结道,“中间层将继续支持 OCI，并且实际上会支持 CRI-O([“OCID”，在我们讨论](https://thenewstack.io/oci-distances-ocid-container-project-now-named-cri-o/)的时候)到支持 OCI 的程度。但是 Mesosphere 的“通用容器运行时”将以不同于 CRI-O 的方式实现这种支持。

这让我们着眼于围绕编排方式的竞争市场，而不是被编排的内容。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>