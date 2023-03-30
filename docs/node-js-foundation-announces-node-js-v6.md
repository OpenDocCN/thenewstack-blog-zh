# 新的 Node.js 加载模块的速度提高了四倍

> 原文：<https://thenewstack.io/node-js-foundation-announces-node-js-v6/>

服务器端 JavaScript 运行时引擎 Node.js 已经快了很多。

Node.js 基金会周二发布了 Node.js 的[版本 6，它将提供安全更新、性能改进和增强的稳定性。](https://nodejs.org/download/release/v6.0.0/)

这次更新对开发者最大的好处是性能。Node.js v6 加载模块的速度是其 LTS(长期支持)前身 Node.js v4 的四倍。由于大多数节点部署依赖于多个外部模块，这一改进可以显著缩短启动复杂的基于节点的部署所需的时间。

通过包含最近更新的 v8 JavaScript 引擎 vesrion 5.0，Node v6 还支持新的 [ECMAScript 2015 (ES6)标准](https://thenewstack.io/ecmascript-6-biggest-update-javascript-yet-start-rolling-annual-improvements/)。因此，现在 Node.js v6 版本也支持 93%的 ES6 功能，而 Node.js v5 和 Node.js v4 的支持比例分别为 56%和 50%。新的 ES6 特性包括默认和 rest 参数、析构、class 和 super 关键字。

随着新的 Buffer API 的加入，安全性也得到了提高，旨在减少泄漏到应用程序中的 bug 数量。它使用一种新的构造方法来创建缓冲区实例，并为空缓冲区使用命令行标志。

## 节点使用

像 NASA 和网飞这样的组织已经依赖 Node.js 和 NodeSource 这样的平台来支持他们的基础设施，两者都将 Node.js 的可伸缩性作为其突出的特性之一。

MRI Technologies 的软件工程总监兼首席架构师 Collin Estes 表示:“随着我们从传统环境过渡到现代的基于节点的架构，N|Solid 以及 NodeSource 的支持证明是非常宝贵的，它允许我们在专注于核心任务的同时快速扩展。

网飞最初从企业级 Java 环境迁移到 Node.js 是为了简化其[用户界面体验](https://thenewstack.io/netflix-uses-node-js-power-user-interface/)，尽管它在 OSS 中已经活跃了一段时间。网飞甚至开发了自己的[开源云奖](https://github.com/Netflix/Cloud-Prize)竞赛，自 2013 年起每年举办一次。当使用 Node.js 时，它发现构建速度也显著提高了。“Java 应用程序可能需要长达 40 分钟的启动时间，这并不完全有助于快速的 DevOps 过程，”网飞用户界面工程主任金·特罗特说。

## Node.js 提高生活质量

当在任何开发管道中工作时，自动化工作流是至关重要的，开发人员经常面临跨平台运行应用程序的挑战。当 Gojko Adzic 开始构建 [Claudia.js](https://github.com/claudiajs/claudia) 部署实用程序时，他注意到在 Node.js 中工作意味着这些问题被绕过，同时还允许自动化方面的更大灵活性。Claudia.js 帮助开发人员快速完成工作，使他们能够自动化样板代码，专注于更高优先级的工作负载。

“跨平台部署者让开发人员去处理特定于语言的问题和需求。因为克劳迪娅只负责 Node.js 项目，所以我们可以比一般的部署人员自动化得多——我们知道典型的 Node.js 项目中的文件是如何组织的，需要发送什么，以及需要如何配置，”Adzic 说。

随着 Node.js 继续塑造今天的开发前景，毫无疑问，Node.js 基金会和它的许多项目贡献者以及 NPM 都将目光投向了这种语言及其框架的未来。

通过 Pixabay 的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>