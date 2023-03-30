# 未来的一年:Node.js 和所有的互联网事物

> 原文：<https://thenewstack.io/year-ahead-node-js-internet-things/>

*在本周的 New Stack，在名为“未来一年”的系列中，我们将探讨一些技术和技术问题，我们预测这些技术和技术问题将在 2016 年对我们的读者非常重要。无状态计算是我们计划在 2016 年密切关注的一个领域。*

对于 Node.js 服务器端 JavaScript 运行时来说，2015 年是非常好的一年。开源技术[已经得到了一些正式的治理](https://thenewstack.io/foundation-node-js-will-bring-back-fork/)，[与它自己的分叉版本](https://thenewstack.io/io-js-and-node-js-have-united-and-thats-a-good-thing/)重聚，并继续努力进入[企业](https://thenewstack.io/node-js-long-term-support-ready-enterprise/)和[网络规模的公司](https://thenewstack.io/netflix-uses-node-js-power-user-interface/)，即使支持工具[仍在构建和发布](https://thenewstack.io/tns-analysts-node-js-tooling-enterprise-please/)。

Node.js 最初立足于 web 应用程序，现在正迅速成为至少一些企业作业的替代选择。Net 或企业 Java。但在本月早些时候在波特兰举行的 Node Interactive conference 上，我们发现开发人员让 Node 从事另一项工作:为新兴的物联网(IoT)构建应用程序。

您可能对物联网很熟悉，甚至可能对这个短语感到厌倦。但是，随着处理器成本的下降和无处不在的互联网，物联网将是不可避免的。分析公司 IDC 预测，到 2020 年，全世界将在所有互联网事物上花费 1.7 万亿美元。

在 Node Interactive，[在线教育网站](https://twitter.com/chalkers?lang=en) [Treehouse](https://teamtreehouse.com/) 的老师 Andrew chalk ley[讲述了](https://youtu.be/KS6GxMOJjA8?list=PLfMzBWSH11xYjL8oFumSfzOf6-kr8_t-o)Node 如何已经被用于许多低功率[业余爱好者设备](/tag/off-the-shelf-hacker/)。这些家庭项目将成为物联网设备的原型，这些设备将在未来几年实现工业化和商业化:

[https://www.youtube.com/embed/KS6GxMOJjA8?list=PLfMzBWSH11xYjL8oFumSfzOf6-kr8_t-o](https://www.youtube.com/embed/KS6GxMOJjA8?list=PLfMzBWSH11xYjL8oFumSfzOf6-kr8_t-o)

视频

Chalkley 解释说，Node 和 Node 使用的编程语言 JavaScript 可以以多种方式与物联网设备交互。一些高响应性但很小的微控制器，如 Espruino 或 Tessel，能够直接运行 JavaScript，通常是通过精简的 JavaScript 引擎。

然后是嵌入式设备，它非常像完整的 Linux 服务器，可以为运行 Node 提供完整的支持。在这里，我们谈论的是 Tessel 2，树莓派。“你可以在上面安装任何东西，包括全节点，”Chalkley 说。本质上，它们是真正的“互联网事物”

对于那些已经存在了一段时间的人来说，物联网听起来可疑地像过去被称为嵌入式计算的东西，也许还有一些额外的后端数据处理，以解决运营效率低下和客户洞察。由于这些微控制器的初始处理和内存限制，嵌入式开发人员倾向于使用低级的、接近金属的语言，如 c。

然而，JavaScript 和 Node 可能为物联网黑客提供许多优势，尤其是在酷孩子中的受欢迎程度。英特尔 Chrome OS 工程总监梅丽莎·埃弗斯·胡德(Melissa Evers-Hood)表示:“Node 在生态系统中拥有巨大的发展势头。

都是人的问题。例如，在其研究中，英特尔发现超过一半的 Android 应用程序以某种形式使用 JavaScript。所以有很多 JavaScript 开发者，还有很多可重用的代码。“你可以很容易地将它扩展到新的领域，”Evers-Hood 说。

由于 [Codecademy](https://www.codecademy.com/learn/javascript) 、 [Hour of Code](https://hourofcode.com/us) 以及无数其他促进计算机编程素养的努力，越来越多的初级 JavaScript 程序员上线了。Evers-Hood 说，在接下来的十年里，我们将经历一个“人们将真正在 JavaScript 上成长的浪潮”。

![Node and Javascript top a survey of Stack Overflow developers' planned languages toi adopt (Research: TNS/Lawrence Hecht).](img/59d5103812a070ad6e07200623255e31.png)

Node 和 Javascript top 栈溢出开发者计划采用的语言调查(研究:TNS/Lawrence Hecht)。

“这些年轻人正在进入市场，他们将创新并创造新的使用模式和新的应用。Evers-Hood 说:“在物联网方面，它们将成为一个有趣的点。

瑞安·达尔[创建了](https://www.youtube.com/watch?v=ztspvPYybIY) Node.js，它本身是用 C 语言编写的，[用来解决网络应用](https://thenewstack.io/getting-handle-node-js-deployments-dynatrace/)中的 I/O 阻塞问题，并于 2009 年发布了该软件。当网页从数据库或磁盘请求某些东西时，会发生 I/O 阻塞，导致所有后续操作暂停，至少是暂时暂停，直到响应到达。Node.js 使用一个事件循环线程来处理多个杂务。Node 可以为每个函数分配一个回调，而不是等待响应，因此事件循环可以继续到下一个任务，并在函数响应到达时返回到函数响应。因此，它速度很快，并且可以扩展。

[![Walmart's Jason Pincin, celebrating 500 million page views, served up by Node.js, on Black Friday 2014](img/99e80978a68d59f02ec11e888dff5511.png)](https://twitter.com/jasonpincin/status/538369235848679424/photo/1?ref_src=twsrc%5Etfw)

力矩节点。JS 成为企业中的一个重要竞争者:沃尔玛的杰森·平辛在 2014 年黑色星期五庆祝了 5 亿次页面访问，全部由 Node.js 提供

作为一种 Web 技术，Node 还提供了一套一致的 API，这将有助于解决物联网将在其上运行的各种平台。

Evers-Hood 说:“你可以获得部署能力的一致性。“核心开发资产可以很容易地跨平台转移到开发平台，因为这些 API 在整个操作系统中是一致的，所以您可以更加灵活地开发代码。”

但是 JavaScript 本身呢？Brendan Eich 在 10 天内为 Netscape Communications 创建了 JavaScript，它已经被视为有点像[的杂牌](http://www.outpost9.com/reference/jargon/jargon_26.html)，尤其是被那些老顽固们。尽管出身卑微，JavaScript，或者至少它的一部分是“辉煌的”，程序员[道格拉斯·克洛克福特](http://www.crockford.com/)在[的一次关于语言表达能力的演讲](https://www.youtube.com/watch?v=RO1Wnu-xKoY)中说道。

克罗克福德说:“所选择的功能以及它们是如何组合在一起的，好得令人吃惊。”。"这是一种具有惊人表现力的语言。"

谁会想到，到 2016 年，所有语言中的 JavaScript 会在你的冰箱里运行呢？

英特尔是新堆栈的赞助商。

专题图片:[Sens 大主教 Gauthier Cornut 展示荆棘王冠](http://www.metmuseum.org/collection/the-collection-online/search/471219)，[纽约修道院](http://www.metmuseum.org/visit/visit-the-cloisters)博物馆的 13 世纪彩色玻璃艺术。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>