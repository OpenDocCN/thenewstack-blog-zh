# Dark，一种用于“无部署”部署的新编程语言

> 原文：<https://thenewstack.io/dark-a-new-programming-language-for-deployless-deployments/>

据保罗·比格(Paul Biggar)称，如今技术界有太多的渐进主义者，他和[埃伦·千纱(Ellen Bernstein)](https://www.linkedin.com/in/ellenchisa/)一起发布了 [Dark](https://darklang.com/) ，这是一种旨在简化软件部署的编程语言。

“如今构建后端的复杂性已经失控。它是基础设施，它是部署，它是 APIs 黑暗是要消除所有这些复杂性，”比格说。

该技术涉及一种整体编程语言、结构化编辑器和用于构建后端 web 服务的基础设施。

“我们不断增加东西，但我们从不拿走东西。AWS 有 200 项服务，从来没有拿走任何一项，”他说，称垃圾收集是该行业最后一项真正好的创新。

在一个解释 Dark 哲学的视频中，之前创建了 [CircleCI](https://circleci.com/) 的 Biggar 指出了[云原生景观图](https://cdn.thenewstack.io/media/2016/12/e99e2b63-cloud-native-lanscape-v0.9.2.jpg)中的 455 个工具。

“今天要构建一个后端，你需要知道 Kubernetes、Docker、Git、负载平衡器、数十种 AWS 服务、SQL、NoSQL、Kafka、Unix、GraphQL、gRPC、Thrift 和 Memcached……你需要安全、优化、联网和可观察性，而且复杂性还在不断增加，”他说。

他坚持认为你不需要 AWS 或容器或 Docker 文件或服务网格或 API 网关或 Kubernetes。

## 无部署技术

总部位于旧金山的公司[在 7 月底从隐身中出现](https://techcrunch.com/2019/07/29/dark-emerges-from-stealth-with-unique-deployless-software-model/)，并宣布在 2017 年筹集了 350 万美元的种子资金，但直到现在一直对其技术保密。

Bitnami 的联合创始人和前首席运营官(首席运营官)，现任 GitHub(收购了 Bitnami)的首席运营官，是该公司的投资者之一。她称 Dark 是“一个大胆的愿景”，并补充道“我认为很少有人真正有能力很好地执行它。艾伦和保罗是一个强大的团队，也是抓住这一巨大机遇的合适创始人。”

> 就像无服务器中有服务器一样，无部署中也有部署，只是你不必去想它。—保罗·比格

千纱在一次采访中解释道，“当人们构建一个开发工具时，他们会选择一个特定的问题来解决，然后在那个空间中继续增量工作。他们会制作一个更好的文本编辑器版本，制作一种略有不同的语言，或者制作一个更好的 CI 工具，制作一个更好的版本控制工具，但很少制作跨越这些界限的工具。”

Dark 的语言、编辑器和基础设施紧密集成在一起，共同简化事情。它被描述为“无部署”，这个术语是由湾区工程师杰西·弗雷泽勒创造的。

但是就像在无服务器中有服务器一样，在无部署中也有部署，你不必去想它，Biggar 说。该公司宣称在黑暗中部署需要 50 毫秒。

“当您在函数或 HTTP/事件处理程序中编写新代码时，我们会将抽象语法树的差异(我们的编辑器和服务器在幕后使用的代码表示)发送到我们的服务器，然后当请求到来时，我们会运行该代码。所以部署只是对数据库的一个小的写入，它是即时的和原子的。我们的部署如此之快是因为我们将部署缩减到了最小，”他在[的博客帖子](https://medium.com/darklang/how-dark-deploys-code-in-50ms-771c6dd60671)中解释道。

## 语言、编辑器和基础设施相互交叉

他称黑暗是一种抽象，一种凌驾于云端的语言。它涉及那些以前写过后端的人所熟悉的原语。

“如果你用 Rails、Node 或 Express 或 Django 写过任何东西，这些都是标准的原语，”他说。

结构化编辑器对您编写的代码进行结构化，以防止出现错误。它不会让你写胡言乱语。不可能写出语法错误，因为没有解析器。每一次按键都会修改抽象语法树( *AST* )，类似于 [Paredit](http://danmidwood.com/content/2014/11/21/animated-paredit.html) 、 [Sketch-n-Sketch](https://ravichugh.github.io/sketch-n-sketch/) 、[豆腐](https://gregoor.github.io/tofu/)、 [Prune](https://www.facebook.com/notes/kent-beck/prune-a-code-editor-that-is-not-a-text-editor/1012061842160013/) 和 [MPS](https://www.jetbrains.com/mps/) 。

函数式/命令式混合语言受到了 [Elm](https://elm-lang.org/) 、 [Rust](https://www.rust-lang.org/) 、 [OCaml](https://ocaml.org/) 、 [Swift](https://swift.org/) 、 [Ruby on Rails](https://rubyonrails.org/) 、 [Clojure](https://clojure.org/) 和 [TypeScript](https://www.typescriptlang.org/) 的影响。

“你仍然以一种很大程度上命令式的方式编码，但是我们已经受到函数式语言的很多影响，”他说。

“我们尽量不在语言上做太多创新。我们做有趣的事情是在边界上——编辑器和语言之间的边界，语言和基础设施之间的边界，语言和编辑器之间的边界，特别是这三者的交界处。”

根据千纱的说法，尽管他们研究了现有的语言，但它们并不真正适合他们试图做的事情。

“JavaScript 很棒，但它不是为直接进入分布式系统而设计的。我们的编辑器的工作方式…它已经知道你在写什么代码，我们知道它不会破坏什么，”她说。

此外，如果他们只使用一种语言，那么他们会把所有的时间花在添加更多的语言上，而不是构建更多的功能。

它使用[特征标志](https://thenewstack.io/what-we-mean-by-feature-flags/)作为一切的关键。功能标志使开发人员能够隐藏功能，向有限的一组用户提供访问权限，或者立即执行 kill switch。

## 内置功能标志和监控

一切都被写成一个特性标志，提供了安全性。特征标志创建沙箱。您正在编辑的所有代码都被锁定，先前的版本仍在运行，并且在您同意之前不会被释放。然后，它可以被逐步发布给一定比例的用户，这样你就可以看到它是如何工作的，直到百分之百。

今天，开发人员可以在那里使用基于浏览器的集成测试。未来，Dark 将增加单元测试和功能测试。它将添加版本控制。

“我们希望这些成为你可以追溯历史的一个分支，就像 Git 一样，”他说。

语言、编辑器和基础设施的紧密集成也提供了从黑暗编辑器到您的实时生产系统的可观察性。每一个痕迹都被记录下来。它不再需要单独的监控、跟踪、检测、日志记录和错误处理。

“我喜欢跟踪功能，它允许我在创建新端点或在后端进行更改时查看实时数据。没有什么比这更好的了，”蔡斯·奥利维耶里说，他使用 Dark 创建了一个提供个性化航班服务的订阅服务[。](https://usealtitude.com/?source=post_page---------------------------)

[Birb](https://hellobirb.com/?source=post_page---------------------------) ，一个项目跟踪工具，是 Dark 的另一个产品用途。

Biggar 在回答 Hacker News 上提出的问题[时写道:“Dark 是为那些想要构建后端的现有开发者而构建的，而不是新手。”。它的目标是两个主要领域:客户端应用程序的后端，如移动应用程序，或用 React、Vue、Angular 编写的单页 web 应用程序；以及在现有的基于微服务的架构中构建新的服务。](https://news.ycombinator.com/item?id=20394166)

它旨在帮助您以很少甚至没有扩展和维护开销的方式构建后端服务。

“另一方面，如果你正在构建像嵌入式系统、定理证明器或机器学习模型这样的东西，Dark 在很多年内都不会支持这种应用，”他说。

[Andre ius Bartulis](https://twitter.com/AndriusBartulis/status/1161217768097759232)，Cre8ion 的技术负责人，在一条名为 Dark 的推文中写道，“这是目前编程语言/平台领域最令人兴奋和雄心勃勃的项目之一。”

*另请参见“[深度潜水:从编辑器到基础设施不到 50 毫秒](https://thenewstack.io/dark-deep-dive-from-editor-to-infrastructure-in-less-than-50-milliseconds/)”*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>