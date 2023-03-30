# 认识 Bun:一个适用于整个开发生命周期的 JavaScript 运行时

> 原文：<https://thenewstack.io/meet-bun-a-javascript-runtime-for-the-whole-dev-lifecycle/>

作为运行 JavaScript 和 Typescript 应用程序的替代产品， [Bun，](https://bun.sh/)是一个新的 JavaScript 运行时，由 [JavaScriptCore](https://github.com/gtk2hs/webkit-javascriptcore) 引擎构建，旨在成为一个以闪电般的速度捆绑、传输和运行代码的一体化工具。

Bun 由 Stripe 的前前端工程师[贾勒德·萨姆纳](https://github.com/Jarred-Sumner)创建，旨在“在浏览器之外运行世界上大多数的 JavaScript，通过更好、更简单的工具为未来的基础设施带来性能和复杂性的增强，以及开发人员的生产力，”萨姆纳在由 [Ping Labs](https://ping.gg/) 首席执行官西奥·布朗主持的 [YouTube 采访](https://www.youtube.com/watch?v=rL4qpniIR7o)中说。

在渲染 React 服务器端时，Bun 每秒处理的 HTTP 请求大约是 Node.js 的三倍。WebSocket、ReadableStream 和 fetch 是内置的。邦也是一个 transpiler，所以打字稿和 JSX 的工作开箱即用。因为 Bun 实现了 Node.js 的模块解析算法，所以 npm 包也能工作。

Sumner 说:“JavaScript 的速度如此之慢让我感到沮丧，我认为，我知道，JavaScript 可以快得多。”

## 战胜缓慢的迭代周期

正是速度首先带来了对新事物的需求，导致了 Bun 的诞生。当时，萨姆纳正在 Next.js 中开发一款游戏，但对迭代周期的速度感到沮丧。  第一个解决方案是将 [esbuild](https://esbuild.github.io/) builder 与 [Next.js](https://nextjs.org/) 一起使用，但这并没有带来他想要的结果，即使在获得了与插件一起工作的技术之后。萨姆纳的下一个想法是构建一个捆绑器和一个传输器，但最终，他构建了一个包含捆绑器和传输器的运行时。

在采访中，萨姆纳解释说，他知道 JavaScript 可以更快，因为他有过用 Objective-C 编写本机代码的经验。苹果的 [NSLog](https://developer.apple.com/documentation/foundation/1395275-nslog) 的速度，相当于 JavaScript 中 console.log 的 Objective-C，向他展示了写入终端的速度有多快。这是一个洞察可能减缓 JavaScript 应用程序的工作流的窗口。

在研究了许多构建 Bun 的语言之后，Sumner 最终选择了相对鲜为人知的 Zig T2。Zig 的“comptime”元编程方法有助于达成交易。Comptime 是基于编译时代码执行和惰性评估的元编程。

在 Zig 中，程序员可以在编译时标记变量，向编译器保证变量的每次加载和存储都在编译时执行。本质上，comptime 可以在编译时运行任意代码。“我只是尝试了一下，并意识到 comptime 对于编写快速代码来说是一个非常强大的工具，”Sumner 解释道。

在 Bun 之前，Sumner 从未在 Zig 中写过一行代码。他认为 discord 服务器的帮助是他能够完全用 Zig 写 Bun 的原因之一。

Comptime 用于词法分析器，称为“lexer”，是 Bun 解析中最慢的部分之一。它的工作是遍历所有文本，以确定当前令牌是有效的标识符还是关键字。由于 comptime 的原因，Bun 使用编译时生成的位集。这个过程使 Bun 的性能提高了 2%。

对于技术挑战，其中有很多，萨姆纳特别指出，“在 Bun 上工作真正教会我很多的事情之一是如何阅读错误信息。”他指的是 Zig 错误信息中的措辞看起来更像编译器中的措辞。例如，单词 token 在词法分析或语法分析中最常见，但在他收到的错误消息中却非常常见。

Sumner 计划将来至少有两个权限模型，其中一个是二进制死代码消除。该模型将打开和关闭特性，因此如果某个特性没有在应用程序中使用，Bun 将没有该代码。由于每次访问权限都会影响性能，因此根据关闭了多少功能，性能影响会更小。

眼下，萨姆纳推荐[铁路](https://railway.app/)或 [fly.io](http://fly.io) 作为最佳部署选项。将有一个内置的选项，但现在还为时过早，任何额外的细节。Express、Angular 和 Jest 的测试 API 是 Sumner 正在努力添加适当支持的特定技术，但对于一般的 JavaScript 框架，他说，“我不会说我在与任何框架竞争，因为我希望所有这些框架都使用 Bun。”

## 把虫子抖出来

最后但同样重要的是，测试。小圆面包是新的，它有虫子。萨姆纳意识到了这一点，并认为缺乏广泛的测试是错误百出的原因之一。关于这一点，他说，“bun 没有足够的测试覆盖率，这就是为什么它有这么多 bug。”Bun 有一个 JavaScript 测试运行器，cli 命令是`bun wiptest`。

开发者和萨姆纳都对 Bun 感到非常兴奋，虽然它仍然是新的，但对它有很高的期望。Sumner 说，“我一直从‘它需要尽可能地与现有的生态系统合作，因为人们不应该重写他们的代码’的角度出发，但也许我应该开始更多地考虑如果我们制造/什么新东西是可能的，因为 APIs bun 使之成为可能。”

[https://www.youtube.com/embed/rL4qpniIR7o?feature=oembed](https://www.youtube.com/embed/rL4qpniIR7o?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>