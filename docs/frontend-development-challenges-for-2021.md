# 2021 年的前端发展挑战

> 原文：<https://thenewstack.io/frontend-development-challenges-for-2021/>

在[我的 2021 年网络发展预测](/6-web-development-predictions-for-2021/)中，我确定了今年的两个主要趋势:无服务器向功能更全面的平台扩展(例如，有状态应用在无服务器上成为现实)，以及 JavaScript 的持续增长(尤其是 React)。Jamstack 是另一个增长领域，尽管它还处于早期阶段。为了讨论这些和其他前端趋势，我采访了提供应用程序监控平台的[哨兵](https://sentry.io/welcome/?utm_content=inline-mention)的联合创始人兼首席技术官[大卫·克莱姆](https://twitter.com/zeeg)。你可以在 [The New Stack Makers](/podcasts/makers) 播客上听到完整的讨论，但在本文中，我将回顾一下主要的讨论要点。

在观看了最近由 Sentry 举办的名为“[Frontend](https://youtu.be/DY0tiVlIR3M)的未来”的虚拟活动后，我渴望与 Cramer 交谈他在演讲中说“应用程序是前端”，“前端是你的业务。”他的意思是，在数字时代——尤其是在当前的疫情时代——很多人很可能主要通过应用程序与企业互动。想想你现在如何与你的银行打交道——如果它没有一个加载速度快、用户界面好的像样的移动应用程序，那很可能是转移到另一家银行的理由。

[面向 2021 年的前端开发挑战，带 David Cramer–Sentry](https://thenewstack.simplecast.com/episodes/frontend-development-challenges-for-2021-w-david-cramer-sentry)

因此，如果前端是当今商业应用程序的一个关键部分，那么开发人员在构建这些前端时需要改进什么呢？根据 Cramer 的说法，一个普通的 web 应用程序必须加载的 JavaScript 数量是一个大问题。

“每个人都会注意到它，因为它需要很长时间(加载)。所以我确实认为有些事情必须改变。我不知道是在今年还是明年，我们会重新思考这些想法，比如，我们是否应该将所有的逻辑和代码都推送到客户端？还是回到网络的本来面目，使用服务器将数据传输给我们的客户？”

JavaScript 代码的复杂性和膨胀也给调试带来了问题。克莱姆如何看待这个问题在 2021 年及以后得到解决？

“我认为我们在 JavaScript 方面面临的挑战——过去是，你有一个 JavaScript 应用程序，它可能是动画和一些花哨的加载东西，如果有错误，可能不会影响你。它不像你的整个网站。这是进化而来的。现在，整个事情都是 JavaScript！”

所以问题是，JavaScript 在 20 世纪 90 年代中期开始作为 HTML 页面中的小代码插件，现在已经成为网页或应用程序的一个更大的组成部分。有时候甚至会带动整个 app。Cramer 认为浏览器公司必须负起责任，几乎从网络标准的角度来处理这个问题。

“浏览器供应商必须对此负责，就像他们对广告拦截器和其他工具链负责一样。如果你想在生态系统中支持这种东西(高级 JavaScript)，你需要一个更容易支持的平台。所以我天真的想法是:为了调试和丰富这些大型复杂的应用程序，我们需要在浏览器中有一个标准库。我们需要浏览器供应商从我们正在做的事情中提取很多东西——坦率地说，我们都做同样的事情，看起来都一样，对吗？让这些普通的东西变得像网络标准一样。但我不知道这是否会发生。”

> Kubernetes“实际上并没有简化我们作为开发人员——编写业务逻辑的人——所面临的许多问题。”

大卫·克莱默

Cramer 的另一个有趣的理论是，软件开发的平台层——目前由 Kubernetes 主导——将越来越多地外包给像 Vercel 和 Heroku 这样专注于开发人员的平台公司。原来克莱姆并不是库伯内特的粉丝。

“我不认为 Kubernetes 是未来。这可能有争议，但我认为 Kubernetes 是基础设施团队管理配置的另一个工具。它实际上并没有简化我们作为开发人员(编写业务逻辑的人)所面临的许多问题。”

这当然就是所谓的“平台即服务”工具出现的地方，比如 Heroku 和 [Cloud Foundry](https://www.cloudfoundry.org/?utm_content=inline-mention) 。但是 Cramer 认为那些减轻开发者基础设施负担的工具仍然是“非常非常早的”因此，在 2021 年，我们可能会看到进一步转向 PaaS 和更新的面向工作流的平台，如 Vercel。

我在我的 2021 年预测帖子中指出，现在有太多的静态托管服务:[、亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)、Amplify、Azure 静态网络应用、Netlify、Vercel、Firebase 和 Cloudflare 页面。这种趋势也在 Jamstack 上演。但是为什么目前静态托管这么流行呢？

“如果你回到那个 JavaScript 开发者——如果我只知道如何写 JavaScript 或简单的网页，我可以托管一个静态网站，而且速度很快。如果突然之间，我必须构建一个 Node.js 应用程序或 Python 应用程序，并且我必须找出如何优化它，那么对我来说，这是一套全新的技术和知识。[开发者]想要他们容易获得的东西。CDNs 内容交付网络][……]已经成为解决许多真正复杂问题的管道胶带解决方案——无论是缓存还是分发或类似的问题。他们一直都在那里。”

因此，cdn 通常提供的静态文件变得流行起来，因为它们通过提供 Cramer 所谓的“管道胶带”解决方案来帮助减轻开发人员的负担。但是这不是一个理想的解决方案，尤其是当需要提供这么多 JavaScript 时。

“是的，JavaScript 加载速度很快，”Cramer 说，“但它仍然需要处理所有这些逻辑、运行时间和执行。而且带宽还是个问题，对吧？”

或许在 2021 年，我们将开始看到像 Sentry 和 Vercel 这样专注于前端的公司解决基础设施复杂和 JavaScript 臃肿的问题。更多详情，请查看我与大卫·克莱姆的播客。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>