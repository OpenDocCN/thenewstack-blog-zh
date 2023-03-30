# TypeScript 能否帮助更多开发者采用 ECMAScript 模块？

> 原文：<https://thenewstack.io/can-typescript-help-more-developers-adopt-ecmascript-modules/>

模块是您将代码组织成自包含块的方式，您可以在不同的代码库中重用这些块，并在必要时导入。JavaScript 直到 ECMAScript 2015 才拥有标准的模块系统(支持 [ES 模块](https://hacks.mozilla.org/2018/03/es-modules-a-cartoon-deep-dive/)到 2018 年到达各大浏览器)。在那之前，使用 JavaScript 进行更大和更复杂开发的开发人员转向社区模块系统，如 [AMD](https://github.com/amdjs/amdjs-api/blob/master/AMD.md) (异步模块定义)加上 [RequireJS](https://requirejs.org/) 、 [Webpack](https://webpack.js.org/) 或[CommonJS](https://nodejs.org/api/modules.html#modules-commonjs-modules)(node . js 中的模块系统)。

ES 模块系统被开发成 AMD 和 CommonJS 用户都感到舒适的方法。Node.js 于 2017 年在 v8.5.0 中增加了实验性支持，稳定支持将于 2021 年年中在 [Node v15.3.0](https://github.com/nodejs/node/blob/master/doc/api/esm.md) 中到来。重要的是，这让节点开发人员可以访问所有已发布的模块。

“ES 模块作为一种创作格式非常成功，”TC39 联合主席 Rob Palmer 告诉 New Stack。“如果你在 GitHub 上，这是你看到源代码被创作的主要形式。它将看起来像 ES 模块。”

## 世界上的大部分地区都是在公共基础上运行的

尽管用于创作包的 ES 模块很流行，但是当这些模块被执行时，它们实际上可能被编译(通过 Node 或 TypeScript)并作为 CommonJS 运行。

Palmer 解释说:“世界上的大部分仍然运行在 CommonJS 上，即使它看起来像是在 ES 模块中创作的。

默认情况下，为了向后兼容，Node.js 将您导入的 JavaScript 代码视为 CommonJS 模块。帕尔默警告说，这意味着认为他们正在编写 es 模块的开发人员实际上并没有，这意味着他们无法获得 ES 模块的功能，如即将到来的新顶级 ECMAScript 2022。“这是大多数开发人员真正喜欢的人体工程学特性，”他补充道。

ES 模块支持其他一些重要的 Node.js 特性，比如包导出——可以封装一个包，这样开发人员只能访问特定的入口点，而不能调用包中的任何内容。这意味着有人可能依赖于某个特性的实现方式，这在以后的版本中可能会改变。

帕尔默说:“以前，节点包是免费的。“你可以加载你喜欢的包中的任意文件:只要写下目录和文件名，你就可以加载它。而现在，对于包导出，你可以说不，只有这些特定的入口点才是公共的，里面的所有东西都是包的私有的。这是生态系统所需要的关键部分，一旦 TypeScript 支持 Node 风格的 ES 模块，这将是我们真正享受的美妙待遇之一。”

## **具有挑战性的变化**

微软 TypeScript 高级项目经理[丹尼尔·罗森瓦塞尔](https://twitter.com/drosenwasser)解释说，支持开发人员过渡到 ES 模块一直是“一个持续的痛点”。这是开发人员必须处理的复杂性，不管他们是否使用 TypeScript。

“JavaScript 开发人员基于他们在 CommonJS、bundlers 和浏览器 es 模块支持方面的经验，对事情应该如何工作建立了很多期望，”他说，“而在 Node 中事情不是那样工作的。”

他将 CommonJS 描述为“使用起来极其方便，但最终不同于浏览器所需要的”。

由于 ECMAScript 侧重于开发人员的生产力，因此在 TypeScript 中添加对 Node.js 的 ECMAScript 模块支持似乎是一个显而易见的步骤。它最初计划在 TypeScript 4.5 中作为[模块:节点 12](https://github.com/microsoft/TypeScript/pull/44501) 和模块解决方案:节点下一个模式，要么匹配 Node.js 行为，要么使用 TypeScript 特性来提供相同的功能。

“为了给开发者提供一个桥梁，我们正在试验他们对 ES 模块的支持，看看我们能在哪里减少开发者可能遇到的一些问题，”Rosenwasser 说。

但是新模式[还没有为 TypeScript 4.5](https://github.com/microsoft/TypeScript/issues/46452) 做好准备，部分原因是 Deno、ts-node、Webpack 和 Vite 等工具生态系统的复杂性；部分原因是因为包的作者很容易错误地配置包，使得开发人员很难使用它们。因此 TypeScript 团队不想让情况变得更糟。还有一些关于使用新模式的缺省值应该是 node12 还是 nodenext 的争论，因为 Node 12 没有顶级 await。

“现在是 TypeScript 支持这一点的时候了，因为生态系统的其他部分已经采用了它，人们希望访问 Node 在这里提供的功能，”Palmer 告诉我们。“但做到这一点真的很有挑战性。这与 TypeScript 无关；新旧格式之间的兼容性是固有的挑战。

## 使这两个系统互操作的困难

这两个模块系统不仅有不同的语法，它们的工作方式也有很大不同。

“冲突的根源在于 CommonJS 是同步的，”Palmer 继续说道。“当它运行时，它只是运行直线代码:没有间隙，没有时间延迟。ES modules 支持异步工作，在这种情况下，您可以随着时间的推移将工作拆分开来。”

这很重要，因为当您编写将在浏览器中运行的代码时，您必须能够确保页面的其余部分不会因为等待长时间运行的脚本而被耽搁。

因为它们是同步的，所以 CommonJS 模块在执行过程中被动态解析——所以您可以从 IF 语句内部调用模块，因为依赖图将在程序运行时构建。因为 ES 模块是异步的，解释器在它们运行之前构建一个依赖图，这意味着它可以优化代码(所以不会被调用的代码不包括在内)。注意:对于 CommonJS 来说，通过树抖动来删除不必要的代码是可能的，但是 bundlers 通常不会默认这样做。

模块文件的命名方式还有一个额外的复杂性。的。mjs 和。cjs 扩展明确了您使用的是 ECMAScript 还是 CommonJS 模块(TypeScript 的等效模块是。mts 和。cts)。然而，它们是可选的，因为一些开发人员强烈认为 JavaScript 代码应该总是使用。js 作为扩展，即使对于模块也是如此。

## TypeScript 可以提供帮助的地方

有了新的 Node.js ES 模块支持，TypeScript 将理解这些扩展。但是如果开发人员不使用它们，TypeScript 将需要确定一个代码文件是否是一个模块，以及使用什么导入语法。选择错误的文件可能会导致从包中取出不同的文件，使得 TypeScript 团队很难[选择正确的导入默认值](https://github.com/microsoft/TypeScript/issues/46012)。如果设计 TypeScript 的人很难理解什么是正确的行为，那么向不是模块系统专家的开发人员解释他们应该做什么将会更加困难。

这些差异增加了两个系统互操作的难度。到目前为止，新的模块支持只在 TypeScript 的夜间版本中作为一个实验标志提供，所以开发人员必须明确选择它。

“人们会喜欢用 TypeScript 来解决这个问题，”帕尔默指出。“在某些方面，期待 TypeScript 提供神奇的解决方案是不公平的，因为他们不可能完全扮演这个角色。”

尽管如此复杂，他还是称赞了 TypeScript 处理 Node.js 风格 ECMAScript 模块支持的方式。“我真正喜欢的是，他们开始实施这一点，然后，因为他们以开发人员体验而闻名，他们发现当人们试图使用这一点时，体验并不是他们希望的那样。”

帕尔默总结道:“它正在走向成熟，反馈正在进入，他们正在做出回应。”。“但这是一个真实的例子，他们不只是把它扔出门外；他们非常努力地弥补不是他们造成的问题，这些问题是生态系统的其他部分造成的。”

## **结论**

TypeScript 希望提供的是一个大的特性，它将提供开发人员一直要求的许多改进。JavaScript 社区是如此之广，以至于关于 TypeScript 应该在这里做什么的争论还在继续，所以在更广泛的 JavaScript 工具生态系统中支持新模块选项的工作正在[进行中](https://github.com/vitejs/vite/pull/5510)。但是许多导致 TypeScript 4.5 推迟该特性的问题已经得到了解决，目前的计划是将它包含在 TypeScript 4.7 中(将于 5 月发布)。

目前，对于开发人员来说，在 Node.js 中配置 es 模块时很容易出错。由于延迟导致的额外讨论，应该提供一个使 ES 模块更容易理解和调试的特性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>