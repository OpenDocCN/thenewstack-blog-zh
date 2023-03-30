# io.js 和 Node.js 联合起来了，这是一件好事

> 原文：<https://thenewstack.io/io-js-and-node-js-have-united-and-thats-a-good-thing/>

io.js 从 Node.js 中分离出来已经有一年多了，很多人都想知道这种分离的长期影响。io.js 会成为服务器端 Javascript 的新标准吗？io.js 是否会分化和碎片化不断增长的社区？这两个项目会解决他们的分歧，并有一天重新统一为一个整体吗？虽然有些人对合并有点不情愿，但 io.js 和 Node.js 的重新合并已经正式宣布，许多人认为这是两个项目向前迈出的一大步。

## 一堂历史课

对于那些没有在过去一年中关注这一行动的人来说，你可能想知道为什么 io.js 分支会首先出现。主要原因是:许多核心 Node.js 贡献者想要一个更加开放的治理模型。Node.js 项目最初是在 BDFL(benevolent-dictator-for-life)模式下运行的，在这种模式下，一小部分人对任何项目提交拥有最终决定权。Joyent 的 Scott Hammond 在他的博客中写道:“从历史上看，领导层对项目的管理相当严格，一小群核心开发人员按照 BDFL 的模式工作。新人很难加入这个项目，而且对于这样一个多样化的、充满激情的社区来说，没有足够的透明度让他们有一种主人翁感。因此，一群希望在更开放的治理模式下运营的开发人员创建了 io.js fork。”

紧密的 BDFL 模型成为热门话题，因为它阻碍了 Node.js 新特性和改进的推出。让人们参与开发 Node.js 带来的额外问题产生了双重影响，迫使人们需要做出改变。

Io.js 一直在实践让更多功能进入开发者手中的想法。一个重要的例子是:io.js 高度重视保持最新版本的 Google V8。(谷歌 V8 是支持谷歌流行的 Chrome 网络浏览器的 Javascript 引擎；Node.js 使用 V8 来执行代码。)Node.js 附带了不再受支持的 V8 版本。鉴于 V8 是 Node.js 的一个重要组成部分，保持 V8 的最新版本可以让 Node.js 利用 Google 为 V8 设计的所有最新的性能和安全优势。这是一个相当大的胜利，因为谷歌投入了相当多的资金使 V8 成为一个非常健壮的 Javascript 运行时。

## 节点基础

Node.js 基金会是一个独立的基金会，旨在管理 Node.js 项目。以前，Joyent 管理它。虽然 Joyent 将不再是 Node.js 项目的正式所有者，但他们致力于为项目的发展做出积极贡献。对于 io.js 的人来说，这正是他们想要的。由于 Node.js 现在运行在开放治理上，创建 io.js 分支的最初动力已经消失了。因此，在 io.js 5 月 13 日的会议上，io . js 正式决定合并回 Node.js

## 前进的道路

关于如何实现合并的大部分讨论和细节可以在 io.js' Github repo 上找到，特别是[第 978 期](https://github.com/nodejs/io.js/issues/978)和[第 1664 期](https://github.com/nodejs/io.js/issues/1664)。长话短说:作为合并的一部分，将使用 Node.js 名称，但 io.js 代码 repo 将作为基础。

我很高兴看到 io.js 和 Node.js 社区重新团结为一体。这使得许多开发人员不再担心由于没有在两者之间做出正确的选择而产生技术债务，并且没有人需要在战斗中选择任何一方。祝贺 Node.js 和 io.js 社区各自的成员能够为了 Javascript 社区的更大利益走到一起。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>