# AWS 无服务器快递现在已经完全成熟

> 原文：<https://thenewstack.io/aws-serverless-express-is-all-grown-up-now/>

当[亚马逊网络服务(AWS)](https://aws.amazon.com/) 和[蒂姆·瓦格纳](https://www.linkedin.com/in/timawagner/)，也就是[无服务器计算之父](https://www.hpe.com/us/en/insights/articles/containers-and-microservices-and-serverless-oh-my-1805.html)第一次提出事件驱动计算的想法时，他们没有想到[无服务器计算会成为一种新的计算范式。哦，好吧，你不可能把它们都弄好。](https://aws.amazon.com/lambda/)

它并没有立即发生。Lambda 在 Node.js 的支持下推出。这有助于带来许多客户，因为他们已经知道了 JavaScript。但是顾客想要更多。他们想要熟悉的框架，比如 [Express](https://expressjs.com/) ，在其上构建他们基于 Lambda 的 web 应用。进入 [Serverless Express GitHub 项目](https://github.com/vendia/serverless-express)。

这很快就非常成功。开发人员可以使用他们已经知道的工具和框架来创建 Lambda 项目。而且，他们喜欢它。今天，[AWS-server less-express](https://www.npmjs.com/package/aws-serverless-express)NPM 软件包每月获得超过 130 万次下载，其 GitHub 库拥有超过 37k 颗星。无服务器快递也是从 [AWS 实验室](https://github.com/awslabs/)毕业的。

然而，无服务器快递没有的是公司的支持。现在，Lambda 的发明者兼[Vendia](https://vendia.net/)(Venn Diagram 的简称)的首席执行官 Tim Wagner 凭借其无服务器分布式应用互操作性平台，也在积极支持和赞助 [aws-serverless-express](https://github.com/vendia/serverless-express) 开源项目。

为什么？Vendia 希望无服务器社区取得成功。毕竟，Lambda 和其他无服务器产品支持“Vendia 的实现，并帮助我们为客户提供可扩展的低成本代码和数据共享解决方案。”如果无服务器快递是成功的，不仅你会赢得你的项目，也将 Vendia。该公司表示，目标是“为开发人员提供一个简单、可扩展的平台，满足他们的需求，然后帮助他们获得云所能提供的最佳功能……而无需不必要的再培训、重写或移植练习。”

为了帮助实现这一点，无服务器快递的原作者[布雷特·安德鲁斯](https://twitter.com/AWSbrett)加入了 Vendia。该计划旨在通过在 Vendia 的存储库中永久支持代码和数据，进一步帮助客户有效地共享代码和数据。

无论如何，这都不是一种尝试，一种尝试。正如安德鲁斯和瓦格纳所写的:“作为最初的项目发起人，并在项目最初作者的指导下，AWS 相信我们是这个项目的深思熟虑和积极主动的管理者。我们将继续每月与 AWS 会面，以收集客户反馈，并了解即将发布的 AWS 无服务器版本，以便我们成为发布合作伙伴，并在无服务器快递中提供第一天支持。”

如果你已经是一个快乐的无服务器快速用户，你不需要做一件好事。为了您的方便，Vendia 发布了[AWS-server less-express v 3 . 4 . 0](https://www.npmjs.com/package/aws-serverless-express)。这使用了对新官方包的直接依赖。因此，当你升级到[AWS-server less-express @ 3 . 4 . 0](https://www.npmjs.com/package/aws-serverless-express)时，你将获得所有下游补丁和功能，而无需更新你的代码。就是这样。仅此而已。

这样，您就可以在 AWS Lambda 和 Amazon API Gateway 之上，使用现有的 Node.js 应用程序框架运行无服务器应用程序和 REST APIs。

展望未来，Vendia 将于 2021 年 1 月发布无服务器 Express v4。其新功能将包括:

1.  支持除 API Gateway 之外的事件源，如 ALB、Lambda Edge、HTTP API，并可以轻松地为与 Lambda 集成的其他服务提供您自己的自定义事件源映射。
2.  改进了日志记录和调试支持。
3.  可扩展性更强，使用更简单，开发人员体验得到改善。
4.  默认情况下使用[承诺解决方案](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/resolve)。
5.  升级到 Node.js 10(兼容 Node.js 12+)。
6.  使得使用自定义域名更加容易。
7.  改进了文档和示例。
8.  支持多个标题值。

不熟悉无服务器 Express，不知道如何开始？只需按照 GitHub 上的[无服务器快速基本启动程序，您将在五分钟内启动并运行。如果你已经是 Lambda 用户，这是显而易见的。尝试一下这个新版本和即将推出的无服务器 Express 版本。你会很高兴你做了。](https://github.com/vendia/serverless-express/tree/master/examples/basic-starter)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>