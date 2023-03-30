# 单核:争论仍在继续

> 原文：<https://thenewstack.io/unikernels-the-debate-continues/>

尽管这项技术相对较新，但单核及其在数据中心的潜在用途继续在 IT 社区激发 T2 激烈的辩论。

对于 [Cloud Foundry](https://www.cloudfoundry.org/) 和 EMC 来说，使用单核有很多好处。然而，开发人员可能会发现自己对一项一次只能运行一个进程的技术持怀疑态度。单核的好处是否足以抵消开发人员对这项新技术的担忧？时间会证明一切。

在这一集的[新堆栈制造商](https://thenewstack.io/podcasts/)播客中，新堆栈主持人 [Lee Calcote](https://twitter.com/lcalcote) 采访了 EMC 首席技术官办公室的 [Idit Levine、](https://twitter.com/Idit_Levine)以及 EMC Cloud Foundry Dojo 的首席技术官；还有云铸造咨询公司的首席执行官尼克·威廉姆斯。他们讨论了在生产中使用 uni kernel 的好处，开发人员如何在自己的项目中实施 uni kernel，以及使用 uni kernel 如何让 EMC 和 Cloud Foundry 受益。

[Nic Williams 博士和 Idit Levine 在云铸造峰会上](https://thenewstack.simplecast.com/episodes/dr-nic-williams-and-idit-levine-at-cloud-foundry-summit)

T21 的对话也可以在 YouTube 上欣赏。

Levine 通过强调 EMC 的[开源项目 UniK](https://github.com/emc-advanced-dev/unik) 开始了讨论，这是一个单核编译和部署平台，致力于帮助开发人员快速启动并运行单核。“人们有这样一种观念，即设置单内核非常困难，因此，人们并没有真正使用它。Docker 之前的 Linux 容器也是如此。我们决定为 Unikernel 做一个 Docker，由 EMC 开源，让用户能够轻松无缝地在云或任何嵌入式设备上构建 Unikernel。”

unikernels 没有将可能永远不会用到的依赖项和库塞进一个容器中，而是剥离了这些部分来简化应用程序的性能。Levine 解释说，虽然 unikernels 仅限于其中只有一个运行的进程，但它们非常适合基于云的开发和创建基于物联网的项目。

“单内核的理念是，如果你看看今天的堆栈，你正在运行一个管理程序、驱动程序、顶层系统、内核、系统进程、顶层容器、容器中的库，等等。单核正在做的是他们说，“所有这些都是不必要的。”最终，我们试图在一台服务器上运行一个用户。我们从应用程序开始，看看应用程序真正需要什么。如果它不需要 USB 驱动程序，因为它在云中，它就不会在那里。它只拿走它需要的东西，”

在 Williams 的猛烈抨击下，Levine 解释说，虽然开发人员可能不愿意在他们的堆栈中采用单核，但它们有很大的好处，如大小和速度。Levine 强调，当容器的大小增长到千兆字节时，UniK 可以用少得多的空间运行基本上是完整的堆栈。“单核的主要特点是大小。我们创建了小型单内核虚拟机，使用真正的 DNS 进行服务发现。在常规虚拟机只有几千兆字节的情况下，我们用 300 MB 来做这件事，”Levine 反驳道。

Williams 继续他的问题，提出了这样的想法，即习惯于运行 Docker、传统 VM 和 BOSH 的开发人员可能会发现单核的概念很难理解。然而，Levine 指出，开发人员基本上不必偏离他们所知道的，因为单核本质上是虚拟机。例如，UniK 可以在一个 unikernel 中创建 Cloud Foundry。

“单核的优势在于你基本上不需要改变。如果你仔细想想，这是一个虚拟机。您仍然在运行您的虚拟机管理程序，您获得了容器的所有好处，但是仍然在运行成熟的虚拟机管理程序技术。您拥有两个世界的优点，而且更加安全。容器的所有问题都不适用于单核。你基本上仍然在运行一个虚拟机，所以你以前做的一切，你都可以继续做下去，”莱文解释说。

Levine 还强调，为了支持持久性，Cloud Foundry 还将 UniK 加入了 Deigo DBS。Calcote 提到，通过这样做，Cloud Foundry 开启了单核成为物联网“事物”的机会，在物联网中，可能性是无限的。拥有持久化的单核将新旧两者联系起来，让开发人员更加熟悉和灵活，Levine 在结束讨论时提到了这一点。

“现在，您可以持久地运行 unikernels。如果您丢失了一个单核，Cloud Foundry 会知道旋转一个新的并附加一个新的单核。这很酷，因为您可以通过 V-Motion 和 vDR 获得老式的虚拟机质量。但是，您运行的空间要小得多，并且具有容器的性能和虚拟机的安全性。”

[Cloud Foundry](https://www.cloudfoundry.org/) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>