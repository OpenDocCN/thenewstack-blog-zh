# 减少技术债务，消除依赖性(和重构)

> 原文：<https://thenewstack.io/to-reduce-tech-debt-eliminate-dependencies-and-refactoring/>

最近退休的眼镜供应商 Warby Parker 的首席架构师罗伯特·莱夫科维茨建议:[如果你想消除技术债务，那么停止使用开源库和框架。](https://www.linkedin.com/in/robert-lefkowitz-921610166/)

“如果你不想要技术债务，避免使用库或框架，”莱夫科维茨说，他在上周举行的[奥赖利软件架构](https://conferences.oreilly.com/software-architecture/sa-ny)会议上发表了受欢迎的年度演讲。他还建议以这样一种方式编写代码，这样以后就不需要重构了。

Lefkowitz 承认他的观点在开源社区可能不受欢迎，因为对他们来说，共享包是一种实践，而包是建立在这种实践之上的。然而，他认为，在许多情况下，共享软件包会导致更多的困难，而不值得这么做。

在最近对其用户的调查中，Appian 发现 58%的组织说:“技术债务是开发利用商业机会所需的应用程序的障碍。”

维基创始人沃德·坎宁安[在 1991 年创造了术语](https://www.agilealliance.org/wp-content/uploads/2016/05/IntroductiontotheTechnicalDebtConcept-V-02.pdf)“技术债务”。就像有人会因购买需要在未来某个时间偿还的商品和服务而累积财务债务一样，快速修复或仓促实施也需要资源在以后某个时间进行修复，从而剥夺了添加新功能或能力的精力。

Lefkowitz 反驳说，虽然这些问题通常不是来自代码本身，而是通过使用第三方库引入的。

## 依赖于依赖

作为一个例子，Lefkowitz 提到了 [React.js](https://reactjs.org/) ，这是一个用于构建前端 web 组件的流行库。脸书设计了 React 来为十亿用户简化复杂的网络和移动前端的设计。然而，大多数公司都没有这么大的项目。在这种情况下，使用 React 会降低开发速度。

作为一项实验，Lefkowitz 从一个长达 80，000 行的示例 iOS 应用程序中删除了所有依赖项，包括外部库，如由 80，000 行代码组成的 Swift HTTP 库 [Alamofire](https://github.com/Alamofire/Alamofire) 。缺失的功能可以从操作系统本身获得(iOS 已经理解 HTTP ),或者从头重新编码。通过这种方式，他能够将程序缩减到 35，000 行代码。这就减少了 45，000 行代码。

即使代码是导入的，如果所有者更新了代码，那么代码也需要在使用它的程序中更新。“你欠下的技术债，就是你借的所有代码，以及他们借的所有代码，等等，”他说。一个应用程序依赖于 300 个依赖项，并且每个依赖项每年更新一次，这意味着该应用程序几乎一年中的每一天都必须重新构建。

当人们知道框架会使部署和维护变得复杂时，他们还会使用框架吗？程序员最初可能使用一个库来覆盖一些难以实现的功能，或者可能在一个不熟悉的平台上工作。

虽然共享代码以便每个开发人员都不必重新发明轮子的想法看起来很有吸引力，但 Lefkowitz 认为这仅适用于非常大的项目，例如那些有 500 万行或更多代码的项目(即数据库)。

在这些情况下，从头构建功能可能需要更长的时间，但从长远来看，它实际上会消耗更少的程序员时间。以 2016 年的 [LeftPad 崩溃为例，它涉及一个用空格填充一行代码的包，这些空格从 NPM 仓库中删除了。这一举措打破了依赖它的数十万个程序。然而，这是一个可以很容易地从头开始创建的功能。](/the-kik-kerfuffle/)

“你必须掌握你所拥有的工具，”他建议道。选择你能解决最多问题的技术，*，即使它们不是解决所有问题的最佳技术。*“如果你知道如何使用 JavaScript，React 的很多功能都已经内置在 JavaScript 中了。”

## 重构

对于 Lefkowitz 来说，理想情况下，目标应该是编写不需要重构的代码。他以丹尼尔·j·伯恩斯坦写的 QMail 为例，他在 1997 年悬赏 500 美元寻找发现程序漏洞的人。后来，他把金额增加到 1000 美元，因为没有人愿意接受。直到 2005 年才有人发现一个 bug。

莱夫科维茨还提到了他自己在摩根士丹利的工作。20 世纪 80 年代初，他开发了一个用于超高速交易的数据库系统。他说，他在 20 世纪 80 年代初离开了公司，并在 90 年代末接到了电话。该公司仍在使用该数据库系统，没有任何问题，但它需要退役，因为它运行的平台不符合 2000 年要求。

尽管有时重构是不可避免的。目前正在经历重构的一款广泛使用的软件是 Kubernetes，它最初是用 Java 编写的，VMware 高级开发人员倡导者 [Kris Nova](https://github.com/kris-nova) 在 [FOSDEM 2019](https://fosdem.org/2019/) 的一次单独演讲中指出，“[隐藏在 Kubernetes 代码库](https://www.youtube.com/watch?v=4VNDjwzzKPo)内的 Clusterfuck。”

[https://www.youtube.com/embed/4VNDjwzzKPo?feature=oembed](https://www.youtube.com/embed/4VNDjwzzKPo?feature=oembed)

视频

Nova 指出，即使在用 Go 编程语言重写了许多代码之后，Java 的许多面向对象的概念仍被带到了 Go 中，还有一些现在需要重构的“反模式”。对于同时工作在不同部分的多个贡献者来说，用于代码库的大型、主要的整体存储库可能是一个瓶颈。许多部分是紧密耦合的。例如，API 服务器与控制平面紧密相连，因此在服务器上工作意味着也要处理控制平面。Kubernetes 中的对象可以通过 Go 自己的内置结构对象定义更容易地实现。

从理想的角度来说，Lefkowitz 的想法可能会让实践者抓狂，但是那些因为支持如此多的语言和框架以及迭代-快速-修复-以后的风气而不堪重负的组织可能要考虑在什么时候使用您最熟悉的工具从头构建它会更容易。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>