# StepZen GraphQL Studio 将 API 访问合并到一个端点中

> 原文：<https://thenewstack.io/stepzen-graphql-studio-combines-api-access-in-one-endpoint/>

到目前为止，您可能已经听说过 GraphQL 及其众多好处，但是采用它的过程可能看起来很费力，并且受到手动迁移任务的束缚，例如需要定义一个图和操作一个 GraphQL 服务器。由 API 管理平台 [Apigee](https://techcrunch.com/2016/09/08/google-will-acquire-apigee-for-625-million/) 的前成员于去年创办的初创公司[step Zen](https://thenewstack.io/stepzen-one-api-to-connect-all-the-data/)，通过为开发者提供托管的 GraphQL 服务来简化从众多来源获取数据的过程，从而帮助他们迁移到 GraphQL。

现在，StepZen 继他们的首次发布之后，又发布了其 [GraphQL Studio](https://graphql.stepzen.com/) 的[版本](https://stepzen.com/blog/stepzen-graphql-studio-launch)，这是一个被称为 GraphQL IDE 的工具，它为用户提供了几十个预配置的 API，这些 API 来自“内容管理系统(CMS)、电子商务、社交媒体、开发人员生产力工具，甚至像 Airtable 这样的数据存储”，可以通过单个端点混合、匹配和再次访问。

根据 StepZen 产品负责人 Bill Maggs 的说法，StepZen 正处于 20 年转型的末期，Cloudflare 和 Netlify 等公司已经改变了前端内容的交付方式，而后端的运营方式与 20 年前几乎相同。

“通常有一些巨大的数据存储，一些大型 MySQL 数据库，它非常集中，或多或少是你赚钱的来源，”Maggs 说。“我的意思是，按钮、HTML 和 CSS 都很好，但真正驱动应用程序的是数据，这家公司的创始人说，看，我们必须让构建和部署后端像构建和部署前端一样简单。”

Maggs 说，在 REST APIs 的世界里，GraphQL 是他们正在寻找的答案。StepZen 提供了一个单一的 GraphQL 端点，您可以从中调用多个 API，甚至是遗留的 REST APIs，处理错误处理、缓存、返回逻辑和路径优化等功能。

“GraphQL 正在改变这种对 REST APIs 长达 20 年的投资。人们已经建立了 100，000 个 REST 端点，或多或少是基于互联网的模型。你发出一个 HTTP 调用，你得到的东西回来，你真的不能控制那是什么，”他说。“图形 QL 给你控制权，它给你声明的能力，做前端只为所有数据做的事情。”

GraphQL Studio 为开发人员提供了一个基于 web 的图形用户界面，他们可以在这个界面上整合多个 API，然后由 StepZen 托管的一个 GraphQL 端点访问这些 API。目前，GraphQL studio 附带了 35 个预配置的数据源，StepZen 要么提供模拟数据，以便用户可以探索模式，要么允许用户提供自己的 API 键来检索真实世界的结果。

Maggs 解释说，使用 StepZen，用户还可以按顺序进行 API 调用，允许他们从一个 API 调用中获取数据，以便使用该数据从下一个 API 调用中检索数据。StepZen GraphQL Studio 还附带了几个预配置的 API 组合来展示这一功能。例如，“按 IP 划分的本地货币”组合使用一个 IP 查找服务来获取地理位置，然后使用另一个 API 来确定该位置的货币。

[https://www.youtube.com/embed/LxKvc_IQyLI?feature=oembed](https://www.youtube.com/embed/LxKvc_IQyLI?feature=oembed)

视频

除了 GraphQL Studio，StepZen 还推出了 JSON2SDL.com 的[，这是一个将 JSON 数据转换为模式定义语言(SDL)的自省工具，同样专注于从 REST 到 GraphQL 的过渡。马格斯说。](http://json2sdl.com/)

“几乎世界上的每一个 REST API，当你请求它的时候，响应主要是以 JSON 的形式出现。我想说，REST APIs 在世界上的惊人成功并不是真正基于 REST 原则，而是基于这样一个事实，即 JSON 已经成为计算机之间相互交流的通用语言，”他说。“当那个 JSON 回来的时候，要理清它的意思和样子是非常非常困难的。”然后，JSON2SDL“将所有这些 JSON 转换成非常结构化的 SDL，或多或少地告诉你你的数据是什么样的，”他补充道。

目前，JSON2SDL 是一个复制和粘贴工具，但很快 StepZen 计划将这一功能包装到其主要工具中，允许开发人员添加自己的数据源和第三方 API，所有这些都将再次通过单一的 GraphQL 端点可用。

“我们打算这样做，你只需出现，按下按钮，给我们访问权限，你基本上可以说，‘我想做一个终端，为我的应用提供动力，这里有五、六、七样东西，一半是我的，一半是第三方的，把它们放在一起’，它们就是一个终端。它是你的了。你拥有完全的安全性和控制力，而且是自动完成的，这将在接下来的几个月内推出，”Maggs 说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>