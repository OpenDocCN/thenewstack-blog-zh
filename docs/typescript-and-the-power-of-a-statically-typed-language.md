# TypeScript 和静态类型语言的威力

> 原文：<https://thenewstack.io/typescript-and-the-power-of-a-statically-typed-language/>

如果说 TypeScript 的成功有一个[秘诀，那就是类型检查，确保流经程序的数据是正确的数据类型。类型检查减少了错误，为更好的工具奠定了基础，并允许开发人员在更高的层次上映射他们的程序。而](https://thenewstack.io/how-typescript-helps-enterprise-developers/) [TypeScript](https://www.typescriptlang.org/) 本身，一个静态类型化的 JavaScript 超集，确保了一大批 JavaScript 程序员能够以最小的学习曲线轻松享受这些高级编程的好处。

在最新一期的 [The New Stack Makers 播客中，](/podcasts)我们采访了一些 TypeScript 的设计者和维护者，以进一步了解这种语言的设计: [Ryan Cavanaugh](https://www.linkedin.com/in/ryan-cavanaugh-aa4a37106/) ，微软[的首席软件工程经理](https://www.microsoft.com/)；[卢克·霍班](https://www.linkedin.com/in/lukejhoban/)，[普鲁米](https://www.pulumi.com/)的首席技术官，打字稿的原创者之一，以及；[微软高级项目经理 Daniel Rosenwasser](https://www.linkedin.com/in/daniel-rosenwasser-b56b7837/) 。TNS 编辑 [Darryl Taft](/author/darryl-taft/) 和 [Joab Jackson](/author/joab/) 主持了讨论。

[打字稿和静态类型语言的力量](https://thenewstack.simplecast.com/episodes/typescript-and-the-power-of-a-statically-typed-language)

时任微软开发人员工具小组成员的霍班回忆道，2012 年，TypeScript 作为一种帮助 C++或 C#开发人员编写大型 web 应用程序的方式出现在微软内部。

自然的选择是使用 JavaScript，这是网络的主流语言。但是 JavaScript 并没有提供很多工具来帮助开发人员组织、协助和检查他们的代码编写。霍班说，微软和其他网络规模的公司开发的各种早期解决方案主要是将 C++等传统语言编译成 JavaScript，尽管这让开发人员“与平台保持一定距离”。

他们希望开发一种语言，能够“将类型表达到语法中，作为 JavaScript 的轻量级扩展，但是……仍然提供尽可能多的推理，所以你需要尽可能少地使用那些注释，”霍班说。

答案是创建一个与 JavaScript 完全兼容的 JavaScript 超集，并且可以转换成 JavaScript 以实现完全的浏览器兼容性。为了增加严密性，它附带了额外的类型检查。但是这是一种细微的类型检查形式，对开发人员来说不会太痛苦。

该项目的开发人员为 TypeScript 提供的灵活性感到自豪。他们承认，简单地要求开发人员给每个变量分配一个预先定义的类型是多余的。开发人员可能想做一些棘手的事情，比如创建一个函数，它可以复制一个对象的相同副本，但是属性名都是小写的。类型系统必须支持这种复杂性。

“在我们的类型系统中，我们有很多表达能力，”卡瓦诺说。“随着时间的推移，我们在类型系统中建立了许多结构，当你创建一个类型时，你实际上是在我们的类型系统中通过一种迷你编程语言来运行它。”

开发团队希望最近已经实现了递归类型，其中自定义类型可以是一组编程规则。

“我们试图启用正确的模式，让你能够真正表达你的 JavaScript 在运行时正在做什么。卡瓦诺说:“我们不希望人们走极端，但我们正努力避免让他们陷入某些情况。”。

TypeScript now [实现了](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-0.html)一个基于控制流的局部变量和参数的类型分析。为此，设计团队进行了代码流分析，以更好地了解数据类型是如何被使用的，因此 TypeScript“就像自动获取类型在程序中的流动方式一样，所以你只是在一天结束时真正编写 JavaScript，”Cavanaugh 说。(尽管类型检查有好处，但如果它发现自己融入 JavaScript 本身，可能需要一段时间，我们的小组成员同意这一点。对于浏览器来说，基本的类型检查很容易，但是最复杂的评估在运行时很难实现。)

有了 TypeScript，开发人员能够在更大的范围内设计他们的程序，这种方式对后来加入项目的其他人来说是有意义的。“所以你开始看到更丰富和更复杂的应用程序，否则这是不可能的，”卡瓦诺指出。例如，TypeScript 在微软的大部分网络应用程序中都有使用。它是 JavaScript 框架开发人员的最爱，包括 Angular.js. Slack 使用 Typescript 构建其桌面客户端。它是一个流行的开源网页设计工具 [Figma](https://www.figma.com/about/) 的[组成部分](https://www.figma.com/plugin-docs/typescript/)。

但是它也可以用于较小的项目。Rosenwasser 回忆说，他为一个一次性项目写了一个小脚本。最初，他选择了 JavaScript，这样他就不必经历 transpiler 步骤。然而，他陷入了寻找一个难以捉摸的错误。他通过 TypeScript `ts-check`工具运行代码，立即发现了错误。

打字也有助于安全。JavaScript 是为敌对的 web 环境构建的，它已经有了很好的内置安全性，内置内存安全性和一系列运行时检查。Typescript 有助于显示和防止更高级别的逻辑错误，尤其是那些错误处理输入数据所导致的错误。

“数据损坏会导致安全问题。卡瓦诺说:“确保你总是以正确的方式称呼事物只是其中的一部分。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>