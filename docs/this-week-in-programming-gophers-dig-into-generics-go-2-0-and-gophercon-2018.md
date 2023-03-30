# 本周编程:地鼠挖掘泛型，Go 2.0 和 Gophercon 2018

> 原文：<https://thenewstack.io/this-week-in-programming-gophers-dig-into-generics-go-2-0-and-gophercon-2018/>

在过去的一周里，将近 2000 只地鼠(你们这些 Golang 人是这么称呼自己的，对吗？)来到一英里高的城市参加第五届年度 Gophercon(T1)，希望不会有太多的人因为像 T2 的仿制药(T3)或 T4 最近采用的 vgo 语义版本控制(T5)之类的事情爆发打斗。正如你可能预料的那样，这次活动为 Golang 世界提供了一些重大消息，包括即将发布的最新版本的 Go，对下一个大版本 Go 的窥探，以及一些关于如何确定下一个大版本的过程的讨论。所以，从本周开始，我们将为你的 Golang 爱好者们快速浏览一下最新消息。

首先，最新版本 Go 1.11，[在大会之前发布](https://blog.golang.org/go1.11)，它见证了“对工具链、运行时和库的许多改变和改进，但有两个特性特别令人兴奋:模块和 WebAssembly 支持。”

[https://www.youtube.com/embed/rWJHbh6qO_Y?feature=oembed](https://www.youtube.com/embed/rWJHbh6qO_Y?feature=oembed)

视频

正如我们上周所讨论的，这个最新版本“为一个叫做“模块”的新概念[、](https://golang.org/doc/go1.11#modules)增加了初步的支持，这个新概念仍然“被认为是实验性的”，并且是前面提到的、有点争议的 vgo 的重命名版本。Go 1.11 还为 [WebAssembly](https://golang.org/doc/go1.11#wasm) 增加了一个实验端口，该端口“允许程序员将 Go 程序编译成兼容四大 web 浏览器的二进制格式。“当然，到现在为止，你已经阅读了所有关于 1.11 版本的内容。但是如果你还没有，总会有[发布说明](https://golang.org/doc/go1.11#minor_library_changes)，以及 [JAXEnter](https://jaxenter.com/go-1-11-modules-webassembly-148629.html) 和 [InfoWorld](https://www.infoworld.com/article/3201037/google-go/whats-new-in-googles-go-language.html) 中的一个特性综述，它们做得很好。

当然，Gophercon 的最大亮点可能是“对错误处理和泛型更改的可能设计的初步草案的一瞥”，你可以观看 Go 项目负责人 Russ Cox 在这里讨论的内容:

[https://www.youtube.com/embed/6wIP3rO6On8?feature=oembed](https://www.youtube.com/embed/6wIP3rO6On8?feature=oembed)

视频

科技博客 [PacktHub 提供了关于 Go 2.0](https://hub.packtpub.com/go-2-design-drafts-include-plans-for-better-error-handling-and-generics/) 的快速阅读，指出 Cox 似乎还不太相信泛型的必要性。在上面的视频中，Cox 说“我最近一直在研究泛型，但是我对 Go 用户需要泛型来解决的详细、具体的问题没有清晰的印象。结果，我无法回答像是否支持泛型方法这样的设计问题。”Cox 还讨论了采用新功能的过程，并评论说 Go 2.0 目前正处于“识别和解释问题”阶段，这必然是在提出和讨论解决方案之前。(这是否感觉像是“请不要对任何事情过于生气？”对其他人吗？)

当然，我们可以详细讨论 Go 2.0，但在继续本周的其他新闻之前，还有更多值得注意的地方！微软本周也加入了 Golang 新闻周期，在[宣布了 Project Athens 和 GopherSource](https://open.microsoft.com/2018/08/28/announcing-project-athens-gophersource-go-community/) ，它说这“代表了微软一直在做的工作中的一个重要里程碑，使 Go 开发者能够构建和运行更好的应用和服务，在 Visual Studio Code 和 Visual Studio Team Services 等工具中以及在我们的 Azure 云平台上支持 Go。”开源项目 Athens 致力于为围棋模块创建第一个代理服务器，而 [GopherSource](https://gophersource.com/) 则是一个社区空间，据 [JAXEnter](https://jaxenter.com/go-athens-gophersource-148902.html) 称，用于“为围棋提供反馈和评论，提出官方围棋建议并加以实施，培养更好的围棋社区，并为开源做出贡献”。万一你错过了…

## 本周的节目中

*   **GitHub 介绍了一个善意但可能命名不当的“项目剪纸”:**我不知道你，但当我想到剪纸时，我会退缩。嗯，这是 GitHub 最新努力的名字，[项目剪纸](https://blog.github.com/2018-08-28-announcing-paper-cuts/)，它声称要解决“每天困扰你的可用性挑剔，但可能不是我们更大的产品计划的一部分。”我明白了。剪纸很小。这些问题都很小。但是“千刀万剐”(如果你喜欢，也可以叫剪纸)指的是[，通常是](https://www.investopedia.com/terms/d/death-1000-cuts.asp)，指的是“许多小问题导致的失败”哦，好吧，我想我们正在翻转这一个在它的头上并且谈论申请一些液体绷带到这些剪纸？是啊，就这么办吧。无论如何，剪纸项目“致力于直接与社区合作，解决中小型工作流问题，迭代 UI/UX，并通过更仔细地倾听和“观察更广泛的 GitHub 社区创建的自组织[“功能请求”存储库](https://github.com/isaacs/github)和[浏览器扩展](https://github.com/collections/github-browser-extensions)，以及[积极寻求反馈](https://twitter.com/lukehefson/status/1022553956466216960)，找到其他最重要的快速改进方法”撇开我自己对这个名字的问题不谈，这听起来是一个很大的进步。

https://Twitter . com/aero drive _ India/status/1033779730653241344

*   **GitHub 为 GitHub for Visual Studio 添加检查和状态:**同样在 GitHub 的世界里，一个[对 GitHub for Visual Studio 的快速更新](https://blog.github.com/2018-08-28-checks-and-status-GfVS/)，现在支持 pull 请求中的检查和状态。根据公告，检查和状态有助于确定是否满足为存储库设置的条件，它们的添加将允许每次提交显示每个检查的挂起、通过或失败状态，并提供“审查和合并拉请求的必要信息”，并“使我们离构建完整的拉请求工作流更近一步。”
*   **平台风险、锁定和关心:**本周有几篇关于平台风险、锁定以及这些公司是否关心 API 和依赖它们的开发者/用户的文章值得注意。首先，ProgrammableWeb 写道 [23andMe 将关闭其公共 API，给开发者两周的通知](https://www.programmableweb.com/news/23andme-to-shutter-public-api-gives-developers-two-weeks-notice/brief/2018/08/24)，并跟随许多其他公司的脚步，似乎在一毛钱上放弃了他们的开发者。该 API 已经存在了六年，“旨在让开发者能够利用该公司的基因数据集来构建应用和工具。”不幸的是，23AndMe 告诉其开发者，它计划“专注于基于我们向客户提供的解释和结果的应用程序”，仅此而已。与此同时，网站上的另一个故事讲述了两个开发者和他们对[挑战谷歌地图定价](https://www.programmableweb.com/news/time-to-challenge-google-maps-pricing/elsewhere-web/2018/08/26)的呼吁。他们说，谷歌地图“客观上是其市场上最好的产品”，但该产品“最近价格的大幅上涨使其成本远远高于替代品。”最后，像这样的故事，以及 Twitter 最近的头条新闻再次关闭 API，不得不让人怀疑——正如 API 传播者 Kin Lane 沉思的那样——公司是否对 API 带来的互操作性感兴趣。剧透一下，他们不是。

*   **Babel 7 现支持 TypeScript:** 没错，微软本周宣布 [TypeScript 和 Babel 7](https://blogs.msdn.microsoft.com/typescript/2018/08/27/typescript-and-babel-7/) 现已狼狈为奸。显然“Babel 用户中的一个共同主题是试图设置 TypeScript 太难了”，所以现在微软已经与 Babel 团队合作，使之变得容易。对于不熟悉的人， [Babel](https://babeljs.io/) 将最新的 JavaScript 特性转换到旧的运行时和浏览器上，但是，正如微软指出的，“不做类型检查，我们的团队相信这可以将体验带到另一个水平。”虽然 TypeScript 可以做这两种事情，他们写道，“我们希望在不强迫用户从 Babel 切换的情况下，更容易获得这种体验。”因此，新发现的支持。对于那些希望使用这个组合的人，请确保进一步阅读，因为“用户应该知道的第一件事是，Babel 不会对 TypeScript 代码执行类型检查；它只会转换您的代码，不管是否存在类型错误，它都会编译。”
*   **期待 JavaScript 2018:** 最后，Mary Branscombe 从我们自己的页面中查看了 JavaScript 2018 中的[，写道“2018 年 6 月发布的最新年度](https://thenewstack.io/whats-coming-up-in-javascript-2018-async-generators-better-regex/) [ECMAScript 更新](http://www.ecma-international.org/ecma-262/9.0/index.html)，是迄今为止最大的年度发布。”根据 Brandscombe 的说法，“这个版本中最大的两个开发人员特性是异步生成器和一些期待已久的正则表达式改进，以及 rest/spread 属性”，但这篇文章提供了几个进一步的细节。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>