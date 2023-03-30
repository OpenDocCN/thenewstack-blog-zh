# WebAssembly 允许开发人员组合语言

> 原文：<https://thenewstack.io/webassembly-to-let-developers-combine-languages/>

如果有一种方法可以使用你想要的任何一种编程语言的库并将它们编译在一起会怎么样？如果开发人员不是在遥远的未来，而是在年底就能做到这一点，那会怎么样呢？

据字节码联盟[技术指导委员会](https://github.com/bytecodealliance/governance/blob/main/TSC/charter.md)、 [Bailey Hayes](https://github.com/ricochet) 新任命的主任称，这正是[字节码联盟](https://bytecodealliance.org/)今年计划解决的问题。

“我们正在制定路线图，”Hayes 说，他也是 Wasm 云公司的董事。“我们有这个工作的演示——泡泡糖，一些电线，它工作了。但是我希望我们能有更多真正的演示，可能在今年年底。我们说的是几个月的事，不是几年。”

字节码联盟基金会是一个非营利组织，致力于实现基于 W3C 标准的软件基金会，包括 [WebAssembly](https://thenewstack.io/key-concepts/wasm/) (又名 Wasm)和 [WebAssembly 系统接口(WASI)](https://wasi.dev/) 。Hayes 说，该联盟最初由 [Mozilla](https://thenewstack.io/mozilla-and-the-planet-incinerating-ponzi-grifters/) 、 [Fastly](https://thenewstack.io/glitch-fastly-developer-experience/) 、 [Intel](https://thenewstack.io/intel-ceo-sheds-light-on-emerging-software-strategy/) 和 [Red Hat](https://thenewstack.io/red-hat-helps-make-kubernetes-security-more-accessible/) 于 2019 年创立，Wasm 生态系统的第一个目标是确保它保持安全和默认拒绝。

## WASI 是什么？

最初，WASI 被称为“ [POSIX](https://pubs.opengroup.org/onlinepubs/9699919799.2018edition/) -like”，指的是“便携式操作系统接口”——在维基百科中被定义为“由 IEEE 计算机协会指定的用于维护操作系统之间兼容性的一系列标准”然而，这种类比被证明是令人困惑的。

“这并不意味着是 POSIX——这是一个常见的误解，”Hayes 告诉新堆栈。“我们真正的意思是，有一套你所期望的通用 API，他们(开发人员)几乎可以像对待你所针对的运行时一样对待它们，这让你可以在浏览器之外运行得很好。几乎每个应用程序都依赖或期望某些东西。如果没有这些，那么 WebAssembly 模块的功能就会受到很大的限制。”

WASI 为开发人员提供了访问文件系统、执行标准 I/O 等功能，以及开发人员从代表标准 C 库的 [libc](https://man7.org/linux/man-pages/man7/libc.7.html) 中获得的其他功能。Hayes 说，开发人员将称它们为标准外部函数接口(FFI)绑定，但实际上它们是主机运行时以能力驱动的方式给予 WebAssembly 模块的句柄。

海斯说:“这就是 WASI——一套 API，一套通用的 API，如果你以这套通用的 API 为目标，你现在可以在浏览器之外或任何 T2 JavaScript T3 运行时之外运行得很好。”。

## WASI 预览版 2 的预览:组件模型

这是 WASI 预览版 1 的工作，它是稳定的。字节码联盟目前正在开发 WASI 预览版 2，预计将于今年推出。

“我认为这将是一件大事，”海耶斯说。“这让我们想到了我们一直在研究的新提案，另一个标准。它开始被称为接口类型提案，但现在已经合并为我们所说的组件模型。”

[组件模型](https://github.com/webassembly/component-model)基本上是一种新的操作模型——人们构建 WebAssembly 应用程序的新方式。这将允许开发人员打破语言孤岛并结合其他语言的库，使用 Wasm 作为语言" [one ring](https://lotr.fandom.com/wiki/One_Ring) "来绑定它们。

“当今世界的运作方式是，因为你存在于 JavaScript 生态系统中，我存在于 Rust 生态系统中，我们不能相交，这意味着整个系列的开发人员，你的前端人员和你的后端人员几乎相互敌对，”海斯说。“这是组件模型的一部分，我可以以一种可移植的方式无缝地跨越语言界限。”

她解释说，有了组件模型，开发人员可以用 C++构建一个库，用 [Rust](https://thenewstack.io/developers-most-likely-to-learn-go-and-rust-in-2023-survey-says/) 构建一个库，用 [Python](https://thenewstack.io/key-concepts/python/) 或任何其他语言(包括 JavaScript)构建一个库，并能够像乐高积木一样将它们组装在一起，形成一个完整的应用程序。由于安全性是 WebAssembly 的首要考虑因素，他们能够以一种安全的方式完成这项工作。

“人们将理解的最简单的类比是，这就像从静态库、静态可执行文件到能够使用动态库——但是在 WebAssembly 模块和严格类型方面，并且能够将这些类型暴露给作为组件的其他 WebAssembly 模块，”Hayes 说。“这意味着我们完全改变了现在编写软件的方式。这意味着所有这些存在了 20 年的孤岛都不复存在了。”

不难看出这对软件开发来说是多么具有革命性，

目前，重点是 Rust，JavaScript，C++，但也有人在从事 [Ruby](https://thenewstack.io/ruby-devs-try-sinatra-before-moving-up-to-ruby-on-rails/) ，Python 和 [Go](https://thenewstack.io/developers-most-likely-to-learn-go-and-rust-in-2023-survey-says/) 。但它并不局限于这些语言，海斯强调说。

“它将从小规模开始，我认为它将呈指数级增长，”她说。

## 构建组件注册表

字节码联盟也有一个特别兴趣小组致力于构建一个组件注册中心，尽管 Hayes 说这仍然是“非常早期的阶段”它的目标是设计一个协议，以便其他注册中心可以使用组件的语言，比如知道组件的类型。

“同样，我们必须回到我们设计自己的注册中心和自己的协议的原因，这样我们就可以在内容哈希方面引入最新的安全技术，确保所有内容都以正确的方式签名，并拥有不可变的日志。”

以 JavaScript 为例，其中的生态系统通常涉及[NPM](https://thenewstack.io/is-npm-a-hotbed-of-malware/)——节点包管理器。

“在注册表中，如果你说 npm 安装，可能会有一些我们发明的新标志，但一些新标志说我正在处理一个组件，它会拉入一个使用我们称为 WARG 协议的组件 WebAssembly 注册表协议，”她说。“这将使你能够安装理论上用任何语言编写的组件，所以你不必学习另一种语言。”

然后，开发人员只需要知道需要库中的哪些部分，以及要调用什么函数。上周在云原生安全大会上，[凯尔·布朗](https://github.com/Kylebrown9)提供了一个名为 Warg (WebAssembly ReGistry)的新协议的概述，并发出了一个[的呼吁，要求安全研究人员](https://www.youtube.com/watch?v=yjPRcGCwaTI)帮助注册。

“我们不希望犯和我们之前的所有注册机构一样的错误，”Hayes 说。

## 开发者可以从 WebAssembly 开始

Hayes 说，虽然 WASI 预览版 2 的细节仍在解决中，但 WebAssembly 已经标准化了很多，开发者可以进行试验。

她说:“WASI 预览版 1 以及 WebAssembly 规范 1.0 和 2.0 在任何地方都受到非常好的支持。”“比方说，你想使用目前网络上不支持的语言，并在前端运行它们，这是一个很好的可靠用例。”

她补充道,[工具链是一个很好的起点。例如，对于了解 JavaScript 并希望学习一点 C++的人，或者了解 C++并希望学习一点 JavaScript 以使他们的应用程序在 web 中工作的人来说，这很有帮助。铁锈是另一个很好的起点。](https://emscripten.org/)

“一旦网络组装工作开始进行，就好像生锈了一样，”Hayes 说。“因此，这两项技术确实随着时间的推移而共同发展，这对于开始使用 Rust 和 WebAssembly 的人来说意味着非常无缝。这是实实在在的开发者体验。”

例如，使用…

…以 wasm32 二进制为目标。然后可以用 Wasm 运行时(如 Wasmtime)运行。Wasmtime 使 Wasm 模块在许多不同的地方成为可能，比如在桌面上、在边缘、作为无服务器功能等等。，海斯解释道。

她总结道，字节码联盟正在做的工作是为 Wasm 建立一个默认安全、功能驱动和可移植的软件基础。他们希望生态系统扩展到许多不同的环境，从网络到边缘。她鼓励任何对联盟内的任何项目感兴趣的人观看[每月社区流](https://www.youtube.com/live/9pLa7PUhPYA?feature=share&t=25)了解概况，并加入 [Zulip](https://bytecodealliance.zulipchat.com/) 讨论字节码联盟项目的开发。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>