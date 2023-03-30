# Amazon Web Services 全栈无服务器的兴起

> 原文：<https://thenewstack.io/theres-a-service-for-that-amazon-web-services-and-serverless-computing/>

[](https://twitter.com/ricmac)

 [理查德·麦克马努斯

理查德是《新书库》的高级编辑，每周撰写一篇关于云原生互联网未来发展的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) [](https://twitter.com/ricmac)

本周，我与亚马逊网络服务公司(AWS)的高级开发人员 Nader Dabit 谈论了无服务器技术的现状。Dabit 还有一本新书，由 O'Reilly Media 出版，书名为“[全栈无服务器](https://www.amazon.com/Full-Stack-Serverless-Application-Development/dp/1492059897)”这是一个使用 React、AWS、GraphQL 和 AWS Amplify 构建全栈应用的指南。

AWS 是无服务器的主要支持者，大约从 2015 年开始通过其 [Lambda 服务](https://aws.amazon.com/lambda/)推广该术语。从那时起，Dabit 已经成为无服务器领域的重要声音，拥有超过 39，000 名 Twitter 追随者。

无服务器可能是一个加载的术语，但基本上它意味着抽象掉后端，这样开发者可以专注于前端。当我问 Dabit 如何定义无服务器时，他引用了伯克利大学 2019 年 2 月的一篇关于无服务器计算的论文 (PDF)，其中用这个等式进行了总结:无服务器计算= FaaS[功能即服务]+BaaS[后端即服务]。

然而，Dabit 更愿意将无服务器视为“一种开发理念”

“云计算的准入门槛真的很高，”他解释道，“我认为，由于云计算提供的所有好处，前端开发人员或对云计算不感兴趣的开发人员都渴望开始使用它。”

无服务器趋势实际上是为开发人员提供构建云应用所需的工具、库和 API。这减轻了他们的后端负担。

虽然 serverless 旨在帮助前端开发者构建云应用，但我想知道在 2020 年成为“全栈开发者”有多普遍。这些开发人员是后端和前端的专家。所以我问 Dabit 全栈开发者的角色在过去十年左右是如何演变的。

“当 Rails(Ruby on Rails)真正流行的时候，”他回答说，意思是大约 10 到 15 年前，“新一代的全栈开发人员有很大的吸引力来构建前端和后端。我认为，在过去 10 年左右的时间里，随着前端变得越来越复杂——随着[单页面应用程序](https://en.wikipedia.org/wiki/Single-page_application)和所有不同的工具[用于]构建单页面应用程序——……然后前端开始变得太复杂，人们无法深入理解这两者。”

这导致了当前的时代，正如 Dabit 所说，全栈开发人员是“局外人”。这就是无服务器发挥作用的地方。它允许前端开发人员构建“全栈”应用程序，因为像 AWS Lambda 这样的无服务器平台会自动管理后端。

根据 Dabit 的说法，只要前端开发人员了解如何使用 API，并熟悉命令行工作，那么他们就可以成为等同于全栈开发人员的人——至少就他们现在可以构建的应用类型而言。

“现在有了云提供商提供的所有这些新的抽象，前端开发人员成为全栈开发人员变得更加容易，而不必花费大量时间专门研究整个栈。”

## AWS 放大器及其与 Netlify 的比较

Dabit 在 AWS 的部分角色是与 [AWS Amplify](https://aws.amazon.com/amplify/) 的开发者关系，这是一个面向 AWS 上的移动和网络应用的 JavaScript 开发框架和网络托管服务。这是 AWS 无服务器军械库中的一个关键工具，因为它使前端开发人员能够直接开始构建云应用。正如 Dabit 在他的书中所写的，Amplify CLI[命令行界面]“允许开发人员直接从他们的前端环境创建、配置、更新和删除云服务。”

Amplify 与我最近分析的 JAMstack 公司有些相似，因为它提供了一个 JavaScript 开发框架([如 Gatsby](https://thenewstack.io/gatsbys-content-mesh-and-its-role-in-jamstack/) 和 [Vercel](https://thenewstack.io/vercels-frontend-and-the-rise-of-the-hybrid-developer/) )以及托管部分([如 Netlify](https://thenewstack.io/why-netlify-is-tech-agnostic-and-its-role-in-jamstack-development/) )。Dabit 告诉我，Amplify 可以与所有现有的框架一起工作，如 React、Gatsby、Vercel 和其他框架，如 Vue 和 Angular。

Amplify 似乎直接与 JAMstack 公司竞争的地方是 Netlify。该控制台是 Amplify 工具集的一部分，被描述为“一个静态 web 托管服务”，它提供了“一个用于构建和部署静态 web 应用程序的简单 CI/CD 工作流”。这同样可以描述 Netlify 所做的事情(尽管两者之间有一些不同之处)。

Amplify 和 Netlify 也都支持无服务器功能，无服务器功能是执行特定任务的编程单元，托管在托管服务环境中。它们通常由事件触发。 [AWS Lambda](https://aws.amazon.com/lambda/) 是亚马逊以这种方式运行功能的服务。事实上，用 Berkeley 的术语来说，Lambda 是一个 FaaS(功能即服务)平台。Amplify 工具集是 Lambda 的补充，如构建在 AWS 上的示例无服务器 web 应用程序图所示:

[Netlify Functions](https://www.netlify.com/products/functions/) 的功能实际上依赖于 AWS Lambda，但它声称与 AWS 相比，它使无服务器功能“无痛”。Netlify Functions 的标语强调了这一信息:“由 AWS Lambda 提供支持。被 Netlify 简化了。”

## API 是无服务器的最佳用例

我问 Dabit AWS 客户倾向于用 Amplify 和 Lambda 这样的产品做什么？

“我会说 API 是无服务器的头号用例，”他说，“因为你可以使用 Lambda 与 AWS 中的任何其他服务进行对话。所以你可以用λ与数据库对话，你可以用λ与你的认证服务对话，你可以用λ做几乎任何事情。”

说到 API，这就是 GraphQL 进入无服务器模式的地方。GraphQL 是 API 的开源数据查询和操作语言；有些人把它比作 SQL，但是是针对 API 而不是数据库。由于 Dabit 的书的副标题中提到了这个术语，所以我问他这个术语对于现在的云应用程序有多重要。

“我们看到的是，人们正在用 GraphQL API 取代传统的 API 网关，”他回答道。“这是一个非常好的使用案例，因为当你使用微服务架构并将所有这些端点拼凑在一起时，很多时候你会在 API 创建和 API 文档等方面出现不一致的情况。”

和 React JavaScript 库一样，GraphQL 也是在 2012-15 年期间从脸书出来的。由于 graph QL API[是按照类型和字段](https://graphql.org/)来组织的，而不是按照端点来组织的，这使得跟踪特定应用程序中的多个 API 变得更加容易。

“GraphQL 提供的是你的数据的统一图形，以及你可以与之交互的所有方式，”Dabit 说。“因此，只要涉及到数据层，任何新的开发人员都可以进入您的应用程序，查看您的 GraphQL 模式，了解周围发生的一切。”

Dabit 在 AWS 看到的是客户创建他们的 GraphQL API，然后“在他们所有的端点上迁移”

但是等等……有一种服务可以做到这一点。除了许多其他云服务，AWS 还为 GraphQL 提供了一个托管服务，名为 [AppSync](https://aws.amazon.com/graphql/) 。

事实上，在与 Dabit 交谈并浏览了他的新书后，我意识到尽管 AWS 确实让云时代的开发者生活变得更加轻松，但仍有许多事情需要考虑。无服务器可能意味着将后端抽象化，但是每年越来越多的东西堆积在前端。

也许很少处理服务器，但是开发者现在有许多 T2 服务 T3 要处理。这带来了一系列的复杂性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>