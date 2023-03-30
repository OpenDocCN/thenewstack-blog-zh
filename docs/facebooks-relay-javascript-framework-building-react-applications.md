# 脸书的接力:一个给 React 更大范围的 JavaScript 框架

> 原文：<https://thenewstack.io/facebooks-relay-javascript-framework-building-react-applications/>

期待已久的 React 的 [Relay JavaScript UI 框架](https://facebook.github.io/relay/)近日问世。如果你没有听说过，React 是脸书发布的一个 JavaScript 库，作为一种创建用户界面的新方法。虽然 Angular 和 Ember 等流行的 JavaScript 框架在其设计中采用了更“包含电池”的方法——包括从 HTTP 库到 UI 路由器的一切——但 React 的方法显然更简单。Relay 是一个 JavaScript 框架，用于构建数据驱动的 React 应用程序。

用[官方 React 网站](http://facebook.github.io/react/)的话来说，它“只是 UI”，“很多人把 React 当作 MVC(模型-视图-控制器)中的 V”

> 尽管 React 的极简性在许多方面令人耳目一新，但它带来了一些没有答案的问题，许多开发人员不确定如何使用 React 构建网站。

脸书的流动建筑是一种方法。然而，尽管 Flux 为如何使用 React 设计用户界面提供了一些指导，但它并没有回答所有问题。

就像 React 一样，Flux 并不渴望成为一个框架。它是一种设计模式，而不是正式的框架。脸书发布的 Flux 代码包含一个简单的集中式调度程序，仅此而已。用户有责任让调度程序正确地实现一个 Flux 架构。仍然存在大量没有预定义的最佳实践或模式的架构问题。

然而，随着 Relay 的发布，React 成为一个成熟的框架，具有更广泛的范围。React 和 Relay 协同工作，提供了一个更加开箱即用的解决方案。不管你的背景如何——无论是使用 RESTful 后端还是 Flux React 应用程序——Relay 都有很多变化，需要一定程度的适应。

## 通量呢？

接力借用了 Flux 的一些概念，但也改变了很多东西。

> 继电器被描述为通量的“进化”和通量的简化。

简化的一个方法是在商店领域。在 Flux 应用程序中，与传统的 MVC 模型不同，Flux 有着某种程度上相关的数据存储概念。对于每个起反应组件，通常有该组件的对应存储。使用 Relay，所有数据都有一个集中的存储，而不是每个组件都有自己对应的存储。

此外，Flux 通过一种称为“动作”的结构触发数据变化，而 Relay 则使用一种称为“突变”的东西。突变比动作更强大，因为它们也管理服务器上的数据。

这将我们带到下一个重点:中继应用程序与一个 [GraphQL](https://facebook.github.io/react/blog/2015/05/01/graphql-introduction.html) 端点而不是 REST 端点对话。

## 使 GraphQL 成为一个需求

与许多前端框架不同，Relay 不是后端不可知的；您需要为您的中继应用程序实现一个 GraphQL 端点。虽然 React 可以很容易地放到任何项目中进行试验，但 Relay 的情况就不一样了。中继应用程序有三个必须满足的前期要求:一个 GraphQL 模式、一个 GraphQL 服务器和中继本身。

### GraphQL 模式

虽然我们在上一篇文章中讨论了查询 [GraphQL，但是还没有任何关于如何定义查询将运行的模式的规范。从那以后，脸书提供了 GraphQL](https://thenewstack.io/react-with-graphql-for-architecting-apps/) 的 [JavaScript 参考实现，我们可以用它来定义模式。然而，你也可以自己选择一种语言。例如，一个社区成员在 Ruby](https://github.com/graphql/graphql-js) 中提供了一个 [GraphQL 的实现。](https://github.com/rmosolgo/graphql-ruby)

### GraphQL 服务器

下一个主要组件是 GraphQL 服务器。这个服务器将用于加载和连接 GraphQL 模式。脸书已经提供了一个 [Express.js 参考实现，](https://github.com/graphql/express-graphql)但是同样，你可以自由地使用你喜欢的栈来实现它。

### 继电器

最后一个组件是继电器本身。在高层次上，Relay 将现有组件包装在中继组件中，然后使用这些组件的中继版本。然而，这并不是百分之百的神奇，在创建中继包装器时，您必须提供一些额外的代码。具体来说，您将提供该组件所需的 GraphQL 数据查询。这遵循了查询及其相应视图的协同定位的中继设计原则。

虽然有些人可能会说这违反了适当的关注点分离，但事实并非如此。给定组件或视图所需的数据查询是其不可或缺的一部分，将其提取出来与其说是关注点的分离，不如说是技术的分离。这在精神上类似于 React 不相信视图和控制器的分离是有意义的，而是将它们一起存放在 JSX 文件中。

> 这种共存的另一个好处是它允许 Relay 为我们做大量的查询优化。

如果多个查询需要相同的数据，Relay 将为您有效地批处理和聚合这些查询。与典型的 REST 风格的应用程序相比，这有可能获得巨大的成功。例如，如果您从站点上的多个位置提取端点信息，那么您通常会为需要这些数据的每个位置发送一个 GET 请求。相反，您可以尝试自己聚集这些，但是这将使应用程序更加难以推理。相比之下，中继方法允许我们拥有简单的概念模型，在每个需要的地方声明我们的数据需求，但是具有将所有查询放在一个位置的性能优势。这是一个相当大的双赢。

## 摘要

尽管 React 提出了激进的改变，但它迄今为止相当成功，并迅速赢得了开发人员的认可。虽然 MVC 长期以来被誉为唯一的做事方式，React 已经成功地挑战了这一假设。有了 GraphQL 和 Relay，脸书现在开始质疑当前 RESTful API 后端的黄金标准。也许在不久的将来，GraqhQL 端点会比 RESTful 端点更受青睐。看看 Relay 提出的新想法是否会像 React 带给我们的一样成功，这将是非常有趣的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>