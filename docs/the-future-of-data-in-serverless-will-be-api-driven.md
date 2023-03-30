# 无服务器数据的未来将是 API 驱动的

> 原文：<https://thenewstack.io/the-future-of-data-in-serverless-will-be-api-driven/>

在[无服务器](/category/serverless/)范例中，想法是抽象出后端，这样开发者就不需要处理它。对于像 Kubernetes 这样的服务器和复杂基础设施来说，这一切都很好。但到目前为止，数据库系统还没有典型地成为无服务器剧本的一部分。假设开发人员将构建他们的无服务器应用程序，并选择一个单独的数据库系统来连接它——无论是传统的关系数据库、NoSQL 系统，甚至是[数据库即服务](/database-as-a-service-a-win-for-app-developers-but-not-dbas/) (DBaaS)。

但是，无服务器的流行推动了数据市场的进一步创新。在本期[新堆栈分析师](/podcasts/analysts)播客中，我们讨论了在无服务器系统中管理数据的最新进展。

我的两位客人是[Evan Weaver](https://twitter.com/evan),[Fauna](https://fauna.com/)的联合创始人兼首席技术官，以及[Greg McKeon](https://www.linkedin.com/in/gregmckeon/),[cloud flare](https://www.cloudflare.com/)的产品经理。Fauna 正在为无服务器应用构建“数据 API ”,这样开发人员甚至不需要接触数据库系统，而 Cloudflare 运行一个名为 Cloudflare Workers 的无服务器平台。

[未来无服务器中的数据将是 API 驱动的](https://thenewstack.simplecast.com/episodes/the-future-of-data-in-serverless-will-be-api-driven)

Fauna 和 Cloudflare 对无服务器上的数据采取了不同的方法，但两者都在推动云原生时代数据库*的边界。*

Weaver 指出，无服务器只是 20 世纪 90 年代模式的现代版本，其中“的想法是，你可以消费你的基础设施，而不必做任何操作工作。”Fauna 正在做的是将数据库操作添加到无服务器抽象出来的事物列表中。

“我们对动物群所做的，”他说，“是采用许多传统数据库的原语，如 RDBMS[关系数据库管理系统]或 Postgres 或诸如此类的东西，并把它们翻译成网络本地的、安全的、无处不在的全球 API。”

这意味着开发人员可以使用数据库系统的等价物，但是——正如 Weaver 所说——他们不需要“成为 DevOps 工程师”

Cloudflare Workers 与典型的基于容器的无服务器平台略有不同。Workers 不是使用容器，而是使用 Google 的开源 V8 JavaScript 引擎开发的。

“我们很早就做出了一个非常关键的决定，在 V8 分离株上运行，而不是在容器上运行，”McKeon 解释道。“这是支持 Chrome 网络浏览器的同一个 V8 版本[……]，因此工作人员也实现了许多你习惯于从浏览器环境中使用的相同 API。”

根据 Cloudflare 几年前的一篇文章，隔离“使得在单个操作系统进程中运行来自许多不同客户的不受信任的代码成为可能。”

虽然 Workers 对于无服务器应用程序来说确实有性能优势，但是从数据的角度来看还是有一些限制。

“我们实际上不支持来自工人环境的 TCP 连接，”McKeon 说，并补充说“这是我们正在努力解决的一个痛点。”

然而，工作人员可以通过 HTTP 连接到外部数据库服务(如动物群)。那么，这是否意味着 API 连接是无服务器领域数据的未来？

虽然 McKeon 和 Weaver 都承认传统的关系数据库还会存在很多年，但是在应用程序开发中使用 API 方法和边缘网络是一个明确的趋势。

“我们在这里看到的技术，”Weaver 在谈到新兴的应用程序模型(Fauna 已将其标记为 [client-serverless](https://fauna.com/client-serverless) )时说，“是 ReactJS、GraphQL、Swift、Android 堆栈等东西，以及像[Cloudflare] Workers 这样的东西——它们在边缘上运行，而不是在少数超大规模数据中心中运行——它们都通过 API 进行交互，组成逻辑，构建动态应用程序，与传统的三层堆栈相比，开销更少，上市时间更快。”

同样在这个播客中，我们讨论了有状态无服务器应用的出现，NoSQL 数据库服务如何适应无服务器世界，等等。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论故事的读者通过[推特](https://twitter.com/thenewstack)或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>