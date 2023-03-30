# 另一位受人尊敬的开发人员向 Node.js 告别，并向您问好

> 原文：<https://thenewstack.io/another-respected-developer-says-farewell-to-node-js-and-hello-to-go/>

TJ Holowaychuk 是一位杰出的模块作家，他告别了 Node.js，并转向 Go，他称之为“下一代”，与 Rust 和 Julia 在同一家公司的编程语言。

正如 Zef Hemel 在今天的一篇文章中指出的，这是 Node.js 最近一次高调退出。他特别提到了[菲利克斯·盖森多弗](http://felixge.de/)，这位经常投稿的作者在 2012 年离职。

赫梅尔还引用了提供基于网络的开发环境的 [Koding](https://www.quora.com/Node-js/Why-did-Koding-switch-from-Node-js-to-Go) 。

[Holowaychuk](https://medium.com/code-adventures/farewell-node-js-4ba9e7f3e52b) 是 [Luna 编程语言](https://github.com/luna)的创造者。他也是 Koa、Express、Stylus、Cluster、Mocha、Jade 和 node-canvas 的幕后推手。

他在昨天发表的一篇文章中写道，Node.js 在某些方面做得很好，但它不适合他目前对分布式系统的兴趣。Node.js 强调性能胜于可用性和健壮性。他发现 Go“性能更好，更容易维护，测试覆盖率更高，因为同步代码通常更好用，也更简单。”

他喜欢 C 语言，但这不是一门每天都要使用的语言。

对于 Holowaychuk 来说，对 Go 最满意的是它的迭代速度。他希望社区愿意在 Go 中打破常规，但他认识到，在大公司的支持下，打破常规对于管理大系统的人来说可能是个问题。但这可能有助于使它更有弹性、更强大。

## 为什么去

总的来说，他说 Go 对于它的时代来说是健壮的，重构类型是愉快而简单的。用于分析和调试工作的工具和社区在文档、格式、基准和 API 设计方面有着非常强的约定。

Go 的原语比 Node.js 的生成器更适合分布式计算。Node.js 没有单独的堆栈错误处理。没有它，报道是平庸的。

> 我也不想等到 3 年后社区才进行碎片整理，因为我们现在已经有了解决方案，而且效果很好。

还有 Go 的错误处理功能，Holowaychuk 说它更胜一筹。Node.js 让你看到每一个错误，这有助于开发人员思考，但它也有一些缺陷，他列出如下:

*   *您可能会收到重复的回电*
*   *你可能根本得不到回电(迷失在地狱边缘)*
*   *您可能会遇到带外错误*
*   *发射器可能获得多个“错误”事件*
*   *失踪的“错误”事件把一切都送进了地狱*
*   *经常不确定什么需要“错误”处理程序*
*   *“错误”处理程序非常冗长*
*   *回调吸*

Howaychuk 是一个哲学和自然作家。他对 Node.js 持批评态度，但态度积极。特别是，他将使 Node.js 更易于使用的责任推给了 Joyent。

我写过关于 [Poptip 移动到](https://thenewstack.io/from-node-js-to-go-why-one-startup-made-the-switch/)的文章。许多新兴服务也使用 Go。Docker、CoreOs、Dropbox 和 MongoDB，这些都是比较突出的用户。

Node.js 的问题是被夸大了还是被误导了？我对这个很好奇。也许是时候在谷歌上讨论一下这个话题了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>