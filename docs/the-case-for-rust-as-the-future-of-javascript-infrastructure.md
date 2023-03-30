# Rust 会是 JavaScript 基础设施的未来吗？

> 原文：<https://thenewstack.io/the-case-for-rust-as-the-future-of-javascript-infrastructure/>

[](https://www.linkedin.com/in/leeerob/)

[Lee Robinson](https://www.linkedin.com/in/leeerob/)

[Lee Robinson 是一名开发人员、作家和创作者，他与 Vercel 的客户密切合作，并通过教育和培训帮助发展 Next.js 社区。在加入 Vercel 之前，他在一家价值 100 亿美元的零售商处负责网络开发。](https://www.linkedin.com/in/leeerob/)

[](https://www.linkedin.com/in/leeerob/)[](https://www.linkedin.com/in/leeerob/)

[Rust](https://www.rust-lang.org/) 最初由 Mozilla 创建，是一种快速、可靠、内存高效且非常受欢迎的编程语言，旨在提高性能和安全性。事实上，它已经被选为最受欢迎的编程语言六 年一 排在栈溢出调查并且被广泛应用于超大规模公司，如[](https://engineering.fb.com/2021/04/29/developer-tools/rust/)[苹果](https://twitter.com/oskargroth/status/1301502690409709568)[亚马逊](https://aws.amazon.com/blogs/opensource/why-aws-loves-rust-and-how-wed-like-to-help/) ，[Rust 现在正在取代 JavaScript 网络生态系统的一部分，如 minification (Terser)、transpilation (Babel)、formatting(prettle)、bundling (webpack)、林挺(ESLint)等等。让我们深入探讨一下为什么这种趋势越来越流行，越来越被广泛采用。](https://twitter.com/ryan_levick/status/1171830191804551168)

## **什么是铁锈？**

Rust 帮助开发人员编写节省内存的快速软件。它是 C++或 C 等语言的现代替代品，关注代码安全和简洁的语法。Rust 与 JavaScript 截然不同。JavaScript 试图找到不使用的变量或对象，并自动将它们从内存中清除。这叫做 [垃圾收集](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)) 。这种语言将开发人员从考虑手工内存管理中抽象出来。有了 Rust，开发人员可以更好地控制内存分配，而不会像 C++那样痛苦。

*“Rust 使用了一种相对独特的内存管理方法，融合了内存‘所有权’的思想。基本上，Rust 跟踪谁可以读写内存。它知道程序何时在使用内存，并在不再需要时立即释放内存。它在编译时强制执行内存规则，使得几乎不可能有运行时内存错误。您不需要手动跟踪内存。编译器会处理它。”——*[](https://blog.discord.com/why-discord-is-switching-from-go-to-rust-a190bbca2b1f)

 *## **领养**

除了上面提到的公司，Rust 还被用于流行的开源库，如:

*“Rust 是我们团队的力量倍增器，押注 Rust 是我们做出的最佳决定之一。除了性能，它的人体工程学和对正确性的关注也帮助我们驯服了 sync 的复杂性。我们可以在类型系统中编码关于我们系统的复杂不变量，并让编译器为我们检查它们。”——*[](https://dropbox.tech/infrastructure/rewriting-the-heart-of-our-sync-engine)

 *## **从 JavaScript 到 Rust**

JavaScript 是使用最广泛的编程语言，可以在任何装有网络浏览器的设备上运行。在过去的 10 年里，围绕 JavaScript 已经建立了一个庞大的生态系统:

*   开发者想要将多个 JavaScript 文件捆绑成一个。
*   开发人员想在支持旧浏览器的同时编写现代的 JavaScript。
*   开发者希望生成尽可能小的文件。
*   更漂亮的:开发人员想要一个能正常工作的固执己见的代码格式化程序。
*   ESLint :开发人员希望在部署之前发现他们代码的问题。

已经编写了数百万行代码，甚至修复了更多的错误，为今天的 web 应用程序的发布奠定了基础。所有这些工具都是用 JavaScript 或 TypeScript 编写的。这已经很好地工作了，但是我们已经用 JS 达到了峰值优化。这激发了一类新的工具，旨在极大地提高 web 构建的性能。

### **SWC**

[【SWC】](http://swc.rs/)创建于 2017 年，是一个基于 Rust 的可扩展平台，用于下一代快速开发者工具。它被 Next.js、Parcel 和 Deno 等工具以及 Vercel、字节跳动、腾讯、Shopify 等公司使用。SWC 可以用于编译、缩小、捆绑等等——并且是为扩展而设计的。您可以调用它来执行代码转换(内置的或自定义的)。运行这些转换是通过像 Next.js 这样的高级工具进行的。

### **德诺**

[Deno](https://deno.land/) ，创建于 2018 年，是一款使用 [V8](https://v8.dev/) 并使用 Rust 构建的简单、现代、安全的 JavaScript 和 TypeScript 运行时。这是一个取代 Node.js 的尝试，由 Node.js 的原创作者编写，虽然是在 2018 年创建的，但直到 2020 年 5 月 才打到 [v1.0。Deno 的 linter、代码格式化程序和文档生成器是使用 SWC](https://deno.com/blog/v1) 构建的 [。](https://twitter.com/devongovett/status/1369033422002389000)

### **esbuild**

[esbuild](https://esbuild.github.io/) 创建于 2020 年 1 月，是一个比现有的用 Go 编写的工具快 10-100 倍的 JavaScript bundler 和 minifier。

“我正试图创建一个构建工具，它 a)对给定的用例(绑定 JavaScript、TypeScript，可能还有 CSS)工作良好，b)重置社区对 JavaScript 构建工具快速性的期望。在我看来，我们目前的工具太慢了。”— [*埃文*](https://news.ycombinator.com/item?id=22336334) *，esbuild* 的创建者

在 esbuild 发布之前，用系统编程语言(如 Go 和 Rust)构建 JavaScript 工具是相当小众的。在我看来，esbuild 激发了更广泛的兴趣，试图让开发者工具更快。Evan 选择使用 Go:

经过足够的努力，生锈的版本可能会以同样的速度工作。但是从更高的层面来说，和围棋一起工作要愉快得多。这是一个附带的项目，我必须为它感到有趣。”——[*埃文*](https://news.ycombinator.com/item?id=22336284) *，esbuild 的创建者*

一些人认为 Rust 可以表现得更好，但两者都可以实现 Evan 影响社区的最初目标:

*“即使只有基本的优化，Rust 也能胜过超级手动调整的 Go 版本。这是一个巨大的证明，与我们不得不深入研究 Go 相比，用 Rust 编写高效的程序是多么容易。”——*[*不和*](https://blog.discord.com/why-discord-is-switching-from-go-to-rust-a190bbca2b1f)

### **罗马**

[罗马](https://rome.tools/blog/2020/08/08/introducing-rome) ，创建于 2020 年 8 月，是一个 linter，编译器，bundler，测试运行器，以及更多用于 JavaScript，TypeScript，HTML，JSON，Markdown，CSS 的工具。他们的目标是替换和统一整个前端开发工具链。它是由塞巴斯蒂安·麦肯齐创造的，他也创造了巴别塔。

那为什么要重写一切呢？

对 Babel 进行必要的修改，使其成为其他工具的可靠基础，这需要对所有东西进行彻底的修改。该架构绑定到我在 2014 年学习解析器、自动测试系统和编译器时做出的最初设计选择。”——[*塞巴斯蒂安·麦肯齐*](https://rome.tools/blog/2020/08/08/introducing-rome)

 *Rome 目前是用 TypeScript 编写的，在 Node.js 上运行。但是他们现在正在使用 RSLint 解析器和他们自己的访问者系统进行 AST 遍历，在 Rust 中进行 [重写。](https://rome.tools/blog/2021/09/21/rome-will-be-rewritten-in-rust)

### **NAPI**

Rust 与 Node.js 的集成比其他低级语言要好。 [皮娜-rs](https://napi.rs/) 允许你用 Rust 构建预编译 Node.js 附加组件。它为交叉编译和发布本地二进制文件到 NPM 提供了一个现成的解决方案，不需要`node-gyp`或`postinstall`脚本。您可以构建一个 Rust 模块，可以直接从 Node.js 调用，而不需要创建一个像 esbuild 这样的子进程。

### **Rust + WebAssembly**

[web assembly](https://webassembly.org/docs/use-cases/)(WASM)是 Rust 可以编译成的可移植的低级语言。它运行在浏览器中，可与 JavaScript 互操作，并且在所有主流的现代浏览器中都得到支持。

*“WASM 肯定比 JS 快很多，但不完全是原生速度。在我们的测试中，package 编译成 WASM 时的运行速度比本地二进制文件慢 10-20 倍。”——*[*德文·戈维特*](https://twitter.com/devongovett)

虽然 WASM 还不是完美的解决方案，但它可以帮助开发者创造极快的网络体验。Rust 团队 [致力于](https://www.rust-lang.org/what/wasm) 高质量和尖端的 WASM 实现。对于开发者来说，这意味着你可以拥有 Rust(相对于 Go)的性能优势，同时仍然可以为网络编译(使用 WASM)。

这一领域的一些早期库和框架:

这些编译成 WASM 的基于 Rust 的 web 框架并没有试图取代 JavaScript，而是与之并行工作。虽然我们还没有到那一步，但有趣的是看到 Rust 在 web 的两边都出现了:让现有的 JavaScript 工具更快，以及将 [编译成 WASM](https://rustwasm.github.io/docs/book/introduction.html) 的未来想法。一路都是铁锈。

## **为什么不生锈？**

Rust 有一个陡峭的学习曲线。这是比大多数 web 开发人员习惯的抽象层次更低的抽象层次。一旦你使用本机代码(通过 Rust、Go、Zig 或其他低级语言)，算法和数据结构比语言选择更重要。这不是银弹。

Rust 让你思考对系统编程至关重要的代码维度。它让你思考内存是如何共享或复制的。它让你思考真实但不太可能发生的情况，并确保它们得到处理。它可以帮助你以各种可能的方式编写出极其高效的代码。”——[*汤姆·麦克赖特*](https://macwright.com/2021/01/15/rust.html)

此外，Rust 在网络社区的使用仍然是小众的。它还没有达到临界采用。尽管学习 Rust for JavaScript tooling 会成为入门的障碍，有趣的是，开发人员宁愿拥有一个更快的 [工具，也不愿为](https://twitter.com/devongovett/status/1261379312898306048) 做出贡献。 [快软件胜](https://craigmod.com/essays/fast_software/) 。

目前，很难找到一个 Rust 库或框架来支持您喜欢的服务(如身份验证、数据库、支付等)。我认为，一旦拉斯特和 WASM 达到临界采用，这将解决自己。但还没有。我们需要现有的 JavaScript 工具来帮助我们弥合差距，并逐步采用性能改进。

## **JavaScript 工具的未来**

我相信 Rust 是 JavaScript 工具的未来。 [Next.js 12](http://nextjs.org/12) 开始了我们的过渡，用 SWC 和 Rust 全面取代 Babel (transpilation)和 Terser (minification)。为什么？

*   可扩展性:SWC 可以在 Next.js 中用作板条箱，而不必派生库或解决设计约束。
*   性能:通过切换到 SWC，我们在 Next.js 中实现了大约 3 倍的快速刷新速度和大约 5 倍的构建速度，并且仍有更多的优化空间。
*   WebAssembly: Rust 对 WASM 的支持对于支持所有可能的平台和在任何地方进行 Next.js 开发都是必不可少的。
*   社区:Rust 社区和生态系统是惊人的，而且还在增长。

不仅仅是 Next.js 采用了 SWC:

*“包裹像图书馆一样使用 SWC。在我们使用 Babel 的解析器和用 JS 编写的自定义转换之前。现在，我们使用 SWC 的解析器和* [*自定义 Rust*](https://github.com/parcel-bundler/parcel/tree/v2/packages/transformers/js/core/src) *中的变换。这包括全面的提升实现、依赖集合等等。这在范围上类似于 Deno 如何在 SWC 的基础上进行构建。”—* [*德文·戈维特*](https://twitter.com/devongovett)

这是 Rust 的早期阶段——一些重要的部分仍在研究中:

*   **插件:**对于许多 JavaScript 开发者来说，用 Rust 编写插件并不容易。同时，在 JavaScript 中公开一个插件系统可能会抵消性能的提升。一个确定的解决方案还没有出现。理想情况下，未来将结合 JavaScript 和 Rust。如果你想用 JavaScript 写一个插件，可能会牺牲速度。需要更高的性能？使用 Rust 插件 API。
*   捆绑:一个有趣的发展领域是`swcpack`，它是 SWC 对 webpack 的替代。它仍在开发中，但可能非常有前途。
*   如上所述，编写 Rust 并编译到 WASM 的前景很诱人，但仍有工作要做。

## **结论**

在可预见的未来，Rust 的受欢迎程度将继续增长，并对 JavaScript 生态系统产生重大影响。想象一下，在 Next.js 中使用的所有构建工具都是用 Rust 编写的，从而为您提供最佳性能。然后，Next.js 可以作为静态二进制文件[](https://en.wikipedia.org/wiki/Static_build)从 NPM 下载。对我来说，那将是一个生活(和发展)的理想世界。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>***