# TypeScript 如何帮助企业开发人员

> 原文：<https://thenewstack.io/how-typescript-helps-enterprise-developers/>

对于许多企业来说，用 JavaScript 编写的 web 应用程序是其开发过程的标准部分，无论是面向客户的还是内部的业务线应用程序。当他们拥有大规模开发团队时，[TypeScript](https://www.typescriptlang.org/)——JavaScript 的静态类型超集——越来越证明是比普通 JavaScript 更合适的选择。

这可能是打字稿工作[比 JavaScript 工作](https://insights.stackoverflow.com/survey/2021#worked-with-vs-want-to-work-with-language-worked-want-prof)报酬更高的原因之一，平均每年近 5000 美元。

TypeScript 并没有试图成为一门独立的编程语言；它实际上是工具和可选、可移除类型的组合。从技术上讲，TypeScript 是静态类型检查器和编译器的组合(它也可以充当[传输器](https://thenewstack.io/javascript-transpilers-need-know/))。但是最基本的想法是用最广泛使用的语言——JavaScript——来提高开发人员的生产力。

当 TypeScript 在 2011 年在微软开始时，JavaScript 缺乏构建大型代码库的关键功能:模块、类、接口，尤其是静态类型系统。开发 TypeScript 的目的是为开发人员提供他们在 C#等具有现代语言结构的语言中所习惯的生产力(并在依赖于它们的开发人员工具中启用功能)。

JavaScript 既强大又灵活。你可以快速制作出一个原型，构建服务器后端以及浏览器或桌面应用。但是 JavaScript 在管理和理解大型代码库方面并没有像其他语言那样给开发人员提供太多的帮助。

“JavaScript 是最普遍的语言之一。Dojo 的联合创始人 Dylan Schiemann 指出:“它无处不在，但它是最弱的开发人员人机工程学或生产力体验之一。”Dojo 是最早的 JavaScript 框架之一，也是早期的 TypeScript 爱好者。“因为简单所以简单，但有时候做正确的事其实很难。”

开发人员喜欢自由地编写代码，删除代码并用其他代码替换，但“没有接口，你真的做不到，”他补充道。“没有类型，就没有接口。

“TypeScript 正在修复一些从根本上来说很脏的东西。JavaScript 有点脏，而 TypeScript 让它不那么脏了。”

## 你从 TypeScript 中得到什么

稍微令人困惑的是，TypeScript 指的是几个不同的东西:

*   TypeScript 和 JavaScript 语言的类型检查器。
*   一种向 JavaScript 添加类型语法的“超集”语言。
*   对你的代码进行类型检查和转换的官方编译器。
*   与编译器共同开发的编辑体验，捆绑在 Visual Studio 和 Visual Studio Code 等编辑器中。

所有这些都是将静态类型添加到 JavaScript 并交付工具以使其易于使用所必需的。TypeScript 的高级项目经理 Daniel Rosenwasser 指出，将 TypeScript 称为 JavaScript 的强类型上标可能会让人认为它改变了 JavaScript 的工作方式(或者改变了你的代码)。

他更喜欢称之为静态类型，“因为我们只是在你运行代码之前执行一些检查。我们的愿景是让 TypeScript 尽可能地补充和改进 JavaScript。”

随着 JavaScript 语言本身的发展，TypeScript 的目标已经发展了很多年；在 ECMAScript 6 启动[之前，TypeScript 作为 transpiler 的角色是获得语言改进的重要途径，比如箭头函数和枚举。](https://thenewstack.io/javascript-forecast-whats-ahead-for-ecmascript-2022/)

现在，这种语言只实现了已经达到 [TC39 标准化](https://thenewstack.io/javascript-forecast-whats-ahead-for-ecmascript-2022/)过程第三阶段的新特性，这些特性已经准备好内置到 JavaScript 实现中以获得反馈。“打字稿创新的地方是打字系统，而不是运行时间，”打字稿专家和彭博软件工程师 Titian Cernicova Dragomir 说。

TC39 联合主席 Rob Palmer 将 TypeScript 解释为语法:“它是类型注释，只是你可以添加到 JavaScript 中的额外字符，以赋予它更多的意义，并允许编译器检测更多的错误，并为你提供越来越多的好处，因为它更了解你对代码的真正意义。”

与 JavaScript 没有冲突或竞争。Schiemann 建议将 TypeScript 更像一个林挺工具或代码执行工具，而不一定是一种偏离 JavaScript 的编程语言:“它实际上是一组使 JavaScript 变得更好的工具，但被删除了。”

[https://www.youtube.com/embed/BUo7B6UuoJ4](https://www.youtube.com/embed/BUo7B6UuoJ4)

视频

这就是为什么 Rosenwasser 更喜欢称 TypeScript 为“具有可擦除类型的 JavaScript”开发人员在他们的代码中标记类型；编译器检查它们，然后生成干净的 JavaScript 代码，看起来就像是人类开发专家写的。

德拉戈米尔指出，你也可以逐步采用打字稿。如果您查看 TypeScript 具有的所有编译器设置，您可以将它们视为一个刻度盘，从最低设置开始，并随着您的操作逐步增加安全性和严格性

这意味着您可以在一种像 JavaScript 一样灵活的语言中选择您想要的表达性和正确性的组合——因为它是 JavaScript。

现代 JavaScript 代码是有效的 TypeScript 代码，并且 TypeScript 可以在 JavaScript 运行的任何地方运行，在任何具有支持 ECMAScript 3 或更高版本的 JavaScript 运行时的设备上运行，无论是复杂的网站、后端服务还是移动设备。

## 企业为什么需要打字稿

尤其是当多个开发人员用成千上万行代码构建大型 web 应用程序时，JavaScript 中的动态类型意味着代码即使有错误会停止运行也能编译，这使得很容易以难以调试和维护的混乱代码告终。企业还不起那种技术债。

对于复杂的代码，强制类型使得在没有注意到的情况下引入错误变得更加困难，因为它们告诉编译器和开发人员代码应该如何运行。

像处理 Typescript 一样，在编译代码时就获取类型错误，这样您就可以在编写代码时发现问题，而不是在几个小时后才发现，这使得调试项目比在运行时出现这些错误要容易得多。

静态类型检查不仅有助于发现类型错误和因类型而无效的操作；这使得[集成开发环境(IDE)](https://thenewstack.io/are-cloud-based-ides-the-future-of-software-engineering/) 更容易发现方法名中的拼写错误。

类型允许像自动完成这样的上下文感知建议，允许更好的代码导航(通过查找代码中的所有引用或带您到定义)和更好的自动重构。“过去需要一整天的事情通过重构只需要一秒钟，这是非常宝贵的，”微软的技术人员和 Typescript 的核心开发者[安德斯·海尔斯伯格](https://www.linkedin.com/in/ahejlsberg/)指出。

类型还使阅读代码的人更容易理解一个方法的参数和值，而无需钻研注释和文档(对于您的代码以及任何库和框架)。

> 像处理 Typescript 一样，在编译代码时就获取类型错误，这样您就可以在编写代码时发现问题，而不是在几个小时后才发现，这使得调试项目比在运行时出现这些错误要容易得多。

您可以用 JSDoc 记录代码和注释类型，但是您仍然必须确保代码和文档相匹配:其他开发人员必须首先相信代码被正确记录，并且任何更改都反映在文档中。

对于编写大量代码的大型团队来说，这些好处可以极大地提高生产率。“像 Outlook Web 和 Office 中的其他团队正在考虑从 C#等语言编译到 JavaScript，这样他们就可以获得现代语言结构、类型检查和良好的工具，”Rosenwasser 告诉新堆栈。

“我们知道这不是获得这些好处的正确方式，因为你不能忽视底层平台——如果你想构建最好的 JavaScript 应用，你必须从 JavaScript 开始。”

使用 TypeScript，企业可以获得他们选择 JavaScript 进行的快速开发，以及提供开发人员生产力的类型检查和工具。

## 企业已经依赖于 TypeScript

企业几乎肯定会使用使用 TypeScript 的软件。Rosenwasser 指出，不仅 TypeScript 本身是用 TypeScript 编写的，Visual Studio 代码、Excel 引擎的 web 版本、Slack Desktop、微软的新 Fluid framework 和 [Figma 设计工具](https://thenewstack.io/top-5-internet-technologies-of-2021/)也是如此，这些技术正在推动企业将依赖的下一代协作应用程序。

“很明显，TypeScript 将为该领域的许多富应用提供动力，”他说。

Schiemann 告诉新堆栈:“Dojo 和 Angular 2 是值得注意的早期采用者，我们知道问题，我们知道痛点，我们知道这有可能帮助我们。”

Rosenwasser 说，现在几乎每一个主要的前端框架都是用 TypeScript 编写的:“在某种程度上，问题变成了，谁没有使用 TypeScript？”

Airbnb 拥有超过 20 亿行 JavaScript 和 100 多个内部 npm 模块。在观察了六个月的事后分析并发现 [TypeScript 可以防止 38%导致生产事故的错误](https://www.youtube.com/watch?v=P-J9Eg7hJwE)后，它决定将 TypeScript 作为其前端 web 开发的官方语言。

> “TypeScript 正在修复一些从根本上来说很脏的东西。JavaScript 有点脏，而 TypeScript 让它不那么脏了。”

—Dylan Schiemann，Dojo 的联合创始人

Slack 也有过类似的经历，当[转到 TypeScript 编写 Slack 桌面](https://slack.engineering/typescript-at-slack/)时，立即发现了数量惊人的小 bug。它还发现生产率的提高如此显著，以至于公司在开始转换现有代码库的几天内就开始将它用于所有新代码。

“TypeScript 给了我们一个保证，代码中的结构依赖是合理的，” [Felix Rieseberg](https://twitter.com/felixrieseberg) ，Slack 转向 TypeScript 时的工程经理，在一次关于采用语言的演讲中指出[。](https://slides.com/felixrieseberg/typescript-slack#/12)

采用类型肯定会有一些开销，但是对于拥有大型代码库的大型团队来说，开发人员的生产力是非常有吸引力的。Rosenwasser 说，能够依靠代码完成和代码库导航这两个 TypeScript 的功能，有助于团队扩大规模。

“像‘这个功能应该如何使用？’以及“我可以在这里访问哪些属性？”没有打字稿可能很难回答，”他说。

“在我们的经验中，很少看到有人放弃 TypeScript，因为基线体验很难放弃，”他补充说，特别是代码完成功能及其帮助用户避免打字错误的能力。

德拉戈米尔附和了这些观点。“我觉得自己没有能力写纯 JavaScript。限制太多了，”他说。“一旦你习惯了，如果你试图回到 JavaScript，你会感到痛苦。

“这是因为你已经习惯了它为你做一切事情的想法，但你突然觉得自己开车没有系安全带，这感觉很痛苦。”

但 Rosenwasser 指出，采用这种语言需要一个学习曲线，企业开发团队在转向 TypeScript 时需要考虑到这一点。

“也许完整的 TypeScript 不会是每个项目的最佳工具——特别是非常小的程序和简短的脚本，”他说，“所以我们试图提供像 checkJs 这样的模式，在那里你可以用普通的 JavaScript 编写 JSDoc 类型注释，并从 TypeScript 获得检查。”

> Airbnb 在观察了六个月的事后分析后，发现 TypeScript 可以防止 38%导致生产事故的错误，于是决定将 TypeScript 作为其前端 web 开发的官方语言。

TypeScript 的用法在服务器端代码中不太常见，尽管它与 Node.js、Deno 和许多其他无服务器运行时一起使用；彭博在其统一前端和服务器端系统中使用 TypeScript。

Rosenwasser 说:“虽然有大量 Node.js 开发人员使用 TypeScript，但在 Node 领域，人们不太愿意添加编译步骤。

他说，Webpack 和 Rollup 已经将这一步骤规范化为前端开发人员构建链的一部分。“TypeScript 在前端有优势，这在很大程度上是因为像捆绑这样的构建步骤已经变得无处不在。”

## 打字工具

TypeScript 开发者可以使用任何 JavaScript 工具、库和框架；如果这些的类型定义没有包含在包中，那么它们几乎肯定可以从 [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped) 中获得(并通过 npm 交付)。

帕尔默认为，这种网络效应增加了 TypeScript 的受欢迎程度(并简化了企业的采用)。

“你可以得到世界上几乎任何库、任何包的类型信息，”他说。“当然，当你试图为生态系统中需要工作的每个包做些什么时，人们愿意做一次工作。但你不可能让全世界都为每一种类型的系统做这项工作。”

早期，使用 TypeScript 的最佳地方是在 Visual Studio 中，这意味着使用 Windows 并购买高端的 Microsoft 开发人员工具，或者错过作为 TypeScript 体验关键部分的工具。企业可能在已经习惯了其他语言的现有开发团队成员中拥有这方面的专业知识，但并不是所有新的 web 开发人员都具备这种专业知识。

> 对于具有 Python、C 或 Java 经验的开发人员来说，TypeScript 带来的工具是熟悉的，也是他们所怀念的。对于年轻的开发者来说，他们更可能是新奇的。

Visual Studio 代码的出现改变了这一点，其他流行的编辑器如 [Atom](https://github.com/TypeStrong/atom-typescript) 和 [Sublime](https://github.com/Microsoft/TypeScript-Sublime-Plugin) 支持它(直接或通过插件)，使用允许 TypeScript(和你的编辑器)理解哪些属性和方法在某些对象上可用的语言服务。

Rust 的座右铭是“无畏并发”Rosenwasser 喜欢暗示 TypeScript 的超能力是“无畏的重构”

“我们的动机是我们在现实世界中看到的常见错误，”他说。随着 TypeScript 使用范围的扩大，团队可以看到代码中的各种问题。

Rosenwasser 说，TypeScript 旨在识别常见的 JavaScript 模式，这样你就可以编写 JavaScript 而无需记住你正在编写 TypeScript。

“从某种意义上来说，我们正在让语言更具表现力，而不是试图将表达自己的负担推给类型系统，”他说。“我们做这种事情越多，你就越能避免类型断言”——或类型转换——“它们经常违反类型系统的假设。”

## TypeScript 最喜欢的功能

最近发布的 TypeScript 增加了一些特性，使得使用异步函数(一种在 JavaScript 中使用承诺的期待类型)以及在设置属性和检索属性时使用不同的类型(因为您可能接受整数和字符串，但在存储它们之前将这些字符串转换为整数)变得更加容易。

Rosenwasser 最喜欢的一个特性是 TypeScript 处理联合类型的方式。

“TypeScript 不是唯一一个具有未标记的结构联合类型的类型系统，但它是一个你通常不会在动态语言如 JavaScript 的类型系统之外看到的类型系统，”他说。“能够混合和匹配一个函数可能取的值是非常强大的。”

一些特性，比如消除递归类型之间的尾部调用，非常强大，主要针对编写库的开发人员。“间接地，我们已经在我们的类型系统中建立了一个小型函数式编程语言，其中一个挑战是如何让人们有效地使用这些构造，”Rosenwasser 说。

其他的，比如代码片段补全，将被证明对许多大规模工作的开发人员是有用的。这个特性允许您添加默认文本，并在不同选项之间切换，选择您可能想要调整的代码片段。开发人员可以专注于代码的核心逻辑，而不是键入大量的样板文件。

事实上，随着 TypeScript 对开发人员如何编写 JavaScript 代码进行了更多的语义理解，有更多的地方它知道需要什么类型。因此，开发人员不必自己提供那些类型注释，无需额外的工作就可以获得控制流分析的好处。

如果你有一个可以是类型或者 null 的变量，并且它不是 null，那么这个类型会自动变成它应该的类型。

对于具有 Python、C 或 Java 经验的开发人员来说，TypeScript 带来的工具是熟悉的，也是他们所怀念的。对于年轻的开发人员来说，他们更有可能是新奇的 Schiemann 将 TypeScript 最近的流行归功于此。

TypeScript 中的语言服务意味着像 Visual Studio 代码这样的编辑器可以在没有类型提示的情况下获得对普通 JavaScript 代码的额外理解。帕尔默指出，这为自动补全、代码导航和重构提供了动力。

“很多人会认为他们只是在使用 Visual Studio 代码，”他说。"他们不会意识到所有这些能力都来自于运行在引擎盖下的打字稿."

## TypeScript 的影响越来越大

TypeScript 也开始影响新的语言，比如 WASM 的汇编脚本和 T2 的二头肌汇编脚本。Rosenwasser 将其中的一部分归功于对 JavaScript 的熟悉，就像许多语言采用 C 语言的惯例一样:“如果你的语法看起来接近 C 语言家族中带有花括号之类的东西，你会因为熟悉而受益匪浅。”

但是同样值得注意的是，静态类型使得 TypeScript 在一些 JavaScript 可能不适合的领域中变得重要。

在很多方面，TypeScript 是教微软如何做好开源的项目。(微软[内部的其他开源项目维护人员称赞 TypeScript 团队](https://thenewstack.io/open-source-is-clearly-mainstream-now-at-microsoft-but-also-very-new/)带领他们度过了项目的早期阶段。)

Typescript 团队的前项目经理 Jonathan Turner 回忆起他们是如何赢得 Dojo 等框架和大型项目开发人员的支持的，他说:“打开我们的大门，把每个来找我们的工程师都当成好的有趣的问题，告诉他们如何使用 JavaScript。”

从一个 TypeScript 用户的角度来看，Schiemann 称构建这个工具的团队是“最谦逊、最热情、最有魅力的一群天才”

“他们只是一直在寻找那些很难做的东西，以及如何让它更符合人体工程学，更容易使用，”他谈到 TypeScript 背后的人时说。“他们说，我们如何才能让它对你更有用？他们会倾听，会做那些事情，然后人们会很开心。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>