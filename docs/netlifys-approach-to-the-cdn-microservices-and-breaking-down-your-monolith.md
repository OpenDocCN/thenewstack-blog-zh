# Netlify 的 CDN 方法，微服务，打破你的铁板一块

> 原文：<https://thenewstack.io/netlifys-approach-to-the-cdn-microservices-and-breaking-down-your-monolith/>

[Netlify 的 CDN 方法，微服务，打破你的铁板一块](https://thenewstack.simplecast.com/episodes/netlifys-approach-to-the-cdn-microservices-and-breaking-down-your-monolith)

在今天的 [The New Stack Makers](https://thenewstack.io/podcasts/makers) 播客中，TNS 创始人 Alex Williams 探讨了 [Netlify](https://www.netlify.com/) 如何创建其内容交付网络、微服务和 AWS Lambda 的兴起，以及规模化工作如何影响当今的开发人员及其工作流程。在 SXSW 期间，Netlify 首席执行官兼联合创始人[马特·比尔曼](https://www.linkedin.com/in/mathias-biilmann-christensen-a5a3805)和 Netlify 总裁兼联合创始人[克里斯·巴赫](https://www.linkedin.com/in/christianbachdk)参加了威廉姆斯的采访。

在强调他的背景时，Biilmann 解释说，随着更新、更高效的技术取而代之，开发人员曾经经常要求的功能现在已经成为过去。

“前端开发人员的工作方式已经发生了根本性的变化。当我开始 Webpop 的时候，第一个功能需求，没有比较，是 FTP 访问。现在就像，什么？你为什么想要一个 FTP？Git 成为一个巨大的现象，不仅是为了版本控制，也是为了开发者的互动。浏览器变得比以前更加强大。您可以直接从浏览器调用服务，前端构建工具完全改变了前端开发人员的工作方式。”

巴赫接着指出，以 Git 为中心的工作流和微服务已经“改变了游戏的名称”

Netlify 的团队不得不非常仔细地考虑如何组合构建工具。Biilmann 强调，在创建其 CDN 时，Netlify 希望为实际的 HTML 文件提供自动部署和即时缓存验证的能力。通过使用一致状态的快照，Netlify 为缓存保留了一个参考点，以触发下一个实时版本。

“我们对架构非常固执己见。该架构是这种缓存保证的一部分，您永远不会拥有由服务器与数据库对话而动态呈现的内容。你将会有一个构建过程，说‘现在新版本已经准备好了’，然后你将会发布这个版本。一旦您购买了该架构，我们就可以为您提供一个完全自动化的工作流，您不必考虑缓存和缓存自动化，我们可以为您实现自动化。

[https://www.youtube.com/embed/4plzNu4UF64?feature=oembed](https://www.youtube.com/embed/4plzNu4UF64?feature=oembed)

视频

### 在这个版本中:

[4:05:](https://thenewstack.simplecast.com/episodes/netlifys-approach-to-the-cdn-microservices-and-breaking-down-your-monolith?t=4:05) 整体式应用和可扩展性的问题
6:23:这是如何将表示层从后端分离出来并实现增量更新的？
[9:05:](https://thenewstack.simplecast.com/episodes/netlifys-approach-to-the-cdn-microservices-and-breaking-down-your-monolith?t=9:05) 缓存和资源驱动方法
[13:06:](https://thenewstack.simplecast.com/episodes/netlifys-approach-to-the-cdn-microservices-and-breaking-down-your-monolith?t=13:06) Netlify 的创建有助于开发人员工作流
[13:45:](https://thenewstack.simplecast.com/episodes/netlifys-approach-to-the-cdn-microservices-and-breaking-down-your-monolith?t=13:45) 探索 Netlify 的底层架构
[15:28:](https://thenewstack.simplecast.com/episodes/netlifys-approach-to-the-cdn-microservices-and-breaking-down-your-monolith?t=15:28)Netlify 如何使用 AWS Lambda

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>