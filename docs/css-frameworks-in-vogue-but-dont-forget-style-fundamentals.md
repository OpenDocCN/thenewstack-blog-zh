# CSS 框架很流行，但是不要忘记样式的基本原则

> 原文：<https://thenewstack.io/css-frameworks-in-vogue-but-dont-forget-style-fundamentals/>

[](https://twitter.com/ricmac)

 [理查德·麦克马努斯

理查德是 New Stack 的高级编辑，每周撰写一篇关于网络和应用程序发展趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) [](https://twitter.com/ricmac)

你们中年龄足够大的人，如果还记得 20 世纪 90 年代末的网络，会记得那段时间用 CSS(层叠样式表)编码的噩梦经历，主要是因为浏览器不兼容。但是从那以后我们已经走了很长的路。正如 CSS 先驱 Eric Meyer 在最近的博客文章中所说，今天的网络，包括 CSS，拥有“巨大的能力和广泛的兼容性”。他补充说，CSS 的转折点是在 2017 年 4 月，“当时四个主要的网格实现在几周内发货，并且彼此非常接近 100%一致。”

CSS 网格布局是一种响应式网页设计技术，相当于使用 HTML 表格来控制布局。Grid 于 2017 年 1 月在 Google Chrome [中可用](https://developers.google.com/web/updates/2017/01/css-grid)，尽管它在[万维网联盟](https://www.w3.org/) (W3C)仍处于[草案状态](https://www.w3.org/TR/css-grid-1/)，但它正在成为一个网络标准。

正如 Meyer 所指出的，我们有 web 标准的倡导者，比如从 90 年代末到 2013 年的 Web 标准项目 (WaSP ),以及今天的 W3C 的 CSS 工作组,感谢 CSS 的健康发展。但是这个时代的主流浏览器——Google Chrome、Firefox、Safari 和 Microsoft Edge——在 CSS 方面大多都是相互兼容的。

## CSS 框架的兴起

另一个引人入胜的趋势是 CSS 框架的不断崛起，如 [Bootstrap](https://getbootstrap.com/) 、[物化 CSS](https://materializecss.com/) 和 [Tailwind](https://tailwindcss.com/) 。前两个已经有将近十年的历史了。Tailwind 是 2017 年 11 月推出的新产品。根据 [2020 年 CSS 状况报告](https://2020.stateofcss.com/en-US/)由 [Sacha Greif](https://twitter.com/sachagreif) 和[raphal benitet](https://twitter.com/benitteraphael)运行的独立报告，Bootstrap 是目前使用最多的 CSS 框架——86%的调查受访者使用它，相比之下，第二大流行框架 Materialize CSS 只有 33%。但顺风的满意度(87%)和兴趣度(62%)排名最高。值得注意的是，Bootstrap 在两项指标中都接近垫底。

Bootstrap 和 Tailwind 之间有一些关键的区别(挑选两个谈论最多的 CSS 框架)。网格布局就是其中之一。Tailwind 支持 CSS 网格，但是 Bootstrap 有一个实现网格布局的替代系统。

但是根本的区别在于，Tailwind 有一个“实用优先”的方法，而 Bootstrap 是一个 CSS“工具箱”,有预定义的组件，其中许多组件都是 JavaScript 驱动的。这个想法是，通过从 Bootstrap 的组件库中进行选择，可以很容易地快速启动一个新的网站或应用程序。Tailwind 是一个较低层次的抽象，因此它在设计上提供了更多的灵活性。

Tailwind 依赖于实用类，Michelle Barker 将这些实用类[定义为](https://css-irl.info/a-year-of-utility-classes/)“服务于一个特定用途的 CSS 类名，并以此命名。”她举了一个例子。bg-blue 类，它将背景色定义为蓝色。Tailwind 文档列出了一系列背景颜色工具以及你可以应用的样式(悬停、聚焦等)。).在 Tailwind 中，一切都是在 HTML 文件中完成的，而不是在一个单独的 CSS 文件中。Tailwind 的标语很好地总结了这一点:“不用离开你的 HTML 就能快速建立现代网站。”

## CSS 框架批评家

虽然 Tailwind 是时髦的新 CSS 框架，但它也不是没有批评者。正如 CSS 书籍作者 Ahmad Shadeed [指出的那样](https://ishadeed.com/article/on-tailwindcss/)，“当标记和样式混合在一起(在 HTML 中)时，如果你在一个复杂的多语言、响应性和主题化的用户界面上工作，事情会变得混乱。”

web 标准社区中一些有影响力的人也不喜欢实用程序类，因为它们缺乏语义。正如 Jeffrey Zeldman 几年前写的，“引用视觉样式的无意义类名总是一个坏主意。”

另一个问题——或者说优势，取决于你的观点——是 Bootstrap 和 Tailwind 都大量使用了 JavaScript。在今天的 web 开发世界中，使用 JavaScript 为您的网站或应用程序添加强大的交互功能是一个常见的主题。正如 Barker 在她关于实用程序类的文章中所说的:“因为 Tailwind 是用 Javascript 配置的，所以你可以编写函数并把它们传递到你的配置中。”

当然，缺点是 JavaScript 增加了复杂性。为什么要让 CSS 中已经很复杂的 web 标准变得过于复杂呢？

如果你告诉我 2000 年初的自己，CSS 将在 20 年后成为 JavaScript 的伙伴，我会感到惊讶。在那些日子里，我在我的网站上手工编写 CSS 代码，并定期参观 [CSS 禅苑](http://www.csszengarden.com/)。CSS 是为了表示，JavaScript 是为了交互性——在那个时候，这是一种清晰的关注点分离。(旁白:1996 年，网景试图将 JavaScript 和样式表结合起来，发明了一种基于 JavaScript 的样式机制，叫做基于 JavaScript 的样式表(JSSS)。它甚至将其提交给 W3C，作为当时新生的 CSS 项目的替代方案。不出所料，JSSS 很快就销声匿迹了，再也没有消息了。但是如果今天发行，也许会很受欢迎！)

与 React 和 Vue 等 JavaScript 框架一样，更大的哲学问题是 CSS 框架的流行是否导致了一代不了解网络基础的网页设计师——如 CSS。因为像 Tailwind 和 Bootstrap 这样的框架是 CSS 代码上的抽象层，它们本质上对设计者和开发者隐藏了代码。眼不见心不烦。

苹果网站开发者体验团队的布道者，同时也是 W3C CSS 工作组的成员，Jen Simmons 在她的推特上总结道，“当你可以记住 CSS 属性时，为什么要记住 Tailwind 类？”

## 结论

Jeffrey Zeldman 在 2018 年提出，虽然框架无疑是有用的，但网页设计师也可以使用普通的 CSS 完成很多事情。他谈到 CSS Grid 并不像人们想象的那样难学，并且经常是框架的替代方案。

他写道:“你可以用它来完成各种过去需要 JavaScript 和框架的布局，加上还没有人尝试过的新布局。”

然而，现实情况是，设计者和开发人员将把框架的使用与 CSS Grid 等新兴的 web 标准混合起来。这是明智的做法；危险在于，当你变得过度依赖框架，而不学习抽象之下的基础知识时。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>