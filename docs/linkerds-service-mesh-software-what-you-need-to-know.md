# Linkerd 的服务网格软件:你需要知道什么

> 原文：<https://thenewstack.io/linkerds-service-mesh-software-what-you-need-to-know/>

随着越来越多的人和公司使用应用程序，应用程序开发人员必须不断寻找改进应用程序的方法。该领域的最新发展之一是服务网格。当今市场上最具创新性的服务网格产品之一是一种叫做 [Linkerd](https://linkerd.io/) 的产品。

[buppy](https://buoyant.io/)是 Linkerd 背后的公司，它已经做出了改进，使服务网络对企业更具吸引力。例如，2018 年 9 月，[公司对 Linkerd 进行了全面改造](https://thenewstack.io/buoyant-overhauls-linkerd-moves-to-a-simpler-service-mesh-model/)，使其比过去的版本更快，更适合开发者或微服务所有者。在这个新兴技术领域，它与许多其他服务网格包竞争，包括流行的 Istio。(Istio 通常与 Envoy 结合使用，后者提供数据平面功能，以配合 Istio 的控制平面管理)。

“Linkerd 的优势在于它比 Kubernetes 的任何其他服务网络都更轻、更快、更简单，”浮力公司的首席执行官、Linkerd 的创始人之一威廉·摩根断言。“我们专注于为您提供服务网格模型的所有功能，而不增加复杂性。正因为如此，林克尔德的气势从来没有比今天更高。”

“我们的用户看到了像 Istio 这样的东西带来的复杂性，将它与他们愿意添加到系统中的复杂性进行比较(基本上是‘尽可能接近零’)，最终对 Linkerd 非常满意，”他说。

如果需要，开发人员可以只为一个服务或应用程序部署它。Salesforce 和 PayPal 是加入 Linkerd 并在早期阶段蓬勃发展的品牌之一。

## 服务网格的世界

在研究服务网格如何工作之前，有必要讨论一下微服务。它们代表了一种新的开发方式，包括将应用程序构建为小型服务的集合。

应用程序开发人员构建一个微服务来服务于一个独特且定义明确的目的。微服务也在自己的进程中运行。因此，可以部署、扩展或升级任何微服务，而不会中断与之相关的所有其他服务。它们通常是自动的，允许实时更新，不会对最终用户产生负面影响。

简而言之，微服务在一个紧凑的单元中提供专门的服务，并在企业级交付它。

“服务网格是一个基础设施层，它在微服务之间的通信上运行，”Morgan 解释道。“通过智能监控和处理这种流量，服务网格为平台所有者提供了理解、控制和保护生产中微服务的关键功能，而无需接触应用程序代码。随着组织转向云原生架构，类似服务网状的 Linkerd 对于确保他们能够扩展这种方法至关重要。”

服务网格促进微服务之间的传入和传出通信。它是一个专用的基础设施层，提供了一个应用程序范围的点，提供了对运行时的可见性，并允许对它进行控制。

服务网格处理微服务之间的通信，微服务进而向最终用户提供完整的服务。

## 很容易安装

选择使用 Linkerd 的开发人员可以期待一个快速、轻松的部署过程。它适用于大多数应用程序，没有复杂的 API 或配置细节。启动并运行 Linkerd 的控制平面也同样简单。它在几秒钟内安装到一个命名空间。然后，人们可以根据需要向服务网格添加微服务。

没有必要为微服务更改代码。此外，数据代理是超轻和超快的。这意味着它们能提供应用开发者想要的可见性，而不会导致速度变慢。

## 访问关键指标

应用程序开发人员知道监控应用程序后端发生的事情有多重要。未能及时了解这些情况可能意味着应用程序会在没有警告的情况下关闭。Linkerd 的一个便利之处是，该软件提供了关于服务网格中每个应用程序的可操作的见解。它让人们可以访问谷歌所谓的黄金指标，包括成功率和请求量。

此外，Linkerd 还提供了一套深度运行时诊断工具。它们包括实时流量样本和自动服务依赖地图。

## 它提供额外的控制

Linkerd 的诞生是因为其背后的团队在 Twitter 和微软等公司积累了操作大型生产系统的经验。个人意识到在那些环境中最不寻常和最复杂的行为来自服务之间的通信，而不是服务本身。

Linkerd 通过在应用程序之上添加一个抽象层来解决这个问题，该抽象层负责跨服务通信中所有容易出错的部分。由于这种增强的控制，应用程序的代码变得更具可伸缩性和弹性。由于 Linkerd 作为独立的代理运行，它不需要特定的语言或库。相反，用户可以选择最适合他们应用程序的语言。

因为 Linkerd 将通信机制与应用程序的代码分开，所以人们只需使用与服务网格相关的软件，就可以监视或更改它们，而不会影响应用程序本身。不足为奇的是，林克尔德的引擎盖下发生了很多事情。

它执行双重任务，同时在目的地实例上应用路由规则和负载平衡，以及与现有的服务发现方法进行通信。它同时协助上述通信和报告指标。

## 当前使用案例

企业具体如何使用 Linkerd 来满足自己的需求？

最近，来自 Attest、Nordstrom 和 Kairos [的代表参加了一个现场讨论](https://buoyant.io/resources/nordstrom-kairos-and-attest-share-application-monitoring-best-practices-with-linkerd/)，讨论他们如何使用 Linkerd 作为总体应用健康战略的一部分。它允许他们监控 Kubernetes 应用程序，并在灾难性事件发生之前很好地发现奇怪的行为。

此外，行星实验室依靠 Linkerd[为全球卫星网络提供集群范围的可见性](https://buoyant.io/resources/kubecon-2018-na-talk-how-planet-labs-uses-linkerd-for-monitoring-satellite-data/)。它监控延迟和服务故障，然后发送寻呼机通知，根据紧急程度对事件进行分类。当服务速度变慢或发生其他问题时，Linkerd 会使它变得更容易。它还可以通过确定问题是否直接影响客户来更好地分配资源。

这里的例子展示了 Linkerd service mesh 如何为开发人员提供了一个可视化的级别，否则将很难或不可能实现。有了这些信息，他们可以在问题发生时迅速做出反应，甚至在问题发生前发现特征并进行干预。

## 最近的大笔投资

虽然 bubbly 已经对 Linkerd 进行了重大改进，但它现在有更多的资源在未来几个月内完成这项工作。这是因为 GV——前谷歌风险投资公司——加入了现有投资者 Benchmark 和 A Capital，三个[共同出资 1000 万美元](https://buoyant.io/2019/03/14/welcome-to-the-linkerd-party-google-ventures/)来进一步推动 Linkerd 的发展。

在 bubbly 从事 Linkerd 工作的人说，他们活跃而活跃的用户社区帮助他们关注对用户最重要的事情，并交付给用户。毫无疑问，这项新投资将允许更多的用户友好的增强功能发生。

“服务网仍处于早期阶段，有大量的炒作，”摩根承认，“所以很难理解这个前景。”然而，Linkerd 似乎将成为将服务网格带入公众视野的决定性平台之一。

## 性能和感知

关于 Linkerd，“它与其他服务网络产品或项目有一些不同，”汞合金洞察公司的研究员汤姆·佩特罗塞利说。“有的很好，有的没那么好，有的很中性。”

从积极的一面来看，Petrocelli 指出，Linkerd 包括一个控制平面和数据平面。

“这确保了任何一个方面的变化都是相互协调的，”他解释道。“与 Istio/Envoy 相比，这是一个优势，后者是两个不同的独立项目，不需要协调。Linkerd 是一个完整的包，NGINX 也是。”

“从技术上讲，”Petrocelli 指出，“Linkerd 1.x 分支存在一些问题，阻碍了它在市场上的应用。它与 Java VM 相关联，与其他服务网格代理相比，它的 sidecar 代理占用空间大(每个代理 100-150mb)且延迟高。”

“2.x 分支纠正了这些问题，”他说。“不幸的是，Linkerd 的声誉是由 1.x 分支机构决定的，并且经常与 Envoy 相提并论。与竞争对手相比，Linkerd 的许多负面观点是 1.x 版代理的结果。这不公平，但事实就是如此。”

Petrocelli 还指出，Linkerd 是一个云原生计算基础项目。“这应该是相对于 Istio 的一个优势，后者缺乏真正的独立治理，以及专有或开放的核心技术。然而，林克尔德并没有从这种联系中看到多少好处。更多的供应商接受了 Istio/Envoy 项目。特使也是 CNCF 项目，有点诡异。”

“总的来说，Linkerd 2.x 在技术上与其竞争对手的项目和产品不相上下，”Petrocelli 总结道。“它缺乏供应商支持，尤其是与 Istio/Envoy 相比，只有 buoy 提供发行版。原因更多是历史原因，而非技术原因，但这就是市场现状。”

## 令人兴奋的事情即将到来

这篇综述介绍了一些亮点，这些亮点使得 Linkerd 和 Buoyant 在未来几个月和几年中值得关注。

保持应用程序正常运行对于帮助公司获得用户满意度至关重要。由于它提供的可见性和控制，Linkerd 可以帮助拥有微服务的公司。

云计算原生计算基金会是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>