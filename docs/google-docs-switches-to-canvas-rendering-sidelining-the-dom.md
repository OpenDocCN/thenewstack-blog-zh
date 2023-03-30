# 谷歌文档切换到画布渲染，把 DOM 放在一边

> 原文：<https://thenewstack.io/google-docs-switches-to-canvas-rendering-sidelining-the-dom/>

本月早些时候，谷歌[宣布](https://workspaceupdates.googleblog.com/2021/05/Google-Docs-Canvas-Based-Rendering-Update.html)正在更新谷歌文档呈现文档的方式——从传统的基于 HTML DOM 的方法(文档对象模型)到使用名为 [Canvas](https://www.w3.org/TR/2dcontext/) 的网络标准。元素通常用于通过 JavaScript 在网页上绘制图形。所以从某种意义上来说，谷歌文档从现在开始要做的就是*在网页上绘制*文档。虽然这种方法有技术上的好处(我将在下面概述)，但在画布中呈现也有潜在的问题——特别是在可访问性方面。

 [理查德·麦克马努斯

Richard 是 New Stack 的高级编辑，每周撰写一篇关于 web 和应用程序开发趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) 

谷歌表示，画布渲染的变化将“提高性能，改善内容在不同平台上的一致性。”这对 Chrome 扩展的开发者来说有着直接的影响，然而，Google 已经给出了如何将扩展移植到新框架的指导。

然而，更大的问题是，这种变化会对其他 web 应用程序的构建产生什么影响？由于谷歌是现代网络开发中的一股强大力量(Chrome 是网络上的主导浏览器)，一些人想知道这种向 Canvas 的转移是否树立了一个不好的先例。

让我们后退一步，检查一下这种变化。到目前为止，Google Docs 已经在过去的 15 年中按照大多数 web 应用程序熟悉的模式发展了:它的交互性很大程度上是通过大量使用 JavaScript 代码来操作 DOM 实现的。然而，在线文字处理器需要在页面上精确呈现大量对象，这很难通过 DOM 来实现。Canvas 的吸引力在于，它使 Google Docs 的开发人员能够绕过所有挑剔的 DOM 争论，直接将文档“绘制”到页面上。

令人感兴趣的是，谷歌文档向画布渲染的转变可能是网络应用程序构建方式发生更大变化的早期迹象。正如 Matthew MacDonald 在 Young Coder 博客上的一篇优秀文章中所说:

*“现在感觉像是熟悉的模式——下载纯文本 JavaScript 代码并对可检查的 HTML 文档执行它——可能只是 web 开发不断发展的道路上的一个短暂停留。”*

麦克唐纳指出，谷歌地图多年来一直在进行画布渲染，这是谷歌跨平台颤振工具包的默认方法。这也是 Google Sheets 呈现内容的方式。因此，这不是一个全新的发展，而是谷歌随着时间的推移不断迭代的一种方法。

## 易接近

但是关于可访问性的问题呢？在画布上绘图意味着您没有使用 DOM 所提供的语义基础。在 DOM 的树形结构中，[的每个节点](https://en.wikipedia.org/wiki/Document_Object_Model)是一个对象，代表文档的一部分。对于 Canvas，它更像是一大块代码，而不是一棵树。

画布渲染的变化是在上周的谷歌 I/O(该公司的年度开发者大会)上讨论的，在[的“问我任何事情”(AMA)](https://events.google.com/io/session/7abba483-65cd-4de0-8d42-6f54375a7b6f?lng=en) 会议上，谷歌的 [Dion Almaer](https://twitter.com/dalmaer) (网络开发者生态系统总监)和[Paul kin LAN](https://twitter.com/Paul_Kinlan)(Chrome 开发者关系全球负责人)。主持人杰克·阿奇博尔德半开玩笑地问这两个人，“DOM 死了吗？”

Almaer 首先讨论了一个在线代码编辑器，这是他和他的同事 [Ben Galbraith](https://twitter.com/bgalbs) 在 2009 年推出的，当时他们在 Mozilla 工作，叫做 be spin——也是基于 Canvas 的。他们选择使用 Canvas 是因为它提供的性能优势。考虑到可访问性的限制，他们创建了一个“处理可访问性的辅助 DOM”他证实这也是 Google Docs 采用的方法。

“如果你真的玩过谷歌文档的[Canvas]版本，你会注意到它实际上与当前的 DOM 版本非常相似。这是因为他们也使用了侧 DOM 策略，并为此投入了大量工作。”

AMA 发布后，我和阿尔迈尔澄清说，他指的是隐藏的 DOM，终端用户看不到的东西，只是为了满足可访问性。他还提到，谷歌和其他公司正在研究一个名为[可访问性对象模型](https://wicg.github.io/aom/spec/) (AOM)的 W3C 规范，该规范将为开发者提供高级原语，使网页具有可访问性。

“所以你可以进来，以编程方式对屏幕阅读器和其他可访问的设备说话，”阿尔梅尔谈到 AOM 时说，“所以你可以获得更多的控制权，特别是如果你正在做这些丰富的事情(如谷歌文档)。”

侧边 DOM 方法和 AOM 都在新的谷歌文档中使用。“它们都来自同一个地方，”Almaer 说，“但是 DOM 结构本身专门用于视觉表示。我们正在为屏幕阅读器支持做一些完全不同的事情。基本上只是使用了[ARIA Live regions](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Live_Regions),原因是它们并没有被发明出来，这是一个文本到语音的引擎。”

## 选什么:DOM 还是 Canvas？

目前，如果您的应用程序需要大规模的性能提升，画布渲染方法可能是唯一有吸引力的解决方案。

在 AMA，Archibald 说并不是所有的网络应用程序都需要画布。“当你在编写一个原生应用时，”他说，“你不会直接使用汇编语言——只有当你真的真的需要那种能力时，你才会使用汇编语言。”同样，值得注意的是，很少有公司拥有(或需要)谷歌的规模。对于最终用户来说，Google 通过 Canvas 寻求的性能提升可能相对较小，但在 Google 的规模上，它有着实质性的影响。

基于 DOM 的呈现方法可能会在一段时间内(可能在未来很长一段时间内)继续在 web 开发中占据主导地位，但这并不是没有问题的。也许考虑到这一点，金兰认为选择 Canvas“给浏览器工程师施加了压力，要求他们实际上改进 DOM。”他引用了黑客新闻帖子[，其中谷歌文档的创建者之一概述了它多年来必须克服的各种与 DOM 相关的障碍。](https://news.ycombinator.com/item?id=27129858)

[史蒂夫·纽曼](https://twitter.com/SteveScalyr)是 2005 年发布在线文字处理器 Writely 的初创公司 Upstartle 的联合创始人。Upstartle 于 2006 年被谷歌收购，Writely 成为谷歌文档的基础之一。在《黑客新闻》中，纽曼写道，在线文字处理器“对布局、渲染和增量更新有着极其特殊的要求”，而 DOM 并不总是适合满足这些要求。他举了一个例子:

*"[…]要突出显示混合从左到右/从右到左文本中的文本选择，需要获得关于文本布局的非常具体的信息；DOM 可能无法提供的信息。*

纽曼补充说，Writely 在 2005 年的第一个版本是“一堆不洁的垃圾，摇摇晃晃地停在 contenteditable 上面”(指的是 HTML 的一个全局属性，允许用户编辑内容)。所以当时需要很多变通方法。

## 结论

当 Gmail 在 2004 年采用 Ajax 技术时，它是第一个在后台从服务器发送和检索数据的跨浏览器网络应用程序(而不是每次收到新数据时重新绘制页面)。这种方法后来成为 web 应用程序的标准。这种模式，即谷歌推广一种全新的网络开发方法，可能会在 21 世纪 20 年代的画布渲染中重演。

因此，Google Docs 有可能在十年后被视为用 DOM 方法呈现页面的煤矿中的金丝雀。然而，canvas 方法中的可访问性仍然需要“side DOM”这一事实意味着，要使 Canvas 呈现易于实现，还有很多工作要做。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>