# 最新发布的 ECMAScript 8 为并发 JavaScript 处理奠定了基础

> 原文：<https://thenewstack.io/newly-released-ecmascript-8-sets-stage-concurrent-javascript-processing/>

上周， [ECMAScript 8，【ECMAScript 2017 的规范通过了最终批准。该规范将作为 JavaScript 不同实现的蓝图，包括新的异步特性、用于并发处理的共享内存和原子以及字符串填充。](https://www.ecma-international.org/publications/standards/Ecma-262.htm)

“ECMAScript 8 中的大部分变化都是 JavaScript 程序员生活质量的改变。JavaScript 标准库正在变得越来越好，” [npm 公司](https://www.npmjs.com/)的首席技术官 [CJ Silverio](https://www.linkedin.com/in/ceejbot/) 说

他指出，Node.js 包管理器(npm)中的许多早期内容都是为了补偿 JavaScript 内置的失败。

“有一个非常流行的包叫做 [Lodash](https://lodash.com/) 。这是 JavaScript 应该一直拥有的实用程序库。每一个 ECMAScript 版本都使 Lodash 变得更小，因为它所做的事情出现在语言中。像字符串填充这样的东西，在我看来，应该一直存在，”西尔维奥说。

同样，[object.values/object.entries](http://2ality.com/2015/11/stage3-object-entries.html)是另一个改进。object.entries 函数可用于迭代对象( [finally！](http://exploringjs.com/es6/ch_iteration.html#sec_plain-objects-not-iterable))同样，object.values 返回可枚举的字符串键属性的值。

## 浏览器支持呢？

在过去的几年里，JavaScript 开发人员将不得不等待几年，等待所有的浏览器都支持新的规范。

然而今天，多亏了 [Babel 项目](https://github.com/babel/babel)，JavaScript 开发者已经使用 ES8 的一些特性有一段时间了。也许最值得注意的是，异步函数在 Babel 中已经存在了将近两年。这是因为 Babel 的全部目的是消除浏览器 JavaScript 实现之间的不一致。

不到二十年前，这样做意味着编写某种装置来修复 Microsoft Internet Explorer 中的 JavaScript 的错误实现，但今天，问题是 JavaScript 实现版本在较旧的浏览器中通常已经过时。用户继续使用旧版本浏览器的问题不会很快消失。

## 巴别塔

最初，巴别塔被称为 625，该项目的贡献者亨利·朱说。他说，在他加入之前，该项目的第一个目的是建立一个编译器，可以将 ECMAScript 6 代码转换为 ECMAScript 5 代码，使其能够在旧浏览器上运行。

从那时起，第二个任务就是在浏览器支持之前传播语言更新。Babel 为开发人员提供了一种尝试最新特性的方法，甚至可以在主流支持可用之前在应用程序中使用它们。

这有一个额外的效果，即在新的 ECMAScript 提案完成之前允许对它们进行反馈。由于语言更新的分散性，JavaScript 社区长期以来一直在寻找与 ECMAScript 委员会合作的更好途径。

一个完美的例子就是在 [ECMAScript 8](http://2ality.com/2016/02/ecmascript-2017.html) 中新添加的异步函数。这一功能早在 2015 年就被添加到 Babel 中，使社区能够在它到来之前很久就习惯这一新功能的功能和语法。

本质上，异步函数也将取代 JavaScript 社区提出的另一个解决方案:[公司](https://github.com/tj/co)。

ECMAScript 8 中的另一个主要变化是添加了新的 [SharedArrayBuffer](http://2ality.com/2017/01/shared-array-buffer.html) 构造函数和原子。这些结合在一起，通过提供共享和访问多个处理线程使用的数据的安全方法，使 JavaScript 中的并行性和并发性更容易构建。

ES8 中一个近乎幽默的新增功能是字符串填充。众所周知，Node.js 社区开发了一个向代码添加左补的小应用程序，当它被它的创建者从 npm 的仓库中删除时[，Babel 和其他包都崩溃了。这在整个 JavaScript 世界引发了一连串失败的 npm 构建，尽管它很快就被轻松地纠正了。在 JavaScript 中添加字符串填充至少从根本上解决了问题。](https://thenewstack.io/the-kik-kerfuffle/)

朱说，在 npm 事件发生时，字符串填充已经在工作中。“这很有趣，因为它是在事件发生之前提出的。已经是第三阶段了。人们开玩笑说这就是它被推倒的原因，”朱说。

由 [Martin Reisch](http://unsplash.com/photos/6DivtP_WRYs?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 通过 [Unsplash](https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>