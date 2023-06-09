# Golang 将在 2019 年推出什么:模块、泛型、更好的错误处理

> 原文：<https://thenewstack.io/whats-coming-to-golang-in-2019-modules-generics-better-error-handling/>

2019 年，围棋界将发生巨大变化。为了了解更多信息，我们采访了史蒂夫法兰克王国，他于 2016 年加入谷歌，成为其 Go 产品负责人，并处理这种流行编程语言的开发者关系。在加入谷歌之前，法兰克王国[领导着*两家*世界上最成功的开源公司](https://stevefrancia.com/#about)，先是在 MongoDB 担任首席开发倡导者，然后在 Docker 担任副总裁兼首席运营商。

法兰克王国向我们讲述了 Go 创新的新模块系统、错误处理、Go 2、修改后的提议流程、Go 社区的重要性以及其他话题…

**你说过你将“对 Go 的语言和工具进行重大改变，最大的改变将是依赖管理。”你能告诉我更多关于模块的事情吗？**

所以模块是——这不是一个新概念。(笑)这是一种存在于许多其他语言中的语言。

但是我们正在采取一种新的和有点创新的方法。我们已经做了大量的工作，使其与所有 Go 工具紧密集成，以确保我们的用户有一个良好而简单的体验，同时也消除了一些存在于其他语言和以前存在于 Go 中的问题，即更好的安全性、更好的可靠性和可重复的构建。作为其中的一部分，有许多幕后的安全工作正在进行，以确保人们可以拥有这些东西。

**你说的是证书和注册中心，对吗？**

没错。对于证书，我们实际上启动了一个公证人来签署东西。

**然后会有一个 Go 模块索引，类似于分散式社区中的中央目录。**

完全正确。目标之一就是让开发者更容易找到他们需要的东西。我们希望这将是对他们使用围棋方式的重大改进。我们的总体目标是让开发人员能够快速找到他们想要的东西，并对其进行评估。因为正如你所熟悉的，不是每个图书馆的质量都和其他图书馆一样。不是每一个都符合你的需求。因此，我们试图让评估过程尽可能简单，然后让他们能够尽可能容易地实际使用和消化它们。

Go 的独特之处在于我们从来没有一个 Golang 包的中央注册中心，这一点也不会改变。我们仍然没有一个中央登记处。所以与许多其他语言不同，在那里你需要注册“我拥有包 X…所以其他人都必须有一个新的名字”，我们的语言更加分散，人们在 GitHub、GitLab、Google Source 等上发布包。这种情况将继续下去。但是我们正在做一些事情来启动对镜像代理的支持，这将提供比我们今天拥有的这些单一来源更高的可用性，并且在其上也有更好的安全性。

这种方法的一个优点是 *go get* 不会改变。你仍然要使用*去得到*，就像你或多或少以前做的那样。我们真的想完整地保留 Go 一直以来非常简单的工作流程，我认为我们在这方面已经取得了很大的成功。将会有一些小的调整，但或多或少的工作流程非常类似于您以前所拥有的，或者我们的用户在过去 10 年中所经历的，只是获得了更高的可用性和更高的安全性。

模块添加的最大变化是*获得了*以前没有的版本能力。总是获取最新的东西，随着项目的成熟，他们很难发布有突破性变化的新版本。随着这种需求的增加，对版本感知工具的需求也在增加。这确实是推动这一发展的重要因素之一。

所以看待模块的另一种方式是给*添加版本支持。*

**预计到达时间是多少？**

我们将分阶段推出产品。我们预计在第二季度初，我们将有一个我们称之为 Alpha 的版本。它将是公开的，我们将让人们来开发它，然后我们将在 Q2 的其他地方工作，直到第三季度有一个完全稳定的版本。所有这些都是 Go 1.13 的前奏，它将在 8 月份发布，默认情况下会有模块。这是该版本的主要特点。

**是什么推动了这种变化？是用户要求这样做，还是你真的想添加一个不错的东西？**

这主要是由用户反馈驱动的。Go 一直都有内置的依赖管理支持——但是它有一些非常明显的限制。随着项目的扩大，随着我们社区的扩大，这些限制变成了用户的摩擦点。人们创造了许多解决方案来解决这些问题，但所有这些都有一些局限性。随着用户群的成长和成熟，这成为我们用户群日益增长的需求。

我们通过调查获得这些信息，我们已经做过调查— [年度用户调查](https://blog.golang.org/survey2018)。非常*大的*年度用户调查，以及通过问题跟踪器和提案以及各种方式进行的用户对话和反馈。

我认为，在某些方面，你知道，Go 已经有点落后于其他一些社区，以前，到模块。Node 是一个很好的例子，它使得获取模块变得非常容易。或包或插件或每种语言使用的任何术语。Ruby 和 bundler 也是一个灵感来源。Php 有 Packagist，所以很多语言已经有了这种支持。

我觉得围棋，有了模块，不仅赶上了他们，还做了一些创新的东西。希望随着时间的推移，我们会意识到这些创新是积极的，你知道，也许其他语言会注意到这一点。尽管我认为评审团还需要一段时间*(笑)*来看看这些创新有多受欢迎。

**您已经对您的提案流程做了一些更改。这是怎么回事？**

很好。我不认为这是一个新的提案流程，而是对我们已经使用了几年的流程的改进。而且提炼已经很好了。这是一个以前不太理想的地方。时机很好。我们真的开始了我们所谓的 Go 2.0。或者，去 2-抱歉没有“0 分”只是 Go 2。对语言和工具进行更多的修改。

Go 模块是我们将要推出的第一个重大变化，我们正在做其他事情。其他即将到来的事情是 Go 处理错误的方式——我们有一个提案，我们正在努力解决这个问题——以及泛型。我们在去年年底公布了这些提案，我们正在与机构群体合作。这是一个非常社区驱动的努力，得到反馈和改进。这是我们非常注重为用户提供的两件大事。

**那么这些到底什么时候落地呢？**

当我们做对了。因为我们真的——我们真的尊重我们的用户。我们想确保我们做得对。对我们来说，给他们一个正确的解决方案(比如说两年后)比现在就给他们一个不能完全满足他们需求的解决方案更重要。所以，你知道，我们确实感到了很大的压力，要把事情做好，这比我们现在感到的压力要大得多。我们认为这是我们能为用户做的正确的事情

**你还得担心保持向后兼容性。**

这是我们的一大焦点…

2009 年 11 月，我们开源了 Go，几年后，我们发布了第一个 1.0 版本，当时我们承诺不会对该语言做任何改动。未来的任何版本都将与为 1.0 编写的代码兼容。在过去的五年多时间里，这一点一直保持不变…

这就是为什么我区分了“Go 2.0”和“Go 2”。我们在这里的意图实际上是保持一切与 Go 1 兼容，并且永远不要有突破——我们没有意图，并且我们正在努力避免突破性的发布。而且，你知道，我们可能最终会意识到我们需要这样做，但到目前为止，我们乐观地认为我们不会有突破性的发布，我们可以将这些伟大的功能添加到语言中，同时保持与过去 10 年来编写的所有 Go 代码的兼容性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>