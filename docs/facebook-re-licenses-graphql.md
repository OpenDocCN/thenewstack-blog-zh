# 脸书在无专利的麻省理工许可下重新许可 GraphQL

> 原文：<https://thenewstack.io/facebook-re-licenses-graphql/>

在羽翼未丰的 GraphQL 社区内部积怨日深之后，[脸书](https://code.facebook.com/projects/)本周宣布将改变与 GraphQL 规范相关的许可证。 [GraphQL.js](https://github.com/graphql/graphql-js) 参考实现和被称为 [Relay](https://facebook.github.io/relay/) 的客户端框架也将被改为 MIT 许可。

本周，脸书试图删除迄今为止一直用于其开源项目的 [BSD + Patents](https://opensource.org/licenses/BSDplusPatent) 许可:本周早些时候[该公司宣布](https://thenewstack.io/react-gets-new-front-end-library-new-license/)React 和其他开源项目在 BSD + Patents 许可下的许可变更。取代与 GraphQL 规范及其任何实现相关联的许可，该规范现在将在开放网络基金会的协议下被许可。

这澄清了大量关于脸书到底想用它以前的许可模式做什么的困惑。有些人会说，该公司只是在以新的有趣的方式保护自己，就像 IBM 和甲骨文这样的公司如何防御性地申请专利，以阻止潜在的专利流氓。

事实上，早在 2012 年，脸书就已经获得了 GraphQL 的专利。他们社区的基本理解是，这将保护每个人免受专利流氓的侵害，特别是因为 BSD +专利许可证允许脸书反诉任何围绕 GraphQL 规范起诉他们专利侵权的人。

然而，最终，这些类型的权利对最终开发人员来说是无关紧要的，并且有另一个许可证要处理会使谈判桌上的每个人都更加困难。这是一种常见的模式，在开源中已经重复了很多年。公司喜欢认为自己是特殊的，需要自己独特的许可证来参与开源。微软用 [Codeplex](https://www.codeplex.com/) 进行了尝试。孙一直喜欢自己的牌照，就像[的](https://opensource.org/licenses/CDDL-1.0)。

他们总是回到主要的许可:GPL、MIT 和 Apache。Sun 在 GPL 下授权 Java，微软现在喜欢 T2 的 Apache 2。这些是公司和律师理解的许可证。尝试不同事物的公司看到他们的项目被规避:因此[提前行动](https://github.com/developit/preact)。

 [麻省理工学院许可证

麻省理工学院许可证是一个简短的许可许可证，条件是只要求保留版权和许可证通知。许可的作品、修改和更大的作品可以在不同的条款下发布，并且没有源代码。](https://github.com/thomaspark/bootswatch/blob/gh-pages/LICENSE) 

这种情况经常发生，以至于 Apache Foundation 有自己的不兼容许可类别:[类别 X](https://www.apache.org/legal/resolved#category-x) 。这是有意义的，因为确保开源许可证的兼容性是这样的基金会和标准机构能够帮助企业更好地理解所有这些法律术语的主要方式。

在 Apache 的例子中，甚至 GPL 也包含在 x 类中。这是因为 GPL 比 Apache 许可证更严格:这就是这两个许可证不兼容的全部原因。7 月，脸书的 BSD +专利许可证被归入这一类，GraphQL 和 React 社区一直在敦促脸书做出改变。

脸书试图捍卫自己的立场，并在八月份给了社区一个相当艰难的“不”字。显然，这一次他们决定快速行动，打破常规。最后，这对参与其中的每个人都有好处，最重要的是，对 GraphQL 社区也有好处，因为它正处于形成发展的关键阶段。

开源先锋 Bruce Perens ，他实际上创造了“开源”一词的法律定义，他说脸书已经试图解决这个许可问题有一段时间了，尽管本周有所改变，但仍然没有把事情做好。

他指出，以前的许可证本质上是授予 GraphQL 用户免费使用标准背后的专利，但也规定这种用法禁止在任何地方就任何专利侵权起诉脸书。Perens 认为 IBM 在 Apache 基金会中的影响力可能导致该组织不喜欢 BSD +专利许可证。

然而，佩伦斯继续说，OWFa 许可证很少被使用，并且为其专利授权提供了一个重大而可怕的漏洞。

佩伦斯说，问题出在 OFWa 许可证的第 2 小节第 8.6 段，内容如下:

*8.6。许可用途。“允许使用”是指制造、使用、销售、要约销售、进口或分发规范的任何实现，1)仅在实现规范的范围内，2)只要规范的所有要求部分都已实现。允许的用途不延伸到规范中未包括的任何实施部分。*

这意味着专利许可只授予规范的完全实现。佩伦斯说，这可能会导致一些非常糟糕的后果。

“如果你实现一个微小的部分，他们不想给你他们的专利，”佩伦斯说。“假设你实现了标准中的一行，而且是在一个与标准完全无关的程序中完成的，你对法官说，‘我有标准专利授权的许可。’脸书不想这样被利用，所以他们说你必须实现标准的所有要求部分。那要求太多了。我同意这样的措辞，“标准的很大一部分。”如果你说所有要求的部分，你不允许人们在标准中创新。他们不能扩展它或丢弃他们不想要的东西。"

佩伦斯说，更糟糕的是，这样的条款可能会导致专利保护授权失效。想象一下，一个 bug 禁用了标准的一个特性，以至于它不起作用。这会使专利授权无效吗，因为规范的一个关键部分没有实现？

Perens 说，问题是，脸书可能真的必须自己编写许可证，才能从 GraphQL 的开源规范中得到它想要的东西。没关系，他说。问题不在于脸书试图以自己的方式做到这一点，而在于脸书已经在黑暗中做到了这一点，并简单地将新获得许可的软件扔到了墙外。

“他们需要更多的机构群体审查，然后才能向我们透露这些信息。也许他们不应该给我们，也许他们应该先提出一些建议，”佩伦斯建议道。考虑到本周的许可变更现在都处于未决状态，并且正在进入商业项目，这无疑是与社区合作的一个很好的理由，而不是简单地选择，然后在几个月后由于争议而改变决定。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>