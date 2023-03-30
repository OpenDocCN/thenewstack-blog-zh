# 什么是 Typescript？|新堆栈

> 原文：<https://thenewstack.io/what-is-typescript/>

TypeScript 是一种构建在 JavaScript 之上的编程语言。但是是什么让 TypeScript 成为用户可以信任的语言呢？

让我们更深入地了解什么是 TypeScript，它能为 JavaScript 用户做些什么。

## 理解 TypeScript

TypeScript 是一种基于 JavaScript 的强类型、面向对象的编译编程语言。它是 JavaScript 语言的超集，旨在为您提供任何规模的更好的工具。

TypeScript 背后的首席架构师是微软的 C#设计师安德斯·海尔斯伯格。TypeScript 是开源的，由微软支持，被认为是一种语言和一套工具。

TypeScript 称自己为“ [JavaScript，带有类型的语法](https://www.typescriptlang.org/)简而言之，它是带有一些附加特性的 JavaScript。

## TypeScript 的组件

TypeScript 包含三个主要组件:语言、TypeScript 编译器和 TypeScript 语言服务。

1.  **语言:**语法、关键字和类型注释。
2.  **TypeScript 编译器(TSC):** 将用 TypeScript 编写的指令转换成 JavaScript 的等价形式。
3.  TypeScript 语言服务:类似编辑器的应用程序的附加层，例如语句完成、签名帮助、代码格式化和着色等。

## TypeScript 做什么

TypeScript 通常被认为是“ [JavaScript 和更多的](https://www.typescriptlang.org/)”更准确地说，TypeScript 有四个主要目标:

1.  让 JavaScript 开发更加高效
2.  向 JavaScript 引入可选类型
3.  有助于更早发现错误
4.  实现未来 JavaScript 的计划特性

## JavaScript 中的缺口

JavaScript 是一种松散类型的编程语言，由 ECMA 技术委员会开发。在许多方面，JavaScript 是 web 的通用语言，有多个供应商支持不同的实现，例如 Google、Microsoft、Oracle 等。

要理解 TypeScript 与 JavaScript 的关系，必须记住 JavaScript 最初是作为客户端语言引入的。但是随着 Node.js 的发展，JavaScript 现在也被认为是一种新兴的服务器端技术。

这就是问题开始出现的地方。

随着 JavaScript 的发展，它变得越来越复杂，这使得用户在维护和重用代码时很难保持整洁。

但是这并不是阻碍 JavaScript 作为服务器端技术发展的唯一障碍。

由于忽略了强类型检查、编译时错误检查和面向对象等新特性，JavaScript 无法成为成熟的服务器端技术——如果它要在企业级取得成功，就必须成为成熟的服务器端技术。

另外，JavaScript 仍然是一种松散类型的语言，这本身就具有抑制性。由于函数参数和变量提供的信息很少甚至没有，开发人员经常在黑暗中摸索，试图确定什么类型的数据在 JavaScript 的什么地方被传递。他们要么不得不浪费时间查看文档，要么——在最糟糕的情况下——只是根据实现尽力猜测。

## TypeScript 如何填补 JavaScript 的空白

作为一种基于 JavaScript 的强类型编程语言，TypeScript 的使命是介入并填补这些空白，以更好地实现应用程序规模的开发。

### 增强的 IDE 支持

总的来说，TypeScript 极大地增强了 JavaScript 用户的开发体验。

在许多方面，这主要是由于 TypeScript 带来的改进的 IDE(集成开发环境)支持，其中 TypeScript 编译器实时通知 IDE 丰富的类型信息。

这对用户来说有几个好处。

首先，它更容易捕捉错误。编码时，编译错误直接在 IDE 中用红线标识。当你对一个库可能提供什么功能有疑问时，你可以得到内嵌的帮助，这要感谢代码完成。这简化了工作流程，因为您不再需要停下来寻求外部在线参考的帮助。

总之，这种增强的 IDE 支持提高了用户的整体工作效率。

### 静态类型和类型推理

JavaScript 是动态类型的。换句话说，直到变量在运行时被实例化，JavaScript 才知道它是什么类型。

但在某些情况下，这可能为时已晚。如果一个变量被错误地假定为某种类型，这可能会导致严重的错误。

这是 TypeScript 增加对松散类型 JavaScript 支持的另一个领域。

使用 TLS(上面提到的 TypeScript 语言服务)，TypeScript 有一个可选的静态类型和类型推断系统，可以推断未声明的变量。因此，通过向 JavaScript 添加类型支持，TypeScript 可以有效地减少编译 JavaScript 期间的类型错误。

### 汇编

同样，JavaScript 的最大缺点之一是很难发现和纠正错误。

这部分是因为 JavaScript 是一种解释型语言，因此必须运行来测试它的有效性。并且在出现错误的情况下，用户经常被留在一个寻找代码中的错误的野鹅追逐中。

TypeScript 有助于简化错误检查。

当 TypeScript 编译代码时，它将识别语法错误，并通过生成编译错误来通知用户。因此，TypeScript 帮助用户在编译时捕获错误，而不是等到运行时。

## ECMAScript 功能

虽然 JavaScript 语言通过 [ECMAScript 标准](https://thenewstack.io/can-typescript-help-more-developers-adopt-ecmascript-modules/)实现了标准化，但并不是所有的浏览器和 JavaScript 运行时都支持所有的 ECMAScript 标准。

这就是 TypeScript 发挥作用的地方，帮助用户了解 JavaScript 的未来——今天。因为有了 TypeScript，开发人员甚至可以在 web 浏览器或其他环境完全支持 ECMAScript 特性之前，使用许多最新的 ECMAScript 特性(例如，模块、lambda 函数、类、spreader 运算符和析构)。

此外，该语言允许用户将 ECMAScript 特性翻译成他们选择的旧 ECMAScript 目标。这提供了安全使用新特性的能力，同时始终保证与旧浏览器和 JavaScript 运行时保持向后兼容。

## 面向对象编程

最后，与 JavaScript 不同，它还没有接受面向对象的编程，TypeScript 在类、接口和继承方面支持面向对象的编程概念。

## 打字稿竞争者

当然，其他语言编译成 JavaScript，其中 CoffeeScript 和 Dart 最受欢迎。然而，TypeScript 始终在这些竞争对手中脱颖而出。

例如， [CoffeeScript](https://coffeescript.org/) 是一种轻量级语言，旨在简化 JavaScript。但是它为用户带来了可读性，却失去了工具的深层可读性，因为它缺少 TypeScript 提供的可选静态类型。

与此同时， [Dart](https://dart.dev/) 虽然也是 JavaScript 的类型化超集，但更像是该语言的完全替代品。

然而，对这些竞争对手来说，最具挑战性的是它们与 JavaScript 的互操作性；由于 Dart 和 Coffeescript 是相对较新的语言，对 JavaScript 的扩展需要更多特定于语言的执行。另一方面，TypeScript 在扩展到 JavaScript 方面具有明显的优势。

## 为什么使用 TypeScript？

TypeScript 建立在 JavaScript 之上，可以有效地填补空白，为开发人员提供更好的工具。与竞争对手相比，TypeScript 更容易也更有效。

### 易用性

TypeScript 的主要优点之一是易于使用。如果您至少对 JavaScript 有一点熟悉，那么开始使用 TypeScript 将不费吹灰之力。这是因为所有的 TypeScript 代码都被转换成 JavaScript 代码来执行。

反之，任何 JavaScript(。js)文件可以重命名为 TypeScript(。ts)文件，以便与其他类型脚本文件一起编译。

### 轻便

在许多方面，TypeScript *是* JavaScript，也就是说，TypeScript 代码转换成 JavaScript 以在 JavaScript 运行的任何地方运行。因此，用户可以确信 TypeScript 可以在 JavaScript 运行的任何环境下运行——浏览器、设备和操作系统。

这与许多 TypeScript 竞争对手形成了鲜明的对比，后者需要专用的 VM 或特定的运行时环境来执行。

### 强大的开发人员工具支持

总的来说，TypeScript 旨在通过减少错误、帮助解决问题和大规模交付更好的工具来提高开发人员的效率和生产力。

TSC 对开发人员也有好处，因为它可以作为后台进程运行，以支持编译和 IDE 集成。

## 如何开始使用 TypeScript

要开始使用 TypeScript，最好的方法是逐步采用。

这意味着逐步将类型应用到 JavaScript 中，以改进代码库和编辑器支持。

使用 TypeScript 的最常见方式是使用 TSC:

1.  编写类型脚本代码。
2.  然后，使用 TSC 将 TypeScript 代码编译成普通的 JavaScript 代码。
3.  最后，将 JavaScript 代码部署到任何运行 JavaScript 的环境中。

如果你想更深入地了解打字稿的细节，可以看看这篇全面的[打字稿教程](https://thenewstack.io/typescript-tutorial-a-guide-to-using-the-programming-language/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>