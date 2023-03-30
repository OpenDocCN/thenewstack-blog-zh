# 与 GraphQL 合作设计应用

> 原文：<https://thenewstack.io/react-with-graphql-for-architecting-apps/>

正如我们在 [React 中看到的，](https://www.google.ca/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0CB0QFjAA&url=https%3A%2F%2Ffacebook.github.io%2Freact%2F&ei=ZRRaVcLZD4m4oQSviYDwCw&usg=AFQjCNHa_1d2VQ9XLEwLkZFQYYmqt39aoQ&bvm=bv.93564037,d.cGU)脸书不怕尝试革命性的方法来设计应用程序，并质疑许多长期以来被接受的 web 开发最佳实践。例如，脸书的 React 避开了模板，而是选择用 Javascript 操作和呈现数据。鉴于 React 的工作方式与通常的客户端代码完全不同，传统的获取数据的方式并没有让 React 发挥出最大的作用。

脸书发表的第一个方法是通量模式。Flux 模式有各种框架实现，许多 React 应用程序选择使用 Flux 模式。然而，并不是每个人都选择在他们的 React 应用程序中使用 Flux 事实证明，就连脸书自己也在开发设计 React 应用程序的替代方法。进入[继电器和 GraphQL](https://gist.github.com/wincent/598fa75e22bdfa44cf47) 。

Relay 和 GraphQL 背后的中心思想是视图代码是定位数据获取代码的最佳位置。为此，每个 React 组件将使用 GraphQL 查询指定其所需的数据；然后，Relay 将获取 GraphQL 指定的数据。您可能想知道 Relay 的附加值是什么，以及为什么 GraphQL 不针对数据访问服务器本身，而只是指定数据需求。原因是每个 GraphQL 查询并不映射到执行一个服务器请求的中继，因为这样做会带来很大的性能损失；这将是低效的，因为您将经常在多个地方指定相同的数据依赖关系。

相反，Relay 将接收发送给它的所有不同的查询，并将它们批处理在一起。这意味着如果有多个 React 组件通过 GraphQL 指定了相同的数据依赖关系，它们都将通过 Relay 从同一个服务器请求中获取数据。对我来说，这感觉类似于 React 组件如何向虚拟 DOM 声明它们所有的呈现需求，然后在进行任何操作之前与实际 DOM 进行区分。虚拟 DOM 和 Relay 都允许 React 开发人员显式地陈述他们的组件的需求，而不必因为性能原因而尝试最小化。

## GraphQL 查询

让我们更详细地讨论一下只获取模型数据子集的想法。React 组件对应于我们后端的特定模型是非常常见的。然而，很可能不存在一个组件对一个模型的关系。更有可能的是，一个应用程序会有各种视图组件，每个组件都由特定模型的部分组成。正因为如此，每个视图抓取一个模型的每个属性是没有意义的；使用 GraphQL，React 组件可以指定它需要的精确属性，这就是它将得到的全部回报。

数据库中的用户记录可以包含许多与该用户相关的字段。假设我们在网站上制作了一个显示用户姓名、年龄和州的盒子。在我们的数据库中，我们有几个关于用户信息的其他字段，可能是不相关的数据，比如用户对电子邮件通知的偏好，或者是私人数据，比如用户的电话号码。

如果只获取我们关心的数据，GraphQL 应该是这样的:

```
{
  user(id:  4000)  {
    id,
    name,
    age,
    state
  }
}

```

这将给我们:

```
{
  user:  {
    id:  4000,
    name:  'Beth',
    age:  32,
    state:  "Wisconsin"
  }
}

```

这种工作方式相当直观。在我们指定用户 ID 的地方之外，我们实际上已经编写了一些 JSON:我们指定了键，但是遗漏了值。GraphQL 通过使用传入的 ID 填充这些 JSON 值来响应，并使用完全符合 JSON 的响应来响应。GraphQL 本质上也是分层的，允许您进一步嵌套请求的参数。

在上述查询的上下文中，假设我们也想返回用户的头像，并使其大小为 100:

```
{
  user(id:  4000)  {
    id,
    name,
    age,
    state
    avatar(size:  100)  {
      uri,
      height,
      width
    }
  }
}

```

这将给我们:

```
{
  user:  {
    id:  4000,
    name:  'Beth',
    age:  32,
    state:  "Wisconsin",
    avatar:  {
      uri:  "http://some-site.com/picture.png",
      height:  100,
      width:  100
    }
  }
}

```

## 前方的道路

虽然 GraphQL 在正式发布时会有很好的第一级中继支持，但 GraphQL 作为一项独立的技术也能很好地工作。我认为在不久的将来，GraphQL 会有很多令人兴奋的应用，无论是在 Relay 内部还是外部。虽然与大多数开发人员习惯的为应用程序获取数据的方式有很大不同，但这些变化背后的理由是充分的，这项技术正在接受脸书的生产审查。请关注未来的新闻，因为脸书发布了更多关于 GraphQL 的技术细节。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>