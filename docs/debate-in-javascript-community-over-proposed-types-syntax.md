# JavaScript 社区中关于建议类型语法的争论

> 原文：<https://thenewstack.io/debate-in-javascript-community-over-proposed-types-syntax/>

如果本周公布的一项[提议得以实现，JavaScript 开发者将很快拥有他们中的许多人长期以来](https://devblogs.microsoft.com/typescript/a-proposal-for-type-syntax-in-javascript/)[向](https://2020.stateofjs.com/en-US/opinions/missing_from_js/)要求的东西:一个[类型的系统](https://en.wikipedia.org/wiki/Type_system)，至少是某种类型的。

TypeScript 高级项目经理 [Daniel Rosenwasser](https://devblogs.microsoft.com/typescript/author/danielrosenwasser/) 的一篇博客文章展示了 JavaScript 中类型语法的[提案的背景和理由。他写道，“如果我们完成了这一切，我们就有机会对 JavaScript 世界做出最有影响力的改进。”](https://devblogs.microsoft.com/typescript/a-proposal-for-type-syntax-in-javascript/)

由来自微软、彭博、Igalia 和一些其他来源的作者组成的[提案](https://github.com/giltayar/proposal-types-as-comments)建议 JavaScript 开发者应该能够“向他们的 JavaScript 代码添加类型注释，允许那些注释被 JavaScript 外部的类型检查器检查”，然后在运行时被忽略。

Rosenwasser 在他的博客文章中写道:“因为这种新语法不会改变周围代码的运行方式，它实际上可以充当注释，”随后补充道，“JavaScript 可以为引擎完全忽略的类型创建一套语法，但 TypeScript、Flow 和其他工具可以使用这些语法。这使我们能够保留您喜欢的 TypeScript 的东西——它的类型检查和编辑体验——同时消除开发中的构建步骤。”

到目前为止，类型被归入 TypeScript，部分原因是这个构建步骤也可以用于为各种浏览器编译代码。然而，随着不断更新的 evergreen 浏览器的出现，该提案的作者写道，他们“预计开发人员将不再需要向下编译”，因此，“对于许多 TypeScript 用户来说，编写代码和运行代码之间唯一必要的步骤是删除类型注释。”

提案中一个值得注意的部分准确地列出了没有提出的内容:

“我们的团队并不建议在每个浏览器和 JavaScript 运行时都加入 TypeScript 的类型检查功能，也不建议在浏览器中加入任何新的类型检查功能。我们认为这样做会给 JavaScript 和 TypeScript 用户带来一系列问题，比如运行时性能、与现有 TypeScript 代码的兼容性问题，以及停止类型检查领域创新的风险。”

类似地，TypeScript 中生成代码的几个特性，如[枚举](https://www.typescriptlang.org/docs/handbook/enums.html)、[名称空间](https://www.typescriptlang.org/docs/handbook/namespaces.html)和[参数属性](https://www.typescriptlang.org/docs/handbook/classes.html#parameter-properties)，被明确排除，“因为它们具有运行时语义，生成 JavaScript 代码，而不是简单地被剥离和忽略。”

正如您所料，JavaScript 中潜在的类型添加——即使是完全可选的类型——并不是每个人都完全同意的。

对于许多批评者来说，他们的论点是，将类型作为注释添加会不必要地使代码在视觉上变得复杂，并使新开发人员更加困难。他们还认为，为了避免代码膨胀，仍然需要一个额外步骤来删除代码。其他人仍然认为 TypeScript 是 TypeScript，而不是 JavaScript 是有原因的，但是他们可能忽略了这个提议有意排除了许多 TypeScript 特性。

“这个提议是一个平衡的行为:试图尽可能地兼容 TypeScript，同时仍然允许其他类型系统，并且不会过多地阻碍 JavaScript 语法的发展，”该提议在这一点上提出。

正如该提案的作者所指出的，该提案本身是以“斯特劳珀森提案”的形式提出的，正因为如此，它旨在引发这种激烈的辩论。到目前为止，似乎已经有了足够的争论，同时对你身边的 JavaScript 的类型功能的到来也有相当强烈的热情。

## 本周的节目中

*   **谷歌代码之夏滴滴导师名单:**对于那些考虑申请[谷歌代码之夏(GSoC) 2022](https://summerofcode.withgoogle.com/) 的人来说，[导师组织名单已经揭晓](http://opensource.googleblog.com/2022/03/Google-Summer-of-Code-2022-mentoring-orgs-revealed.html)。它增加了 32 个新的组织，使总数达到 203 个开源项目。[组织](https://summerofcode.withgoogle.com/programs/2022/organizations)包括各种基金会 Linux 基金会、云计算基金会、Eclipse 基金会、Python 软件基金会等等——以及开源项目，如 TensorFlow、GitLab、Jenkins、Dart、Ruby、Julia 等等。GSoC 每年(北半球)夏季运行，以开源软件贡献的方式指导开发人员。申请于 4 月 4 日(星期一)开始，4 月 19 日(星期二)结束。
*   **DHH 事件的余波还在继续:**上周，我们讲述了 Ruby on Rails 的创作者 [DHH 和 RailsConf 如何在 RailsConf 团队要求他分享主题演讲台后分道扬镳](https://thenewstack.io/railsconf-and-dhh-go-their-separate-ways/)，而本周余波还在继续，因为 Rails 核心团队成员[卡斯珀·蒂姆·汉森](https://github.com/kaspth)相当突然地[离开了核心团队](https://twitter.com/kaspth/status/1501186646418640898)。汉森在一周前就已经表达了他对这种情况的不满，当时他在推特上说他不想在 DHH 的博客文章中被提及，此后不久他发出了一个简单的请求“我要离开 Rails core，我对成为校友不感兴趣”当 [Kasper 加入 Rails 核心](https://rubyonrails.org/2016/7/19/Kasper-joins-Rails-core)的时候，有一个很好的宣传，如果对他的 tweet 和 pull 请求的回应是任何迹象的话，这个[Rails 第十一多产的贡献者](https://contributors.rubyonrails.org/contributors)看起来会被整个社区错过。
*   **嵌入式软件开发进入 VS 代码:**继[发布类似的 Visual Studio 2022](https://devblogs.microsoft.com/cppblog/visual-studio-embedded-development/)之后，微软[发布了](https://devblogs.microsoft.com/cppblog/vscode-embedded-development/)Visual Studio 代码的[嵌入式工具扩展](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-embedded-tools)，根据扩展的描述，它“为 [CMSIS-SVD](https://www.keil.com/pack/doc/CMSIS/SVD/html/index.html) 文件提供了一个注册查看器，以及一个支持 [Azure RTOS](https://azure.microsoft.com/en-us/services/rtos/) 和 [FreeRTOS](https://www.freertos.org/) 的 RTOS 数据查看器。”该扩展与新的 [vcpkg 工件功能](https://devblogs.microsoft.com/cppblog/vcpkg-artifacts/)一起使用，有助于获取嵌入式工具依赖关系，允许开发人员快速启动嵌入式开发机器并开始使用。随着这一扩展的加入，VS Code 现在为开发人员提供了所有常见的功能，包括代码导航、智能感知、构建、部署、调试，以及围绕外围寄存器和实时操作系统(RTOS)对象视图的新的诊断功能。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>