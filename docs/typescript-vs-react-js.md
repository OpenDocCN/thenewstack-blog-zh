# Typescript vs React |新堆栈

> 原文：<https://thenewstack.io/typescript-vs-react-js/>

无论是运动队，总会涌现出一个明星球员，受到最多的关注。然而，没有一个明星球员可以独自赢得比赛。互补的玩家为赢得比赛创造了条件。在足球比赛中，进攻线允许四分卫、跑卫和接球手获得码数和触地得分。在篮球比赛中，总是获得重要篮板的大前锋或防守型后卫会让组织者打进制胜一球。

[什么是 Typescript？让我们找出答案。](https://thenewstack.io/what-is-typescript/)

## JavaScript 受到明星待遇

编程语言中也存在明星玩家和补充玩家——尽管形式不同。例如，我们可以说 [JavaScript](https://www.w3schools.com/js/) 是一个超级明星。毕竟，JavaScript 已经成为世界上最流行的编程语言，而且 stakes 声称自己是网络编程语言。开发人员使用 JavaScript 创建动态的交互式网页。

和许多明星玩家一样，JavaScript 也有一些影响性能和开发能力的问题。诸如 TypeScript 和 React 之类的补充工具克服了可能导致错误的问题，并提供了使 JavaScript 成功的工具。

虽然[动态类型](https://levelup.gitconnected.com/understanding-javascript-coercion-in-a-dynamically-typed-language-8807d6331fa2)通过将类型分配延迟到代码运行时才分配给所有变量，给 JavaScript 带来了灵活性和敏捷性，但它也为使用错误类型的变量导致的错误打开了大门。即使有无效的类型参数或不匹配的数据，JavaScript 也能顺利编译。

JavaScript 中的类型检查发生在运行时，基于当时的变量值。任何检测到的错误都会导致一个警告，让开发人员有机会在崩溃发生之前修复代码。不幸的是，另一个问题也会影响性能。作为一种[弱类型语言](https://www.oreilly.com/library/view/javascript-design/0735711674/0735711674_ch02lev1sec3.html#:~:text=One%20last%20characteristic%20of%20JavaScript,with%20typing%20from%20your%20keyboard.)，JavaScript 享有可变类型协议自由。这种自由鼓励类型检查器对变量类型做出假设。关于变量类型的假设可能会产生一种级联效应，这种效应从误解开始，持续到不产生错误，最后将错误引入生产环境。

## TypeScript 改变游戏

JavaScript 的根源可以追溯到客户端和服务器端编程。然而，随着时间的推移和应用程序转向企业级面向对象编程，庞大、复杂的 JavaScript 代码已经不能满足需求。微软开发了开源的、面向对象的编程语言 Typescript 来改变游戏。JavaScript 的所有优秀元素都融入到 TypeScript 中，并改进了模型以满足企业级需求。

微软的 TypeScript 语言是 JavaScript 的超集。任何在 Typescript 上运行的代码也可以在 JavaScript 上运行。那么 JavaScript 的超集也能起到补充作用吗？

这个问题的答案在于在 TypeScript 中使用静态类型。与 JavaScript 中的动态类型不同，静态类型允许程序员在输入代码时检测错误。TypeScript 还消除了与 JavaScript 中出现的错误假设相关的错误。通过将类型信息添加到代码中，程序员还可以使用[集成开发环境](https://www.techtarget.com/searchsoftwarequality/definition/integrated-development-environment) (IDE)和构建过程来检查类型。因此，JavaScript 包含的所有功能变得更加高效，而且没有风险。

另一个要点强调了 JavaScript 和 TypeScript 之间的区别。JavaScript 是弱类型的，而 TypeScript 是强类型的。因此，Typescript 允许开发人员将变量和数据结构声明为特定的，并鼓励使用强类型进行企业范围的开发。TypeScript 的类型支持通过接口、混合类型、枚举、访问修饰符和其他工具增强了 JavaScript 的灵活性和可靠性。

TypeScript 还通过支持[欧洲计算机制造商协会脚本](https://www.techopedia.com/definition/14291/ecmascript#:~:text=ECMAScript%20(European%20Computer%20Manufacturers%20Association,as%20well%20as%20other%20browsers.) (ECMAScript) 2022 通用编程语言标准来补充 JavaScript。通过使用最新的 ECMAScript 功能，同时保持与旧功能的兼容性，这种支持的影响变得很明显。开发人员可以使用模块、类和 lambda 函数，而不会牺牲与旧版本 JavaScript 运行时的向后兼容性。

## React 帮助 JavaScript 获得赢得游戏的性能

JavaScript 允许程序员改变网页的行为。程序员可以创建、设计、添加和删除元素来改变内容和实现交互性。然而，构建吸引用户的网页只是在新的用户界面、移动密集型环境中取胜的一部分。用户寻求并期望轻松访问信息和难忘的网络体验。

React 由脸书(现为 Meta)于 2013 年发布，通过提供构建响应用户输入的高级用户界面所需的工具，进一步提升了交互性。像篮球一样，教练们寻找能够得分、抢篮板、防守、反击的混合球员，将本地应用程序开发与 JavaScript 用户界面开发结合起来。此外，React 允许开发人员在创建新应用程序时[重用组件](https://www.clariontech.com/blog/7-advantages-of-reactjs-for-building-interactive-user-interfaces)。

React Native 的操作与 React 类似，但它为移动应用程序提供了一个混合移动应用程序开发框架。虽然 iOS 和 Android 的[原生模块](https://www.altexsoft.com/blog/engineering/the-good-and-the-bad-of-reactjs-and-react-native/)负担很重，但程序员可以用 JavaScript 编写代码，然后跨平台共享代码。

但是，与 TypeScript 不同，React 不是一种语言。相反，React 是一个围绕构建用户界面的可预测性、功能和效率而构建的 JavaScript 库。React 使用不同的 IDE 工具套件，这些工具套件提供了一个集成代码编辑器、编译器、调试器、代码库、自动化工具和测试平台的框架。

速度取胜。React 不使用文档对象模型(DOM)中的数据输入和输出，而是利用[虚拟 DOM](https://reactjs.org/docs/faq-internals.html) 来改善用户体验。虽然 DOM 依赖服务器来更新文档的 DOM 树中可能成千上万的元素，但 React 使用虚拟 DOM 来更新用户应用的哪怕是最小的更改，而不会影响界面的其余部分。通过这种方法，Reach 加快了更新速度，提高了性能并有助于加快编程速度。

## Typescript 与 React:谁赢了？

球员之间的友好比赛可以在练习场上或球场上提高技能。在组建团队时，教练寻求最佳的技能组合来建立获胜优势。例如，在足球比赛中，教练可能会把一个利用身体大小和力量压倒对手的进攻线员安排在另一个利用技术和智力进行阻挡的进攻线员旁边。

Typescript 和 React 通过可靠性、灵活性、可重用性和多功能性采取不同的途径来补充 JavaScript。让我们花一点时间来强调一下这两个玩家之间的一些关键差异。

## TypeScript 与 React —比较

*   TypeScript 是一种语言。
*   React 是一个库。
*   TypeScript 支持企业范围的开发。
*   ReactJS 和 React 本机支持 web 和移动应用程序的用户界面。
*   TypeScript 利用数据结构和变量。
*   React 使用虚拟 DOM。

尽管 TypeScript 对 React 的场景看起来是可能的，但 React 框架通过为 React 应用程序提供使用 [JavaScript 或 TypeScript](https://blog.bitsrc.io/5-strong-reasons-to-use-typescript-with-react-bc987da5d907) 的选项来保持中立。因为 TypeScript 减少了出错的机会，所以代码库变得更容易使用。

此外，React 库支持在 TypeScript 中看到的类型定义，并提供数据绑定。因此，开发人员可以[跟踪对不同数据段所做的](https://www.clariontech.com/blog/7-advantages-of-reactjs-for-building-interactive-user-interfaces)更改。当从一个项目到下一个项目重用组件时，程序员也可以利用通过 TypeScript 提供的可靠性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>