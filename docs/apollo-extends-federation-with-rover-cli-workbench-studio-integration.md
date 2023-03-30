# Apollo 扩展了与 Rover CLI、Workbench 和 Studio 集成的联盟

> 原文：<https://thenewstack.io/apollo-extends-federation-with-rover-cli-workbench-studio-integration/>

在本周举行的 [GraphQL 峰会](https://summit.graphql.com/)之前，GraphQL 工具提供商 [Apollo](https://www.apollographql.com/) 发布了对其 [Apollo Federation](https://blog.apollographql.com/apollo-federation-f260cf525d21) 工具的一系列更新，该工具于 2019 年首次推出，此后成为通过应用编程接口(API)打破单一架构的公认模式。

本周的发布包括将 federation 集成到 Apollo Studio 中，这是一个更新的 Apollo Workbench Visual Studio 代码扩展，并引入了 [Rover 命令行界面(CLI)](https://github.com/apollographql/rover) ，以便更轻松地将 [GraphQL](https://graphql.org/) 设计和测试引入企业持续集成和持续交付(CI/CD)管道。

GraphQL 查询语言颠覆了传统的 REST API 模式，它能够请求细粒度的响应，而不是一连串的信息。但是转向 GraphQL 的企业发现，随着时间的推移，他们面临着一个类似的难题:他们的 GraphQL 部署变得难以管理。网飞最近向[提供了自己对这个故事的讲述](https://www.youtube.com/watch?v=QrEOvHdH2Cg)，讲述了他们的图表是如何变得如此之大，以至于它的 API 团队的任何一个成员都不知道。作为回应，该公司的工程师使用 GraphQL Federation 将他们的图表分成几个部分，其中各个团队拥有自己的图表部分，然后由单个统一的 API 网关呈现。

[https://www.youtube.com/embed/QrEOvHdH2Cg?feature=oembed](https://www.youtube.com/embed/QrEOvHdH2Cg?feature=oembed)

视频

Apollo 首席技术官兼联合创始人 Matt DeBergalis 将 GraphQL Federation 与许多其他现代技术进行了比较，比较其将整体架构分解为可组合部分的能力，从而实现团队级别的敏捷性。

“联合是如何有机地做到这一点的答案，每个团队如何在拼图中找到自己的一块来解决自己的需求，但以一种共同组成结构化整体的方式，类似于 React 如何让多个团队构建一个 UI 的各个部分，这些部分在屏幕上优雅地共存，或者类似于 Kubernetes 如何允许多个团队在一个公共环境中运行自己的微服务，而不会踩到彼此的脚趾，”DeBergalis 解释说。

“我认为企业过去几年的故事是可组合的。联邦图是第一个可组合的 API。它让多个团队各自专注于自己的工作，但也让他们能够利用彼此的工作，并带来比各部分之和更大的成就。”

DeBergalis 解释说，从将联邦集成到 Apollo Studio 开始，本周的发布旨在帮助企业采用联邦，并“绘制从他们拥有的 API 到公共数据图的增量路径”。Apollo Studio 通过帮助团队理解谁拥有图的哪一部分并促进他们之间的交流来做到这一点。Apollo Studio 还将帮助可视化从图的不同部分提取数据的查询将如何工作，特别是在响应图的变化时。

类似地，Apollo Workbench 将同样的功能直接引入到 VS 代码中，允许开发人员对图形建模，并验证它如何与其他团队所做的工作相关联。同样，联合的思想是将 API 所有权分解成更小的、可组合的部分，这些工具旨在促进这一点。

“我们推荐的模型几乎是一种控制混沌的方法。你不想要瀑布式的方法，你想要一种每个团队都可以快速移动的方法，这种方法随着时间的推移会导致真正健康的融合。“我们从几乎每一个与我们合作的客户那里听到的事情之一是，围绕图形设计的最佳实践对团队进行教育是多么重要，以及如何在公司中实践反映这一点的中央图形功能，因此这些工具正是为了做到这一点而设计的。”

最后，Rover CLI 通过 Rust 内置的一个轻量级二进制文件，将模式更改的测试、发布和管理引入 CI/CD 管道。虽然让 GraphQL 成为 CI/CD 管道的一部分可能并不新鲜，但 DeBergalis 解释说，Rover 的重要性在于它能够在企业中经常出现的众多环境中运行，这些环境通常混合了传统和现代基础架构。DeBergalis 解释说，总的来说，正是这种灵活性从整体上定义了联邦，给 GraphQL 带来了在不同环境中运行的能力，而不是迫使大型异构企业将所有东西都塞进一个单一的同质整体中。

“你永远不会推出一个单片 GraphQL 服务器来处理整个企业的需求。那完全是胡说八道。你需要的是一种声明式的方法，一种模块化的方法。“这就是联合，其中图形的每个部分都以自己的语言、自己的 DevOps 基础架构单独实施，所有这些都是分离的，然后联合就是粘合剂。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>