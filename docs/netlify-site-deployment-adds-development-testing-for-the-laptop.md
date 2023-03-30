# Netlify 将本地开发服务器添加到 JAMstack 应用平台

> 原文：<https://thenewstack.io/netlify-site-deployment-adds-development-testing-for-the-laptop/>

专注于使 web 开发更容易的初创公司 Netlify 继续构建其基于 web 的 web 开发平台，增加了 [Netlify Dev](https://www.netlify.com/blog/2019/04/09/netlify-dev--our-entire-platform-right-on-your-laptop/) ，这是一个插件，允许开发人员直接在笔记本电脑上构建和测试他们的应用程序。

Netlify Live 上周在纽约市的 JAMstack_conf 上首次亮相，并创造了最大的[轰动](https://twitter.com/search?q=netlify&src=typd)，这是一个项目预览开发者可以流式传输到一个随着代码变化而更新的实时 URL。

“现代应用程序……你有无服务器功能，这需要 Lambda，配置网关，很难处理。去年，Netlify 让事情变得简单了，他说，“我们有自己的网关，我们有自己的认证服务。”所以我们能做的就是把它推送到 Lambda，认证它——你需要做的就是把它上传到 git 文件夹。Netlify 的联合创始人[克里斯·巴赫](https://twitter.com/chr_bach?lang=en)解释说:“留下来的是你如何在本地使用这个桌面服务器。

“今天，我们发布了一款产品。包装您最喜欢的构建工具——web pack 或 Gatsby 或其他任何工具。它包含了你的 YAML 脚本框架和任何你用来构建网站的东西。它围绕着您的无服务器功能，它围绕着 CDN edge logic 等高级事物…所有这些完全是您可以在笔记本电脑上测试的东西，将其投入使用，它的行为方式是一样的。”

该插件处于公开测试阶段。

Netlify 提供了一个专门构建的现代应用交付网络，将前端和后端以及建筑物和主机分离开来，而不是一个前面有内容交付网络(CDN)的网站。开发人员只需将项目推送到 Git，Git 的自动化服务就会处理好所有的事情。

Netlify Dev 在本地 Dev 服务器中运行生产路由引擎，以使所有重定向、代理规则、功能路由或附加路由在本地可用，并注入正确的环境变量。

该公司已将其整个边缘重定向引擎编译成 WebAssembly，因此开发人员可以在命令行界面中使用现代 JavaScript，在部署到生产之前进行本地测试，并将 Lambda 功能作为完整的 API 端点进行部署。

它自动检测常见的工具，如 Gatsby，Hugo，React Static，Eleventy 等。

“即使你的构建生成器没有任何管道，你也可以利用无服务器功能、依赖性和所有这些，”首席执行官兼联合创始人 Matt Biilmann 在会议演示期间解释道。

“它采用了我们所有的边缘逻辑，并通过生产库在本地提供。每当你把更多的功能推到边缘，你也可以在本地的笔记本电脑上得到它。它采用了我们所有的功能，并为您提供了这种非常简单的工具，包括搭建、编译依赖项、运行本地服务器，以及处理所有的代理和路由，否则您必须在本地进行设置。它负责这些 API 集成，同步和注入环境变量。所有这些都是在本地运行的。”

Biilmann 创造了术语 JAMstack 来指代客户端 JavaScript、可重用 API 和预建标记。

要使用 Netlify Dev，您应该拥有其 CLI 的最新版本。

去年，Netlify [推出了 Netlify Functions](https://thenewstack.io/netlify-embeds-serverless-functionality-web-app-development-platform/) ，这是一个工具，它使得 AWS Lambda 功能的部署像向项目的 Git 存储库添加文件一样简单。在[的前一集《新堆栈制造商](https://thenewstack.io/netlifys-approach-to-the-cdn-microservices-and-breaking-down-your-monolith/)播客中，比尔曼和巴赫谈到了该公司如何使用 AWS Lambda 及其对以 Git 为中心的工作流和微服务的关注。

[https://www.youtube.com/embed/4plzNu4UF64?feature=oembed](https://www.youtube.com/embed/4plzNu4UF64?feature=oembed)

视频

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>