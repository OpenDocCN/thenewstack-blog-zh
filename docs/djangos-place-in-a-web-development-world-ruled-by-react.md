# Django 在 React 统治的 Web 开发世界中的位置

> 原文：<https://thenewstack.io/djangos-place-in-a-web-development-world-ruled-by-react/>

2021 年的 Web 开发被 JavaScript 及其许多前端框架所主导，有时人们很容易忘记传统的服务器端 web 应用程序架构不仅还活着，而且还在蓬勃发展。参加年度 [StackOverflow 调查](https://insights.stackoverflow.com/survey/2020#technology-most-loved-dreaded-and-wanted-web-frameworks)的 Django 开发者中有 55.3%的人表示他们将继续使用它；49.3%的人对[的 Ruby on Rails](https://rubyonrails.org/) 也有同样的看法。Django 和 Ruby on Rails——两个领先的后端 web 开发框架，都是开源的——从 2000 年代中期就出现了。它们不再是 web 开发中时髦的年轻人，但它们仍然分别是第七和第十一大最受欢迎的 web 框架。

在今年早些时候的专栏中，我讨论了 base camp——开发 Ruby on Rails 的公司——如何通过一个新发布的叫做 [Hotwire](https://hotwire.dev/) 的框架来适应前端趋势。Hotwire 的目标之一是通过“通过网络发送 HTML 而不是 JSON”来减少 JavaScript 代码的使用量。这既是对 React 和 Next.js 等领先前端框架的 JavaScript 依赖的挑战，也是 Ruby on Rails 保持相关性的一种方式。

为了找到 Django 对我们当前以 JavaScript 为主的网络环境的看法，我联系了它的联合创始人之一——Simon Williamson。如今，威廉森正[专注于他的最新项目](https://thenewstack.io/datasette-a-developer-a-shower-and-a-data-inspired-moment/)[dataset](https://datasette.io/)，这是他为探索和发布数据而开发的开源工具。但他最出名的是在 2003 年共同创建了 Django，作为一个 Python 框架，帮助开发人员构建复杂的、数据库驱动的网站。当时，威廉森和他的合作者[阿德里安·霍洛维蒂](http://www.holovaty.com/)正在为一家美国小报社工作，所以[的想法是](https://simonwillison.net/2005/Jul/17/django/)帮助报纸的作者和编辑轻松地将内容放入数据库，然后发布到网站上。

 [理查德·麦克马努斯

Richard 是 New Stack 的高级编辑，每周撰写一篇关于 web 和应用程序开发趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) 

在过去 15 年左右的时间里，Django 已经成为许多大规模互联网产品不可或缺的一部分，[如](https://www.geeksforgeeks.org/top-10-django-apps-and-why-companies-are-using-it/) Instagram、Pinterest 和 Spotify。正如一位 Instagram 工程师在 2019 年 9 月[指出的那样](https://instagram-engineering.com/types-for-python-http-apis-an-instagram-story-d3c3a207fdb7)，“Instagram 服务器是一个 Python 整体，有几百万行代码和几千个 Django 端点。”

不太为人所知的是，Django 有时会与 React 和 Vue 这两个当今领先的前端框架一起使用。这并不奇怪——insta gram 显然同时使用了 Django 和 React，因为后者是由其母公司脸书运营的项目。但是从 Willison 最近的 Twitter 评论来看，Django 不能与 JavaScript 前端框架一起工作是一个[常见的误解](https://twitter.com/simonw/status/1361999971629756472)。

“技术上正确的答案是，”当我问及这个问题时，威廉森告诉我，“像 Django 这样的后端框架可以与任何前端框架一起工作，因为关注点是分离的:如果一个 web 框架可以用 JSON 和 HTML 响应 HTTP 请求，那么它可以与任何东西一起使用。”

然而，他指出 Django/JS 框架关系的某些方面让人们感到困惑，“尤其是新开发人员。”

“像用于认证的 JWT(JSON Web Token)这样的东西是一个热门话题——Django 项目的核心成员认为 JWT 的设计有缺陷，并反对在 Django core 中提供对它的支持，将其留给第三方包。但是很多开发者想使用 JWT，却很难找到方法。”

他说，默认的解决方案是使用 [Django REST 框架](https://www.django-rest-framework.org/)，这是一个构建 Web APIs 的工具包。该工具包包括对 JWT 的支持。他自己经常使用的另一种方法是编写标准的 Django 视图，让[返回 JSON](https://docs.djangoproject.com/en/3.1/ref/request-response/#jsonresponse-objects) 。

将两个框架配对的例子是使用 React 处理用户界面，根据需要从 Django 后端获取数据。例如，[本教程](https://www.digitalocean.com/community/tutorials/build-a-to-do-application-using-django-and-react)展示了如何构建一个待办应用程序，使用 React 向 Django REST API 发出 HTTP 请求，以获取和设置数据。

## 单页应用程序(SPAs)的问题

虽然 Django 和 React 可以很好地合作，但是最近几年有很多关于 React 应用程序开发模型的争论。有些人认为 React 给 web 开发带来了太多的复杂性，现在被过度使用了。

在去年五月一篇有影响力的博客文章中，软件工程师 Tom MacWright 写道“web 开发的新兴规范是构建一个 React 单页面应用程序，并提供服务器渲染。”服务器端呈现(SSR)意味着在后端运行 JavaScript 前端代码，以便预填充 HTML 页面(然后将页面发送到客户端，客户端通常会运行更多的 JavaScript 代码以使页面具有交互性)。MacWright 说，这种方法对于许多用例来说是不必要的，指出它可能会产生“混乱的优化”和数据获取问题。

根据 MacWright 的说法，数据获取“在 React 领域非常重要，也非常奇怪。”尽管他喜欢将 GraphQL 作为获取数据的方式，但他说“对于一个通过从 API 获取数据来加载数据的 React 组件来说，解决方案只会变得更奇怪。”

威廉森同意麦克赖特关于温泉过度使用的观点。

“在过去的 5-10 年里，”威廉森说，“新的开发者似乎成长在一个 SPA 是构建几乎任何东西的默认方法的世界里。我认为对许多项目来说，这是一个可怕的违约。”

除了技术效益不确定之外，威廉森认为，一些温泉项目可能会比必要的时间拖得更久。

“我见过 SPA 项目比我预期的要多花几个月的时间，如果它是用无聊的旧的无 JavaScript HTML 表单构建的话。”

## 现代网络开发不应该意味着忽视经典

回到 Tom MacWright 的文章，他(我认为相当不公平地)给 Django 贴上了“不酷”的标签，并暗示它“超出了现代 web 开发的规范”但是如果你接受他的观点，即 React 单页面应用程序有许多问题，那么一个乏味的老 Django 网页或应用程序在许多用例中肯定是足够的——至少在不需要复杂用户界面的情况下。

但同样，在 Django 和 React 中，我们有两个应该互补的框架——一个是后端框架，另一个是前端框架。正如 Simon Willison 指出的，有一些相对简单的方法可以让 React 构建的用户界面根据需要从 Django 后端获取数据。

正如 21 世纪生活中的许多领域一样，有时我们只是将 web 开发中的事情过于复杂化了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>