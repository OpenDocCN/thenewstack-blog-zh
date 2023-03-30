# Typescript 与 Javascript |新的堆栈

> 原文：<https://thenewstack.io/typescript-vs-javascript/>

对于 [Typescript](https://thenewstack.io/what-is-typescript/) vs. JavaScript 的争论，没有简单的答案。答案在很大程度上取决于您组织的需求以及直接为您工作的开发人员/技术人员的个人偏好和专业知识。

架构总监亚当·艾布拉姆斯 [Optimove](https://www.optimove.com/) 建议，当考虑 Typescript 和 JavaScript 时，首先要看你的具体组织和用例，而不是网上的一些通用比较表。“例如，我们在前端和后端大量使用 JavaScript，但我们的后端系统也主要利用其他技术堆栈。NET 和 Java。此外，我们在中等规模的团队(大约六个开发人员)中开发微服务，并且需要由不同的人在逐个冲刺的基础上维护相同代码的能力。

Abrams 解释说，Optimove 开发人员习惯于输入语言，测试方法依赖于空引用和未初始化变量等基础知识，由编译器处理，而不是由开发人员手工处理。“这就是我们在大多数服务中对 Typescript 进行标准化的原因。为了加快进行概念验证或测试假设的速度，小型或一次性服务仍在用 JavaScript 开发。对于其中的一些，我们后来已经以渐进的方式将代码迁移到 TypeScript。这是一个无痛的过程(通常会改进代码并发现一些隐藏的 bug)。)"

**阅读相关:** [打字稿和静态类型语言的力量](/typescript-and-the-power-of-a-statically-typed-language/)

Abrams 补充道，“你在代码中加入的业务逻辑越多(而不仅仅是 I/O)，你就能更好地使用 TypeScript 来用适当的类型自我记录你的代码。在 JavaScript 中，很容易混淆单元/类型，在没有注意到的情况下得到无意义的结果。我们注意到，它还强制要求开发人员在实际代码中使用 JavaScript 的优秀部分，而忽略特殊部分。”

## 类型脚本和 JavaScript 的挑战

Veritone 的工程总监 Andrew Pierno 认为，在打字稿和 JavaScript 的争论中，任何一个答案都存在挑战。

皮尔诺解释说，JavaScript 令人困惑，令人沮丧，看似容易上手，却不可能掌握。这是如此灵活，很容易把自己打成一个结。做事情的方式有一百万种，每天都有新的工具出现，而且只要它存在，它就是编程语言丑陋的继子。

根据 Pierno 的说法，JavaScript 的一个优势是，从网络应用程序到桌面应用程序，甚至是与区块链相关的应用程序都可以使用它。TypeScript 解决了 JavaScript 具有“奇怪”类型的问题。

“但根据我的经验，这不是一个实际问题，”皮尔诺说。“我从未因为打字稿问题而导致生产系统瘫痪。打字稿是解决一个我从未见过也从未有过的问题的两倍工作量。TypeScript 为来自其他编程语言的人提供了强类型语言的便利。您可以将它附加到大多数应用程序中，并在应用程序的最关键部分引入它。”

根据 Pierno 的说法，Typescript 为大型团队增加了额外的保护，它引入了编译器通常会在其他语言中发现的错误，但如果没有普通 JavaScript 中的 TypeScript，就不会被发现。

## TypeScript 和 JavaScript 之间的微小差异

Schellman 安全倡导者和新兴网络趋势分析师 Jacob Ansari 表示:“如果您已经在使用应用程序框架或组件，或者正在使用基于 JavaScript 的现有代码，转换到 TypeScript 可能会涉及一个重大提升，特别是如果您的开发人员和支持人员具有 JavaScript 而不是 TypeScript 方面的专业知识。”在 Typescript 与 JavaScript 的讨论中，没有令人信服的赢家，您从语言转换中获得的任何好处都可能会在测试功能和重新培训人员方面付出巨大的代价。

“我的怀疑是，出于安全原因在现有代码基础上做出这样的举动很少是值得的，除非你突然得到一个新的开发团队，他们在新语言方面有很多专业知识，并且讨厌旧语言，”安萨里补充道。“大多数组织最好充分了解他们的语言、工具集和技术提供的安全性权衡，并根据这些因素做出设计和实现决策。更好地满足其需求(为什么)？”

## 打字稿的情况

尽管安萨里支持使用你现在正在使用的任何东西，但 Raven Code Limited 的联合创始人兼全栈开发者卡尔·桑德斯认为，TypeScript 显然是这场辩论的赢家。

“TypeScript 是你应该使用的唯一一个，因为它向下转换为 JavaScript，”Saunder 说。“在大多数情况下，您甚至不必编写 TypeScript——Visual Studio Code 和 WebStorm 等现代编辑器将推断出开箱即用的类型(与 TypeScript 集成)。这带来了巨大的好处，因为 IntelliSense 支持将自动完成代码，甚至在开发人员做错事情时突出显示(类型检查)。仅这一点就可以在执行代码审查之前阻止大多数错误提交到代码库中。”

桑德斯说，有了 [TypeScript](https://thenewstack.io/typescript-tutorial-go-beyond-hello-world/) ，开发人员可以轻松地编写干净且可维护的代码，让他们能够专注于编写功能。TypeScript 的另一个好处是，开发人员可以在 ECMAScript 规范提案公开发布之前采用它们，在幕后，TypeScript 将填充这些特性。

“TypeScript 也可以用作命令行界面(CLI)，”桑德斯补充道。这意味着开发人员可以将其作为开发人员工作流程的一部分，在后台任务中运行。更重要的是，它可以作为持续集成(CI)构建管道的一部分来执行。这使得错误甚至可以在代码被部署给用户之前就被发现。”

## 你应该用哪一个？

很明显，选择 Typescript 还是 JavaScript 将取决于您是否已经使用了其中的一个，并且对它感到满意。如果是这样，浏览一下上面的讨论，看看是否有任何令人信服的理由来改变。

如果从零开始，你会想要通读上面的讨论，做一点实验，看看哪个看起来更适合你的组织。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>