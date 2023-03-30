# Docker 宣布格式战争结束，将一个通用运行时嵌入到所有容器中

> 原文：<https://thenewstack.io/declaring-format-wars-over-docker-slips-a-universal-runtime-into-all-containers/>

正是在技术发展的这个阶段，围绕它形成了某种“开放”标准。我们已经在开源操作系统、云服务平台以及最近的大数据产业中看到了这一点。一个或多个不同的联盟可能会围绕集装箱化标准的一些变体而形成，如果有多个联盟，它们会为了谁最“开放”而相互争斗。周一在 DockerCon 2015 上的问题是，一个开放的容器联盟在多大程度上是真正包容的——换句话说，对开放的想法开放？

如果你想一想，Docker Inc .很可能已经宣布自己是集装箱领域的主导者，并建立了一种行业共识联盟，使其与 **appc** 、[一种仅在几个月前由 CoreOS 管理的替代标准](https://thenewstack.io/coalition-for-app-container-spec-shows-docker-is-not-the-standard-for-everyone/)直接竞争。它已经有了微软的支持，并有可能正式支持 VMware。拿下 IBM 和亚马逊，Docker 就能垄断市场。

在周一旧金山举行的 DockerCon 2015 主题演讲上，Docker CTO Solomon Hykes 在数千名与会者面前与 CoreOS 首席执行官 Alex Polvi 握手，温暖了许多人的心。这是一个迹象，表明两位高管已经意识到，就本应简单的组织形式展开公开争吵，将对两个品牌造成更大的损害。

他们的握手标志着非官方的，但非常引人注目的，开放容器基金会的启动。

“有一件事我特别不喜欢:毫无理由地争论盒子的大小和形状等细节，”Hykes 说，然后邀请 Polvi。“在业内，我们称之为‘标准战争’“标准战争”是一件丑陋、可怕的事情。如果可能的话，它们既糟糕又无聊。我们的行业以前经历过标准战争，我认为有一段时间，我们中的许多人都不清楚这是否会发生在我们身上，即使是现在。我决定我很高兴，因为我可以告诉你很明显这不会发生。"

Hykes 和 Polvi 不同意统一他们的格式。然而，他们的握手代表了一种共同的愿望，即共同参与加强他们将参与竞争的行业的基础。

然而，那次握手所代表的协议并不是在没有一定的知识产权交换的情况下达成的。几分钟前，Hykes 向观众介绍了一些真正令他们惊讶的东西:一个为容器生产通用运行时的项目，使它们的构造或 CTO 所说的“管道”可以通过一种公共语言来访问。

它的名字将会是 **runC** ，以小写的“r”和大写的“C”结尾，只是为了迷惑所有的编辑。“它基本上是我们为管理操作系统容器而编写的所有代码，被分成一个小型的轻量级工具…它基本上是在低级系统上运行容器所需的一切，除此之外别无其他。”

**RunC** 的目的，根据[周一](https://blog.docker.com/2015/06/runc/)的这篇博客文章，是让容器用来访问系统服务的代码，可以被外部通信访问。据说芯片制造商英特尔、IBM、高通和 ARM 以及微软都在为这一新工具做出贡献，尽管这些公司都没有派代表出现在周一的舞台上。(微软定于周二向 DockerCon 做演示。)

Hykes 说 Docker 已经向 Linux 基金会捐赠了 runC，这是一个令人惊讶的举动，表明最直言不讳的开源倡导者可以在需要时保守秘密。但 Docker 的这一举动可能是明智的，因为另一个原因:仅凭借其完成的方式，以及与 CoreOS 首席执行官的握手，Docker Inc .确保了开放容器项目基线的关键组件之一[在此插入不适当的 RoboCop 参考]将是一个严格遵循 Docker 架构的可管理性平台。

这样，一个与 CoreOS 最强的支持者 Google 结盟的,**appc(**,将无法产生一个比主要或单独支持 Docker 的版本更好的 Kubernetes。现在，Docker Inc .因成为和平缔造者而获得赞誉，与 CoreOS 一起获得了荣耀，同时又注入了一个庞大的 Docker DNA 的胚胎开放容器项目。

“随着我们开始在 OCP 规范上的合作，我们开发应用容器的经验将发挥关键作用，”[Alex Polvi 周一在 CoreOS 的博客文章中写道。“我们预计 App Container 的大部分将直接集成到 OCP 规范中，并进行调整，以提供与现有 Docker 生态系统的更大兼容性。最终目标是汇聚到一个标准容器格式的单一统一规范上，OCP 的成功将意味着 App Container 的主要目标得到满足。”](https://coreos.com/blog/app-container-and-the-open-container-project/)

Polvi 接着说 appc 的 Brandon Philips 和 Vincent Batts 将会签约成为 OCP 的维护者。但是他结束了这一段，称从 T2 到 OCP 的过渡是“平稳的迁移”“今天 **rkt** 是 **appc** 的领先实现，”Polvi 写道，“我们计划让它成为 OCP 的领先实现。”

周一，CoreOS 没有打出白旗，但某种程度上，它的产品身份确实被放弃了。虽然我们期望行业能够共同制定所有容器格式的基本原则，但似乎 Docker Inc .在规定该基本原则的高度方面发挥了主导作用。否则， **runC** 不可能发生。

CoreOS 和 Docker 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>