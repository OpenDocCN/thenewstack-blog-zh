# Stackery 无服务器平台增加了 JAMstack 支持

> 原文：<https://thenewstack.io/stackery-serverless-platform-adds-jamstack-support/>

无服务器开发平台提供商 [Stackery](https://www.stackery.io/) 推出了对 [JAMstack](https://thenewstack.io/the-sweetness-of-jamstack-javascript-apis-and-markup/) web 开发模式的支持，该模式主要依靠 JavaScript、API 和 Markdown (JAM)通过内容交付网络(cdn)以更快的速度交付可扩展的 web 内容。

从技术上讲，没有什么严格限制开发人员使用无服务器函数来代替 JavaScript。对于 Stackery 来说，这里的无服务器概念不仅包括功能即服务的概念，还包括通过 API 将托管服务组合在一起的能力，就像 JAMstack 一样。在这种情况下，这些功能只是可以通过 HTTP API 访问的另一个托管服务，并且在精神上与 JAMstack 方法保持一致——开发人员没有后端、没有 web 服务器、没有传统的[灯堆栈](https://en.wikipedia.org/wiki/LAMP_%28software_bundle%29)需要管理。

在一篇介绍新功能的博客文章中，Stackery 的工程副总裁 Ryan Coleman 指出“这种风格的 web 开发非常适合无服务器架构”，他在与新 Stack 的一次采访中详细阐述了这一点。

“我们看到人们为了无服务器提供的所有这些速度、安全性和按消费付费的好处而转向无服务器，我看到人们出于同样的原因转向 JAMstack。科尔曼说:“就如何构建这些应用程序的架构而言，这是一种非常值得称赞的心态。“我认为这个空间，这种无服务器风格的托管服务和 JAMstack 风格的 web 架构的融合，是一个巨大的工具，可以让企业戏剧性地重新思考，‘我们如何赢得这场比赛？我们将如何保护我们客户的数据，提供良好的用户体验，以一种吸引我们的开发人员并让他们比以往任何时候都更有生产力的方式做到这一点？我打赌这个十字路口就是它要去的地方。"

JAMstack 模式的一些基本方面包括客户机和服务器的分离，以及在运行时和交付之前预先构建内容。Stackery 的无服务器方法，在 Amazon Web 服务之上提供了一个抽象层，使得服务更容易连接和作为独立的服务处理。科尔曼说，当他们看到一些用户倾向于将 AWS 的后端服务与其 CDN [CloudFront](https://aws.amazon.com/cloudfront/) 相结合时，他们开始想知道这是怎么回事。

“这些客户正在建造 JAMstacks。他们并不是真的这么叫他们，但他们就是这么做的，”科尔曼说。“他们正在构建这些丰富的网络体验，但他们在 Stackery 中表达了大多数硬件基础设施，然后他们试图链接到 Netlify 或这些其他服务，这些服务将完成构建他们的网络应用程序的最后一英里，将其交付给 CDN，并可能将其连接到一些 lambda 功能。”

通过这次更新，Stackery 帮助将用户的各种 AWS 服务直接集成到他们的 CI/CD 管道中，然后帮助与 static-site generator for build 集成。对于对测试 JAMstack 支持感兴趣的用户，Stackery 已经创建了一个[教程](https://docs.stackery.io/docs/tutorials/jamstack-ghostgatsby/)，它将“指导你使用无服务器方法部署和托管一个带有 [Gatsby](https://www.gatsbyjs.org/) 前端的 [Ghost CMS](https://ghost.org/) 的过程。”Stackery 对 JAMstack 的支持包括添加了[网站资源](https://docs.stackery.io/docs/api/nodes/Website/)，这有助于简化像 Gatsby 这样的静态站点生成器的构建过程，并将其添加到其虚拟白板中。

目前，正如 Coleman 在他的博客文章中指出的，使用 JAMstack 方法，“静态应用程序不断构建并交付到 CDN 源，就像每次提交时的 S3 桶一样。”虽然这里的自动化是可取的，但他认为这是下一级创新的起点，这些静态站点生成器提供了一种减少不可避免的长构建时间的方法。

“当谈到每一个单独的框架时，您如何能够构建一个企业 web 应用程序，获得我们刚刚谈到的所有好处，而又不会有很长的构建时间？”科尔曼说。“这种架构方法的一个很大的缺点是，每次你对你的网站做出改变，这些框架中的每一个都要从头开始经历整个过程；它获取您的源代码，与所有这些第三方 API 进行交互，然后构建每一个网页并交付这些内容。在这个领域有很多工作正在进行，其中每个框架都在构建工具，以了解从后端角度来看哪些内容发生了变化，然后为我们这样的平台提供使用这些信息的能力，以加快构建周期。”

亚马逊网络服务是新堆栈的赞助商。

来自 Pixabay 的 mac231 的特征图像

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>