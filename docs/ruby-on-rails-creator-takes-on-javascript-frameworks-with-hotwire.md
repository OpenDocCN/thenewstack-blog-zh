# Ruby on Rails Creator 通过 Hotwire 实现了 JavaScript 框架

> 原文：<https://thenewstack.io/ruby-on-rails-creator-takes-on-javascript-frameworks-with-hotwire/>

Ruby on Rails 的创造者[大卫·海涅梅尔·汉森](https://twitter.com/dhh)最近在[芝加哥计算机械协会](https://youtu.be/HNMA-uXhxuQ) (ACM)的一个虚拟聚会上发言。Hansson 在过去的 15 年中一直站在 web 开发的最前沿，他谈到了 JavaScript 框架的现状、他正在跟踪的前端开发趋势以及他帮助创建的一个新框架 Hotwire。

 [理查德·麦克马努斯

Richard 是 New Stack 的高级编辑，每周撰写一篇关于 web 和应用程序开发趋势的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) 

像 Ruby on Rails 一样， [Hotwire](https://hotwire.dev/) 也是在 [Basecamp](https://basecamp.com/) 的管理下发布的——这家公司是汉森与首席执行官[杰森·弗里德](https://twitter.com/jasonfried)等人共同创立的。Hotwire 提供了“一种不用太多 JavaScript 就能构建现代网络应用的替代方法。”它被描述为一种“HTML-over-the-wire”方法，这意味着它在服务器上生成 HTML 文件，然后将其传递给浏览器。这是传递 JSON 的一种替代方式，JSON 是一种数据格式，许多大量使用 JavaScript 的 web 应用程序使用这种格式将内容从服务器发送到客户端。

当 Hotwire 在 12 月向世界宣布时，Hansson [在推特上说它是“我们用来构建 https://hey.com 前端的所有技巧和工具”的混合物。他指的是 Basecamp 的网络电子邮件产品](https://twitter.com/dhh/status/1341420145265291264) [HEY](https://hey.com/) ，这是 Gmail 的竞争对手[于去年 6 月](https://thenewstack.io/basecamps-hey-app-attempts-to-re-invent-email/)推出的。因此，Hotwire 与 Ruby on Rails 有着相似的起源故事，后者于 2004 年从 Basecamp 产品中脱颖而出。虽然，与 Ruby on Rails 不同，Hotwire(到目前为止)还没有被开源。

Hotwire 的一部分是 [Turbo](https://turbo.hotwire.dev/) 框架，Hansson [将](https://twitter.com/dhh/status/1341420144308981760)描述为“一套免费的[原文]技术，用于加速页面更改和表单提交，将复杂的页面分成组件，并通过 WebSocket 传输部分页面更新。”他补充说，所有这些都是在没有 JavaScript 的情况下完成的。

在由 Heroku 的 Valerie Woolard 主持的 ACM 采访中，Hansson 说 Hotwire 是他的“默认推荐”,现在人们可以用它来开发类似 GitHub、Basecamp 或 Shopify(这三个最流行的应用都是用 Ruby on Rails 开发的)的网络应用。他还解释说，开发 Hotwire 是为了解决基于 JavaScript 的 web 开发日益复杂的问题。

“今天的 web 开发非常复杂[……]因为前端非常复杂，”他说，举了两个例子“建立你的构建管道和 webpack 配置”。他补充说，建设现代化的前端“真的很吓人，它以一种[它]过去没有的方式隔离。”

## Hotwire 和 JavaScript 框架有竞争吗？

自然，Hansson 仍然相信框架是简化开发的一种方式。虽然他现在专注于推广 Hotwire，但他指出 Ruby on Rails 仍然很强大——事实上它被用来构建 HEY。

Ruby on Rails 的全盛时期是在 Web 2.0 时代，但它在许多方面为当今流行的 JavaScript 框架——React、Angular、Vue.js 等——铺平了道路。

然而，Ruby on Rails 也在与这些 JavaScript 框架竞争——至少是为了吸引开发者的注意力——所以 Hotwire 也必须从这个角度来看待。所以我联系了 [Daniel Kehoe](https://twitter.com/yaxdotcom) ，他在十年前创立了[Rails app 开源项目](http://railsapps.github.io/)并写了《学习 Ruby on Rails 这本书。如今，凯霍经营着一个开源项目[Yax.com](https://yax.com/)，该项目倡导一种“无框架”的 web 标准方法来进行 web 开发。

Kehoe 认为 Hotwire 很有趣，“因为它展示了 Hansson 如何希望 Rails 保持对全栈开发的有用性和相关性。”由于 Ruby on Rails 运行在 web 服务器上，它通常被视为后端框架。但 Kehoe 的观点是，Rails 也希望在前端保持相关性，尤其是考虑到 JavaScript 在当今网络中的重要性。

“另一种选择是让 Rails 完全成为后端应用的框架，”Kehoe 继续说道，“让前端和其他 JavaScript 框架做出反应。Hotwire(带有 WebSockets 和 Action Cable)展示了 Rails 如何作为 React etc 的替代方案用于交互式前端，将 Rails 的使用范围扩展到 CRUD[创建、读取、更新和删除]应用程序之外。”

Hansson 确实想让整个 web 开发栈对于 web 开发者来说是可以理解的。他对此有一个特别的理论，叫做“概念压缩”，他在 ACM 会议上多次提到这个理论。

Hansson 说，“Ruby on Rails 的整个精神是，你构建伟大的应用程序所需的一切”在“大部分时间”都是可用的。“你要做一些非常难、需要专家理解的事情，比如建立你的 JavaScript 构建管道，你要一路压缩它，直到它可以作为一个切片(从许多其他切片中)进入单个开发人员的大脑。”

这基本上也是 React、Next.js 和 Angular 等 JavaScript 框架试图做的事情。事实上，对于当今 web 开发的许多方面来说，这是一种越来越受欢迎的方法——CSS 也有自己的框架，比如 [Tailwind](https://tailwindcss.com/) 。

关于汉森的“概念压缩”理论，凯霍说，Hotwire“提出了一种替代方法，用 JavaScript 的混合在 Rails 中构建一个‘宏伟的整体’。”但是凯霍，这位“在一家拥有笨重的铁路公司担任工程总监”并不认为这是一个好主意。

“在后端，Rails 依赖活动记录作为到单个数据库的 ORM(对象关系映射),这导致了庞大而繁琐的应用程序；将 Hotwire 添加到前端(而不是单独的前端应用程序)只会使整体变得更大。”

他的观点是，运行使用 Hotwire 的应用程序仍然需要 JavaScript 专业知识，这意味着在这样的系统中，web 开发过程仍然很复杂。

“Hotwire 试图减少所需 JavaScript 的数量，”Kehoe 说，“但是仍然有 JavaScript，仍然需要既有 JavaScript 技能又有 Ruby 技能的开发人员。专业化还会继续；也许有了新的 Rails，真正聪明的全栈开发人员(像 Basecamp 的那些)有足够的技能来做前端和后端。但我仍然担心，对于许多临时或兼职的 web 开发人员来说，web 开发已经变得太复杂了。”

## 前端的未来

所以大卫·海涅梅尔·汉森想要前端框架的一块馅饼；鉴于他在用 Rails 革新后端开发方面的记录，你将会是一个勇敢的开发者来打消他对 Hotwire 的野心。

汉森对“我们刚刚经历的这波 JavaScript 浪潮之后会发生什么”感到兴奋——指的是过去十年 JavaScript 推动的网络创新和 Chrome 等网络浏览器的日益成熟。他认为 Hotwire 可以帮助简化前端开发，就像 Ruby on Rails 为后端所做的那样。

“我关心整个网络堆栈，”他说，“很长一段时间我非常关心后端。现在我觉得前端有这样的机会——hot wire、浏览器内置 ESM(EcmaScript 模块)、ES6。我们终于可以抛弃过去几年中让 JavaScript 变得可行的很多东西了。现在我们不再需要它们了——所有的脚手架都可以拆掉了。”

JavaScript 脚手架可能真的要倒了，但现在的问题是:你将使用谁的框架来构建？

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>