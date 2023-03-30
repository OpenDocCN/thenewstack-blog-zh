# 无服务器框架如何重塑 AWS Lambda

> 原文：<https://thenewstack.io/how-serverless-is-reshaping-aws-lambda/>

在本期 [The New Stack Makers](/tag/the-new-stack-makers/) 播客中，我们将探索最近发布的[无服务器](https://serverless.com/)框架 1.0 测试版如何重新定义开发人员如何使用亚马逊网络服务的 Lambda 无服务器云服务。

在与无服务器创始人和创造者 [Austen Collins](https://twitter.com/austencollins) 的访谈中，我们还讨论了开源社区的反馈如何塑造了无服务器的发展方向，以及无服务器架构在当今系统中的采用。

今年早些时候,[无服务器框架](https://www.github.com/serverless/serverless)被发布到[黑客新闻](https://news.ycombinator.com/)后，获得了巨大的兴趣。Serverless 是一个开源项目，因此社区反馈从一开始就是必不可少的，为 v1.0 beta 版奠定了基础。

“无服务器 1.0 版绝对是反馈的反映。柯林斯告诉我们:“开源项目产生的成果是惊人的，尤其是这个项目，因为我们正在做的是一个构建无服务器应用的框架。但是在 Lambda 上部署代码只是开发人员开发无服务器应用程序的一半。另一半是他们需要管理 Lambda 使用的基础设施。"

[无服务器框架如何重塑 AWS Lambda](https://thenewstack.simplecast.com/episodes/how-the-serverless-framework-is-reshaping-aws-lambda)

在 v1.0 测试版发布之前，无服务器项目从各种插件开始，随着社区表达对它们的需求，集成被添加进来。

柯林斯继续解释说，任何包含的插件都必须简单，便于用户根据自己的需要进行更换，“有多少开发人员，就有多少开发人员风格。为了满足所有这些人的需求，很明显，我们必须在第一天就有一个插件架构，并使其健壮且易于插入。此外，作为一名开发人员，我喜欢破解东西。我想很多其他开发者也有同感。如果我不能破解、修改或扩展(一个软件)，我会非常不喜欢它。”

在增加对其他提供商的支持的情况下，Serverless 已经与微软 Azure Functions 和 IBM Open Whisk 的团队合作，这两家公司都致力于与 Serverless 框架的集成。

虽然围绕无服务器的讨论越来越多，但一些组织仍然对采用这种架构犹豫不决。柯林斯将此归因于这样一个事实，即处理和操作大规模函数的工具还不可用。这就是无服务器框架希望让用户更容易过渡的地方。柯林斯指出，在开发和运营中，由于只需要修改一个部署单元就可以做出改变，因此功能更胜一筹。

“在开发中，如果你有成千上万的 Lambda 文件，那会非常烦人，因为你必须在所有这些独立的文件之间共享代码、基础设施和资源。在开发和部署阶段会变得复杂。作为部署单位的职能是强大的，但作为发展单位的职能是痛苦的，”他说。

虽然与 [AWS Lambda](https://thenewstack.io/tns-research-linking-serverless-distributed-database-trends/) 合作在过去给开发者带来了挑战，因为亚马逊向其用户提供了大量的选择，但 Collins 希望无服务器框架将有助于那些在自己的架构中使用功能的人轻松过渡。“我认为这非常适合我们的框架，让真正重要的东西浮出水面，把那些东西抽象出来，这样你就可以更快地开始工作。”

IBM 是这一新体系的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>