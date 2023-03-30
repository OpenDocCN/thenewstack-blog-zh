# Dygraphs 在 JavaScript 中实现了动态数据可视化的承诺

> 原文：<https://thenewstack.io/dygraphs-delivers-javascript-old-promise-smalltalk/>

在旧金山举行的[流入日](https://influxdays.com/)会议上，时间序列数据是讨论的主题。虽然该活动是由 InfluxDB 时间序列数据库的制造商 [Influx Data](https://www.influxdata.com/) 赞助的，但在这个为期一天的活动中，大多数演讲都专注于消化现代系统日志文件产生的海量信息，而不是任何一个特定的数据库。管理员和操作员工作的现代命脉是密集的分析和跟踪，没有什么比更好的可视化工具更有助于消化数据。

## 闲聊的古老承诺

有一个人长期以来一直在用 JavaScript 开发一个工具，帮助将图表和图形引入巨大的时间序列数据池。通过这样做，他实现了 [Smalltalk](http://squeak.org/) 社区的长期梦想:当代码被编辑时，人们可以拥有实时的动态代码呈现数据分析。这种愿景在 80 年代初作为 Smalltalk 社区被带到了华尔街，但很快就消失了，因为对于这种以编程方式分析数据的创新方法来说，这还为时过早。

Dygraphs 起源于 2006 年的 Google，当时 Dan Vanderkam 决定为他的团队开发一个数据可视化工具。他派生了阿拉斯泰尔·谢的 [plotkit](https://github.com/ept/plotkit) ，并添加了交互性，为他刚刚加入的团队构建了一个仪表板。

到 2009 年，谷歌的另一个团队正在使用它，该项目在 GitHub 和现已废弃的谷歌代码上发布。Dygraphs 在 2013 年真正获得了关注，并成为动态绘制时间序列数据的流行方式。在“涌入日”上，Vanderkam 概述了这个项目及其发展方向。

今天，Dygraphs 仍然在谷歌和其他地方使用，在像 Chronograf 这样的项目中，在像 DuckDuckGo 这样的网站上。Vanderkam 说，他继续明确地将时间序列数据的动态处理作为该项目的优势。哦，而且它的速度不疼。Dygraphs 可以绘制一百万个点，并在几秒钟内动态显示出来。

## Dygraphs 提供

Dygraphs 如此快速和响应迅速的原因之一是它在[画布](https://www.w3schools.com/html/html5_canvas.asp)中渲染，而不是在 [SVG](https://www.w3schools.com/graphics/svg_intro.asp) 中渲染。Vanderkam 说，可缩放矢量图形由 DOM 处理，渲染速度慢得惊人。

“SVG 就像用于绘图的 XML。当你定义一个 SVG 标签时，你可以用 CSS 来设计它们，并使用 DOM APIs 来操作它们。“画布不是这样的。Canvas 对 DOM 和 CSS 是完全不透明的。这是绝对必要的。如果你想改变什么，你要重画整个画布。这听起来很慢，但实际上，DOM 通常更慢。我经常不得不从 SVG 切换到 canvas。这就是 Dygraphs 的优势:它从一开始就使用画布。”

今天，Vanderkam 是 Sidewalk Labs 的高级软件工程师，但即使在 10 年后，他仍然是 Dygraphs 的主要维护者。这并不一定是他引以为豪的事情，他鼓励观众在开始一个开源项目时尽早获得外界的帮助。

因此，Vanderkam 在这一年中断断续续地更新项目，而不是以可靠的节奏更新。然而，这些年来，他提出了一些有趣的工具来帮助外部开发人员和他自己。

其中一个工具是自动截图比较工具，他用它来检查不同版本之间的测试演示。如果结果不同，演示运行的屏幕截图也会不同，这样就可以捕捉到回归错误。

在 Dygraphs.com 大学的其他地方，Vanderkam 一直致力于为用户提供交互查看和尝试 Dygraphs 的工具。dygraphs.com/jsbin 是一个基于浏览器的环境，代码可以写在浏览器屏幕的左侧，并在右侧呈现为图形。

## Dygraphs 的下一步是什么

至于项目管理工具和技巧，Vanderkam 建议开源项目将支持转移到 StackOverflow，在那里关于 Dygraphs 的主题会自动发送给他。因此，当有人遇到问题时，会有很多其他有知识的人首先回答，如果没有，范德卡姆自己也可以回答。已解决的问题由 StackOverflow 进行 SEO，希望下次有人遇到同样的问题时会出现，节省大家的时间。他还建议用户首先在[dygraphs.com/fiddle](http://dygraphs.com/fiddle)发布他们的错误报告，其中嵌入了 GitHub 问题跟踪。

Vanderkam 还在开发一个名为 Just Chart it 的新工具，该工具基于 Visual Studio 代码。这个工具包括代码的自动完成，同时还为输入的数据呈现一个电子表格界面。这为用户提供了一个一体化的时间序列可视化和操作工具，可以在实时操作代码时动态加载更改。

Dygraphs 具有[类型脚本](https://www.typescriptlang.org/)类型注释。这个编辑器与 [Visual Studio 代码](https://code.visualstudio.com/)相同，所以它会自动完成。你还可以设置每个系列的选项，它也有一个突出显示哪个系列的概念，”Vanderkam 说，演示了可以集成到用 Dygraphs 生成的图表中的动态交互元素。

Dygraphs 在今年早些时候达到了 2.0 版本，Vanderkam 有一些想法，他希望将这个项目向前推进。具体来说，他计划将 Dygraphs 的优势翻倍，而不是将其扩展到新的领域，如非时间序列数据。

“创建跟踪数据过程和每日数据的图表可能会更容易，当您进入图表时，可以获取每小时或每分钟的数据。有机会为主题提供可选的支持。可能会有 React 或 Angular 的框架集成，所以我有机会重写一些我想摆脱的 API，”Vanderkam 说。

至于 Dygraphs 与其他 JavaScript 图表工具和库相比如何，Vanderkam 表示，流行的项目 D3 比 Dygraphs 更受关注。他说 D3 是关于将数据绑定到 DOM 元素的，这与 Dygraphs 使用的快速画布渲染不一样。

Vanderkam 说，类似地， [Charts.js](http://www.chartjs.org/) ，另一个流行的开源 JavaScript 图表库，更普遍地专注于图表，而不是专门绘制时间序列数据。

最后，Vanderkam 对所有开发人员提出了一些普遍相关的建议:当编写评论时，你的目标受众是两年后的你，对工作范围没有任何记忆。“当我写评论时，我的目标读者是两年后的我自己，那时我已经完全不知道它在做什么，为什么要做，”范德卡姆说。

[潮人数据](https://www.influxdata.com/)是新栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>