# 阿波罗通过合同大规模生产 GraphQL，新的 Rust 路由器

> 原文：<https://thenewstack.io/apollo-does-graphql-at-scale-via-contracts-new-rust-router/>

GraphQL 工具公司 [Apollo](https://www.apollographql.com/) 在今年的年度 [GraphQL 峰会](https://summit.graphql.com/)上宣布了许多围绕其联合方法的新特性和产品。Apollo first [在 2019 年推出了 Federation](https://www.apollographql.com/blog/announcement/apollo-federation-f260cf525d21/) ，让组织能够拥有一个用于所有数据的单一图表，同时仍然允许团队在该图表中保持独立，“而不会遇到整体的陷阱”

现在，该公司推出了 Federation 2，阿波罗联合创始人兼首席技术官[马特·德贝加利斯](https://www.linkedin.com/in/debergalis)称之为“对 Federation 的重大更新”，这是与网飞共同设计的，同时还有一个新功能，称为[合同](https://www.apollographql.com/docs/studio/contracts/)和带有[阿波罗路由器](https://www.apollographql.com/blog/announcement/backend/apollo-router-our-graphql-federation-runtime-in-rust/)的 Federation 运行时的“全新实现”。DeBergalis 说，这些都有助于公司规模化运营 GraphQL。

“我们已经看到图表滑稽地快速增长，特别是在大公司，所以我们的重点是如何实现规模？”德贝加利斯说。“图表的真实故事是关于可组合性的。这是一种允许多个团队在一个通用 API 上协作的架构，它将对敏捷性和速度产生与云原生在堆栈后端产生的变革性影响相同的影响，并对堆栈前端的反应和设计系统等产生变革性影响。”

## **图的子集的合同**

虽然 Federation 致力于为组织提供这个大型的统一图形，但 Contracts 帮助他们根据各种因素将图形的各个部分分离出来。

“合同是这样一个问题的答案:我如何为我的整个组织建立一个统一的图表？我如何在不同的环境中使用不同的子集或片段？”DeBergalis 说，并以授权集成合作伙伴访问的 API 为例。“你需要一个故事，告诉我如何不拿走我的整个图表，而只拿走我想要的一部分，以授予合作伙伴？”

契约允许图形团队只向合作伙伴开发人员公开图形的特定部分，限制内部访问，并且通常创建一种形式的访问管理，同时仍然允许单个、统一的图形。契约还允许访问仅限于敏感信息和图表的实验部分。DeBergalis 还指出，考虑到移动应用程序必需的生命周期承诺，移动应用程序开发是合同的完美用例。

“移动的一个有趣之处在于，例如，如果你将一个应用程序发布到 Play Store，你就不能收回它，也不一定能改变它。它永远在那里。因此，就生命周期管理和准确理解移动应用程序如何使用图表的能力而言，团队的负担可能比 web 开发更重要。因此我们发现，拥有大型图表的公司不一定希望移动开发者使用图表中的所有内容，”DeBergalis 解释道。“公司使用合同作为一种方式，从本质上围绕图表中现在适合或支持移动使用的部分画一条线，以区别于图表的其他部分。”

## **生锈的路由器**

GraphQL 规模化的另一个方面是快速运行的能力，而 Apollo 的新 Apollo 路由器正好提供了这一点。该路由器完全是在 Rust 中构建的，取代了之前用于阿波罗网关的 JavaScript 和 Node.js，该公司在一篇博客文章中写道，“每个操作增加的延迟不到 10ms，它可以处理 8 倍于 JavaScript 阿波罗网关的负载。”德贝加利斯解释说，选择生锈是显而易见的，因为以前你必须在速度和安全之间做出选择，而现在“我们再也不用选择了。”

虽然延迟对规模很重要，但 DeBergalis 也指出了能源效率是迁移到 Rust 的一个因素，该公司表示[将能源效率提高了 4 倍](https://haslab.github.io/SAFER/scp21.pdf)。

“如果你考虑一下沃尔玛的规模，或者许多其他将面向消费者的核心体验放到图表上的公司，你可以节省的每个 CPU 周期都是很重要的，”他说。“Rust 的多并发模型和管理内存的方式的优势之一是，无需垃圾收集和所有这些后台处理，您可以获得惊人的吞吐量。我们的基准测试显示，单台机器上有超过 10，000 个并发请求，所有延迟都远远低于 JavaScript 或 Node。在我们看来，这正是语言的力量所在。”

## **每个人都有一张图表**

阿波罗路由器和阿波罗联盟 2 都是在[弹性许可](https://www.elastic.co/licensing/elastic-license)下[发布的](https://www.apollographql.com/blog/announcement/moving-apollo-federation-2-to-the-elastic-license-v2/)，而不是该公司之前使用的麻省理工学院许可。虽然弹性许可证不是开源倡议批准的许可证，但 DeBergalis 将其描述为“许可的”，并提供了开放与货币化能力的正确平衡，而不用担心该产品会由另一家公司作为服务提供。

“我的观点是，我们提供世界级图表工具，满足所有这些转向图表的公司日益复杂的需求的最佳工具是拥有一个繁荣的商业模式，增加图表的采用可以转化为增加对有效图表技术的投资，”他说。“我认为开发人员越来越了解，如果我要在一项技术上下注，我的评估从‘我相信长期吗？’因为最糟糕的事情是选择一项技术，然后发现它投资不足，它枯萎并死亡。"

枯萎和死亡当然不是德贝加利斯的计划——恰恰相反。他说，他认为未来每个公司都有一个 graph，那些计划过渡到 GraphQL 的公司将超过那些没有计划的公司。为此，Apollo 正在投资 GraphQL 教育，最近推出了 GraphQL 在线学习平台。

“这里有一个关于如何将图表带给合作伙伴和其他外部团队的路线图，”DeBergalis 说。“随着时间的推移，我们真的很高兴能够建立这种关系。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>