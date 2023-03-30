# js 13 推出了一个更快的基于 Rust 的捆绑器

> 原文：<https://thenewstack.io/next-js-13-debuts-a-faster-rust-based-bundler/>

在最新发布的 [Next.js](https://thenewstack.io/what-developers-told-us-about-vercels-next-js-update/) 中，Vercel 正在用一个新的基于 Rust 的捆绑器取代 Next.js 中的 Webpack，该捆绑器已被下载超过 30 亿次，用于 [JavaScript 和 TypeScript](https://thenewstack.io/typescript-vs-javascript/) 代码。

Turbopack 目前处于 alpha 阶段，据说比 Webpack 快 700 倍，是为开发和生产的增量构建而设计的——该公司在一份声明中说，这是第一个也是唯一一个用于 [JS 和 Typescript](https://thenewstack.io/typescript-vs-javascript/) 的构建系统。这是在旧金山 Next.js Conf 22 会议上公布的 Next.js 13 的一系列变化之一。

“您希望实现动态，但这意味着要处理两套运行时 API——服务器上的 [Node.js](https://thenewstack.io/linux-manage-multiple-versions-of-node-js-with-the-nvm-manager/) 和浏览器中以 web 为中心的 API。你想成为动态的，但往往只在一个地区起源，依赖于传统的，静态的 CDN 缓存，试图执行和扩展。“今天，我们已经准备好迎接新的范式。”

他说，NextJS 13 允许开发人员实现动态网页，这要归功于三个方面的创新: [Turbopack](https://vercel.com/blog/turbopack) ，一种新的路由和渲染基础设施，以及对 Next.js 开发人员工具包中使用的组件和模块的更新。

开发者体验副总裁李·罗宾逊说，它的速度提升不仅仅是为了代码更新，也是为了从低数据服务器启动。Robinson 将开源的 [Turbo](https://turbo.build/) 描述为“高性能裸机工具的新基础”

“Turbo 的性能来自其高度优化的机器代码和用 Rust 构建的低级增量引擎。一旦 TurboPack 执行了一项任务，它就再也不会重新开始，”他说。" Turbopack 侧重于您的本地开发经验，包括快速反应更新."

Robinson 补充说，Turbopack 在处理具有 3000 个模块的大型应用程序时，启动时间为 1.8 秒，这比 Next.js 的早期版本和其他流行工具都要快。

## 递增量

至少有一名开发人员在问答中表达了对从 Webpack 到 Turbopack 的变化的担忧，指出这“感觉就像从她脚下拉出了一张地毯”。

Robinson 回答说，这些变化将逐渐为每个人所接受，而不是一个不和谐的交易，他把舞台让给了 Vercel 的 web 工具工程经理 Maia Teegarden 来解释。

“我们不想离开这个巨大的生态系统，所以我们确实计划有某种迁移路径，”Teegarden 说。“我们可能无法使用你已经在使用的插件，但你可以迁移到替代插件。”

Vercel 的团队一再强调，新工具可以逐步引入新页面，而无需大规模重做网站，以此来缓解开发人员对迁移的担忧。

## 新路由和渲染

Next.js 13 包括一个新的路由和渲染基础设施，具有 React 服务器组件、用于悬念的数据提取(管理 React 应用程序中的异步操作)以及对混合、嵌套布局的支持。该公司在新闻稿中表示，它的设计与 Vercel 基础设施的进步“同步”，包括对流媒体和新缓存策略的支持。

“在 React 多年投资的基础上，我们正在实现大幅减少客户端 JavaScript 的梦想，同时使最雄心勃勃的应用程序不仅可能，而且容易，”劳奇告诉观众。

Vercel 高级开发人员[德尔巴·德·奥利韦拉](https://www.linkedin.com/in/delbaoliveira/?originalSubdomain=uk)说:“我们可以更容易地在组件内协同定位数据获取，从而在您的应用程序中实现全局数据获取。“例如，当您有跨页面共享的动态数据需求时，我们可以更容易地将您的应用程序代码与您的包装(如组件、文本和堆栈)放在一起，这样您和您的团队就不必制定自己的约定和配置。”

她补充说，这就是为什么 Vercel 正在推出一款新路由器，“首先是引入应用程序目录。”她补充说，应用程序目录可以与现有的页面目录共存，以便逐步采用。这将允许开发人员在页面之间重用导航栏，而无需预先渲染屏幕的这一部分。它还支持[流](https://nextjs.org/blog/next-13#streaming)，特别是“将用户界面的渲染单元渐进地渲染并递增地流式传输到客户端的能力”

“这不是一个静态页面，”de Oliveira 说，演示了数据获取代码，它利用了一个新的数据获取 API。“那么，如何从服务器获取和传输数据，同时防止客户端出现大量 JavaScript 和瀑布？我们与 [React](https://thenewstack.io/learn-react-delete-functionality-and-the-set-state-hook/) 核心团队合作，推出了一种新的解决方案来简化整个 React 的修补工作。”

## 开发人员工具包中的新功能

最后，第三个重大宣布是对 web developer 软件套件的升级。

“如果一个真正的 Web SDK 不能解决你在网络上看到的最常见的工件，如图像、字体、脚本甚至社交卡片，它将是不完整的，”Rauch 说。

Next.js 工具包现在包括:

*   **更多支持使用自定义和[谷歌字体](https://fonts.google.com/about)** ，与谷歌开发，但不与谷歌共享网站访问者的信息。谷歌字体有助于生成备用字体，使开发者能够避免 99%的布局变化，并消除任何外部网络请求，以提高隐私和性能，该公司表示。
*   **对<图像>组件**的更新，超过 70%的 Next.js 社区使用该组件。该公司表示，利用浏览器标准的更新，重新设计的组件能够“将更多的任务分配给浏览器，以降低整体成本，因为能够在边缘存储计算图像”。它补充说，当部署到 Vercel 时，图像组件会自动存储在 Vercel Edge 网络上并进行优化，以获得更好的性能。
*   **即时打开图形(OG)图像生成。另一个新增功能是一个用于生成动态社交卡片图像的新库。该公司表示，通过使用 Vercel Edge 函数、WebAssembly 和一个用于将 HTML/CSS 转换为 SVG 的全新核心库，这种方法比现有解决方案快五倍。根据 Agorapulse 的[数据，嵌入卡片的推文的参与度高出 40%。](https://www.agorapulse.com/social-media-lab/link-tweet-with-an-image-vs-tweet-with-twitter-cards-does-it-really-matter/)**

## 新收购

Vercel 还宣布收购总部位于奥地利的数据分析和转换平台公司 [Splitbee](https://splitbee.io/) ，该公司由兄弟[托比亚斯](https://www.linkedin.com/in/tobiaslins/?originalSubdomain=at)和[提莫·林斯](https://www.linkedin.com/in/timolins/)于 2020 年创立。PaaS 的 IDC 研究总监 Lara Greden 表示，此次收购“为 Vercel 的分析战略带来了技术和人才”，并在 Vercel 现有跟踪能力的基础上增加了基于指标的用户体验洞察，无需第三方插件或额外编码。

“Vercel 正在建立一个技术平台，该平台正在重新定义各种规模的公司如何在网络上建立，”Greden 在会议上告诉 New Stack。“Vercel 的方法让开发者处于主导地位，但也将包括营销、产品、设计和高管在内的额外用户群带到了最前沿。”

她补充说，这对初创企业尤其重要，因为它们在人才方面面临更多挑战。

“如果开发人员不必出去寻找定制代码或开源项目来实现给定的功能，相反，如果它可以工作，他们今天就可以为他们的公司带来好处，使他们的整个团队能够进一步专注于和迭代他们的核心业务差异化和业务建设能力，”格雷登说。" Vercel 正在为开发者和他们更广泛的产品团队创造飞轮."

*Vercel 支付了 Loraine Lawson 参加会议的差旅费和住宿费。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>