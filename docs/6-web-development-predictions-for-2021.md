# 6 2021 年网络发展预测

> 原文：<https://thenewstack.io/6-web-development-predictions-for-2021/>

[](https://twitter.com/ricmac)

 [理查德·麦克马努斯

理查德是《新书库》的高级编辑，每周撰写一篇关于云原生互联网未来发展的专栏文章。此前，他在 2003 年创立了读写网，并将其打造为全球最具影响力的科技新闻和分析网站之一。](https://twitter.com/ricmac) [](https://twitter.com/ricmac)

当我们开始 2021 年的应用和 web 开发时，两个趋势似乎注定会继续快速增长:无服务器和 JavaScript 开发。我在上周的年度回顾文章[中提到的第三个趋势 Jamstack 的前景不太明朗，但它也可能会积聚势头。](https://thenewstack.io/up-the-stack-a-year-end-review-of-serverless-jamstack-and-javascript/)

现在互联网发展的主要驱动力是不断增长的将后端复杂性从前端工作中抽象出来的需求。毕竟，这就是无服务器的全部前提——您甚至不需要配置基础架构，因为一切都是为您管理的。它还影响了 JavaScript 在过去十年中的发展，Next.js 和 Vue 等现代框架将 JavaScript 代码打包成可重用的模块，并为常见任务提供了一个抽象层。

由于我是一名科技记者，而不是开发人员，我依靠实际的无服务器、JavaScript 和 Jamstack 从业者对 2021 年做了一些预测。但是我在适当的地方添加了我自己的评论。因此，这里有六件事要在来年注意…

## 1.React 将会变得更加流行

亚马逊网络服务高级开发者倡导者 Nader Dabit 预测，React，用于构建用户界面的开源 JavaScript 库，将继续接管网络开发。他说，部分原因将是 Next.js、Remix 和 Gatsby 等“元框架”越来越受欢迎的结果——所有框架都建立在 React 的基础上。

正如 Dabit 的一位评论者[指出的](https://twitter.com/DennisKortsch/status/1340758138832744450)，React 增长的另一个原因将是对[低代码](https://thenewstack.io/outsystems-pushes-low-code-beyond-its-visual-basic-legacy/)解决方案的日益依赖。“React 将成为许多低代码工具的底层引擎，”软件工程师丹尼斯·科特施说。

Next.js 的创始人，现任 [Vercel](https://vercel.com/) 首席执行官的 Guillermo Rauch ，比大多数人更有理由看好 React。然而，他补充了一个警告。他告诉我，“2021 年，我们将告别银弹幻想，实现出色的前端性能。静态-只有不工作，太限制。光靠 Serverless 是动不了针的。这是一个全面的、以绩效为导向的工作流程。”

## 2.得益于 JavaScript 和无代码，网络标准将获得动力

[studio . zeldman](https://twitter.com/noel)的开发总监 nol Jackson 告诉我，“无代码空间和应用程序框架空间将会有巨大的加速”，并且“web 标准将会在这些工具中获得动力，但是仍然落后于它应该在的地方。”鉴于 Jackson 的同事 Jeffrey Zeldman 是历史上最有影响力的网页设计师之一，并撰写了网页标准的圣经——用网页标准进行设计——我们应该留意以下关于 2021 年网页标准走向的评论。杰克逊谈到 JavaScript 框架和无代码(它也适用于低代码):

*“这些工具将是推广使用网络标准的巨大优势。随着时间的推移，设计系统将变得规范化，并且本质上允许更广泛的使用和 Web 标准的迭代改进。与浏览器相比，服务器上的 JS 将会有更好的理解，这应该有助于 Web 标准，但也将是一个颠簸的旅程。我们将停止争论 CSS 是在哪里写的，并开始接受静态生成的 JS 框架是可接受的，甚至可能是许多场景的最佳选择。JS 将继续占据主导地位，我们将不得不为提出的 web 标准问题制定解决方案，而不是与 JS 对抗。Web 组件将成为一个非常需要的推动力，但仍将是“边缘”。“JS 框架的使用实际上有助于以后在 2022 年采用 Web 组件。虽然存在一些重大障碍，但 2021 年应该会是网络标准成功且富有成效的一年。”*

## 3.无服务器将是突破性的一年

根据蟑螂实验室首席执行官斯潘塞·金博尔的说法，无服务器将建立在 Kubernetes 过去几年的成功基础上，并在 2021 年拥有自己的“时刻”。他告诉新栈:

*“开发人员将不必考虑部署节点或虚拟机。我们将开始看到数据库中的一切都被提取和虚拟化。无服务器还有很长的路要走，但是任何认为无服务器已经过了它的全盛时期或者太过牵强的人都要吃苦头了。随着开发人员承担更多的决策者角色，我们将开始看到开发人员寻求和实现的工具类型的转变。使用 Kubernetes 可以在全球范围内扩展，但是非常复杂。无服务器提供了一个很好的包来实现全球规模。”*

我特别看好无服务器，因为它显示出 2020 年的迹象，表明它准备超越“功能即服务”(FaaS)。虽然 [AWS Lambda](https://aws.amazon.com/lambda/) 可能会继续成为无服务器的市场领导者——而且它绝对是一种 FaaS 服务，这意味着它只迎合无状态应用——但在未来几年，一个更强大的无服务器平台有可能出现。我们*可能不会*很快获得 Kubernetes 规模的开源无服务器平台，但[我已经着眼于](https://thenewstack.io/cloudstate-is-lightbends-attempt-to-define-serverless-2-0/)像 [Lightbend](https://www.lightbend.com/) 这样雄心勃勃的云本土公司来改变现状。Lightbend 是开源 [Cloudstate](https://cloudstate.io/) 项目的幕后推手，旨在为“无服务器 2.0”奠定基础(支持有状态应用等)。

## 4.2021 年，新的 Jamstack 网站将增长 10 倍

Jamstack 网站开发在 2020 年是一个增长行业(尽管也不乏批评者)。Jamstack platform 的首席执行官 Ohad Eder-Pressman 认为这一增长将在未来一年成倍增长。虽然承认 Jamstack 的“核心技术产品”必须“继续巩固”，但他认为 Jamstack 将在 2021 年越来越多地吸引开发者的注意力。

*“我们将看到最受欢迎的[Jamstack]框架继续重组，同时越来越多的大型公司将推出专注于 Jamstack 的产品(例如，Digital Ocean 和 Cloudflare)。这些新的发展将激发人们对这个领域的信心和好奇心，反过来，我预计今年每天创建的 Jamstack 网站数量将增长 10 倍。”*

我同意 Jamstack 可能会继续受到开发人员的欢迎，但就个人而言，我会在平台的内容创建方面对 Jamstack 进行更多的改进。在那之前，它将一直是网站管理的一个小众趋势。

## 5.渐进式网络应用将与操作系统更紧密地结合在一起

渐进式 web 应用程序(PWAs)是一种先进的 Web 应用程序，可以快速缩小与本地应用程序的差距。谷歌[将 pwa 定义为“服用了所有正确维生素的网站”,该公司非常看好它们。在](https://web.dev/progressive-web-apps/)[最近的 Chrome Dev 峰会](https://thenewstack.io/chrome-dev-summit-the-web-is-closing-the-gap-on-native-apps/)上，谷歌项目经理[PJ·麦克拉克伦](https://twitter.com/b1tr0t)表示，pwa“正处于另一个变革时刻的尖端”，类似于 21 世纪初随着 Gmail 的推出，AJAX(异步 JavaScript 和 XML)彻底改变了网络电子邮件。谷歌的网络开发倡导者托马斯·斯坦纳本周在推特上回应了这一观点:

*“在具有真正浏览器引擎选择的操作系统上，渐进式网络应用将与所述操作系统更紧密地集成。[电子](https://www.electronjs.org/)【PWA 包装】将变得越来越不必要。我们会看到一些令人惊叹的 T15 项目府谷 T16 案例研究，但市场仍会因为一家厂商而犹豫不决。”*

## 6.回到网络服务的基础

为微软 Azure 开发项目工作的 Maxim Salnikov 认为网络服务项目会变得更简单，但是在构建过程中会变得更复杂。

*“我的观点是‘回归基础’:随着新一代 CI/CD 工具的出现，以及@AzureStaticApps 等专业云产品之间的竞争日益激烈，web 正在回归‘简单’的服务，而复杂的静态项目构建。”*

除了他自己公司的产品 [Azure Static Web Apps](https://azure.microsoft.com/en-us/services/app-service/static/) 之外，在[的另一条推特](https://twitter.com/webmaxru/status/1340986659396071425)中，他将 Netlify、Vercel、AWS Amplify、Firebase 和 Cloudflare Pages 列为静态托管市场上的竞争产品。这与 Jamstack 趋势紧密相连，像 Netlify 和 Vercel [这样的服务](https://thenewstack.io/vercels-frontend-and-the-rise-of-the-hybrid-developer/)[使用边缘网络](https://thenewstack.io/why-netlify-is-tech-agnostic-and-its-role-in-jamstack-development/)向最终用户提供静态网页和应用程序。正如萨尔尼科夫所说，这是容易的部分——困难的部分，也是典型的[导致技术问题](https://thenewstack.io/gatsby-faces-community-upheaval-over-commercialization-plans-diversity-challenges/)的部分，是构建。但是很高兴看到这么多公司，包括 AWS 和微软这样的大公司，都在努力尽可能简单地提供静态网页和应用程序。

## 你的预言？

当然，我只是触及了 2021 年以后 web 开发和大规模应用程序开发的表面。现在让我知道你的想法！我是 Twitter 上的 [@ricmac](https://twitter.com/ricmac) ，或者你可以 ping 整个团队 [@thenewstack](https://twitter.com/thenewstack) 。此外，请关注我全年的每周专栏，因为我会跟踪这些和其他发展。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>