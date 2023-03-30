# Node.js v8 获得了长期支持——外加来自 Google V8 的承诺

> 原文：<https://thenewstack.io/node-js-v8-gets-long-term-support-plus-commitment-google-v8/>

今年万圣节，全世界的 JavaScript 开发人员得到了一份厚礼:这个星球上最受欢迎的开源 JavaScript 运行时 [Node.js](/tag/node.js/) ，将[版本 8](https://nodejs.org/api/esm.html) 升级为长期服务支持(LTS)状态。与此同时，[Node . js 基金会](https://nodejs.org/en/foundation/)——一个由社区领导和行业支持的联盟，致力于维持和推进 Node 生态系统，正在为对测试和实验感兴趣的开发人员介绍 Node.js 9。

Node 第 8 版在 LTS 上市是一个大新闻，尤其是对于那些对 v8 相对于之前的 LTS 版本 v6 的显著性能改进感兴趣的大型企业用户来说。专注于节点的软件开发公司 nearForm 的测试表明，在典型的网络应用程序中，v8 比其前身快 20%。

就新增功能而言，Node.js v8 是迄今为止最大的版本，也是最容易访问的版本。它提供的特性使得用 JavaScript 编写更加线性，错误更少——因此维护更大的代码库更加容易和稳定。这次更新也是为了使 Node.js 更容易被那些希望从其他语言移植过来的人访问。

Node.js 基金会执行董事 Mark Hinkle 表示:“那些在生产中使用 Node.js 的人现在可以获得性能和功能优势，现在的安全性和稳定性得到了长期支持状态的保证。Hinkle 指出，目前，Node.js 每天收集近 900 万个实例，供 200 多个国家的数万个组织使用。来自开源社区的支持包括 13 个工作组、技术指导委员会的 21 名成员以及 Node.js 核心本身的 1700 多名贡献者。

## v8 发动机在底盘上，V8 发动机在发动机罩下

Node.js 8 搭载了 [V8 JavaScript Engine 6.1](https://v8project.blogspot.com/2017/08/v8-release-61.html) ，谷歌开源的高性能 JavaScript 引擎。这意味着这个版本现在集成了[涡扇](https://github.com/v8/v8/wiki/TurboFan)优化编译器和[点火](https://v8project.blogspot.com/2016/08/firing-up-ignition-interpreter.html)解释器——从而降低了 Node.js 应用程序的内存消耗，加快了启动时间。直播服务提供商 Mixer 报告称，在早期测试中，他们的服务在 LTS 的领导下，网络响应时间缩短了 70%

新的节点还带来了来自 Google V8 团队的一些新的和强有力的合作。[该团队的工程师 Franzi Hinkelmann](https://twitter.com/fhinkel) 上个月在 2017 年 Node.js 互动大会上宣布，Google now 将 Node.js 与 Chromium(谷歌 Chrome 浏览器和操作系统背后的开源项目)放在一起优先考虑。

“Node 现在是 V8 的一等公民——如果它破坏了 Node，任何 V8 提交都不会成功，”Hinkelmann 在主题演讲中告诉观众。“这意味着 Node.js 本身增加了稳定性和更早地适应了 [ESNext](https://esnext.github.io/esnext) 特性，同时也减轻了 Node.js 维护者社区(主要是志愿者)的压力。

与 Node.js 的长期支持(LTS)版本一起，V8 对长期协作的承诺对于在企业环境中采用 Node.js 的许多企业来说是至关重要的。

## v8 糖果袋中有更多美味佳肴

在长期支持下，Node.js v8 的其他特性包括:

*   [HTTP/2](https://blog.risingstack.com/node-js-http-2-push/) ，未来会有变化，允许开发者使用新的协议来加速应用开发。HTTP/2 允许 JavaScript 开发人员撤销许多 HTTP/1.1 变通办法，使应用程序更快、更简单、更强大。
*   [Node.js API](https://medium.com/the-node-js-collection/n-api-next-generation-node-js-apis-for-native-modules-169af5235b06) (N-API)，一个稳定的模块 API，虽然还处于实验状态。它允许本机模块在新版本的 Node.js 上运行，而无需重新编译。这使得包维护者不必更新这些依赖关系，创造了更多的稳定性，并为那些消费模块提供了选择。它还为 VM 中立性和将 Node.js 开放到物联网、移动和各种不同系统的新环境奠定了基础。
*   Node.js 8 完全支持 Async / Await，这使得开发人员可以编写比回调更线性的代码，这吸引了 JavaScript 新手和那些从 C#等语言转向 Node.js 的人，也吸引了那些维护大型代码库的人。
*   [实验性 es 模块](https://nodejs.org/api/esm.html)是一种编写模块化 JavaScript 代码的标准方式，可以在 Web 和 Node.js 上运行。在 Node.js 8.x LTS 中，实验性 ES 模块实现将允许开发人员开始在 Node.js 中试验标准化模块模式，同时团队致力于一流的支持。

Node.js 传统上使用 [CommonJS](http://requirejs.org/docs/commonjs.html) 模式进行模块加载，这将继续是 Node.js 在 8.x LTS 期间的默认行为。

## 我们不要忘记:Node.js v9

Node.js 的奇数发布版本，传统上被称为“当前发布系列”，过去更关注新功能的积极开发和现有 API 的改进。这些版本的生命周期更短，代码更新更频繁，因此，不建议在生产中使用 Node.js 的用户使用。

Node 9 中的大部分变化涉及到弃用或移除遗留 API。此外，Node.js 核心代码库正在慢慢迁移到一个新的错误系统，目标是将一个唯一的代码与 Node.js 抛出的所有错误相关联。这将允许错误消息被更改，而不会被视为“破坏”通过不依赖错误消息，它还将使用户代码更加健壮。

Node.js 这一版本的贡献者来自[阿里巴巴](https://www.alibaba.com/)，GoDaddy，[谷歌](https://www.google.com/)， [IBM](https://www.ibm.com/) ，[英特尔](https://www.intel.com/content/www/us/en/homepage.html)， [Joyent](https://www.joyent.com/) ，[微软](https://www.microsoft.com/)， [nearForm](https://www.nearform.com/) ，NodeSource 以及一大批[个人贡献者](https://nodejs.org/en/blog/release/v8.8.1/#commits.)。Node.js 10 计划于 2018 年 4 月发布，并将于 2018 年 10 月进入 Node.js LTS 发布状态。

谷歌和[微软](https://azure.microsoft.com/en-us/?v=17.14)是新堆栈的赞助商。

米歇尔·吉诺特写插图。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>