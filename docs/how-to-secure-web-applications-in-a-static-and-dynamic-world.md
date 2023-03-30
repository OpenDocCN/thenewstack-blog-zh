# 如何在静态和动态的世界中保护 Web 应用程序

> 原文：<https://thenewstack.io/how-to-secure-web-applications-in-a-static-and-dynamic-world/>

Netlify 是一个受欢迎的静态“ [Jamstack](https://jamstack.org/) ”网站托管平台，被超过一百万的网络开发者使用。虽然 Netlify 因其简单性而广受欢迎，但它为静态环境提供的安全性也同样令人感兴趣。

网络安全是我们新系列“安全@规模”最新一集的主题，该系列将在[与](/podcasts/makers) [Okta](https://developer.okta.com/?utm_content=inline-mention) 的新堆栈制造商上播出。该系列探索了现代环境中的安全问题，讲述了来自战壕的故事，包括安全恐怖故事和离奇的失败。

在这一集里，共同主持人 [Alex Williams](/author/alex/) ，New Stack 的创始人兼发行人，以及[安全服务提供商](https://www.linkedin.com/in/rdegges) [Okta](https://developer.okta.com/?utm_content=inline-mention) 的开发者权益负责人 Randall Degges ，与嘉宾[Netlify 的员工应用安全工程师 Dustin Rogers](https://www.linkedin.com/in/dustin-rogers11/) 谈论所有与静态 web 安全管理相关的事情。

Degges 指出，静态网站有助于组织避免许多安全和其他操作相关的问题，因此需要较少的维护。Rogers 对此表示同意，并指出尽管许多安全最佳实践适用于静态和动态网站管理，但 Netlify 可以为 DevOps 团队做许多繁重的工作，如标题管理。

[Okta 系列——如何通过达斯汀·罗杰斯](https://thenewstack.simplecast.com/episodes/okta-series-how-to-secure-web-applications-in-a-static-and-dynamic-world-w-dustin-rogers) 保护静态和动态世界中的 Web 应用程序

开发人员最终要对安全性负责。例如，静态网站虽然比动态网站需要更少的安全维护，造成的潜在漏洞也更少，但仍然必须维护。Rogers 说:“我只是想确认一下，即使在 Jamstack 的世界里，安全性仍然可以落到开发者的肩上。”。“但我们倾向于认为这些变得更容易了。”

同时，静态站点通常也不是完全静态的。罗杰斯说，典型的“人们想做的动态事情”包括添加论坛数据和论坛信息存储，以及“从外部 API 中获取信息，如用 API 包装的数据库或伪数据库交互”。

“这些是人们将动态数据拉入 Jamstack 网站的一些方式，”罗杰斯说。

在这种情况下，包括 React 在内的动态 JavaScript (JS)框架可以提供许多优势。“我认为动态 JS 框架(如 React)的最大优势是能够重用 JS 代码，”Rogers 说。“因此，它被捆绑在一起，我们看到它的尺寸减小了，更容易渲染。对于移动应用来说尤其如此，因为移动环境通常重量更轻，需要更快的处理速度。”

开发人员在静态网站上可能会犯的一些安全风险，如 Netlify 的平台，包括使用未加密的敏感值作为查询参数。

“多年来，我开始很少看到这种情况，但现在我觉得我看到了更多——至少，我认为将这些内容放在 post 表单中更有意义。但我认为人们使用查询参数的原因通常与可移植性有关——可点击的网址，如营销电子邮件中发送的网址，”罗杰斯说。“我们保证缓存控制…但是如果一个值是敏感的，作为开发人员，您希望尽可能地保护它。这是我经常看到的一件令我畏缩的事情。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>