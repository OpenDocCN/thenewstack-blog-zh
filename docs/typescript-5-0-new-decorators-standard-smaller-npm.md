# TypeScript 5.0:新的装饰者标准，更小的 npm

> 原文：<https://thenewstack.io/typescript-5-0-new-decorators-standard-smaller-npm/>

TypeScript 5.0 于本周发布，支持新的 decorators 标准，并且比 TypeScript 4.9 占用的 npm 空间更小。

微软的[丹尼尔·罗森瓦瑟](https://github.com/DanielRosenwasser)，负责[打字稿](https://thenewstack.io/improve-your-typescript-skills-with-type-challenges/)的程序员经理，在一篇博客中解释了[的变化，承诺 5.0“不是一个颠覆性的版本，你所知道的一切仍然适用。”他补充说，TypeScript 5.0 包括正确性更改和一些不常用选项的弃用。](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/)

“这个版本带来了许多新功能，同时旨在使 TypeScript 更小、更简单、更快，”Rosenwasser 说。“我们实现了新的 decorators 标准，增加了功能以更好地支持节点和绑定器中的 ESM 项目，为库作者提供了控制通用推理的新方法，扩展了 JSDoc 功能，简化了配置，并进行了许多其他改进。”

装饰器在 Python、Java 和 C#中使用，是 JavaScript 的第三阶段提案。据高级软件开发人员 Lawrence Eagles 称，目前，它们可以通过 Babel 和 TypeScript 编译器用于 JavaScript。目前大多数浏览器都支持装饰器。

简而言之，装饰器包括用另一个代码——装饰器函数——包装一段代码，比如一个函数或一个类。目的是在不修改代码的情况下扩展其功能，”[Eagles](https://blog.sessionstack.com/how-javascript-works-a-deep-dive-into-decorators-a3252367fa0)写道。"装饰者非常强大，他们有广泛的应用."

他补充说，用例包括将类方法转换成 REST，记录有用的信息，以及支持代码重用。

根据 Rosenwasser 的报道，新版本还提供了一个更小的典型 npm 包大小，为 37.4 MB，而 Typescript 4.9 为 63.8 MB。

Rosenwasser 说，TypeScript 通过添加可用于类型检查的类型语法建立在 JavaScript 之上。要开始使用 TypeScript 5.0，您可以通过 NuGet 获得它，或者通过以下命令使用 NPM:

```
npm install  -D  typescript

```

## React.dev 推出新的 React Home

本周的其他消息是， [React.dev](https://react.dev/) 即将迎来它的 10 岁生日。为了庆祝，它为大众图书馆和相关文献建立了一个新家。该网站教授现代 React 与功能组件和挂钩，并提供了 500 多个新的交互式示例和沙箱。

以前的文件地点在 legacy.reactjs.org 的[存档。原来的域名——](http://legacy.reactjs.org)[reactjs.org](http://reactjs.org)——将重定向到新的站点。

根据开发者 Dan Abramov 和 Rachel Nabors 的博客文章，更新后的文档从一开始就教导使用钩子，并分为两个主要部分:

*   Learn React 是一门自学课程，从头开始教授 React，并为那些陷入困境的人提供了一个“显示解决方案”按钮。
*   API 参考，它提供了每个 React API 的详细信息和使用示例。每个 API 页面都包括关于参考和使用的信息，使用显示了开发者在实践中为什么以及如何使用 API。

新网站为那些想学习 React 的人提供了一个快速[起始页](https://react.dev/)，以及一个交互式井字游戏教程，教开发人员构建游戏的一个版本。它还包括对 React 中*思维的更新，阿布拉莫夫和纳伯斯说这是“让 React“点击”我们许多人的教程”。*

[根据](https://thenewstack.io/vue-2023/) [2022 年 JavaScript 调查状态](https://2022.stateofjs.com/en-US/libraries/)，React 仍然是最受欢迎和使用最广泛的 JavaScript 库之一。

## Rust 更新到 1.68.1

最后，Rust 在周四发布了一个[新版本，Rust 1.68.1](https://blog.rust-lang.org/2023/03/23/Rust-1.68.1.html) 。点发布是次要的，通常是修复 bug 或执行代码清理。在这种情况下，Rust 1.68.1 对 Rust 的 CI 构建 Windows MSVC 编译器的方式进行了更改，不再为 Rust 代码启用 LTO。

“这导致了 Rust 团队正在调试的错误编译，但与此同时，我们正在恢复更改以启用 LTO，”Rust 团队在一篇博客帖子中声明。“目前认为这对 ThinLTO 的广泛使用没有影响。Rust 编译器在构建过程中使用了一个不稳定的标志来启用 ThinLTO，尽管编译为 dylib。

版本中修复的其他回归:
◨[修复构建编译器时使用–enable-local-rust](https://github.com/rust-lang/rust/pull/109111/)；
♀[将$prefix-clang 视为链接器检测代码](https://github.com/rust-lang/rust/pull/109156)中的 clang；并且
♀[修复了编译器的一个死机问题。](https://github.com/rust-lang/rust/pull/108162)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>