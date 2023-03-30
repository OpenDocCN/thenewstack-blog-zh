# web assembly:2023 年的 5 个预测

> 原文：<https://thenewstack.io/webassembly-5-predictions-for-2023/>

2022 年，WebAssembly(通常简称为 Wasm) [一跃成为焦点](https://thenewstack.io/yes-webassembly-can-replace-kubernetes/)。新的 Wasm 创业公司出现了。老牌公司宣布支持 Wasm。字节码联盟推出了许多 Wasm 标准。[云本地计算基金会](https://cncf.io/?utm_content=inline-mention)举办了两次 WasmDay 活动。Wasm 最大的用户之一 Figma 被 Adobe 以惊人的 200 亿美元收购[。](https://thenewstack.io/adobe-buys-figma-what-does-this-mean-for-web-standards/)

[https://www.youtube.com/embed/-DVcchn4T_Y](https://www.youtube.com/embed/-DVcchn4T_Y)

视频

Wasm 的核心是一种二进制格式。许多不同的语言可以编译成相同的格式，而这种二进制格式可以在各种操作系统和架构上运行。Java 和。NET 在这方面是相似的，但是 Wasm 有一个主要区别:Wasm 运行时不信任它执行的二进制文件。

Wasm 应用程序被隔离在沙箱中，只允许访问用户明确允许的资源(如文件或环境变量)。Wasm 有许多其他令人满意的属性(如非凡的性能)，但正是这种安全模型使 Wasm 在从浏览器到 edge 和物联网甚至到云的各种环境中有用。

如果说 Wasm 在 2022 年有一个趋势，那就是 Wasm 现在在浏览器之外和在浏览器之内一样成功(如果不是更多的话)。这一趋势是 2023 年大部分事情的基础。从嵌入式设备到大型数据中心，Wasm 无处不在，2023 年将成为 Wasm 年。以下是我对 2023 年 Wasm 生态系统的五个预测。

## 1.组件模型将是分水岭时刻

标准很少是生态系统中最令人兴奋的部分。有了像“组件模型”这样的名字，激起人们的兴奋确实是一场艰苦的战斗。但枯燥的名字背后，是 Wasm 给软件世界带来的最重要的创新。

组件模型描述了 Wasm 二进制文件相互交互的方式。更具体地说，这两个组件可以告诉对方它们提供了什么服务，需要满足什么期望。然后 Wasm 模块可以利用彼此的能力。这为软件开发人员提供了一种构建应用程序的新方法。开发人员可以声明他们的应用程序需要哪些组件，或者更抽象地说，他们的应用程序需要哪些功能，而不是以他们首选的源语言来查找库，然后 Wasm 运行时可以代表用户组装正确的组件集。

Wasm 最多产的贡献者之一丹·戈曼写了一篇伟大的 [综述文章](https://blog.sunfishcode.online/what-is-a-wasm-component/) 。而 Fermyon 的 [Joel Dice](https://github.com/dicej) 写了一篇 [技术概述](https://www.fermyon.com/blog/webassembly-component-model) 给那些对内部更好奇的人。

组件模型正在迅速成熟，并且已经出现了参考实现。2023 年将是组件模型开始重新定义我们如何编写软件的一年。

## 2.无服务器将是 Wasm 的最佳选择

无服务器的前景在过去几年里已经很明显了。AWS Lambda 以功能即服务(FaaS)的形式让我们看到了一种新的、简单明了的编程模型。然而，尽管无服务器概念背后的发展势头越来越大，但底层技术的运营成本却很高。而这个成本已经转嫁到了用户身上。此外，虽然 FaaS 应用程序的启动时间比容器快，但它们仍然达不到今天对 web 性能的期望。速度还有提升的空间。

Wasm 已经 [转移了无服务器格局的潜力](https://www.fermyon.com/blog/serverless-reckoning) 。Wasm 二进制文件具有几乎即时的启动时间、较小的二进制文件大小以及平台和架构中立性，只需运行当今无服务器基础设施所需资源的一小部分即可执行。

如果整个经济正在进入一个经济不确定的时期，很高兴知道 Wasm 将帮助我们节省开支，同时也推进了开发人员最喜欢的无服务器功能模型。Wasm 更快的启动时间和适度的资源消耗比基于容器的系统需要更少的计算能力，而且比 Lambda 等 FaaS 系统更便宜。

这种 Wasm 可以改变无服务器格局的认识促使 Fermyon 创建了 [Spin](https://developer.fermyon.com/spin/index) 。Spin 是一个面向开发人员的工具，用于引导、构建、测试和部署无服务器功能。Spin 的核心是其基于 Wasm 的运行时。它是开源的，已经得到了 [Fermyon Cloud](https://www.fermyon.com/cloud) 和 [微软 Azure 的 AKS](https://learn.microsoft.com/en-us/azure/aks/use-wasi-node-pools) 的支持，2023 年还会有更多。

更小、更快、更便宜、更好。这是 Wasm 在 2023 年向无服务器世界提供的组合。

## 3.Wasm 应用程序将存储在 DockerHub 和容器注册表中

包管理。从编程语言到操作系统，再到像 Kubernetes 这样的集群编排器，它都是一个必要的特性。每次我们发明一项新技术，我们似乎注定要(重新)发明一个管理该技术资产的系统。

在 2022 年初，我们看到了几种管理 Wasm 对象的竞争方法。没有人起飞。一小群工程师坚持不懈地推动 OCI 注册中心(又名 Docker 注册中心)作为存储 Wasm 的系统。但是事实是 OCI 注册格式不支持非容器工件。它是用来存储 Docker 图像的。

然后，OCI 登记处的一个重大转变改变了这一局面。OCI ( [开放容器倡议](https://thenewstack.io/open-container-initiative-creates-a-distribution-specification-for-registries/))是一个小型标准团体，致力于管理 OCI 容器(或者我们过去称之为 Docker 容器)的标准。OCI 定义了容器格式、安全模型和运行时。它还定义了容器图像如何在注册中心和客户机之间移动。

接近 2022 年底，OCI 注册工作组宣布了一种存储容器图像以外的东西的官方方法。这可能包括舵图、照片或(你猜对了)Wasm 应用程序。这个新特性被称为“工件存储”

当 DockerHub [宣布支持](https://www.docker.com/blog/announcing-docker-hub-oci-artifacts-support/) 这一新的工件存储规范时，这个信号在 Wasm 生态系统中引起了反响:我们可以简单地将我们的应用程序存储在像 DockerHub 这样的 OCI 注册表中，而不是重新发明轮子。必须在 Wasm 生态系统中完成新的工作，以使这成为现实，但这项工作正在进行中。2023 年将是 Wasm 应用在 OCI 注册中心安家的一年。

## 4.所有大型编程语言都将支持 Wasm

语言支持是 Wasm 成功的关键因素。随着每一种可以编译成 Wasm 的新语言的出现，一个新的开发人员社区获得了 Wasm 的好处。几乎所有排名前 20 的编程语言都是 [加上 Wasm 支持](https://www.fermyon.com/wasm-languages/webassembly-language-support) 。

2022 年，我们看到了 Wasm 的三大飞跃。Python [增加了支持](https://pythondev.readthedocs.io/wasm.html) 。然后 [红宝石](https://www.ruby-lang.org/en/news/2022/12/06/ruby-3-2-0-rc1-released/) 。十月，。长期以来在浏览器中支持浏览器内 Wasm 的. NET 为 Wasm 增加了更深层次的支持，允许它在浏览器 之外运行 [。](https://www.fermyon.com/blog/dotnet-wasi)

另外三种语言今年取得了一些进展，但 2023 年将标志着这些语言准备就绪。这三种语言是 Kotlin、Dart，当然还有世界上最流行的编程语言:JavaScript。

Kotlin 和 Dart 社区都积极参与了 Wasm 编译目标的构建。不过，两者都一直在等待一个特定的 Wasm 标准成熟——一个描述垃圾收集的标准，垃圾收集是语言运行时的一种工具，允许在程序执行时清理内存。我们的预测是 [Wasm-GC 提案](https://github.com/WebAssembly/gc/blob/main/proposals/gc/Overview.md) 将在 2023 年初可用并得到支持，因此 Kotlin 和 Dart 将很快发布 Wasm 编译器

然而，我们最后的语言是如此重要，以至于它值得一个特殊的预测。

## 5.JavaScript 将成为最流行的 Wasm 语言

在所有语言中，JavaScript 与 Wasm 的关系最为复杂。按照最初的设想，Wasm 将在浏览器中与 JavaScript 交互。事实上，Wasm 最初的承诺是将浏览器语言支持扩展到 JavaScript 之外。

但是假设在现实世界的用例面前会逐渐消失。

由于 Wasm 在浏览器之外，许多开发人员希望能够在任何可以运行 Wasm 的地方运行他们的 JavaScript 代码。这最好通过在 Wasm 运行时内部运行 JavaScript 来实现(而不是像在浏览器中那样在它旁边)。2022 年，我们看到几个新的 Wasm 项目专注于将 JS 引入新的运行时。其中大部分使用了一个叫做 [QuickJS](https://bellard.org/quickjs/) 的伟大开源项目。

QuickJS 有许多优点，最重要的是它完全符合最新的 JavaScript 标准。但是它并没有被设计成最快或最健壮的 JavaScript 引擎。它非常容易嵌入，以至于许多早期的 Wasm 项目都想出了将解释器编译成 Wasm，然后在 Wasm 运行时内运行 JavaScript 的方法。

但是有一个主流的 JavaScript 运行时加入了竞争。来自 Mozilla 的 [SpiderMonkey](https://spidermonkey.dev/) 引擎，以其性能和健壮性著称，正在进入 Wasm 世界。它因在 Mozilla Firefox 浏览器中的使用而闻名，但也可以在浏览器之外使用。作为一个可以不断优化它执行的脚本的运行时，SpiderMonkey 引擎将是 Wasm 世界中最快的 JS 引擎。早期数据表明，由于可以在这种环境下进行优化，在 Wasm 版本的 SpiderMonkey 中运行的 JavaScript 可能比在浏览器中运行的 JS 快 13 倍 [。](https://bytecodealliance.org/articles/making-javascript-run-fast-on-webassembly)

JavaScript 是世界上最流行的编程语言。有了像 QuickJS 和 SpiderMonkey 这样的 Wasm 运行时，Wasm 的潜力突然可以被一个巨大的开发人员社区所利用。是的，C 是第一个支持 Wasm 的编程语言。是的，铁锈有一个相当大的立足点。当然，我们也看到了 Python 和 Ruby 的发展。但是 JavaScript 将会像火箭一样飞向 Wasm 的平流层。

## 结论:2023 年是 Wasm 年

我对 Wasm 生态系统内部将会发生什么做出了五个大胆的预测。随着这些里程碑的实现，Wasm 将成为浏览器之外更有用的通用技术。在文章的开头，我提出 2023 年是 Wasm 年。鉴于这五个预测，很容易看出为什么:新特性、巧妙的用例、与 Docker Hub 的集成和广泛的语言支持结合在一起，使这成为一项有巨大前景的开发人员友好的技术。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>