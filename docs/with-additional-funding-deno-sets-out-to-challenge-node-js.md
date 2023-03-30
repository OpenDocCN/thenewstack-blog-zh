# 有了额外的资金，Deno 开始挑战 Node.js

> 原文：<https://thenewstack.io/with-additional-funding-deno-sets-out-to-challenge-node-js/>

如果 [Deno](https://deno.land/) 是 Node.js 问题的答案，那它为什么还没有火起来？

[瑞安·达尔](https://en.wikipedia.org/wiki/Ryan_Dahl)写了 Deno，作为他在之前的创作 [Node.js](https://nodejs.org/en/) 中看到的问题的解决方案。Dahl 认为问题在于设计不良的模块系统、安全问题，包管理器可以被标准的基于 URL 的链接系统所取代。

Deno 于 2020 年推出，是 JavaScript、TypeScript 和 WebAssembly 的新运行时。它建立在由 V8 引擎运行的 Rust 编程语言之上。Deno 试图提供一个独立的工具来快速编写复杂功能的脚本。

Deno 的目的与 Node.js 相似，node . js 是向客户端应用程序提供服务的标准 web 服务工作流(提供文件、提供 API、充当数据聚合器等)..).或许，结果是，Deno 很难获得关注。

“如果我必须在这两种技术之间做出选择，我会选择哪一种？”在 Medium 上写了很多关于 Deno 的开发人员 Mayank Choubey 在接受 New Stack 采访时说。即使 Node.js 不完美，“我的公司有很多项目都使用 Node.js。我们在内部项目中使用 Deno，但在任何关键项目中，它绝对是 Node.js，因为它是一项成熟的技术，没有任何风险。”

6 月，Deno 背后的公司 Deno Land Inc .，[宣布](https://deno.com/blog/series-a)在由[红杉资本](https://www.sequoiacap.com/)牵头的首轮投资中获得了 2100 万美元，这将大大有助于弥补新技术的剩余差距。

Deno 不仅有资金与 Node.js 竞争市场份额，还进一步投资于一种将自己与竞争对手区分开来的商业模式。

## 需要解决什么问题

Deno 必须克服的一个困难是，它并不是一种用户友好、无缺陷的技术。Deno 是一个婴儿，它只在版本 [1.24.2](https://deno.com/blog/v1.24) 中，所以虽然有技术天才在研究它，但错误是这个过程的一部分，但它们确实阻止了较小的开发人员，较大的开发人员对采用这项技术不感兴趣。

[Jennifer Fu](https://jenniferfubook.medium.com/),[Domino 数据实验室](https://www.dominodatalab.com/)的 UI 技术负责人，经常在博客上谈论 Deno，她在 TNS 采访中建议，现在需要的是“可预测的版本以使其工作”Choubey 还建议升级文档，因为它们不够详细，“如果我开始研究这项技术，我会寻找这种文档”。

前两个问题为第三个问题创造了完美的环境，第三个问题就是缺乏第三方包。这是个先有鸡还是先有蛋的问题。

“如果人们不感兴趣，他们就不会为 Deno 开发包，如果没有 Deno 的包，人们也不会感兴趣，”Choubey 解释道。

第三方包是任何技术生态系统中丰富的一部分。它们来自于对创新的需求，但是在一项没有被广泛使用的技术上不会有太多的创新，在一项没有被广泛维护或清晰记录的技术上也肯定不会有太多的工作。

当使用没有很多第三方包的技术进行构建时，有时知道如果出现问题，可能有一个很薄的抽象层会很有帮助。

Deno 大约有 5000 个第三方软件包，是 Node.js 大约 1200 万个软件包的一小部分。

Choubey 说，“很可能你找不到一个能解决你所有问题的包”，他承认 Deno 确实有很多有用的包。

请注意，这些变化并没有说 Deno 是一项糟糕的技术，因为它不是。对于一个已经存在的市场来说，Deno 只是一个新事物。傅支持这项技术:“它有潜力；是时候采用新技术了。”因为这是德诺现在和过去的位置。德诺绝对在行动。

## 额外资金

随着额外资金的到位，达尔和他的团队可以解决上述问题，并带来一些组织的努力。

傅认为，Deno 面临的最大问题是，“过于分散，需要一家公司来采用”，现在应该有所进展。

[Deno Deploy](https://deno.com/deploy) ，Deno 的托管部门，就是这个问题的答案。Deno 去年发布了 Deno Deploy，目前仍在迭代这个“托管 JavaScript 服务器的云服务”。该公司自己的文档指出，“通过将网络浏览器技术重新用于服务器软件，我们的目标是加速新一代极低延迟的边缘应用。”甚至 Deno.com 重定向到德诺部署的权利。

傅最近发表了一个关于 Deno Deploy 的项目，他证明了这一点:“它既方便又有活力。每次我修改代码时，我只需推送到 GitHub，它就会自动发布到服务器端。”Deno Deploy 是一个分布式系统，它在全球范围内在边缘运行 JavaScript、TyopeScript 和 WebAssembly。

除了 Deno Deploy，Deno 还在今年 6 月下旬发布了自己的前端框架， [Fresh](https://fresh.deno.dev/) 以与众多开箱即用的 Node.js 框架竞争。Fresh 基于 [Preact](https://preactjs.com/) 虚拟文档对象模型(DOM)，支持开箱即用的类型脚本。

傅和 Choubey 曾与 Fresh 合作过，他们都认为它有很大的潜力，尽管傅证实说，“在 Fresh 和 Deno Deploy 之间仍然存在一些问题。”

在接下来的几个月里，跟踪这项技术将会非常有趣，因为随着时间的推移，这项技术应该会有一些大的动作。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>