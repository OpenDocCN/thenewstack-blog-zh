# 谷歌和微软联合起来重建 JavaScript

> 原文：<https://thenewstack.io/google-and-microsoft-unite-in-effort-to-rebuild-javascript/>

两项努力——一项由微软发起，另一项由谷歌发起——在用 JavaScript 和 HTML 构建 Web 应用程序时，为熟练的开发人员提供他们喜欢的工具，上周四正式联合起来。谷歌最近推出的 [Angular 2 项目](https://angular.io/docs/js/latest/quickstart.html)的第二阶段和微软于 2012 年开始的 [TypeScript 项目](http://readwrite.com/2012/10/03/microsofts-typescript-fills-a-long-standing-void-in-javascript)开始了联合开发过程，Angular 团队承认他们实际上是在使用 TypeScript 构建 Angular。

该项目是最大的互联网公司如何合作为开发者提供最佳服务的又一个例子。这在另一个时代可能是闻所未闻的，但这是依靠开放社区解决新问题的新一代。

这两个项目都是作为 Web 开发环境的一个新的但必要的特性开始的:transpilers。描述一种重新解释器是一个听起来很糟糕的词，这种重新解释器读取开发人员希望浏览器能够识别的更严格、更安全的代码，并使用它来复制浏览器实际识别的更精简的代码。基于谷歌的团队一直在使用名为 Traceur 的 transpiler 将 ECMAScript 6 语法(JavaScript 目前正由 ECMA 组织标准化)重新解释为 ECMAScript 5 (ES5)。

Angular 开发负责人 Igor Minar 说:“无论您使用新标准 ES6 ES5，还是使用 TypeScript 提供的所有可选类型和注释，您都可以利用 Angular 2。”

[https://www.youtube.com/embed/QHulaj5ZxbI?list=PLOETEcp3DkCoNnlhE-7fovYvqwVPrRiY7](https://www.youtube.com/embed/QHulaj5ZxbI?list=PLOETEcp3DkCoNnlhE-7fovYvqwVPrRiY7)

视频

## 建造房屋的练习

JavaScript 本身并不是任何人对效率、可伸缩性或者特别是美观的偏好。本质上，它是每个人都从 Netscape 的努力中继承的语言，将功能钉在 HTML 上，看起来有点像 Java。经过 ECMA 多年的发展和标准化，它已经逐渐克服了最初实现的主要缺点:缺乏上下文。

没有上下文，类型——程序中变量的一组预定义特征，因此解释器可以分配精确的内存——就无关紧要了。随着网页的组件合并成我们现在所认为的文档对象模型——非常重要的 DOM——类似于上下文的东西开始拼凑起来。对象被赋予可以附加代码的属性。

但是部分是因为浏览器需要轻量级的解释器，部分是因为 HTML 是一种标记语言，允许 JavaScript 在某些时候打断它，Web 开发的不规则性在历史上一直阻碍着那些具有高级语言技能的开发人员。这一直是一种不体面的混合，熟练的开发人员已经尽他们所能来掩盖这种不愉快。(也许 TypeScript 的另一个不错的标题应该是“Febreze”)

就其本身而言， [TypeScript 是一种在开发环境(例如 Visual Studio)中强制变量类型一致性的方法。当实例化一个变量时，不是仅仅让它成为一个动态类型的“var”并让解释器去理解它，而是用它的显式类型来注释变量。这样，IDE 可以确定该变量是否被赋予了解释器可能不期望的值，从而避免用户在运行时发现错误的情况。TypeScript 也接受“类”的命名，它最终将被合并到 ES6 中，但同时 transpiler 将转换成更丑陋的 ES5 等价物。](http://www.typescriptlang.org/Tutorial)

与此同时，[转换了 HTML 和脚本的关系](https://angular.io/docs/js/latest/quickstart.html)。您可以在单独的文件中创建组件。在这里，“宿主”语言是脚本，HTML 代码被分配给变量，或者被断言为方法的操作数。这样，HTML 就变成了组件本身，因此当脚本构造函数引用这些组件时，它们就会被呈现出来。Angular 团队称之为 AtScript 的脚本语法是 ES6 语法的另一个扩展。

当你在 Angular 中使用一个构造函数来定义一个属性时，这个属性可以在组件的 HTML 代码中使用，以表示这个属性应该出现在哪里。这是标记中的标记，Angular 使用{{double-mustache syntax}}，灵感来自于用 JSON 格式的变量模板化的 [Mustache.js 库。](http://coenraets.org/blog/2011/12/tutorial-html-templates-with-mustache-js/)

## 没有差别的区别

Angular 团队一直在使用 Traceur 将 EC6 脚本转换成 EC5，但这种 Jekyll-to-Hyde 变异背后的过程本身可以使用一些脚本自动化。与此同时，TypeScript 团队一直在处理他们的类型一致性愿景和为即将到来的 ES6 构建的愿景之间的一些不兼容性。

去年年底，Angular 团队发表了将更多声明式编程实践融入 ES6 的希望和梦想。正如微软 TypeScript 项目负责人 Jonathan Turner 上周在 Angular 团队的 ng-conf 会议上所说，那时他注意到了一些奇怪的相似之处。

“所以我们联系了 Angular，建立了合作关系，”特纳说。“我们开始讨论，如果我们开始采用 AtScript 的那些功能，并将它们放入 TypeScript，将它与类型系统合并，将它与编译器输出 JavaScript 代码的方式合并，会有什么可能？”

他说，当 TypeScript 团队检查这个问题时，他们共同意识到他们现有的 TypeScript 1.4 没有达到应有的成熟程度。他们认为需要在即将发布的 TypeScript 1.5 中加入更多的 ES6 语法。然后，通过 Angular 协作，TypeScript 将 Angular 的注释思想(在单独的文件中声明的组件)与它自己的注释思想(插入到声明中的变量类型)结合起来。

“TypeScript 的下一个版本真正充实了这个故事，”Turner 继续说，“我们有 ES5，类型位于 ES6 之上，注释与类型配合得很好——跨所有这些功能的良好工具，以及良好的 ES3 和 ES5 输出。”

一旦微软支持的团队根据开发人员期望在 ES6 中看到的内容有效地重新调整了 TypeScript，谷歌支持的团队就没有理由不将他们一直使用的 AtScript 替换为 TypeScript 1.5。

在上周四的一篇博客文章中，微软公司开发部门的副总裁 S. Somasegar 写道，“比起这两个团队已经建立的语言创新和库，我更为我们在 TypeScript 和 Angular 团队之间建立的富有成效的关系和合作伙伴关系感到自豪。两个团队都期待着在未来继续将 TypeScript 和 JavaScript 一起向前推进，包括与 ECMAScript 标准机构合作，共同研究 JavaScript 中类型的未来。”

在他们的演示中，Angular 团队用一张赤脚孩子躺在草地上的照片描绘了这种新的关系。这完全不是科技出版物普遍适用于微软和谷歌的那种超级大国式的“冷战”关系。但这似乎是他们的开发者更喜欢彼此之间的关系:不仅仅是联盟，而是真正的友谊。两个团队对同一问题的古怪和不同的处理方式没有给任何一方带来竞争优势。因此，为了双方的利益，他们都同意消除这些差异。

这种工作关系将确保新的堆栈与旧的堆栈截然不同。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/wwworks/535439394/in/photolist-PjgtG-618n8Q-iCjZL-a29EsL-67Z4zd-eJmrSa-67USSi-67UT4g-67Z4XE-67USMF-eQXzL3-67UTda-67UTfB-67Z4MW-67USZX-o7ghA-o7gjn-o7gg2-rZcCy-68wGJZ-nS1jLg-53j7Vy-ar2iXF-vyBAo-67Z4jS-67Z4o1-67Z4vC-67Z4g9-67Z4sy-o7gi3-o7ge8-o7ggW-o7gfv-o7ggy-eFGgvV-8caf8k-bCDdST-iJYKMV-8zQ7JS-4qje48-q9KMMf-59v18k-pujhPh-puxR7r-qq6iUc-ott4rr-q8PATt-q8H3jw-q8HZvq-q8J2uA)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>