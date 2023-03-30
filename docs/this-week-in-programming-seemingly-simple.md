# 本周编程:看似简单

> 原文：<https://thenewstack.io/this-week-in-programming-seemingly-simple/>

本周的故事部分是忏悔，部分是认错，部分是讨论你是否真的需要使用最新的技术，只是为了避免使用旧的和“过时的”正如我几周前简单提到的那样，我正在为一个网站制作一组图像地图，这个网站我已经维护了 20 年。我知道，我知道——图像地图？我还不如用桌子呢，阿米利特？

这么说吧，在这一点上，我可能也考虑过那些。

试图做一些看似简单的事情，却让你走上了一条如此复杂和令人费解的道路，这是怎么回事？

现在，我要告诉自己，我有时可能是一个多么糟糕、没有好奇心和没有耐心的“程序员”，因为随着 Reddit、StackOverflow 和其他我似乎在网上找到的对我的问题“[如何才能避免图像地图](https://stackoverflow.com/questions/5249502/are-html-image-maps-still-used)”的答案，我的眼睛开始扫视屏幕以外的任何地方，我打开脸书、天气等等的新标签，并且通常会尽一切努力避免提供任何潜在的解决方案。与屡试不爽的方法相比，这些方法似乎都太费力了。

我不想下载一些库，我不想花时间学习使用 JavaScript、JQuery 和 SVGs，我也不想花几天时间在文档中搜寻这个一次性的任务。

所以我发现我自己，有一个看似简单的任务——拿这些[分解图](https://en.wikipedia.org/wiki/Exploded-view_drawing)并让每个部分和数字超链接到网站上它们相应的部分——并想知道为什么它必须如此该死的复杂？

我甚至安装了 Adobe Dreamweaver 和 Illustrator 的试用版(好像这些都很容易),看看它们是否有一些简单的方法来创建 SVG 或图像地图，但我发现自己又一次陷入了永无止境的帮助文档的迷宫，最终毫无进展。唉，感觉这些工具就像我几十年前最后一次使用它们时一样迟钝。因此，相反，我发现自己在避免任何现代的解决方案，你可能会把自己蒙在鼓里，使用一些[免费的、基于网络的图像地图创建器](https://www.image-map.net)来创建基本的 HTML，并从那里继续前进。

在此之前，亲爱的读者，你完全谴责我使用这种古老的技术，我问——有那么糟糕吗？我看到的每一个教程，我读到的每一篇文章，都提供了另一种解决方案，但对这种情况来说毫无意义。(我还应该提到，我们致力于 Shopify，所以在我们自己的可控服务器上使用开源购物车的日子已经过去了……所以就这样了。)这个借口够了吧？此外，我今天在这里向法庭提交的是，我只找到了一小段 JavaScript 代码，它显然会调整和重新计算我的图像地图，使它们“有响应性”，尽管我确实怀疑任何智能手机上的任何人在这种情况下都会觉得它们如此“智能”。

哦，正如许多人很快指出的，图像地图仍然在 HTML5 规范中，所以…一切都好，对吗？

所以，我想这就是我这个星期离开我们的地方。有时候，只是有时候，我认为古老的方法——表格或图像地图——只是比流传的任何新奇的解决方案更好、更合适的解决方案。如果你不介意的话，我要回去创建我的图像地图了…在这周的编程新闻之后。

## 本周的节目中

*   **2018 年 Rust 状态调查开始:**快速前进，Rust 宣布本周在[启动 2018 年 Rust 状态调查](https://blog.rust-lang.org/2018/08/08/survey.html)，这是一个试图考虑所有用户的希望和关切的项目的有希望的例子。我们经常报道[Rust 核心成员 Aaron Turon](https://thenewstack.io/this-week-in-programming-a-peek-into-the-rust-rfc-sausage-factory/) 的思考，它详细描述了这个社区是如何处理一起工作的考验和磨难的。因此，对于那些有意见的人来说，这里是 2018 年锈态调查[，将持续到 9 月 8 日，有 14 种语言版本。去年的结果也可供你参考。](https://goo.gl/forms/jFydE7csObcl6vxr1)
*   Bings 处理时区:你可能没听说过，但是[处理时区是……棘手的](https://zachholman.com/talk/utc-is-enough-for-everyone-right)。微软[宣布](https://blogs.bing.com/maps/2018-08/bing-maps-time-zone-api-working-with-time-zones)Bing 地图时区 API 现已正式发布并且 [ProgrammableWeb 提供了一个简要的概要](https://www.programmableweb.com/news/bing-maps-time-zone-api-now-generally-available/brief/2018/08/15)。基本上，“该 API 是一组 REST APIs，旨在涵盖开发人员在涉及时区时经常处理的各种场景”，并有助于“查找时区、转换为本地时间和列出时区。”
*   **亚马逊的开源 Alexa Auto SDK:** 在过去的一年里，我驾驶汽车在全国各地行驶了[数千英里，我不得不同意——能够与你的手机交谈是非常宝贵的。所以，我希望你继续前进，用亚马逊新发布的](https://thenewstack.io/this-week-in-programming-vandwelling-and-the-new-work-stack/)[开源 Alexa Auto SDK](https://developer.amazon.com/alexa-voice-service/alexa-auto-sdk) 构建有用的工具，其中 [ProgrammableWeb 再次剖析了](https://www.programmableweb.com/news/amazon-releases-open-source-alexa-auto-sdk/brief/2018/08/13)。SDK 允许汽车制造商将其 Alexa 服务集成到他们的汽车中，并“提供与 Alexa 服务通信的运行时引擎，以及控制音频输入、媒体播放和电话控制的界面”，允许用户“执行各种任务，如播放音乐、发起电话呼叫和管理气候控制系统。”在 GitHub 上查看它，旁边是一个示例 Android 应用程序，展示了如何使用 SDK。

*   现在是八月，RedMonk 刚刚发布了其[六月编程语言排名](https://redmonk.com/sogrady/2018/08/10/language-rankings-6-18/)，排名前十的语言变化不大，但其他语言的变化很大。虽然 [ADTMag](https://adtmag.com/articles/2018/08/10/redmonk-june-2018.aspx) 写道 Swift 已经跌出前 10 名，但另一个正在成为头条新闻的举动——与最近的 TIOBE 指数平行——是 Julia 的更快速崛起，该语言在经过近十年的发展后，上周刚刚发布了 1.0 版本。ZDNet 询问 Julia 是否有可能成为 Python 的竞争对手，指出它正在赢得开发者的支持。与此同时，JAXenter 也[关注 Julia](https://jaxenter.com/julia-ama-148245.html) 并指出[该团队最近的 Reddit AMA](https://www.reddit.com/r/IAmA/comments/97jdb9/weve_spent_the_past_9_years_developing_a_new/?utm_term=30731482220&utm_medium=comment_embed&utm_source=embed&utm_name=null&utm_content=footer) 是获得更多洞察力的地方。
*   **Furby 的 ASM 源代码:**没错，还有什么更好的方式用一个. Furby 原源代码的 [PDF 来结束一天的工作](http://www.seanriddle.com/furbysource.pdf)。我的意思是，没有什么比. PDF 格式的 ASM 源代码更适合 90 年代的动物皮毛生物了！

微软是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>