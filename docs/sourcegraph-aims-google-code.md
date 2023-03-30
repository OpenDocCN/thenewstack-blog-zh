# Sourcegraph 的目标是成为“代码的谷歌”

> 原文：<https://thenewstack.io/sourcegraph-aims-google-code/>

从斯坦福大学毕业后， [Quinn Slack](https://twitter.com/sqs) 和 [Beyang Liu](https://github.com/beyang) 在大公司工作，了解到开发人员面临的许多挫折。他们决定必须有一个更好的方法，并着手建立一个开源代码的搜索引擎。

" [Sourcegraph](https://sourcegraph.com/) 就像是[Google for code](https://thenewstack.io/google-launches-carbon-an-experimental-replacement-for-c/)；这是面向所有开发者的公共事业，”Slack 谈到该公司时说。这家总部位于旧金山的公司成立于 2013 年，现已发展到拥有 18 名员工。

该工具使用户能够在他们自己的代码库中进行搜索，并开放源代码。

“在这些大公司里，已经有 1000 个人用代码做了同样的事情。有太多重复和重复的代码，”他说。“人们认为开发人员构建了所有这些复杂的系统，但他们使用的工具实际上比财务团队使用的工具要原始得多。你有比程序员使用的更先进的内容社交媒体分析。”

Sourcegraph 展示了代码在公司内部和世界各地是如何使用的。

“乌兹别克斯坦的某个人可能会写一段代码，通用电气就用在它的喷气发动机上。我们的软件理解这些关系，”Slack 说。“我们可以帮助开发者更好地搜索代码，并做其他真正有趣的事情，比如当你在公司内部改变一段代码时，向你展示连锁反应。这还会搞垮其他什么系统？需要谁批准？这是不是意味着突然之间黑名单上的人就可以开支票账户了？”他说。

“通过不重复编写相同的代码，它节省了公司最宝贵的资源，即时间。不要做那些手工任务，让一个人检查所有这些代码，而计算机可以做得更好。”

## **像拼写检查一样简单？**

Sourcegraph 服务的核心是一个巨大的图形数据库，如果他们使用 GitHub 或 Bitbucket 之类的东西，它就位于他们现有的工作流程之上。

Sourcegraph 构建于其他开源项目之上，包括 JavaScript 代码分析引擎 [Tern](http://ternjs.net/) 、Ruby 文档工具 [YARD](http://yardoc.org/) 和 [Jedi](https://github.com/davidhalter/jedi) 。

该公司自己开发了 srclib，这是一个测试版的多语言代码分析库。它支持跳转到定义、查找用法和文档等功能。

您可以从 web 浏览器中按存储库、包或函数搜索代码，而不必配置编辑器插件。它试图让寻找答案变得像使用拼写检查一样简单:只需将鼠标悬停在一段代码上，就可以找到关于它的大量信息。

https://www.youtube.com/watch?v=ssON7dfaDZo

srclib 库处理诸如包检测、依赖性解析和使用不同版本控制系统之类的任务。

它由面向 Go、Python、JavaScript 和 Ruby 的语言分析工具链组成，具有通用的输出格式和使用这种格式的开发人员工具。它被设计成模块化和可扩展的。可以使用输出 srclib 格式的工具链添加新语言。

它可用于 Go、Java、Python、Scala 和 JavaScript，还有十多种语言正在开发中，包括 C#、PHP、Objective-C、C/C++和 Perl。Slack 说，其中一些来自外部开发人员，他们只想要他们喜欢的语言的 Sourcegraph 功能。

Sourcegraph 还可以让你[直接在博客帖子和论坛中嵌入可点击的交互式代码片段](https://opensource.com/business/15/4/better-software-with-sourcegraph)。它鼓励开发人员让他们的存储库允许其他人在 Sourcegraph 上搜索和浏览代码。

“如果你是一个开源作者，你只想让你的用户更容易地使用这些代码，这样你的库就可以被更多的人使用，”Slack 说。

Sourcegraph 针对 GitHub 的 Chrome 扩展，只针对 Go 和 Java，使每个标识符都成为跳转到定义的链接，通过悬停在标识符上显示文档和类型信息。键盘快捷键 Shift-T 允许您搜索函数、类型和其他定义。

## **许可批评**

然而，由于授权 Sourcegraph 作为[公平源](https://fair.io/)，该公司受到了批评。该许可证允许每个人都可以看到源代码，个人和小组可以用它发布他们自己的项目。它允许授权其产品的公司在客户必须开始付费之前设定一些免费用户。Sourcegraph 将这个数字设定为 15 个用户，之后它就成为一项付费服务。它承认公司的所有用户都可以作为个人注册并免费获得服务，但它指望开发者社区“做正确的事情”

Slack 说:“开发者使用的许多工具都是完全闭源的，所以我们看看我们能做些什么对开发者更友好。”“如果我们完全开源，那么我们必须找到一些其他的商业模式…所以问题是:我们如何使代码完全公开，但仍然有一个可持续的业务？”

他们找到了 Heather Meeker 律师，一位开源许可的专家，他写了一份简单易懂的 22 句话的许可证。“我们决定要超级透明，”Slack 说。

他指出了一些开发人员试图以代码为生的项目，包括开发人员工作区供应商 [Codenvy](https://codenvy.com/legal/fair-source/) ，该供应商使用 Sourcegraph 许可证的衍生产品，但将免费用户的数量限制为五个。虽然 [GitLab](https://about.gitlab.com/2016/03/24/gitlab-look-at-the-fair-source-license/) 认为公平源，但它最终决定引入新的许可模式会给用户带来太多困惑。

Redmonk 分析师 Stephen O'Grady 最近写道，从软件中赚钱比以往任何时候都难，不管是开放的还是封闭的，聪明的公司正在寻找替代的收入模式。

同时， [Matt Asay](https://www.techrepublic.com/article/fair-source-licensing-is-the-worst-thing-to-happen-to-open-source-definitely-maybe/) ，在 TechRepublic 的一篇文章中，称公平源代码是“所有词语中最糟糕的，因为它给许可过程带来了不必要的复杂性，这些都不是为了让开发者受益。”

专题图片:“沙滩双筒望远镜。法国尼斯”由 [Kinolamp](https://www.flickr.com/photos/nbabaian/) 制作，以 **CC BY-SA 2.0** 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>