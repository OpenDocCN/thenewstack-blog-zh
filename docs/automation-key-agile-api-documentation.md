# 自动化是敏捷 API 文档的关键

> 原文：<https://thenewstack.io/automation-key-agile-api-documentation/>

文档化的想法通常会让人打呵欠，随之而来的是老式的、自上而下的瀑布式项目管理。文档经常被视为敏捷项目管理过程的一个负担，这个过程是通过快速迭代、向客户学习和旋转来构建的。

然而，特别是在 API 领域，开发者考虑的最重要的事情是文档。

但是如何将所有重要的文档集成到敏捷世界中而不降低它的速度呢？我将分享一些在为 [APIDays](http://www.apidays.io/) 会议系列撰写[“API 文档的状态”](http://apidocswriter.com)白皮书的过程中与我交谈过的亲文档敏捷人士的智慧，以帮助理解是什么阻碍了我们以及如何推进敏捷文档。

为了这篇文章，我们特别关注敏捷环境中的 API 文档，但是这些经验可以应用于任何敏捷团队。

## 为什么文档不能成为敏捷的一部分？

有些人会说这是文化的结果，或者可能是缺乏所有权的结果。

“API 设计优先天生就不敏捷。我们设计整个东西，然后把整个东西扔出去(宣布)‘成为我们智慧的接受者’，[养蜂场](https://apiary.io/)(目前[正被甲骨文](https://www.zdnet.com/article/oracle-to-buy-api-development-firm-apiary/)收购)产品开发负责人[伊曼纽尔·帕拉斯卡基斯](https://twitter.com/manp)打趣道。

尽管开发人员正在努力打破这些孤岛，但毫无疑问，文档，就像测试一样，仍然是扔给 IT 部门的一块烫手山芋。它不是被认为有趣的事情，尽管所有的证据都相反，它也不是被认为重要的事情。

> “最终，如果没有控制，我们将会有许多不同语言的微服务，这将花费大量资金。”—阿诺德·劳雷特，美国石油学会杂工

科技作家机构 [SynergisTech](http://www.synergistech.com/landing.html) 的创始人 [安德鲁·戴维斯](https://twitter.com/synergistech)说，“在我服务的大多数公司里，关于它是‘人们最想要的东西’的那篇文章并没有注册。并非所有人都在开源领域，在那里文档真正销售产品，但我的大多数客户考虑文档太晚了，当他们发现开发人员技能和技术写作人才的罕见组合时，他们拒绝支付可观的费用。”

毫无疑问，虽然文档一次又一次地被称赞为决策中的一个重要因素，但它被认为是不重要的，特别是在敏捷团队中。

一个问题可能是，在大多数敏捷情况下，项目里程碑只是被故事点评估所取代，仍然有开发人员和团队封锁时间限制，以某种方式进一步限制开发过程，然后创造新的借口来传递文档。

正如来自 [API 杂工](https://apihandyman.io/the-api-stylebook/)的 [Arnaud Lauret](https://www.linkedin.com/in/arnaudlauret/) 所说，“这是敏捷自治的好和坏的一面。”您更快、更高效，并且有更大的能力来满足客户的期望，“但是，最终，如果没有控制，我们将有许多许多不同语言的微服务，这将花费大量资金。”

尽管如此，API 文档应该非常适合敏捷世界“因为你有能力在开发的几乎每个阶段修改驱动整个过程的东西。这些修改会以可控的方式影响它下游的所有工件，”Swagger API 框架的创建者 Tony Tam 说。

Tam 解释说，成功的 API 文档“根本不是一个瀑布式的过程，因为它不是一个连续的过程。在设计变更中，客户端、文档和服务器都是并行发生的。”

正如 Davis 提到的，文档只在一些开源的情况下有用，在这种情况下，你想减少可预防的技术支持呼叫。但是可以肯定的是，随着我们给予开发人员更多的独立性来使用微服务、容器和其他不同语言的小代码，我们对内部团队的文档也有了更大的需求。

事实上，由于敏捷看到内部团队处理代码的速度如此之快，对他们来说，在进行过程中记录文档可能更加重要。

作为一名 [API 顾问](http://richvisotcky.com)， [Rich Visotcky](https://www.linkedin.com/in/richvisotcky/) 发现他需要为建筑行业的客户创建大量的文档。可能有六、七个应用程序团队和另外两个服务团队不得不消耗所有资源。

“更新的、有用的和简洁的文档对这些团队使用我们的服务非常重要，尤其是当他们一个 sprint 接一个 sprint 地改变时，”他说，每个过程持续两到三周。

这意味着他们不能只有一个需要不断更新的 wiki 或 API 手册，所以他们继续努力创建一个尽可能自我描述的 API。

像敏捷领域的所有事物一样，自动化在保持文档更新方面扮演着重要角色。

## 定义语言能让文档变得敏捷吗？

或者一个更好的问题是:API 定义语言，比如 Swagger，能把文档卖给敏捷者吗？

我们很快意识到我们不能做的事情之一是创建脱离代码的文档。它必须直接与我们的代码共存，否则就会立即过时，”Visotcky 说。

为了实现这一点，他使用了由实际方法签名生成的 XML 注释的组合，这是一个名为 [GhostDocs](http://submain.com/products/ghostdoc.aspx) 的 Visual Studio 文档扩展，然后他们使用 XML 文档来生成 Swagger API 文档，他说这将文档和代码内在地联系在一起。

“斯瓦格棒极了，”他说。“这给了我们一些简短的广告词，人们可以在我们内部发布的网站上找到它们。”

Paraskakis 呼应了这种对自动化的需求，并补充说，它让消费者尽早且经常地参与进来。

使用 APIary 的定义语言 [API 蓝图](https://apiblueprint.org/)“我们不仅会让你成为消费者，我们还会以代码服务器的形式给你一个活的原型。你不必等到冲刺或发布的时候。”

当然，原型是一种在敏捷开发过程中测试事物的方法，而不必提前构建太多。此外，这个过程允许自动驱动测试，“所以我们保证这个契约(API 提供者和消费者之间的)不会被破坏。”

Paraskakis 继续说，“很多人谈论你创建它的生命周期，然后是文档，等等。一旦得到反馈，我们就想回去做更多的事情。也许是微服务、用例或合作伙伴 API，但当你需要大量 API 时，你就会达到一个点。”

那时帕拉斯卡基斯提倡一个风格指南，它的很多内容被表达为一个文档。“你需要有工具来获取风格指南，反思它，并在你偏离风格的时候给你建议——不是阻止你偏离，而是提醒你。”

“您还需要与您的版本控制系统集成，以便您可以管理变更、 分支、拉式请求、合并，尤其是当您从外部引入合作者时，”允许他们在不同的分支中提出建议。

[Uri Sarid](https://twitter.com/usarid),[Mulesoft](https://www.mulesoft.com/)的首席技术官和 [RAML](http://raml.org/) API 描述语言的共同创建者，将敏捷描述为“快速变化的能力”。

正是出于这个原因， [Spotify](https://www.spotify.com) 使用 RAML 做前端，Mulesoft 做后端集成。音乐巨头敏捷成功的秘诀是什么？

“如果你想走得更快，你实际上只需要指定 API——只需要足够紧密的耦合，并知道什么不会改变。API 确切地告诉你你依赖什么。好篱笆造就好邻居。API 经济是在松散耦合的基础上发展起来的。”

Sarid 提供了 Docker 作为另一个例子，因为他们有一个定义良好的 API，非常具体地告诉你可以用它做什么。

“不做，就没用。为了更快，你需要准确的合同。因为一艘货船上的所有集装箱都完全一样，他们都需要那份合同。”

基本上，Sarid 把文档作为 API 公开者和 API 消费者之间契约的一个非常重要的部分。

> 我们从来不允许发布没有文档记录的产品，确保文档随着产品的开发而不断重复”——Romain Huet，Stripe。

“你拥有的微服务越多，你需要的灵活性就越大，定义合同就越重要，这样你就知道什么不会改变，什么会改变。”

网飞，以其所谓的 [混沌工程](http://techblog.netflix.com/2014/09/introducing-chaos-engineering.html) 而闻名，实际上使用自动化和文档化来为其大部分内部 API 创造和谐。

Sarid 指出了他们的代码如何以人类和机器可读的方式体现他们的 API。当一个 bug 被发现时，那是因为有人编码错误，表明需要更多的自动生成。

## 没有借口

对于内部或外部的技术作者加入敏捷团队并负责 API 文档来说，这是一个强有力的论据。是的，这对管理这一切很有用。但也许更重要的是让每个开发人员负责记录她或他自己的作品，然后才允许对其进行管理。

正如资深技术作家 James Neiman 所说，文档工作应该与产品发布周期保持一致。

“如果你加入了一个产品和工程团队，在敏捷环境中,‘完成’的定义就是文档被更新。没有是不行的。”

当然，随着项目的进展，这变得更加困难。Scrum 大师或产品负责人需要从一开始就帮助团队勾勒出一个一致同意的“完成”定义，就像测试一样，应该包括文档。

“最重要的是在过程的早期开始文档，并确保它不断更新，”来自 [Stripe](https://stripe.com/docs/api) 的开发者关系团队的 [Romain Huet](https://twitter.com/romainhuet) 说。“我们从不允许发布没有文档记录的产品，确保文档随着产品的开发而不断重复。”

他接着说，这是一个很好的方法，可以在开发者体验发布之前看到它是什么样子，因为，即使当你在更短、更敏捷的开发周期中互动时，你也想确保开发者体验是最重要的。”

Huet 还提醒我们，创建保持更新的简单文档的最简单方法是保持代码简单。Stripe 最近意识到，当通过 Apple Pay 集成支付工具时，他们减少到一行简单的代码。这也不是什么新鲜事。Stripe 是在 2010 年围绕“应该容易设置和接受支付”这一简单原则创建的，这就是为什么 Stripe API 只用 14 行代码就实现了这一点。

通过预先编写文档规范，你可以通过预先规划“理想代码”来变得更加敏捷，这反过来让我们思考开发人员想要写什么，正如 Huet 所说，这是一种令人愉快的集成方式。

在维索特基的敏捷团队中，当文档被整合到过程中时，他们也获得了成功。

编写代码的人更新了我们的文档。这是我们对完成的定义的一部分。”维索特基继续解释说，“我们作为一个团队检查过了。更新 API 或更新端点或改变其行为方式的人可能最需要更新文档，但我们作为一个团队来检查它，以更新 API 中实际发生的行为。”

最后，Visotcky 说他们有两种类型的文档，他称之为“协作”或客户要求的文档，以及为他们自己使用而生成的 Swagger 文档。他们继续根据自己的需要编写和维护文档，不断尝试将它们最小化。

重要的是你有 API 文档，但是，像所有敏捷的事情一样，你如何做应该根据每个客户、每个产品和每个需求来定制。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>