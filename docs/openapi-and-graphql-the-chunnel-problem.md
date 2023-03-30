# OpenAPI 和 GraphQL:通道问题

> 原文：<https://thenewstack.io/openapi-and-graphql-the-chunnel-problem/>

[](https://www.linkedin.com/in/anantjhingran)

 [阿南特·金兰

阿南特是 StepZen 的创始人兼首席执行官，这是一家初创公司，致力于简化开发人员获取数据的方式，以增强数字体验。Anant 的职业生涯跨越了 IBM Fellow、IBM 信息管理部门的 CTO、Apigee 的 CTO 和 Google Cloud 的产品负责人，他的职业生涯一直处于数据库、机器学习和 API 创新的前沿。在 StepZen，Anant 正在享受创建一家公司，将他对这些技术的热爱结合在一起，以简化、加速和扩展前端开发。](https://www.linkedin.com/in/anantjhingran) [](https://www.linkedin.com/in/anantjhingran)

英吉利海峡隧道是连接英国和法国的工程奇迹。火车，以及火车上的汽车，在英国是在左边行驶，在法国是在右边行驶。在多佛海峡中间的某个地方，惯用手无缝地改变了。在 IT 系统中，两个不同视角之间的这种桥梁需要经常出现，有时做得很好，像隧道，有时做得不太好。在这篇文章中，我们将探索前端和后端系统之间的桥梁。

前端——您的移动应用程序、网站等。—希望处理对用户有意义的数据和概念。例如，他们可能希望在电子商务应用程序上提供客户订单的交付状态或客户更新的购物车。另一方面，后端系统通常公开反映后端数据形状的 API。例如，它们存储和处理在业务和技术环境中有意义的数据——规范化的表、REST 接口等等。

这两者就像英吉利海峡的两面。前端越来越希望以 GraphQL 的形式处理数据。因此，应用程序使用 GraphQL 进行的查询必须与需要 SQL 和 REST 接口的数据和操作联系起来。所以更具体的通道问题是将 GraphQL 翻译成 SQL 和 REST 的子部分。出于这个博客的目的，我们将关注休息。

## **你往哪个方向旅行？**

假设英吉利海峡的英语端代表前端，后端系统是法语端。

如果你从英语开始，你可能会:

```
type  Query  {
  weather(city:  String!):  WeatherReport
}

type  WeatherReport  {
  temperature:  Float
  description:  String
}

```

但是后端的天气 API 可能会使用`lat`、`lon`而不是`city`，可能会返回未来 10 天的天气预报，可能会生成字段显示`temp`而不是`temperature`，可能会将`description`编码为两个字母的代码，等等。因此对后端的调用和来自后端的响应必须符合前端(英语)视图。

然而，如果您从法国方面开始，您可能会得到相同的 JSON 响应并创建一个类似于
的 GraphQL API

```
type  Query  {
  OneAPI25ByLatLon(lat:  Float!,  lon:  Float!):  OneAPI25ByLatLonResponse
}
type  OneAPI25ByLatLonResponse  {
  coord:  CoordResponse
  weather:  WeatherResponse
  base:  String
  main:  MainResponse
  ...
}
...
type  Main  {
  temperature:  Float
  ...
}

```

通过这种方式，你获得了非常高的后端保真度，但你也获得了后端产生的所有细节。任何自动生成都会强制生成类型和查询的名称。

如您所见，前端优先(英语)视图和后端优先(法语)视图都不完美。前者剔除了大量有用信息，需要人工或半人工作图。后者向前端开发人员提供大量接口，通常是复杂的自动生成的名称。你想要的是一个折中的方法。

## **海底隧道的其他核心问题**

虽然我们不会深入讨论细节，但还有其他问题需要解决:

*   中间可能没办法见面。或许双方根本不可调和。例如，返回产品的所有订单以便于召回的前端 API 可能需要与“订单的所有产品”相反的后端 API，这样的 API 可能不存在。
*   铁轨可能会很慢。虽然这可能有许多原因，但一个常见的原因是 GraphQL 允许通过企业数据的递归路径。因此，通常，支持它的后端最终会被请求淹没。(一个 GraphQL 请求可能会为不同的后端生成 500 个调用！)
*   两边的仪表可能不同。(我是不是把英吉利海峡隧道的比喻带得太远了？)这是根本性的差距。GraphQL 是强类型的，但是底层的 REST 通常是弱类型的。我喜欢把 Golang/Java 比作强类型，但是 JavaScript 是弱类型。不好也不坏；他们只是不同而已。
*   进出的路标可能不见了。在 REST 世界中，通过 OpenAPI 规范可以获得机器可读的描述。然而，在我们的分析中，100 个 API 中只有一个具有完全正确的 OpenAPI 规范。这导致一些人猜测前端和后端之间的连接。另一方面，GraphQL 是完全自省的，除非它被故意关闭。
*   分页模型在 GraphQL 中很常见，但在 REST 中更多的是留给开发人员练习。
*   GraphQL 中的过滤和选择模型是特定的；在 REST 中同样是特设的，但两者几乎总是不同的。
*   版本控制是 REST 结构的核心，而 GraphQL 强烈主张避免版本控制。
*   AuthN/AuthZ 在 REST 中足够用，在 GraphQL 中不够用。

## **总结**

从根本上说，没有后端就没有前端。然而，双方的语言、视角和实现方式完全不同。英吉利海峡隧道能够而且必须修建。但这需要对双方都有很好的理解，以及明智的“中间碰头”方法。我们在 StepZen 正在建立[一套能力](https://bit.ly/3v7I9eR)来帮助建造隧道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>