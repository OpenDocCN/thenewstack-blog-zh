# JavaScript 程序员需要了解的关于 Transpilers 的知识

> 原文：<https://thenewstack.io/javascript-transpilers-need-know/>

想要跟上 ECMAScript 的步伐，同时又不想落后于那些还没有最新 JavaScript 特性的浏览器吗？或者在即将到来的特性成为标准之前对其进行试验，这样您就可以告诉 ECMAScript 哪些特性适合您，哪些不适合？或者只是利用让 JavaScript 在大型项目中更高效的工具？有运输工具可以帮你做这些。

Transpilers 将代码从一种语言转换为另一种语言，过去更多的是替代编程语言，如 T2 coffee script T3、T4 ClojureScript T5 和 Elm T7，甚至使用 C 和 C++语言，如 Emscripten，它将 LLVM 字节码转换为 asm.js 代码。Mozilla 的战略和研究总监 Dave Herman 指出，这并不是要取代 JavaScript“多种网络编程模式可以愉快地共存，甚至提供健康的竞争和思想的交流。”

## 扩展 JavaScript

类似地，他认为像 [TypeScript](https://www.typescriptlang.org/) 、 [PureScript](http://www.purescript.org/) 、 [Flow](http://flowtype.org/) 和 [JSX](https://facebook.github.io/jsx/) 这样为 JavaScript 添加定制扩展的 transpilers“对网络来说很棒”

TypeScript 是 JavaScript 的一个超集，具有可选的静态类型，加上使编写更高效的工具，具有重构以及检测错误，从方法名称中的拼写错误到由于类型错误而无法工作的操作。您可以在 JavaScript 中试验类型安全，保持人类可读的 JavaScript，而不会被其他语言如 Dart 和 CoffeeScript 所束缚。

当 Babylon.js 在 TypeScript 中重写时， [David Catuhe](http://blogs.msdn.com/b/eternalcoding/archive/2014/04/28/why-we-decided-to-move-from-plain-javascript-to-typescript-for-babylon-js.aspx) 指出“使用 Babylon.js 的开发人员将看不到以前用 JavaScript 开发的版本和用 TypeScript 开发的新版本之间的区别。”他还指出，移植到 TypeScript 帮助他找到了代码中一直存在的许多小错误。

> “拥有一个 transpiler 意味着开发人员可以在编写时接触到更新的特性和 API，这对整个社区都有帮助”——Henry Zhu。

对于编写大量代码的大型团队来说，这些好处可以极大地提高生产率。这就是微软在 2011 年启动 TypeScript 项目时所寻求的。Office Online web apps 有超过 100 万行代码，“当时没有很多工具可以用来构建这样的应用，”TypeScript 团队的前项目经理 Jonathan Turner 告诉我们。计划是使用强大的开发工具支持的静态类型获得更好的 JavaScript 代码，微软开发人员已经习惯了其他语言。

除了 VS Code 和 Visual Studio 中的 TypeScript 支持，还有 Sublime、Emacs 和 Vim 的 TypeScript 插件，以及越来越多的工具中的支持。transpiler 已被 Angular、Asana 和 Dojo 等项目采用，Mozilla 的 Flash 替代品 Shumway，以及 Babylon.js WebGL 框架和 vorlon.js 远程 JavaScript 调试工具。

在微软内部，TypeScript 被 Bing、Visual Studio 和 Visual Studio Online、Azure 和微软的 Xbox 团队使用，但它也在 Adobe、Google、Palantir、Progress(针对 NativeScript)和 SitePen 等公司以及易贝分类广告集团中使用。

除了扩展 JavaScript 之外，TypeScript 还转换您的代码以匹配多种 ECMAScript 标准，这为您提供了一种以更少的努力支持多种浏览器的方法，并在早期尝试提议的 ECMAScript 标准。

开源的 [Babel transpiler](https://babeljs.io/) 也提供了这个特性，这是另一个 JavaScript trans piler。

Babel core 团队的 [Henry Zhu](https://github.com/hzoo) 解释说:“Transpilers 允许开发人员编写面向未来的代码，尽管这种语言的当前版本并不是在所有环境下都受支持。“例如，如果您支持没有任何 ES2015 功能的 Internet Explorer，您将不得不转换文件来实现这一点，因为 IE 不知道新的语法。Babel 是这样一个层，它允许你不必考虑你使用的是什么浏览器，也不必指定你需要传输哪些特性。浏览器需要时间来实现这个规范，而且是逐步实现的。如果没有自动更新功能，那么用户可能永远不会更新他们的 JavaScript 版本，所以编写新版本 JavaScript 的唯一方法就是 transpile。”

朱指出，就像打字稿一样，Babel 不仅仅在翻译方面有用。“Babel 是一个通用的 Javascript 转换工具。这不仅仅是将 ES6 移植到 ES5。”有一千多个插件扩展巴别塔；"人们正在为特定的库编写插件，为像林挺这样的东西编写工具，为浏览器进行优化，以及缩小化."

## 规模化标准

另外，朱说，“拥有一个 transpiler 意味着开发者可以在编写时接触到新的特性和 API，这对整个社区都有帮助。”

“在 TC-39 从第 0 阶段到第 4 阶段的阶段过程中，如果有人为它编写了一个巴别塔插件，规范的创建者将能够获得对提案的反馈，”朱说。“因为有如此广泛的用户基础，它允许许多用户尝试实验性功能，这有助于将功能塑造成更好的功能，而不是仅仅由语言作者批准，而没有经过太多的‘真实世界’测试。因为许多提案都在 Github 上，任何人都可以在提案进行的过程中对提案的未来提出意见。”

赫尔曼热衷于他所谓的“大规模采用 transpiled 标准轨道技术，尤其是巴别塔的成功。对于开发人员来说，直接的吸引力是利用 JavaScript 的改进，甚至在引擎(在浏览器或 Node.js 中)本地支持它们之前。因为这些特性是基于标准的，所以开发人员可以采用它们，而不用担心重大的不兼容更改。在快速发展的 JavaScript 生态系统中，很难夸大这对开发者的价值。”

ECMAScript 标准的编辑、微软 Edge 团队的高级项目经理 Brian Terlson 对此表示赞同。“运输工具非常重要。JavaScript 程序员一般都希望使用最新的特性。迎合最小公约数很惨，没人愿意做。transpilers 让你做的是用你喜欢的新奇语法编写代码，这使你更有效率，使你的应用程序可维护——并将其编译成运行在老式浏览器上的东西，你希望它不存在于市场上，但不幸的是它存在。Transpilers 在 JavaScript 社区编写代码的方式上具有变革性。”

Herman 说，早期使用和来自开发者的反馈会导致良性循环。“Transpilers 引发了新功能的早期采用和社区实验的热潮。它们让 Web 开发人员能够在真实的生产应用程序中尝试功能，并让他们控制升级到最新版本功能的频率和时间。这意味着更多的 Web 开发人员参与到标准跟踪功能的早期审查中，这使他们在标准化过程中拥有更大的发言权，并最终导致更好的标准。”

“多亏了 transpilers，未来版本的功能继续得到大量早期采用和实验。装饰器使得抽象类定义中的常见模式成为可能，并且在 Angular、Ember 和 React 等 Web 框架中很受欢迎，”Herman 说。Ember.js 社区是 Babel 的早期采用者，Herman 说这导致了 ECMAScript 2015 中模块系统的大量可用性反馈。

泰尔森说，反馈也有助于装饰者的标准化。“在 transpilers 中早期实现的特性可以是非常大的、引人注目的特性，比如 decorators 这有助于迭代这些功能的设计。”

“如果你知道有一个功能真的能改善你写的代码和你正在开发的应用程序，”他建议，“只要在 transpiler 或 polyfill 中找到它，使用它，并给我们反馈。”

## 新功能，更快

Transpilers 是处理先有鸡还是先有蛋的问题的一种方式，新特性只有在实现后才能进入 ECMAScript。但是，浏览器供应商不愿意实现尚未标准化的功能，尤其是因为这可能导致开发人员跟不上在标准化过程中发生变化的功能规范。

ECMAScript 2015 不需要以前的实现；“结果，”Terlson 解释说，“在我们批准了代理等某些功能后，实施者遇到了一些问题，但这些问题并没有反映在规范中，因此我们必须在事后进行更改。这凸显了在批准标准之前确保某个特性可以按指定方式实现的重要性。”尾调用优化也有类似的问题，朱指出这两个特性都不能在 transpilers 中尝试，这可能不是巧合。

在一种语言的新版本完全出炉之前，语言的维护者需要来自程序员的反馈。泰尔森认为，运输工具是其中很大的一部分。“Transpilers 正在帮助我们获得语法方面的反馈。我们真的很幸运，拥有像 Babel 和 TypeScript 这样的工具，可以让我们在实现浏览器之前尝试语法。对于某些功能，如果我们能够获得 transpiler 或 polyfill 实现，再加上一个浏览器，我们可以相当确信它们会起作用。”

Transpilers 可以比浏览器更快地开发新功能，Herman 指出，“Babel 是用 JavaScript 实现的，而浏览器是用 C++实现的，所以功能更容易设计。有些功能在与整个浏览器集成时可能会面临更棘手的挑战。JavaScript 引擎都有复杂的多层实时(JIT)编译架构，这通常意味着一个特性需要实现多次，每层一次。浏览器引擎开发团队的职责远不止实现 JavaScript 特性，所以他们必须平衡他们的优先级。”

transpiler 不能给你所有的新功能，Herman 指出，“有些功能，像 ECMAScript 2015 的代理，或者当前的 SharedArrayBuffer 提案，基本上不可能用 trans piler 实现。其他的，比如 ECMAScript 2015 的符号，可以部分实现，但是有一些已知的限制。后一类需要开发人员的一些关注，他们必须确保不要依赖 transpiler 无法正确实现的行为。”

随着 ECMAScript 标准的发展，Transpilers 也不能使您免受 JavaScript 变化的影响。“有一个警告，”特尔森警告说；“我们将听取使用 transpilers 特性的开发者的反馈，规范可能会因此而改变。我们可能会在规范发布前对其进行突破性的修改，因此我们建议您在使用标准之前的功能时要谨慎。”

但即使这样，他们也能帮助你过渡，赫尔曼说。“当需要升级到 transpiler 的新版本时，由于对实验性语言特性的不兼容更改而使其破坏您的代码仍然是令人沮丧和耗时的。因此，像 Babel 这样的 transpilers 允许你设定自己对不稳定性的容忍度。如果你选择使用更具实验性的特性，你会享受到新功能的优势，但你也可能不得不应对更多的流失。或者，您可以选择更保守的设置来降低不兼容更改的风险，同时将自己限制在更稳定的语言功能的较小集合中。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>