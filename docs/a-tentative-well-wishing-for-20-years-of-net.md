# 一个试探性的 20 年的美好愿望。网

> 原文：<https://thenewstack.io/a-tentative-well-wishing-for-20-years-of-net/>

20 周年纪念日。根据 Stack Overflow 的开发者调查，NET 本周即将发布，微软正在全力以赴庆祝它所说的“连续三年最受开发者喜爱的框架——[2019](https://insights.stackoverflow.com/survey/2019#technology-_-most-loved-dreaded-and-wanted-other-frameworks-libraries-and-tools)、 [2020](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-other-frameworks-libraries-and-tools) 、 [2021](https://insights.stackoverflow.com/survey/2021#section-most-loved-dreaded-and-wanted-other-frameworks-and-libraries) ”

第一辆[于 2002 年推出](http://web.archive.org/web/20020205134906/http:/msdn.microsoft.com/vstudio/launch/default.asp)。在某种程度上，微软可以推出. NET 作为其多年来改变方式的证据。它从一个在此版本发布前一年卷入垄断案的公司[,变成了一个后来决定扭转乾坤，改变以往做法，并](https://en.wikipedia.org/wiki/United_States_v._Microsoft_Corp.)[开源的公司。网芯](https://thenewstack.io/why-you-should-care-about-the-new-open-source-net-core/)。

“当微软进行另一次重大转型时，这一次是走向开源。微软在本周的庆祝博客中写道。“到 2012 年，我们已经完全开源了 ASP.NET MVC web 框架，并开始接受贡献。这是当时微软的第一个主要开源项目之一。2014 年，我们开始建立跨平台和开源。我在 GitHub . NET 上看到了这个网站，并被开源社区令人难以置信的支持和贡献深深打动。”

当然，与我们曾经认识的微软相比，它在开源软件和开放性方面已经有了巨大的转变。事实上，这些天来，微软也是开源世界的另一个巨头的代名词，它现在的子公司 GitHub——以及 npm 注册表和无数其他项目。微软已经从一个曾经由一个说“Linux 是一个癌症”的人领导的公司转变为一个最近欢迎 Linux 进入 Windows 桌面的公司，以及许多其他开源努力。

在一篇庆祝 20 周年的博文中。SUSE 高级技术布道者 Robert Sirchia 写了这个转变。

“最初是一个闭源项目，现在是相当开放的源代码。这对任何公司来说都是一个巨大的转变。这种转变不仅开放了代码，还改变了代码的运行方式，”Sirchia 写道，随后补充道，“总而言之，我是因为. NET 而改变了职业生涯的许多人之一。”

当然，这些庆祝活动中没有提到的也许是最大的考验。NET 在开放性方面的优势。去年，我们写道[微软的“热重装”剧提醒我们注意](https://thenewstack.io/microsofts-hot-reload-drama-is-a-reminder-to-pay-attention/)，现在看来仍然值得一提。

当时，互联网上充斥着关于[微软如何试图在它的产品上耍花招的讨论。NET community](https://www.theverge.com/2021/10/22/22740701/microsoft-dotnet-hot-reload-removal-decision-open-source) 通过逆转进程并移除[“热重装”特性](https://devblogs.microsoft.com/dotnet/introducing-net-hot-reload/)从。NET，而不是[将它的作用域扩展到可视代码 2022](https://github.com/dotnet/sdk/pull/22217) 。只是在微软内部的 Scott Hanselman 和其他人发了一系列含糊不清的推文之后，一篇问我们是否可以信任微软开放源代码的文章，以及一个备受关注和支持的撤销决定的请求之后，微软改变了态度，并发表了道歉声明。

这就是说，也许结局好就是好，我们确实应该庆祝开源框架 20 年来的成功。同样，如果我们想在今后庆祝另一个这样的周年纪念，保持警惕可能是必要的。

## 本周的节目中

*   **GitHub 使用 Mermaid 获得图表:**您不再需要在 GitHub Markdown 文件中嵌入图像来显示流程图、UML、Git 图表、用户旅程图或甘特图等内容。取而代之的是，GitHub 现在允许用户[使用美人鱼](https://github.blog/2022-02-14-include-diagrams-markdown-files-mermaid/)在他们的降价文件中包含图表，美人鱼是一个基于 JavaScript 的图表和制图工具，使用“受降价启发的文本定义”在浏览器中动态创建图表。创建这些图表的文本使用了[的美人鱼语法](https://mermaid-js.github.io/mermaid/#/n00b-syntaxReference?id=syntax-structure)，它被用来“生成一个 iframe，该 iframe 采用原始的美人鱼语法并将其传递给 Mermaid.js，将代码转换成您本地浏览器中的图表。”关于 GitHub 如何将这些文本转化为图表的更多细节，请点击博客文章；但是可以说，用户现在有了一种简单的方法来创建图表，而不需要离开 GitHub 编辑器。
*   **吹捧 Rust 的可持续性:**亚马逊长期以来一直对 Rust 编程语言的使用直言不讳，它被用于一些项目，如[鞭炮](https://firecracker-microvm.github.io/)、 [AWS Lambda](https://aws.amazon.com/lambda/) 背后的虚拟化技术，或[基于 Linux 的容器操作系统 Rust](https://aws.amazon.com/bottlerocket/)，甚至[亚马逊简单存储服务](https://aws.amazon.com/s3/)(亚马逊 S3)[亚马逊弹性计算云](https://aws.amazon.com/ec2)(亚马逊 EC2)和[亚马逊 CloudFront【12】虽然采用 Rust 的理由很多——其中性能和内存安全性最高——但亚马逊本周在一篇关于 Rust 可持续性的博客文章中概述了另一个理由。当然，性能可能与这种可持续性有关，因为效率对应用程序使用多少功率有直接影响；亚马逊指出几年前的一项研究发现“C 和 Rust 在能效方面明显优于其他语言”，两者都“比 Java 大约高效 50%，比 Python 高效 98%。”他们进一步指出，正是 Rust 在不牺牲性能的情况下提供了内存安全，这使它在可持续发展的选择上超过了 C。如果你对你的软件大规模运行的环境影响感兴趣(这也是应该的)，Rust 肯定是一个顶级竞争者，AWS 关于这个主题的博客文章是一个很好的起点。](https://aws.amazon.com/cloudfront/)

*   TypeScript 4.6 发布候选版本:TypeScript 的下一个发布候选版本(RC)本周登陆， [TypeScript 4.6 RC](https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-rc/) ，这是同一版本最近 [beta 版](https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-beta/)的后续版本。自从测试版以来[有了一些变化，例如](https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-rc/#beta-delta)[析构的可区分联合的控制流分析](https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-rc/#cfa-destructured-discriminated-unions)和 [es2022](https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-rc/#target-es2022) 输出目标，但除此之外，TypeScript 团队主要专注于错误修复和始终存在的性能改进。然而，除此之外，TypeScript 4.6 将带来这样的能力:允许在 super()[之前的构造函数中使用 dode，对被析构的有区别的联合进行控制流分析](https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-rc/#cfa-destructured-discriminated-unions)，[改进的递归深度检查](https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-rc/#improved-depth-checks)，[索引访问推理改进](https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-rc/#indexed-access-inference-improvements)，[JavaScript 中更多的语法和绑定错误](https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-rc/#syntax-errors-js)，以及 [TypeScript 跟踪分析器](https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-rc/#typescript-trace-analyzer)。还有一些[突破性的变化](https://devblogs.microsoft.com/typescript/announcing-typescript-4-6-rc/#breaking-changes)需要注意，所以在你更新任何东西之前一定要检查一下。
*   **Visual Studio 2022 继续前进:**微软宣布 [Visual Studio 2022 17.1 现已推出](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-17-1-is-now-available/)，随之而来的是大量“令人兴奋的新增功能”，包括 Git、搜索和导航方面的增强，C#和 C++中的生产率提高，以及个性化彩色标签的新增功能。所有这些，你已经在之前的预览中看到了，但是现在已经准备好投入生产使用了——还有社区建议的一些[修复](https://developercommunity.visualstudio.com/fixes)。除此之外，微软表示，在解决方案成交表现方面，也有一些生产力增强和改进。要查看新特性的完整列表，请前往 [Visual Studio 17.1 GA 发行说明](https://docs.microsoft.com/visualstudio/releases/2022/release-notes)。与此同时，Visual Studio 2022 的第二次更新 17.2 的第一个预览版即将发布，并将带来针对的错误修复和改进。NET MAUI 开发、Git 体验的持续增强、对新的 C# 11 重构的支持(例如一个名为[原始字符串文字](https://github.com/dotnet/csharplang/blob/main/proposals/raw-string-literal.md)的新语言特性)以及使用 SQLite、Postgres 和 MongoDB 数据源对数据进行本地开发的新功能。最后但同样重要的是，[Visual Studio 2022 for Mac Preview 6](https://devblogs.microsoft.com/visualstudio/visual-studio-2022-for-mac-preview-6/)也于本周发布，它对上个月预览版中发现的问题进行了大量修复，并继续推进 IDE 向原生 macOS UI 的迁移。
*   **调查说！**关于两种相当流行的语言的两项调查结果本周在网上发布，随着 [Rust Survey 2021 结果](https://blog.rust-lang.org/2022/02/15/Rust-Survey-2021.html)和 [2021 年 JavaScript 状态](https://2021.stateofjs.com/)的发布也终于有了出路。对于对当今最流行的两种语言感兴趣的开发人员来说，这两种语言都提供了一些关于什么是什么的见解，所以请过来看看吧。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>