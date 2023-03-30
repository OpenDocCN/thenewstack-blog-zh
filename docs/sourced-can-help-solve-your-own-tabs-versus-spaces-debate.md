# Source{d}可以帮助解决您自己的制表符与空格之争

> 原文：<https://thenewstack.io/sourced-can-help-solve-your-own-tabs-versus-spaces-debate/>

关于制表符和空格的争论已经持续了几十年，尽管人们试图结束这一争论，但它仍在继续。StackOverflow 的联合创始人杰夫·阿特伍德(Jeff Atwood)曾经写道:“你选择哪种编码风格并不重要。重要的是，你和你团队中的每个人都坚持这些惯例，并始终如一地使用它们。”

为此，source{d}提供了机器学习和分析，以确保适应各种代码库的一致编码风格。换句话说，source{d}可以为您解决这一争论，不是通过询问负责人并自上而下地实施该风格，而是通过分析您现有的代码库，推断实践中的规范，并在您的整个代码库中实施它们。source{d}产品副总裁 [Francesc Campoy](https://github.com/campoy) 说，如果你曾经试图使用风格指南强制推行统一风格，你可能会熟悉随之而来的无用感，但当机器可以为你做到这一点时，这就更容易了。

“公司试图通过风格指南来强化风格。让人类执行这些事情是浪费时间，”坎波伊说。“我们理解您的源代码，并且您需要一致性。我们从您编写的源代码中提取规则，并将其应用到新的贡献中。我们不是强制执行具体的指导方针——现在追溯适用已经太晚了——而是强制执行一致性。”

今年早些时候，该公司发布了由 source{d} Lookout analyzer 进行的机器学习辅助代码审查，根据该公司的一份声明，“理解每个代码库都有自己的细微差别，并学习尽可能精确地为代码库风格建模，而不是依赖于全局风格实践”。

Campoy 解释说，Lookout 超越了风格，然而，不仅使代码本身更容易阅读和关注，而且确保代码尽可能高效。

Campoy 说:“如果你有一种通用的代码编写方式，当人们阅读它时，他们不会关注它看起来如何，所以他们会关注更有价值的东西——代码在做什么，是否有错误。”“复制/粘贴代码不是一项伟大的技术，我们能够检测到这种事情。我们使用模糊逻辑来确定代码之间的相似性，然后我们可以评论代码看起来相似，并建议使用函数来代替。”

Source{d}采用 GitHub 建议的更改来尽可能容易地提交代码更改，并在 GitHub 上提供了一个[演示库](https://github.com/lookout-demo/node/pulls)来演示该功能。目前，样式分析器只适用于 JavaScript，但是 Campoy 说他预计 Python 或 Java 支持将是下一个目标。

最后，曾在谷歌 Go 团队工作的 Campoy 指出 gofmt——面向 Go 开发者的行业标准格式化工具——是一个恰当的例子，指出“Go fmt 的重要事实不是它如何格式化，而是有一个人人都同意的工具。”

[https://www.youtube.com/embed/YLxvK027Npo?feature=oembed](https://www.youtube.com/embed/YLxvK027Npo?feature=oembed)

视频

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>