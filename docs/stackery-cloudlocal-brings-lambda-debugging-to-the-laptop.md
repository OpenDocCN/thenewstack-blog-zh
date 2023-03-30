# Stackery CloudLocal 为笔记本电脑带来了 Lambda 调试

> 原文：<https://thenewstack.io/stackery-cloudlocal-brings-lambda-debugging-to-the-laptop/>

在过去的 web 开发时代，这个过程有点像这样:修改代码，点击保存，切换到 FTP 客户端，将所有内容上传到服务器，切换到浏览器，点击刷新。这是一个缓慢而烦人的手动过程，很快就被各种方法和工具淘汰了，但是近年来对于 Lambda 开发人员来说又重新出现了。随着上周[“cloud local for all”的发布，](https://www.stackery.io/blog/local-debugging-any-aws-lambda-function/)无服务器开发平台提供商 [Stackery](https://www.stackery.io/) 希望结束类似的乏味过程。

“人们在使用无服务器时遇到的最大挑战之一是，你不能在笔记本电脑上运行所有这些东西，这是一个很大的变化。以前，你要建立一个本地开发环境——你要在你的笔记本电脑上安装一个与你的生产相匹配的数据库，安装你需要的任何软件，并在本地运行一切，”Stackery 的产品和工程副总裁 [Sam Goldstein](https://www.linkedin.com/in/samgoldstein/) 在接受新 Stack 采访时解释道。“从开发人员的角度来看，这样做的好处是反馈周期快。我可以修改一行代码，在几秒钟内运行，然后知道什么是好的修改，什么不是。对于无服务器，这变得更具挑战性，因为你不能只在笔记本电脑上运行所有这些托管云服务。”

通过“cloudlocal”开发，使用 Lambda 的开发人员可以减少调试摩擦，并能够通过调用 Stackery 命令更快地发布新功能，该命令本质上导入所有云配置，然后在模仿 Lambda 功能的 Docker 容器中本地运行该功能，但连接到所有其他必要的云服务。

在这里，Goldstein 对“无服务器”的定义可能会派上用场。

“人们倾向于将功能即服务视为无服务器的同义词。这是 It 的一个关键组成部分，但实际上，无服务器方法是关于使用托管服务的，”Goldstein 说。“一个无服务器团队会说‘让我们利用所有这些现在可用的托管服务，它们在成本和负载方面可以扩展到零，并且可以扩展到非常高的负载，然后将它们结合在一起，利用我们的业务逻辑来提供这些云原生可扩展企业应用。’它实际上是将这些部分缝合在一起，并在此过程中能够专注于该业务逻辑，而不是那些底层基础架构组件。简而言之，这是无服务器的。"

因此，Stackery 的 cloudlocal 开发特性将无服务器的功能即服务方面与运行完整应用程序所需的所有其他托管服务连接起来。公告中的“面向所有人”部分事实上是所有人都可以使用该功能，无论他们是否有 Stackery 帐户，并且有多种语言。事实上，该特性只需要两件事 Stackery 命令行界面 (CLI)的[安装和 AWS Lambda 函数的 ARN 以及访问它的帐户权限。](https://docs.stackery.io/docs/using-stackery/cli/)

https://youtu.be/e-BB3rlEQn8

在公告中，Stackery 指出了该功能与 AWS SAM CLI 和其他本地无服务器开发工具的三个不同之处——它独立于框架，它可以调用 86 种 AWS CloudFormation 支持的资源中的任何一种，并且它可以运行非本机 Lambda 函数语言。Goldstein 说，通过这些方式，Stackery 致力于开发一种适用于所有人的工具。

“虽然 AWS 和其他云提供商提供的这些构建模块具有巨大的能力和灵活性，但围绕工作流程存在大量挑战。能够运用这种技术，并将其纳入一个合理的工作流程，让开发团队有效地工作，这是当今无服务器领域最大的挑战。这是许多公司在处理更复杂的应用程序方面的障碍，”Goldstein 说。“现在任何人都可以做到这一点。因此，即使你不是通过 Stackery 部署新的 Lambda，你已经设置好了一些东西，你需要找出一种更好的方法来开发或调试它，现在任何人都可以这样做。在内部，我们为每个人都推出了 cloudlocal，它实际上是为每个人提供基本的开发工作流功能。”

对于 Visual Studio 代码用户来说，Stackery 也注意到这个功能已经与 [Stackery VS 代码扩展](https://marketplace.visualstudio.com/items?itemName=stackery.stackery)集成在一起。

Stackery 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>