# TypeScript 如何赢得开发人员和 JavaScript 框架

> 原文：<https://thenewstack.io/how-typescript-won-over-developers-and-javascript-frameworks/>

TypeScript 最初由微软创建，然后作为 Apache License 2.0 下的开源项目发布，它通常被描述为“JavaScript 的超集”或“带类型的 JavaScript”。自 2012 年宣布以来，根据 2020 年 JS 报告(78%的受访者使用它)，它已经成为 JavaScript“口味”中的[主导者](https://2020.stateofjs.com/en-US/technologies/javascript-flavors/)。在最近的 Stack Overflow 开发者调查中，它也是 T2 第三受欢迎的语言，仅次于 Rust 和 Clojure。

TypeScript 由四个部分组成:编程语言本身；为 JavaScript 提供可选静态类型的类型检查器；将类型脚本代码转换成 JavaScript 代码的编译器；以及一个语言服务程序，它使用类型检查器来告诉编辑器(如 VS 代码)如何为开发人员提供有用的工具。

TypeScript 的许多早期采用者是 JavaScript 框架开发人员，尤其是 Angular 和 Dojo 背后的团队。“从根本上说，我最初对 TypeScript 感兴趣的地方是它引入了语言的接口，” [Living Spec](https://www.livingspec.com/) 的首席执行官、 [Dojo](https://dojo.io/) 框架的创建者 [Dylan Schiemann](https://www.linkedin.com/in/dylans/) 告诉新的 Stack。

“没有接口定义，你就不能安全地交换依赖关系，因为你不知道依赖关系应该做什么，”Schiemann 说。“因此，如果你是一个框架作者或正在开发一个大型应用程序，你无法控制某些东西是否会以它以前的方式运行。我们已经被它咬了一口，因此 Dojo 是 TypeScript 的早期采用者。”

## **静态打字**

TypeScript 对静态类型的支持也不应该被低估。JavaScript 仍然是动态类型的，这可能会在较大的代码库中导致各种难以捕捉的错误。例如，从版本 3 开始，Vue 框架 [100%是用 TypeScript 构建的，官方文档](https://twitter.com/youyuxi/status/1175433025179529216?lang=en)[称“随着应用程序的增长，静态类型系统可以帮助防止许多潜在的运行时错误，这就是 Vue 3 用 TypeScript 编写的原因”。](https://v3.vuejs.org/guide/typescript-support.html)

> "当世界转向 ES6 时，他们也转向了 TypeScript . "

-Dylan Schiemann，Living Spec 的首席执行官和 Dojo 框架的创建者

2015 年，谷歌决定 Angular 2 也将使用 TypeScript 构建，[引用静态类型作为理由之一](http://www.apple.com/uk)。Ryan Cavanaugh 是微软 TypeScript 语言的首席工程师，他认为这是更广泛采用 TypeScript 的主要动力。在一次与莱恩·多诺万讨论[栈溢出的](https://stackoverflow.blog/2020/06/15/talking-typescript-with-ryan-cavanaugh/)时，他说:

“……如果你看一下 TypeScript 的图表，几乎任何图表——GitHub 明星、下载、拉取请求——你都可以看到那个角度声明出现的确切时间点。图表就改变了。它从不回头。你再也看不到曲线上的那个小弯了，因为曲线一直在走。这是一个真正的转折点。

我认为有趣的是，当时人们认为 TypeScript 只是有棱角的人使用的东西，而不是其他东西。事实证明情况并非如此。显然，我们在棱角分明的开发者中还是很受欢迎的。但这对我们来说是一个真正的动力。"

相反，Schiemann 认为是 ECMAScript 6 的到来触发了转折点:“我认为当世界转向 ES6 时，他们也转向了 TypeScript，因为他们说，‘如果我要走这条路，让我在做这件事的时候看看 TypeScript。’"

## **社区的重要性**

不过，在 Schiemann 看来，微软对社区的管理更加重要。

“如果 TypeScript 的人作为一个团队根本不值得信任，我认为人们不会采用 TypeScript，”他说。“问题是，安德斯[海尔斯伯格]这个人超级聪明，但又超级平易近人。整个团队就是这样——他们就像是我合作过的最谦逊、最谦逊的团队，拥有那样的技术能力。”

Schiemann 解释说，当 Angular 背后的团队第一次开始使用 TypeScript 时，他们用它添加了一个他们需要的特性，叫做[decorator](https://www.typescriptlang.org/docs/handbook/decorators.html)。看到这一点，TypeScript 团队伸出了手，建议他们合作将该功能添加到 TypeScript 本身中。

“然后当 React 被更广泛地采用时，TypeScript 团队说，‘好吧，我们与 React 生态系统合作，帮助 TypeScript 更好地与 React 一起工作怎么样’，然后当 Svelte 开始流行时，他们做了类似的事情。所以他们在接触框架方面做得很好，并且说，‘嘿，我们怎么才能支持你？’"

这种拓展已经得到了回报，苗条的团队(像 Vue)在他们的版本 3 中采用了 TypeScript。即使在拥有自己的 Flow JavaScript 类型检查器的脸书，TypeScript 也被越来越多地使用——包括像 JavaScript 测试框架 [Jest](https://github.com/facebook/jest) 这样的项目。

## **开发者工具**

微软对社区的重视也延伸到了开发者工具；Angular 团队决定采用这种语言的另一个原因是。微软自己的 [VS Code](https://code.visualstudio.com) 自然对 TypeScript 有很大的支持，但是 TypeScript 语言服务器提供了一组通用的编辑器操作——比如语句完成、签名帮助、代码格式化和大纲。这简化了替代 ide 供应商的工作，比如带有 [WebStorm](https://www.jetbrains.com/webstorm/) 的 JetBrains(以及他们的一些其他 ide)。

JetBrains 的 WebStorm 项目经理 Ekaterina Prigara 告诉新的堆栈，“这种集成与我们自己的 TypeScript 支持并行工作——语言支持的一些功能由服务器提供，而其他功能，例如大多数重构和自动导入机制，则由 ide 自己支持。”

> TypeScript 语言服务器的出现减轻了工具制作者的开发负担。

集成的细节相当复杂。Prigara 继续说道，“显示了来自服务器的完成建议，但是在某些情况下，它们可以通过 IDE 的建议得到增强。错误检测和快速修复也是如此。格式化是由 IDE 完成的。hover 上显示的推断类型，如果我没弄错的话，来自服务器。但 IDE 总会提供一个后备方案，以防服务器响应时间过长。”

然而，TypeScript 语言服务器的可用性仍然减轻了工具制造商的开发负担。正因为如此，它被大量的工具和框架使用——例如， [ESLint](https://eslint.org) 用于类型检查，而 [Vue 用于它的类型脚本支持](https://v3.vuejs.org/guide/typescript-support.html#augmenting-types-for-globalproperties)。事实上，工具的角度是如此重要，据 Schiemann 所说，“对于一个 IDE 来说，不能快速开发的特性，TypeScript 团队是不会发布的”。

此外，由于 TypeScript 是一个编译器，它可以编译一个代码库来支持旧的浏览器和环境。再加上 linter 和对文档的内置支持，很容易理解为什么 TypeScript 如此引人注目。“在这一点上，我无法想象没有它能写出什么有意义的东西，”Schiemann 说，“因为它能帮助我写出更清晰、更易于维护的代码。”

## **不是你父亲的微软**

鉴于微软的开源历史，反思我们是如何走到这一步的是很有趣的。

当 TypeScript 首次推出时，负责维护和开发 JavaScript 定义的 TC-39 委员会未能就 ECMAScript 4 达成共识。这部分归因于微软:微软在 TC-39 上的代表艾伦·沃夫斯-布洛克认为这种语言太复杂了，对自己不利，[表达了对“网络‘消化’如此巨大变化的能力”的担忧](https://docs.microsoft.com/en-gb/archive/blogs/jscript/ecmascript-3-and-beyond-the-road-to-harmony)。Dojo、JQuery 和 MooTools 等 JavaScript 工具在 2012 年主导了 web 开发领域，但用 JavaScript 编写大规模应用程序仍然具有挑战性。

安德斯·海尔斯伯格称[这样做的原因是“JavaScript 从来就不是为大型应用程序设计的编程语言。这是一种脚本语言。它没有静态类型，但更重要的是，它可能缺少你在大型应用程序中需要的一些结构化机制，比如类、模块，或许还有接口。”](https://www.youtube.com/watch?v=g48K9LEhHWs)

[https://www.youtube.com/embed/BUo7B6UuoJ4](https://www.youtube.com/embed/BUo7B6UuoJ4)

视频

正如 Hejlsberg 指出的，当时一个流行的选择是利用现有的成熟生态系统，然后将应用程序移植到 JavaScript。也许这方面最著名的例子是 Google Web Toolkit (GWT ),它利用了 Java 生态系统，允许开发人员用 Java 编写代码，并使用 Eclipse 和 IntelliJ 等 ide。ScriptSharp 为希望使用 C#和。网络生态系统。

挑战在于，如果你想利用 JavaScript 生态系统中的任何东西，你首先必须封装它；正如 Hejlsberg 所说，“你总是和你瞄准的目标保持一臂之遥。”

> 由于 TypeScript 是基于 JavaScript 的，所以任何 JavaScript 程序也是有效的 TypeScript 程序。

一种解决方案是在语言中添加类和模块，但这并不像乍看上去那样简单。像软件架构一样，语言设计也涉及一系列复杂的权衡。JavaScript 早期的成功至少在一定程度上归因于这样一个事实，即对于 web 设计人员来说，学习和构建工作脚本相对容易，即使它是一种很难真正掌握的语言。通过添加功能来支持更大的代码库，您也增加了学习曲线，并使它更难用于最初打算用于的简单脚本任务。

微软的解决方案不是改变 JavaScript 本身，而是在它的基础上建立一种新的语言，添加他们认为开发更复杂应用程序的开发人员所缺少的东西——如静态类型、类和模块——并让 JavaScript 成为那些需要它的人的简单脚本语言。

这意味着 TypeScript 仍然可以从更广泛的 JavaScript 生态系统中受益。由于 TypeScript 是基于 JavaScript 的，所以任何 JavaScript 程序也是有效的 TypeScript 程序。

当然，开源使得社区围绕这种语言发展成为可能。

尽管如此，当时人们很容易持怀疑态度。微软在开源社区中为自己赢得了一个坏名声。2001 年，微软当时的 CEO 史蒂夫·鲍尔默宣称“ [Linux 是癌症](https://www.theregister.com/2001/06/02/ballmer_linux_is_a_cancer/)”该公司赞助了 [SCO 对 Linux 的版权攻击](https://www.eweek.com/servers/microsoft-and-sco-fud-brothers/),[声称](https://www.eweek.com/servers/author-of-linux-patent-study-says-ballmer-got-it-wrong/) Linux 侵犯了微软未公开的专利，并迫使基于 Linux 的 Android 供应商[为可疑的专利索赔](https://www.zdnet.com/article/microsoft-profits-from-linux-patent-fud/)付费。

> TypeScript 团队已经加入 TC-39，成为试图改进 JavaScript 的更广泛社区的一部分。

长期的行业观察家还会记得微软对“[拥抱、扩展和消灭](https://en.wikipedia.org/wiki/Embrace,_extend,_and_extinguish)”的使用，特别是在 20 世纪 90 年代后半期，导致了故意的浏览器不兼容，阻止了 Office 文档在 IE 以外的浏览器中正确呈现，并破坏了 Java 的可移植性。

相比之下，TypeScript 团队现在已经加入了 TC-39，成为试图改进 JavaScript 的更广泛社区的一部分，而不是试图取代它。此外，TypeScript 一直作为一个适当的开源项目运行。在处理问题时，JetBrains 的 Prigara 告诉我，“我们主要依靠 GitHub 上公开的信息(路线图、问题、提交)。我们有他们项目经理的联系方式，但总的来说，我们更愿意在 GitHub 上提出问题。”

席曼同意了。“TypeScript 团队告诉我的一件事是，”他说，“当他们完全接受开源时，他们仍然会收到企业的请求，比如，‘你能为 X 公司的 TypeScript 添加这个功能吗？’他们会回答‘嗯，不行，你必须在 GitHub 中打开一个问题，提出你的案例，也许还需要提供一个公关。如果你想要这个开源，你必须像一个开源项目一样运行它。”

最终，TypeScript 通过微软成为优秀的开源管理者和公民而获得了胜利。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>