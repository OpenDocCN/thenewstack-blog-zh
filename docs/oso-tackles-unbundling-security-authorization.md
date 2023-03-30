# Oso 拆分安全授权

> 原文：<https://thenewstack.io/oso-tackles-unbundling-security-authorization/>

就在几年前，似乎没有人在谈论授权，但现在每个人都在谈论，T2 Oso T3 的联合创始人兼首席执行官 Graham Neray T1 认为这是一件健康的事情。

[Airbnb](https://medium.com/airbnb-engineering/himeji-a-scalable-centralized-system-for-authorization-at-airbnb-341664924574) 、 [Carta](https://medium.com/building-carta/authz-cartas-highly-scalable-permissions-system-782a7f2c840f) 、 [Slack](https://slack.engineering/role-management-at-slack/) 和 [Intuit](https://medium.com/intuit-engineering/authz-intuits-unified-dynamic-authorization-system-bea554d18f91) 都写过他们如何在自己的公司定制授权。包括 [Authzed](https://authzed.com/?gclid=Cj0KCQjwwNWKBhDAARIsAJ8HkhdLk9qoW426D0S2ucQhLVnaFebyOFasQ96xRFSuGLeqmZMVaeCH88EaAv2AEALw_wcB) 和 [Aserto](https://techcrunch.com/2021/06/09/aserto-announces-5-1m-seed-to-build-authorization-as-a-service/) 在内的初创公司正在潜入授权领域，Authzed 刚刚发布了谷歌[桑给巴尔](https://www.usenix.org/system/files/atc19-pang.pdf)的开源版本，名为 [SpiceDB](https://github.com/authzed/spicedb) 。它是同样基于桑给巴尔岛的开源软件 Keto 的竞争对手。Oso 对这个问题有自己的看法。

Neray 认为授权是应用程序的下一个部分，将按照 Stripe 在支付处理方面和 Twilio 在通信方面的方式进行拆分。它是每个应用程序的基本组件，开发人员花费大量时间为其编写代码，但它不是价值主张的核心部分。

[认证不同于授权](https://thenewstack.io/how-do-authentication-and-authorization-differ/)，正如 Mary Branscombe 最近的文章所指出的:认证涉及验证该人实际上是他们声称的那个人，而授权指的是一个人或服务一旦进入系统就被允许做什么。

然而，尽管跨系统授权的需求不断增长，特别是在微服务领域，但 Oso 联合创始人兼首席技术官 [Sam Scott](https://www.linkedin.com/in/samjs/) 在一篇博客文章中解释道，跨用例以通用方式解决是一个[难题。](https://www.osohq.com/post/why-authorization-is-hard)

**"** 授权用例范围很广:Kubernetes 准入控制、数据库访问控制、微服务/应用授权等。，“黑客新闻[评论员](https://news.ycombinator.com/item?id=28543457) thinrich 指出。“尽管它们都是授权的，但它们在实施点、数据依赖、建模/表达、性能等方面都有自己的需求。因此，面对如此广阔的需求空间，我们最终会有如此有趣和丰富的技术选择，这并不奇怪。”

## 清白的过去

Neray 之前在 MongoDB 工作；斯科特有密码学背景。Neray 说，他们有一个共同的愿景，就是把安全工具交到开发者手中。在合作开发基础设施安全工具的同时，人们不断询问关于构建应用授权的问题，他们将注意力转向了那里，在 2018 年创建了 Oso 公司，并在去年 7 月[开源了该技术。](https://github.com/osohq/oso)

“作为一个行业，我们都是从许多这些 API 即服务开始的——AWS、Stripe、Twilio 等——应用程序的各个部分最容易分离出来，因为它们已经存在于这些清晰可辨的组件中，如计算或存储，”Neray 说。“你知道，授权控制着你进入应用程序后能做什么——你能看到什么数据或打开什么页面——这是一件很难分开的事情。这就是为什么人们问了我们这么多，他们有这么多复杂的问题。但它存在于每一个应用程序中……而且这实际上是一个很难解决的问题。”

在博客文章中，Scott 对其他授权工具提出了质疑，包括 Zanzibar，列举了随着数据过滤变得越来越复杂，需要框架级集成的问题，而大多数都没有提供。

“我认为使我们处于独特地位的一个原因是，大多数竞争对手都是从一些预先存在的想法或产品开始，并在此基础上进行构建。而且…如果他们认为这是一种加快上市时间的方式，我也不会感到惊讶。但是每一种可用于应用程序授权的现有技术都有不小的缺点，这些缺点是每一个供应商现在都不得不面对的。我们从头开始建设。我们实际上与最早的用户一起探索了许多不同的设计选项，看看我们认为最有意义的是什么，我认为产品对它来说更好，”Neray 说。

Oso 以铁锈为核心运作。它提供 Node.js、Python、Go、Rust、Ruby 和 Java 版本的库。Oso 提供了一个心智模型和一个授权系统——一组构建在名为 [Polar](https://docs.osohq.com/rust/learn/polar-foundations.html) 的声明性策略语言之上的 API，加上一个调试器和 REPL——来定义应用程序中的权限。

根据 Neray 的说法，它为开发者提供了三样东西:

*   一个内置了最佳实践的框架，使他们能够快速轻松地构建一些东西。他说，在早期，没有必要学习 Polar 的内部工作原理，这是一种他们专门为授权而构建的语言，但随着事情变得更加复杂，开发人员可以更深入地研究它。
*   他们称之为“永远”的系统，用户不会超越。它支持任何型号，可以很容易地定制。
*   知道 Oso 支持测试、安全并提供大量文档来确保他们做得正确，就可以高枕无忧了。

它的 GitHub 页面声称，“开发人员通常可以在不到 5 分钟的时间内编写一个工作 Oso 策略，在不到 30 分钟的时间内将 Oso 添加到一个应用程序中，并在几个小时内使用 Oso 解决真正的授权问题。”

它在 9 月发布了 Oso 0.20，包括:

1.  **授权建模** —内置的原语将最佳实践更深入地推进到产品中，因此它有效地告诉用户如何建模常见的模式，如基于角色和关系的访问控制(RBAC 和 ReBAC)。
2.  **数据过滤**提供超越是/否问题的能力，例如“只显示 Juno 可以看到的行”以前只在 Python 中可用，这个版本也增加了 Node.js 和 Ruby。它仍然致力于在 Go、Java 和 Rust 中支持这一功能。
3.  **API**帮助开发人员了解他们需要在应用程序中的哪些层添加授权。Oso 0.20 提供了在这些不同层实施授权的本地 API。

[https://www.youtube.com/embed/UsigUU1wu8w?feature=oembed](https://www.youtube.com/embed/UsigUU1wu8w?feature=oembed)

视频

用户包括对讲机、第一共振、Wayfair 和 BioDati。

### 专注于文档

“我在 Visa 使用过 Oso，这是一款非常棒的产品。在它点击之前，Polar 是超级混乱的，但在 Slack 上与团队交谈后。我意识到它是多么容易使用，”一位名叫 stonecharioteer 的黑客新闻评论员写道。

该公司还致力于提供文档来帮助开发者理解授权。这种需求是黑客新闻帖子评论者中反复出现的话题之一。为此，它创建了[授权学院](https://www.osohq.com/developers/authorization-academy)，这是一系列关于构建应用程序授权的技术指南。

Neray 说，这个话题缺乏深刻的相关内容:

“太疯狂了。这就像你要么结束了这些非常沉重，搜索引擎优化和供应商的流行语网页，或这些学术 PDF 风格的网页。这是我们要改变的一部分，只是让所有人都更容易理解整个事情。”

到目前为止，该公司一直专注于建立开源版本的采用，但将在未来建立一个商业产品。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>