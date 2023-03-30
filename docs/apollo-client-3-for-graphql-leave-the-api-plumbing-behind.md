# Apollo Client 3 for GraphQL:抛弃 API 管道

> 原文：<https://thenewstack.io/apollo-client-3-for-graphql-leave-the-api-plumbing-behind/>

GraphQL 工具提供商 [Apollo](https://www.apollographql.com/) 已经[发布了 Apollo Client 3.0](https://www.apollographql.com/blog/announcing-the-release-of-apollo-client-3-0/?mc_cid=e593721cc7&mc_eid=4e4f820c6a) ，它声称这是一年工作的高潮，合并了 55 个测试版，14 个发布候选版，以及数百个已解决的问题和合并的拉请求。Apollo Client 是一个 JavaScript 的状态管理库，它使开发人员能够使用 [GraphQL](https://graphql.org/) 更容易地管理本地和远程数据。

GraphQL 的标准推介通常提供了 REST APIs 和 GraphQL 之间的全面比较，其中后者提供了进行定制查询并获得特定结果的能力，而不是简单地查询一个 API 并获得所有数据。价值主张很简单:GraphQL 为开发人员提供了更高效、可定制的客户端 API 体验，但 Apollo 的首席技术官兼联合创始人 Matt DeBergalis 解释说，Apollo Client 3.0 通过处理他们原本必须在客户端编写的所有粘合代码，真正简化了开发人员的体验。

“在许多方面，React 为用户界面所做的事情，Docker 和 Kubernetes 为在云中运行服务所做的事情，就是 Apollo 为您的 API 所做的事情:它为它带来了结构，以便您可以专注于与您的应用程序和数据有关的细节，并将管道和复杂性留给整个系统，”DeBergalis 说。“应用程序开发人员正在采用 GraphQL，因为它使他们能够摆脱编写大量样板文件和管道代码来将他们拥有的数据连接到他们试图构建的用户界面的工作。”

据估计，Apollo Client 占“市场上 GraphQL 使用量的 95%”，DeBergalis 将 Apollo Client 称为“如何将 web 上的用户界面连接到 GraphQL APIs 的行业标准”，并解释说，虽然开发人员最初采用 GraphQL 是为了上述好处，但他们坚持使用它是因为 Apollo 为他们处理的那些细节中的魔鬼。随着 Apollo Client 3.0 的发布，其中一些细节得到了解决，例如分页帮助、改进的[本地状态管理](https://www.apollographql.com/docs/react/local-state/local-state-management/)，以及[反应变量](https://www.apollographql.com/docs/react/local-state/reactive-variables/)的引入。

“Apollo Client 的工作就是让你屏幕上的所有数据保持最新和同步。如果你改变了屏幕的一部分，Apollo Client 会在幕后确保与之相关的所有其他数据都被刷新。“如果你想到你必须分页的长列表，如果你想到实时界面，当你使用应用程序时信息会改变，所有这些类型的模式都是每个应用程序开发团队每天用代码手工构建的，而 Apollo Client 3.0 就是将所有这些烘焙到一个库中，以便开发人员可以使用现成的，只需键入他们希望应用程序如何运行的描述。”

Apollo Client 3.0 引入了经过全面改进的缓存，旨在提高灵活性和性能，增加了垃圾收集等新功能、新的缓存策略 API 以及存储规范化和非规范化数据的能力。与此同时，反应式变量通过在读取时注册一个依赖项来提供这种后台更新，以后每当值更新时触发一次重新读取。

“反应变量都是关于状态管理的。这是一种编程模式，也是一种能够真正简明地描述某个数据可能会发生变化的方式。当数据改变时，我不想写代码来更新我的屏幕。我不知道这些数据什么时候会改变。“这是一种让团队分离工作的模式，因此负责 UI 一部分的团队可以简单地描述，‘有一个我关心的数据’，当它发生变化时，我希望能够更新我在 UI 中实现的这个部分，而我不必了解我的部分如何适应其他团队负责的用户体验的所有其他部分。”

展望未来，DeBergalis 表示，该公司将在即将举行的 GraphQL 峰会上重点关注和谈论联邦。去年，[已经为联合会推出了](https://thenewstack.io/apollo-introduces-a-graphql-platform-for-shared-data-graphs/)产品，[阿波罗联合会](https://blog.apollographql.com/apollo-federation-f260cf525d21)，但它专注于跨团队的联合会，而不是公司。阿波罗下一步的目标是将同样的想法推广到不同的公司。

“例如，在 Priceline，他们有一个团队为航班和航班搜索开发 GraphQL API，另一个团队为租车搜索开发 GraphQL API。事实证明，在航班搜索过程的最后，当有人购买机票时，你想卖给他们一辆租赁汽车，但将这两者结合起来很有挑战性。因此，他们采用了联邦作为一种方式，能够只编写他们想要的明显功能，其中有一部分应用程序来自这两个数据集，”DeBergalis 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>