# 关于 E 的一切:渗透进 JavaScript 的语言

> 原文：<https://thenewstack.io/all-about-e-the-language-that-infiltrated-javascript/>

Doug Crockford 最为人所知的是他长期从事的 JavaScript 工作和创建的 JSON 数据交换格式。他的观点很有分量——克罗克福德说是时候让 JavaScript 退休了。

“JavaScript，像其他恐龙语言一样，已经成为进步的障碍，”克罗克福德在一次采访中告诉 IT 外包公司 [Evrone。“我们应该专注于下一种语言，它应该看起来更像 E，而不是 JavaScript。”](https://evrone.com/douglas-crockford-interview)

E 是什么？维基百科称 E 为“一种用于保护分布式计算的面向对象语言”从设计上来说，E 强调安全性。但是为了更多地了解 E 对 JavaScript 的影响，新的 Stack 采访了 E 的主要设计师[马克·米勒](https://www.crunchbase.com/person/mark-s-miller)，他与[迪安·特里布尔](https://www.linkedin.com/in/deantribble/)以及几位电子通讯的同事共同创建了 E，包括[克罗克福德](https://www.crockford.com/about.html)，道格·巴恩斯[，丹·博恩施泰因](https://www.linkedin.com/in/danfuzz/)和[芯片晨星](https://www.linkedin.com/in/chip-morningstar-57923/)在 20 世纪 90 年代中期。

“道格和我对这门语言的诞生都有很大的贡献，”米勒告诉我们。"我们非常喜欢我们创造的语言。"

米勒认为这种语言本身已经死了——作为一种开源语言，E 从来没有吸引过超过 100 个用户加入社区，他说。

但是 E 并没有就此罢休——由于 Miller、Crockford 和 ECMAScript 标准委员会其他成员的努力，它的影响在今天的 JavaScript 中依然可见。米勒向 New Stack 解释了 E 如何影响 JavaScript，他的公司 Agoric 如何在 DeFi 和区块链的合作中使用 E 的想法，以及何鄂希望升级到 JavaScript 的其他方面。

## 12 愤怒的男人和 ECMAScript

“你看过电影 [*12 怒汉*](https://www.imdb.com/title/tt0050083/) 吗？”米勒问我。我说过，我回答。“我认为这部电影是解释我加入谷歌时 ECMAScript 委员会的最佳方式。”

2007 年，克罗克福德说服米勒加入该委员会，成为谷歌的另一名代表。该委员会致力于将 ECMAScript 3 升级到 ECMAScript 4，但进展并不顺利。

“从 1999 年到 2007 年，委员会一直在开会，但他们仍然没有一个后续标准。委员会的大部分人都关注 ECMAScript 4，在我看来，ECMAScript 4 是一种可怕的语言，”米勒说。“道格一开始是一个顽固分子——亨利·方达的角色说，‘不，我们不会同意这件事。’"

JavaScript 混乱、复杂且怪异，但 Crockford 让 Miller 相信 ECMAScript 3 拥有类似 E 体验的种子，并且它拥有核心的使能元素，这将使它成为一种类似 E 的安全分布式编程语言。

“我加入了他对 ECMAScript 4 的反抗，那个时候反抗还有其他几个成员——就像在 *12 愤怒的人*中一样——他逐渐说服陪审员加入他的阵营，”米勒说。最终，反抗取得了胜利。ECMAScript 3 的继任者变成了 ECMAScript 5，这个版本是由反叛者设计的，而委员会的其他成员则专注于 ECMAScript 4。

“ECMAScript 5 标准确实为使用 JavaScript 作为直接、简单、安全的编程语言创造了条件。我们都为我们为 ECMAScript 5 所做的一切感到非常自豪，”他说。

他说，他们在 ECMAScript 5 中引入的 E 的一个基本方面是支持对象能力安全模型。

“JavaScript 的函数和用作记录的 JavaScript 的对象可以结合起来创建一种模式，Doug 将这种模式命名为 objects-as-closures 模式，如果您将 JavaScript 用作 objects-as-closures，这种表达感觉很像 e。但从 ECMAScript 3 开始，它还不具备安全性。”

米勒说，ECMAScript 5 中的使能器使他们能够编写 SES-shim，这是一个带来安全语言状态的库，现在被称为硬化 JavaScript。

## 冻结

在 ECMAScript 5 中，他们引入了几个使能器，主要是 Object.freeze()。米勒说，尽管名字如此，但它与不变性没有任何关系。相反，它对对象的表面进行了防篡改，因此对象的客户端现在只能根据对象的显式行为与对象进行交互，Miller 解释道。对象的提供者可以用捕获内部状态变量的方法填充它，并且可以封装该状态，因此对象的客户端不能篡改它。他补充说，“冻结”的意思是物体的属性不再能被改变。

“客户不能再改变对象的形状。所以物体的形状是固定的。内部状态现在对客户是隐藏的，”他说。"现在物体变成了只能根据物体的设计进行交互的东西."

这一步解决了一个安全问题:原型中毒(prototype poisoning ),在这种情况下，用传统 JavaScript 创建的对象都是可变的，可以被任何有权访问它们的人破坏，以迷惑或监视程序的其他部分。

“我们使用 freeze 和 ECMAScript 5 中的其他使能器(Object.getOwnPropertyNames()和 Object.getPrototypeOf())做的事情之一是，我们能够编写我们称为‘harden()’的东西，这是一个遍历对象图的传递性冻结，冻结它通过进行属性遍历找到的所有对象。我们能够枚举所有的原始对象，相同环境中 JavaScript 程序隐式共享的所有对象，如 Array 和 Array.prototype 等。，”米勒说。

## 输入输出表达式

他说，SES-shim 库在开始初始化时，对原基进行一些修复，然后硬化所有的原基。这确保了所有隐式共享的对象现在是真正不可变的。

“我们对委员会做了一些修复，这样原生物就没有任何隐藏的可变状态或隐藏的 I/O 能力，”他说。

他补充道，所有被隐性分享的东西都是完全无力和不可改变的，所以分享并不违反隔离。

另一个重要的促成因素是虚拟化所有 I/O 的能力。米勒说，JavaScript 的一个美丽但未被充分认识的方面是，该语言是关于计算的，而不是关于 I/O 的。JavaScript 程序通过对主机提供的对象(如浏览器中的“文档”或节点中的“进程”)执行全局变量查找来表达 I/O。

这些由主机提供的全局变量没有作为语言标准的一部分进行标准化，而是由主机引入，主机提供了影响外部世界或感知外部世界的所有 I/O 能力。

“这意味着，如果您可以干预全局范围查找，您就可以完全虚拟化所有 I/O，这正是我们通过 ECMAScript 5 中的启用程序实现的。硬化的 JavaScript 继续使用使能器来拦截全局范围查找，”他说。

Agoric 至今仍在使用硬化的 JavaScript。Agoric 在一个叫做 Jessie(一个意在唤起 JS 和 E 组合的名字)的强化 JavaScript 子集内编写了大部分代码。Jessie 强调 Crockford 的 objects-as-closures 模式是 JavaScript 继承机制的替代方案。

## 承诺

Miller 说，E 移植到 JavaScript 的另一个重要方面是非阻塞承诺，这是第一种语言。ECMAScript 6 中的承诺，这些承诺直接基于 E 承诺。

“承诺是由异步函数返回的对象。promise 对象提供了处理操作最终成功或失败的方法，”[MDN web docs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Promises)解释道。 [E 在一个核桃里更详细地解释了诺言](http://www.skyhunter.com/marcs/ewalnut.html#SEC20)。本质上，在 E 之前的 promise 系统中，调用线程会在某个时候阻塞，等待操作完成。在很大程度上，人们不会等待某人完成一个项目中的任务，然后才开始自己的任务，E 的无阻塞承诺使其有可能处理操作的最终成功或失败，而不会阻塞以等待解决方案。

JavaScript 承诺只提供开箱即用的本地异步，但 Agoric 的 Endo 库扩展了它们，在加密协议上也提供了类似 E 的分布式对象能力安全性，使 JavaScript 成为类似 E 的分布式安全语言。

ECMAScript 6 引入了 E 的无阻塞承诺。但是 ECMAScript 6 也引入了类，并且变得至少两倍大…而且还在继续增长，Miller 说。它变得越来越复杂，米勒和克罗克福德都讨厌它。据米勒说，当米勒留下时，克罗克福德离开了委员会，基本上认为 JavaScript 是一个失败的事业。

米勒仍然看到了 JavaScript 的潜力。

“我不认为这是一个失败的事业，”他告诉新堆栈。“我对我们在委员会的努力下持续取得的成就感到非常自豪，这使我们能够将它作为一种类似 E 的分布式安全语言来使用。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>